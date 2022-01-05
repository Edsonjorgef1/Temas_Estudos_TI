## Entendendo o Reducer

App.js 

```js
import { useState } from "react";
import "./App.css";

import { StateProvider } from "./contexts/StateContext";

import Header from "./components/Header";
import Menu from "./components/Menu";
import Body from "./components/Body";

const App = () => {
  const [userName, setUserName] = useState("Beto");
  const [userEmail, setUserEmail] = useState("gilberto-goncalves@outlook.com.br");
  
  let providerValue = {
    theme: 'dark',
    user: {
      name: userName,
      email: userEmail
      
    }
  }

  return (
    <StateProvider value={providerValue}>

      <div className="container">
      
        <Header />
        <section>
          <Menu />
          <Body setUsername={setUserName} />
         
        </section>
      </div>
    </StateProvider>
  );
};

export default App;


```

components/Body.js

```js
import Botao from './Botao'
import { useStateValue } from '../contexts/StateContext'

export default (props) => {
    
    const context = useStateValue()
    
    const handleButton = () => {
    props.setUsername('Paulo')
    }
    return (
        <article className={`box theme-${context.theme}`}>
       <Botao />
       <button onClick={handleButton}> Trocar para Paulo</button>
        </article>
     )
    }
```

components/Botao.js

```js
import { useStateValue } from '../contexts/StateContext'

export default () => {
  const context = useStateValue()

  return (
    <button>{context.user.name} - {context.theme}</button>
  );
};

```
components/Header.js

```js
import Botao from './Botao'
import { useStateValue } from '../contexts/StateContext'

export default () => {
    const context = useStateValue()

    return (
            <header className={`box theme-${context.theme}`}>
            <Botao/>
            </header>
        );
}
```

components/Menu.js

```js
import Botao from "./Botao";
import { useStateValue } from '../contexts/StateContext'

export default () => {
  const context = useStateValue()
  
  return (
        <aside className={`box theme-${context.theme}`}>
          <Botao />
        </aside>
  );
};

```
components/Contagem.js

```js
import { useReducer } from 'react';

const initialState = {
    contagem: 0
};

{/*state, valor atual que tenho salvo neste reducer*/}
{/*action, os dados que vou mandar para meu dispatch*/}
const reducer = (state, action) => {

    switch(action.type) {
        case 'increment':
            return { ...state, contagem: state.contagem + 1};
        break;
        case 'decrement':
            return { ...state, contagem: state.contagem - 1};
        break;
        case 'double':
            return { ...state, contagem: state.contagem * 2};
        break;
        case 'set':
            return { ...state, contagem: action.novacontagem };
        break;
    }

    return state;
}

export default () => {
    const [state, dispatch] = useReducer(reducer, initialState);

    return (
        <div>
            <button onClick={()=>dispatch({type:'increment'})}>+</button>
            <span>{state.contagem}</span>
            <button onClick={()=>dispatch({type:'decrement'})}>-</button>
            <button onClick={()=>dispatch({type:'double'})}>Dobrar</button>
            
            <button onClick={()=>dispatch({type:'set', novacontagem: 20})}>Setar como 20</button>
            <button onClick={()=>dispatch({type:'set', novacontagem: 35})}>Setar como 35</button>
        </div>
    );
}

```

contexts/StateContext.js

```js
import { createContext, useContext } from 'react';

export const StateContext = createContext();

export const StateProvider = ({ children, value }) => (
    <StateContext.Provider value={value}>
        {children}
    </StateContext.Provider>
);

export const useStateValue = () => useContext(StateContext);
```

App.css

```js
body {
    margin: 0;
    background-color: #098dc2;
}
.box {
background-color: #FFF;
border: 1px solid #000;
border-radius: 20px;
padding: 10px;
margin: 10px;
}
.container {
    width: 800px;
    margin: auto;
}
section {
    display: flex;
}
section aside {
    width: 200px;
}
section article {
    flex: 1;
    min-height: 400px;
}
.theme-ligth {
    background-color: #FFF;
    color: #000;
    border: 1px solid #000;
}
.theme-dark {
    background-color: #333;
    color: #fff;
    border: 1px solid #999;
}
```
## Usando mais de um reducer (sem localstorage)


