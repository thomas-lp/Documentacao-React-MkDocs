# Estado e Ciclo de Vida dos Componentes

## Estado

O estado é uma estrutura de dados que pode mudar ao longo do tempo. Diferente das props, o estado é privado e totalmente controlado pelo componente.

### Usando Estado em Componentes Funcionais

Com a introdução dos Hooks no React 16.8, é possível usar o estado em componentes funcionais com o hook `useState`.

#### Exemplo de Uso de `useState`

```
import React, { useState } from 'react';

function Counter() {
  // Declara uma nova variável de state, que chamaremos de "count"
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

### Usando Estado em Componentes de Classe

Nos componentes de classe, o estado é geralmente inicializado no construtor e atualizado usando o método `setState`.

#### Exemplo de Uso de Estado em Componente de Classe

```
import React, { Component } from 'react';

class Counter extends Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
  }

  render() {
    return (
      <div>
        <p>You clicked {this.state.count} times</p>
        <button onClick={() => this.setState({ count: this.state.count + 1 })}>
          Click me
        </button>
      </div>
    );
  }
}

export default Counter;
```

## Ciclo de Vida dos Componentes

Os métodos de ciclo de vida são divididos em três categorias: montagem, atualização e desmontagem.

### Montagem

- `constructor()`: Chamado quando o componente é inicializado.
- `componentDidMount()`: Chamado após o componente ser montado no DOM.

#### Exemplo de `componentDidMount`

```
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

### Atualização

- `componentDidUpdate(prevProps, prevState)`: Chamado após uma atualização no componente.

#### Exemplo de `componentDidUpdate`

```
import React, { Component } from 'react';

class UpdateExample extends Component {
  componentDidUpdate(prevProps) {
    if (this.props.value !== prevProps.value) {
      console.log('Value updated:', this.props.value);
    }
  }

  render() {
    return <div>{this.props.value}</div>;
  }
}

export default UpdateExample;
```

### Desmontagem

- `componentWillUnmount()`: Chamado imediatamente antes de um componente ser desmontado e destruído.

#### Exemplo de `componentWillUnmount`

```
import React, { Component } from 'react';

class Example extends Component {
  componentWillUnmount() {
    console.log('Component will unmount');
  }

  render() {
    return <div>Example Component</div>;
  }
}

export default Example;
```

