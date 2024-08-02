# Boas Práticas

## Estrutura de Diretórios

Organizar seu projeto de forma clara e lógica é fundamental para a manutenção a longo prazo. Uma estrutura de diretórios recomendada para um projeto React pode ser assim:

```
my-app/
├── public/
│ ├── index.html
│ └── ...
├── src/
│ ├── assets/
│ ├── components/
│ ├── pages/
│ ├── styles/
│ ├── App.js
│ ├── index.js
│ └── ...
├── .gitignore
├── package.json
└── README.md
```

- `assets/`: Arquivos estáticos como imagens e fontes.
- `components/`: Componentes reutilizáveis.
- `pages/`: Componentes de página ou layouts.
- `styles/`: Arquivos CSS ou SASS.

## Convenções de Código

Seguir convenções de código consistentes facilita a leitura e manutenção do código.

### Nomeação de Componentes

- Use `PascalCase` para nomear componentes.
- Use `camelCase` para nomear variáveis e funções.

### Exemplos de Nomeação

```
import React from 'react';

// Componente
function MyComponent() {
  // Variável
  const myVariable = 'Hello';

  // Função
  function handleClick() {
    console.log('Clicked!');
  }

  return (
    <div onClick={handleClick}>
      {myVariable}
    </div>
  );
}

export default MyComponent;
```

## Testes em React

Escrever testes é essencial para garantir que sua aplicação funcione como esperado e para prevenir regressões.

### Jest e React Testing Library

Jest e React Testing Library são ferramentas populares para testar componentes React. Primeiro, instale as dependências:

```
npm install --save-dev jest @testing-library/react
```

### Exemplo de Teste de Componente

**MyComponent.js**

```
import React from 'react';

function MyComponent() {
  return <div>Hello, World!</div>;
}

export default MyComponent;
```

**MyComponent.test.js**

```
import React from 'react';
import { render, screen } from '@testing-library/react';
import MyComponent from './MyComponent';

test('renders Hello, World!', () => {
  render(<MyComponent />);
  const linkElement = screen.getByText(/Hello, World!/i);
  expect(linkElement).toBeInTheDocument();
});
```

### Executando Testes

Para executar seus testes, adicione o seguinte script no seu `package.json`:

```json
"scripts": {
  "test": "jest"
}
```

Agora, você pode executar seus testes com o comando: