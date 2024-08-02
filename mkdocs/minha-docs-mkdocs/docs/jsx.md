# JSX

## O que é JSX?

JSX é uma extensão de sintaxe para JavaScript que permite escrever HTML diretamente dentro do código JavaScript. É utilizado com o React para descrever a interface do usuário.

### Exemplo de JSX

```jsx
const element = <h1>Hello, world!</h1>;
```

## Sintaxe Básica

JSX permite misturar HTML com JavaScript. Qualquer expressão JavaScript válida pode ser incluída dentro de chaves {}.

### Exemplo de Sintaxe Básica

```jsx
const name = 'Sara';
const element = <h1>Hello, {name}</h1>;
```

No exemplo acima, a variável name é inserida dentro da tag `<h1>` usando chaves {}.

## Inserindo Expressões em JSX

Você pode inserir qualquer expressão JavaScript válida dentro das chaves em JSX. Isso inclui operações matemáticas, chamadas de funções, e mais.

### Exemplo de Expressões em JSX

```jsx
function formatName(user) {
  return user.firstName + ' ' + user.lastName;
}

const user = {
  firstName: 'Harper',
  lastName: 'Perez'
};

const element = (
  <h1>
    Hello, {formatName(user)}!
  </h1>
);
```

## Atributos em JSX

Você pode usar aspas para especificar valores de string e chaves para expressões JavaScript em atributos.

### Exemplo de Atributos

```jsx
const element = <img src={user.avatarUrl} alt="User Avatar" />;
```

## Filhos em JSX

Se um elemento JSX tiver filhos, você pode colocar esses filhos dentro da tag de abertura e fechamento.

### Exemplo de Filhos

```jsx
const element = (
  <div>
    <h1>Hello!</h1>
    <h2>Good to see you here.</h2>
  </div>
);
```

## JSX e React.createElement()

JSX é uma sintaxe açucarada para React.createElement(). O código JSX:

```jsx
const element = <h1 className="greeting">Hello, world!</h1>;
```

É compilado para:

```jsx
const element = React.createElement(
  'h1',
  {className: 'greeting'},
  'Hello, world!'
);
```

React.createElement() cria um objeto como este:

```jsx
const element = {
  type: 'h1',
  props: {
    className: 'greeting',
    children: 'Hello, world!'
  }
};
```