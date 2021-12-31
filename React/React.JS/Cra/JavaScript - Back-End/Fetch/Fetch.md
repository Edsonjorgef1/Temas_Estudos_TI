Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Buscando dados do servidor e reutilizando o mesmo codigo

Para teste do servidor, pode utilizar este site

```js
httpbin.org
```
Para utilizar, outra vez, use o useHttpGet

ou Pode usar este site, para simular api

```js
https://api.edamam.com/
```


App.js

```js
import React, { useEffect, useState } from 'react';

const useHttpGet = url => {
  const [data, setData] = useState('')
  const [isLoading, setIsLoading] = useState(false)
  const [forceUpdate, setForceUpdate] = useState(0)

  const refresh = () => {
  setForceUpdate(forceUpdate + 1)
  } 
  useEffect(() => {
  const load = async () => {
  setIsLoading(true)
  const res = await fetch(url);
  const json = await res.json();
  setData(json); 
  setIsLoading(false)
  };
  load(); 
  }, [forceUpdate, url]); 
  return [data, isLoading, refresh]
}
  
export default function App() {
  const [data, isLoading, refresh] = useHttpGet('https://httpbin.org/delay/2')
  const ip = data.origin

  if(isLoading){
    return <h1>Is loading</h1>
  }
  return (
    <div className="App">
     <h1>Meu IP: {ip} </h1>
     <button onClick={refresh}>Refresh</button>
    </div>
  );
}
```
