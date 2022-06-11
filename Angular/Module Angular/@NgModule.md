Canal do youtube:

```js
https://www.youtube.com/engenheiroyoutuber
```

## NgModules

Um module é um mecanismo para agrupar components, diretivas, pipes e serviços
relacionados, de forma a combinar com outros módulos para criar um aplicativo.

Uma aplicação angular pode ser pensada como um quebra cabeça. Onde cada bloco,
tem como objetivo fornecer uma funcionalidade ou recurso específico.

Construimos um software como se fosse um quebra cabeça e conforme esse quebra
cabeça cresce, fica difícil e oneroso a sua manutenção. Por isso adotamos alguns
modelos de arquitetura e construção de software. O Angular fornece uma boa
maneira de organizar esses blocos de forma simples e eficaz usando módulos
(também conhecidos como ngModules)

Anatomia (ngModule)

@NgModule({ declarations: [], imports: [], exports: [], providers: [],
bootstrap: [], })

Declarations = serve para declarar nossos componentes dentro daquele modulo
especifico

import = ele importa funcionalidades de outros componentes

export = ele serve para exportar o seu modulo alem de declarar

providers = aonde você quer fazer uma requeisição externa temos que declarar o
nosso service dentro do ngmodel para utilizar nossa injeção de dependencia

bottstrap = utilizar em nosso componente principal, ele é a inicialização do
nosso modulo, que fica no app.component no centro principal de nossa aplicação