Vamos ver como acessar as nossas informações em, qualquer lugar de nosso sistema e 
trocar iformações de forma facil

App.js 

```js
import './App.css';

import { StateProvider } from './contexts/StateContext';

import Header from './components/Header';
import Menu from './components/Menu';
import Body from './components/Body';

const App = () => {
    
    return (
        <StateProvider>
            <div className="container">
                <Header />
                <section>
                    <Menu />
                    <Body />
                </section>
            </div>
        </StateProvider>
    );
}

export default App;
```

components/Body.js

```js
import Botao from './Botao';
import Contagem from './Contagem';
import { useStateValue } from '../contexts/StateContext';

export default () => {
    const [state, dispatch] = useStateValue();
    //Para acessar as informação sempre e assim, exemplo, state.terceiro.blabla, e o dispatch igual abaixo.
    const handleButton = () => {
        //Quando eu der o dispatch, entra no aquivo stateContext.js, e rodar o MainReducer, ele vai verificar dentro de meus objetos se contém setName
        //Todos os dispatch ele roda todos os reducers, mais só vai trocar a informação que o nome for igual a type
        dispatch({
            type: 'setName',
            name: 'Paulo'
        });
    }

    return (
        <article className={`box theme-${state.theme}`}>
            <Botao />

            <button onClick={handleButton}>Trocar para Paulo</button>

            <hr/>

            <Contagem />
        </article>
    );
}
```

components/Botao.js

```js
import { useStateValue } from '../contexts/StateContext';

export default () => {
    const [state, dispatch] = useStateValue();

    return (
        <button>{state.user.name} - {state.theme}</button>
    );
}
```
components/Header.js

```js
import Botao from './Botao';
import { useStateValue } from '../contexts/StateContext';

export default () => {
    const [state, dispatch] = useStateValue();

    return (
        <header className={`box theme-${state.theme}`}>
        <Botao />
            {state.theme === 'light' &&
                <button onClick={()=>dispatch({type:'setTheme', theme: 'dark'})}>Dark</button>
            }
            {state.theme === 'dark' &&
                <button onClick={()=>dispatch({type:'setTheme', theme: 'light'})}>Light</button>
            }
            
        </header>
    );
};
```

components/Menu.js

```js
import Botao from './Botao';
import { useStateValue } from '../contexts/StateContext';

export default () => {
    const [state, dispatch] = useStateValue();

    return (
        <aside className={`box theme-${state.theme}`}>
            <Botao />
        </aside>
    );
};
```
components/Contagem.js

```js
import { useReducer } from 'react';

const initialState = {
    contagem: 0
};

const reducer = (state, action) => {

    switch(action.type) {
        case 'increment':
            return { ...state, contagem: state.contagem + 1};
        break;
        case 'decrement':
            return { ...state, contagem: state.contagem - 1};
        break;
        case 'double':
            return { ...state, contagem: state.contagem * 2};
        break;
        case 'set':
            return { ...state, contagem: action.novacontagem };
        break;
    }

    return state;
}

export default () => {
    const [state, dispatch] = useReducer(reducer, initialState);

    return (
        <div>
            <button onClick={()=>dispatch({type:'increment'})}>+</button>
            <span>{state.contagem}</span>
            <button onClick={()=>dispatch({type:'decrement'})}>-</button>
            <button onClick={()=>dispatch({type:'double'})}>Dobrar</button>
            
            <button onClick={()=>dispatch({type:'set', novacontagem: 20})}>Setar como 20</button>
            <button onClick={()=>dispatch({type:'set', novacontagem: 35})}>Setar como 35</button>
        </div>
    );
}
```

contexts/StateContext.js

