# Roteamento

## React Router

O React Router é a biblioteca padrão para roteamento em aplicações React. Ele permite a navegação entre diferentes componentes, alterando a URL e mantendo a interface do usuário sincronizada com o estado da aplicação.

## Configuração Básica

Para começar a usar o React Router, você precisa instalá-lo e configurar o roteamento básico na sua aplicação.

### Instalando o React Router

Primeiro, instale o React Router com npm ou yarn:

```
npm install react-router-dom
```

### Configuração Básica do React Router

Aqui está um exemplo básico de como configurar o React Router em uma aplicação React:

```
import React from 'react';
import ReactDOM from 'react-dom';
import { BrowserRouter as Router, Route, Switch, Link } from 'react-router-dom';

function Home() {
  return <h2>Home</h2>;
}

function About() {
  return <h2>About</h2>;
}

function Users() {
  return <h2>Users</h2>;
}

function App() {
  return (
    <Router>
      <div>
        <nav>
          <ul>
            <li>
              <Link to="/">Home</Link>
            </li>
            <li>
              <Link to="/about">About</Link>
            </li>
            <li>
              <Link to="/users">Users</Link>
            </li>
          </ul>
        </nav>

        <Switch>
          <Route path="/about">
            <About />
          </Route>
          <Route path="/users">
            <Users />
          </Route>
          <Route path="/">
            <Home />
          </Route>
        </Switch>
      </div>
    </Router>
  );
}

ReactDOM.render(<App />, document.getElementById('root'));
```

Neste exemplo, `BrowserRouter` é usado para envolver a aplicação e fornecer a funcionalidade de roteamento. Os componentes `Link` são usados para navegar entre as rotas, e os componentes `Route` são usados para renderizar componentes específicos com base na URL.

## Roteamento Dinâmico

O React Router também suporta roteamento dinâmico, o que permite que você crie rotas com parâmetros que podem ser extraídos e usados dentro do seu componente.

### Exemplo de Roteamento Dinâmico

```
import React from 'react';
import { BrowserRouter as Router, Route, Switch, Link, useParams } from 'react-router-dom';

function User() {
  let { id } = useParams();
  return <h2>User ID: {id}</h2>;
}

function App() {
  return (
    <Router>
      <div>
        <nav>
          <ul>
            <li>
              <Link to="/user/1">User 1</Link>
            </li>
            <li>
              <Link to="/user/2">User 2</Link>
            </li>
            <li>
              <Link to="/user/3">User 3</Link>
            </li>
          </ul>
        </nav>

        <Switch>
          <Route path="/user/:id">
            <User />
          </Route>
          <Route path="/">
            <Home />
          </Route>
        </Switch>
      </div>
    </Router>
  );
}

function Home() {
  return <h2>Home</h2>;
}

export default App;
```

Neste exemplo, a rota `/user/:id` é definida com um parâmetro dinâmico `:id`. O hook `useParams` é usado dentro do componente `User` para acessar o valor do parâmetro da URL.
