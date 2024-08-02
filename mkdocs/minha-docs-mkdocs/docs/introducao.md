# Introdução ao React

## O que é React?

React é uma biblioteca JavaScript de código aberto para a construção de interfaces de usuário, especialmente para aplicações de página única. É mantida pelo Facebook e uma comunidade de desenvolvedores individuais e empresas.

## História e Evolução

React foi criado por Jordan Walke, um engenheiro de software do Facebook, em 2011. A primeira versão foi lançada em 2013. Desde então, React tem evoluído significativamente, com a adição de recursos como Hooks, Context API e React Suspense.

## Por que usar React?

- **Componentização**: React permite a criação de componentes reutilizáveis, facilitando a manutenção e a escalabilidade do código.
- **Desempenho**: O Virtual DOM de React melhora o desempenho ao minimizar atualizações diretas no DOM real.
- **Ecosistema**: React possui um ecossistema rico com muitas bibliotecas e ferramentas que facilitam o desenvolvimento.

## Código de Exemplo

Aqui está um exemplo simples de um componente React:

```jsx
import React from 'react';

function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

export default Welcome;
```

Este componente recebe uma propriedade (props.name) e exibe uma saudação personalizada.