```js
import { createContext, useContext, useReducer } from 'react';

import ThemeReducer from '../reducers/ThemeReducer' // Primeiro reducer
import UserReducer from '../reducers/UserReducer'   // Segundo reducer

//Os valores inicial que vai estar dentro de meu reducer
const initialState = {
    theme: ThemeReducer(),
    user: UserReducer()
}

const MainReducer = (state, action) => ({
    theme: ThemeReducer(state.theme, action),
    user: UserReducer(state.user, action)
})

export const StateContext = createContext();

export const StateProvider = ({ children }) => (
    <StateContext.Provider value={useReducer(MainReducer, initialState)}>
        {children}
    </StateContext.Provider>
);

export const useStateValue = () => useContext(StateContext);

//Exemplo: se eu colocar state.theme, tenho acesso o que está em theme, state.user.name, tenho acesso ao nome
```
reducers/ThemeReducer.js

```js
const initialState = "ligth"

export default (state = initialState, action = {}) => {
        switch(action.type) {
            case 'setTheme':
                return action.theme
            break;
        }
    
        return state;
    }
```
reducers/UserReducer.js

```js
const initialState = {
    name: 'Visitante',
    email: 'visitante@hotmail.com'
}

export default (state = initialState, action = {}) => {
        switch(action.type) {
            case 'setName':
                return {...state, name: action.name }
            break;
            case 'setEmail':
            return { ...state, email: action.email}
            break;
        }
    
        return state;
    }
```


App.css

```js
body {
    margin: 0;
    background-color: #098dc2;
}
.box {
background-color: #FFF;
border: 1px solid #000;
border-radius: 20px;
padding: 10px;
margin: 10px;
}
.container {
    width: 800px;
    margin: auto;
}
section {
    display: flex;
}
section aside {
    width: 200px;
}
section article {
    flex: 1;
    min-height: 400px;
}
.theme-ligth {
    background-color: #FFF;
    color: #000;
    border: 1px solid #000;
}
.theme-dark {
    background-color: #333;
    color: #fff;
    border: 1px solid #999;
}
```

## Usando mais de um reducer (Armazenando no localstorage)


Vamos ver como acessar as nossas informações em, qualquer lugar de nosso sistema e 
trocar iformações de forma facil

App.js 

```js
import './App.css';

import { StateProvider } from './contexts/StateContext';

import Header from './components/Header';
import Menu from './components/Menu';
import Body from './components/Body';

const App = () => {
    
    return (
        <StateProvider>
            <div className="container">
                <Header />
                <section>
                    <Menu />
                    <Body />
                </section>
            </div>
        </StateProvider>
    );
}

export default App;
```

components/Body.js

```js
import Botao from './Botao';
import Contagem from './Contagem';
import { useStateValue } from '../contexts/StateContext';

export default () => {
    const [state, dispatch] = useStateValue();
//Para acessar as informação sempre e assim, exemplo, state.terceiro.blabla, e o dispatch igual abaixo.

    const handleButton = () => {
         //Quando eu der o dispatch, entra no aquivo stateContext.js, e rodar o MainReducer, ele vai verificar dentro de meus objetos se contém setName
        //Todos os dispatch ele roda todos os reducers, mais só vai trocar a informação que o nome for igual a type
        dispatch({
            type: 'setName',
            name: 'Paulo'
        });
    }

    return (
        <article className={`box theme-${state.theme}`}>
            <Botao />

            <button onClick={handleButton}>Trocar para Paulo</button>

            <hr/>

            <Contagem />
        </article>
    );
}
```

components/Botao.js

```js
import { useStateValue } from '../contexts/StateContext';

export default () => {
    const [state, dispatch] = useStateValue();

    return (
        <button>{state.user.name} - {state.theme}</button>
    );
}
```
components/Header.js

