Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## Calculadora Gorjetas

```js
import React, { useState, useEffect } from "react"; /*Iportando state*/
import { Text, View, Button } from "react-native";
import styled from "styled-components/native";

const Page = styled.SafeAreaView`
  flex: 1;
  align-items: center;
`;
const HeaderText = styled.Text`
  font-size: 25px;
`;
const Input = styled.TextInput`
  width: 100%;
  height: 40px;
  font-size: 18px;
  background-color: #eee;
  margin-top: 20px;
  border-radius: 10px;
  padding: 10px;
`;
const CalcButton = styled.Button`
  margin-top: 10px;
`;
const ResultArea = styled.View`
  width: 100%;
  margin-top: 30px;
  background-color: #eee;
  padding: 20px;
  justify-content: center;
  align-items: center;
`;
const ResultItemTitle = styled.Text`
  font-size: 18px;
  font-weight: bold;
`;
const ResultItem = styled.Text`
  font-size: 15px;
  margin-bottom: 30px;
`;
const PctArea = styled.View`
  flex-direction: row;
  margin: 20px;
`;
const PcItem = styled.Button``;
function App() {
  const [bill, setBill] = useState("");
  const [tip, setTip] = useState(0);
  const [pct, setPct] = useState(10);

  const calc = () => {
    let nBill = parseFloat(bill);

    if (nBill) {
      // setTip(nBill * 0.1)
      setTip((pct / 100) * nBill);
    } else {
      // alert("Digite o valor da conta");
    }
    // alert(nBill);
  };
  useEffect(() => {
    // alert("Executou");
    calc();
  }, [pct, bill]); //[pct, bill], se colocar o bill ele ja calcula automaticamente não precisa mais apertar o botão

  return (
    <Page>
      <HeaderText>Calculadora de Gorjeta</HeaderText>
      <Input
        placeholder="Quanto deu a conta?"
        placeholderTextColor="#000"
        keyboardType="numeric" // default = padrão numeric = só numero e-mail-address = j-a vem com @
        value={bill}
        onChangeText={n => setBill(n)}
      />
      <PctArea>
        <PcItem title="5%" onPress={() => setPct(5)} />
        <PcItem title="10%" onPress={() => setPct(10)} />
        <PcItem title="15%" onPress={() => setPct(15)} />
        <PcItem title="20%" onPress={() => setPct(20)} />
      </PctArea>
      <CalcButton title={`Calcular ${pct}%`} onPress={calc} />
      {tip > 0 && (
        <ResultArea>
          <ResultItemTitle>Valor da Conta</ResultItemTitle>
          <ResultItemTitle>R$ {parseFloat(bill).toFixed(2)}</ResultItemTitle>
          <ResultItemTitle>Valor da Gorjeta</ResultItemTitle>
          <ResultItemTitle>
            R$ {tip.toFixed(2)} ({pct}%)
          </ResultItemTitle>
          <ResultItemTitle>Valor Total</ResultItemTitle>
          <ResultItemTitle>
            R$ {(parseFloat(bill) + tip).toFixed(2)}
          </ResultItemTitle>
        </ResultArea>
      )}
    </Page>
  );
}

export default App;

//Relacionado a ciclo de vida, antigos React
// ComponentDidMount = Quando eu quero executar um componente antes de ele ser montado
// ComponentWillMount = Componente vai ser montado
// ComponentDidUpdate = Se algo for mudada ele vai rodar esse update
//Todos estes foram substituidos pelo useEffect
```
