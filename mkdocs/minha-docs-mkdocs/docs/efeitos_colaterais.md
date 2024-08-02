# Efeitos Colaterais

## O que são Efeitos Colaterais?

Efeitos colaterais são operações que afetam algo fora do escopo da função atual. Em React, operações como buscar dados de uma API, manipular diretamente o DOM, ou configurar um timer são consideradas efeitos colaterais.

## O Hook `useEffect`

O hook `useEffect` é usado para lidar com efeitos colaterais em componentes funcionais. Ele combina o comportamento dos métodos de ciclo de vida `componentDidMount`, `componentDidUpdate` e `componentWillUnmount`.

### Sintaxe Básica do `useEffect`

```
import React, { useEffect } from 'react';

function ExampleComponent() {
  useEffect(() => {
    // Código para efeito colateral aqui
  });

  return <div>Example</div>;
}
```

## Executando Efeitos Colaterais Condicionalmente

Você pode passar uma array de dependências como segundo argumento para `useEffect` para controlar quando o efeito deve ser executado. Se uma das dependências mudar, o efeito será executado novamente.

### Exemplo de Dependências no `useEffect`

```
import React, { useState, useEffect } from 'react';

function ExampleComponent({ someProp }) {
  const [count, setCount] = useState(0);

  useEffect(() => {
    document.title = `You clicked ${count} times`;
  }, [count]); // Só executa o efeito quando `count` muda

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

## Limpando Efeitos Colaterais

Alguns efeitos precisam ser limpos para evitar vazamentos de memória. Para isso, `useEffect` pode retornar uma função de limpeza.

### Exemplo de Limpeza de Efeitos Colaterais

```
import React, { useState, useEffect } from 'react';

function TimerComponent() {
  const [seconds, setSeconds] = useState(0);

  useEffect(() => {
    const interval = setInterval(() => {
      setSeconds(s => s + 1);
    }, 1000);

    // Função de limpeza
    return () => clearInterval(interval);
  }, []); // Array vazio significa que este efeito só executa uma vez (componentDidMount)

  return <div>Seconds: {seconds}</div>;
}
```