```js
import Botao from './Botao';
import { useStateValue } from '../contexts/StateContext';

export default () => {
    const [state, dispatch] = useStateValue();

    return (
        <header className={`box theme-${state.theme}`}>
            {state.theme === 'light' &&
                <button onClick={()=>dispatch({type:'setTheme', theme: 'dark'})}>Dark</button>
            }
            {state.theme === 'dark' &&
                <button onClick={()=>dispatch({type:'setTheme', theme: 'light'})}>Light</button>
            }
            
        </header>
    );
};
```

components/Menu.js

```js
import Botao from './Botao';
import { useStateValue } from '../contexts/StateContext';

export default () => {
    const [state, dispatch] = useStateValue();

    return (
        <aside className={`box theme-${state.theme}`}>
            <Botao />
        </aside>
    );
};
```
components/Contagem.js

```js
import { useReducer } from 'react';

const initialState = {
    contagem: 0
};

const reducer = (state, action) => {

    switch(action.type) {
        case 'increment':
            return { ...state, contagem: state.contagem + 1};
        break;
        case 'decrement':
            return { ...state, contagem: state.contagem - 1};
        break;
        case 'double':
            return { ...state, contagem: state.contagem * 2};
        break;
        case 'set':
            return { ...state, contagem: action.novacontagem };
        break;
    }

    return state;
}

export default () => {
    const [state, dispatch] = useReducer(reducer, initialState);

    return (
        <div>
            <button onClick={()=>dispatch({type:'increment'})}>+</button>
            <span>{state.contagem}</span>
            <button onClick={()=>dispatch({type:'decrement'})}>-</button>
            <button onClick={()=>dispatch({type:'double'})}>Dobrar</button>
            
            <button onClick={()=>dispatch({type:'set', novacontagem: 20})}>Setar como 20</button>
            <button onClick={()=>dispatch({type:'set', novacontagem: 35})}>Setar como 35</button>
        </div>
    );
}
```

contexts/StateContext.js

```js
import { createContext, useContext, useReducer, useEffect } from 'react';

import ThemeReducer from '../reducers/ThemeReducer'; // Primeiro reducer
import UserReducer from '../reducers/UserReducer'; // Segundo reducer

//Os valores inicial que vai estar dentro de meu reducer
const initialState = {
    theme: ThemeReducer(),
    user: UserReducer()
};

const MainReducer = (state, action) => ({
    theme: ThemeReducer(state.theme, action),
    user: UserReducer(state.user, action)
});

export const StateContext = createContext();

const localState = JSON.parse( localStorage.getItem('ctx') );

export const StateProvider = ({ children }) => {
    const [state, dispatch] = useReducer(MainReducer, localState || initialState);

    useEffect(()=>{
        localStorage.setItem('ctx', JSON.stringify(state));
    }, [state]);

    return (
        <StateContext.Provider value={[state, dispatch]}>
            {children}
        </StateContext.Provider>
    );
};

export const useStateValue = () => useContext(StateContext);
```
reducers/ThemeReducer.js

```js
const initialState = "light";

export default (state = initialState, action = {}) => {
    switch(action.type) {
        case 'setTheme':
            return action.theme;
        break;
    }

    return state;
}
```
reducers/UserReducer.js

```js
const initialState = {
    name: 'Fulaninho',
    email: 'visitante@hotmail.com'
};

export default (state = initialState, action = {}) => {
    switch(action.type) {
        case 'setName':
            return { ...state, name: action.name };
        break;
        case 'setEmail':
            return { ...state, email: action.email };
        break;
    }

    return state;
}
```

App.css

```js
body {
    margin: 0;
    background-color: #098dc2;
}
.box {
background-color: #FFF;
border: 1px solid #000;
border-radius: 20px;
padding: 10px;
margin: 10px;
}
.container {
    width: 800px;
    margin: auto;
}
section {
    display: flex;
}
section aside {
    width: 200px;
}
section article {
    flex: 1;
    min-height: 400px;
}
.theme-ligth {
    background-color: #FFF;
    color: #000;
    border: 1px solid #000;
}
.theme-dark {
    background-color: #333;
    color: #fff;
    border: 1px solid #999;
}
```
