# Componentes

## Componentes Funcionais e de Classe

Em React, os componentes podem ser definidos como **funcionais** ou **de classe**.

### Componentes Funcionais

Os componentes funcionais são funções JavaScript que retornam elementos React. Eles são simples e mais fáceis de escrever e entender.

#### Exemplo de Componente Funcional

```jsx
import React from 'react';

function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

export default Welcome;
```

### Componentes de Classe

Os componentes de classe são definidos como classes ES6 e têm mais funcionalidades, como métodos de ciclo de vida.

#### Exemplo de Componente de Classe

```jsx
import React, { Component } from 'react';

class Welcome extends Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}

export default Welcome;
```

## Props e State

### Props

Props são entradas para os componentes React. Eles são passados de um componente pai para um componente filho e são imutáveis.

#### Exemplo de Uso de Props

```jsx
import React from 'react';

function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

function App() {
  return <Welcome name="Sara" />;
}

export default App;
```

### State

State é um objeto privado gerenciado dentro de um componente. Ele pode mudar ao longo do tempo, geralmente em resposta a ações do usuário.

#### 

```jsx
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}

export default Counter;
```

## Ciclo de Vida dos Componentes

Os componentes de classe possuem métodos de ciclo de vida que permitem executar código em pontos específicos do ciclo de vida de um componente.

### Principais Métodos de Ciclo de Vida

* componentDidMount(): Chamado uma vez após a montagem do componente.
* componentDidUpdate(prevProps, prevState): Chamado após a atualização do componente.
* componentWillUnmount(): Chamado antes do componente ser desmontado e destruído.

#### Exemplo de Uso de Métodos de Ciclo de Vida

```jsx
import React, { Component } from 'react';

class Timer extends Component {
  constructor(props) {
    super(props);
    this.state = { seconds: 0 };
  }

  tick() {
    this.setState(state => ({
      seconds: state.seconds + 1
    }));
  }

  componentDidMount() {
    this.interval = setInterval(() => this.tick(), 1000);
  }

  componentDidUpdate() {
    console.log('Component updated');
  }

  componentWillUnmount() {
    clearInterval(this.interval);
  }

  render() {
    return (
      <div>
        Seconds: {this.state.seconds}
      </div>
    );
  }
}

export default Timer;
```


