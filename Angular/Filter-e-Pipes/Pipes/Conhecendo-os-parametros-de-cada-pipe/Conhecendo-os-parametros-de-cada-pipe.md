## Conhecendo-os-parametros-de-cada-pipe

Conhecer os parâmetros de cada pipe é importante porque eles devem ser passados em uma ordem específica.

DatePipe pode receber os seguintes parâmetros descritos na Tabela 1:


```js
{{ dado | date [ : format [ : timezone [ : locale ] ] ] }}
```

- Format	É um formato pré-definido de data ou um nome para um formato nativo. Ex: “dd/MM/yyyy h:mm”, “short”
- Timezone	É o tempo referente a região na qual o usuário está. Ex: “ISP”, “+0530”
- Locale	É o código regra de formatação usada. Ex: “en_US”, “pt”

Para locale usamos pt no Brasil e não pt_BR.

CurrencyPipe pode receber os seguintes parâmetros descritos na Tabela 2.


```js
{{ dado | currency [ : currencyCode [ : display [ : digitsInfo [ : locale ]]]] }}
```

- currencyCode	O código da moeda de acordo com o ISO 4217. Ex: “USD”, “BRL”
- display	Inclui ou não currencyCode na apresentação, se usarmos um booleano, ou substitui esse código por outro texto, se usarmos string. Ex: - “true”, “false”, “USD”, “$”
- digitsInfo	Configuração de casas decimais no formato “minimoDigitosInteiros.minimoDeDigitosDecimais-maxDigitosDecimais”. Ex: “0.2-2”
- locale	É o código regra de formatação usada. Ex: “en_US”, “pt”

