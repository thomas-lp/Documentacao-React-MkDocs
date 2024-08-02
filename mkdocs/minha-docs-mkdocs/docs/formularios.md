# Formulários

## Manipulação de Formulários

Manipular formulários em React é direto, mas pode exigir um pouco mais de código do que em bibliotecas tradicionais. A principal diferença é que você precisa gerenciar o estado dos elementos do formulário manualmente.

### Exemplo Básico de Formulário

Aqui está um exemplo básico de um formulário de entrada de texto em React:

```
import React, { useState } from 'react';

function SimpleForm() {
  const [name, setName] = useState('');

  const handleChange = (event) => {
    setName(event.target.value);
  };

  const handleSubmit = (event) => {
    event.preventDefault();
    alert(`A name was submitted: ${name}`);
  };

  return (
    <form onSubmit={handleSubmit}>
      <label>
        Name:
        <input type="text" value={name} onChange={handleChange} />
      </label>
      <button type="submit">Submit</button>
    </form>
  );
}

export default SimpleForm;
```

Neste exemplo, o valor do input é controlado pelo estado do componente e atualizado via o manipulador de eventos `handleChange`.

## Manipulação de Vários Inputs

Você pode manipular vários inputs adicionando o estado correspondente para cada input no componente.

### Exemplo de Formulário com Vários Inputs

```
import React, { useState } from 'react';

function MultiInputForm() {
  const [inputs, setInputs] = useState({ username: '', email: '' });

  const handleChange = (event) => {
    const { name, value } = event.target;
    setInputs({ ...inputs, [name]: value });
  };

  const handleSubmit = (event) => {
    event.preventDefault();
    alert(`Username: ${inputs.username}, Email: ${inputs.email}`);
  };

  return (
    <form onSubmit={handleSubmit}>
      <label>
        Username:
        <input type="text" name="username" value={inputs.username} onChange={handleChange} />
      </label>
      <br />
      <label>
        Email:
        <input type="email" name="email" value={inputs.email} onChange={handleChange} />
      </label>
      <br />
      <button type="submit">Submit</button>
    </form>
  );
}

export default MultiInputForm;
```

Neste exemplo, usamos um objeto para armazenar o estado de vários inputs e atualizamos o estado corretamente no `handleChange`.

## Validação de Formulários

A validação de formulários é essencial para garantir que os dados inseridos pelos usuários estejam corretos. Em React, você pode adicionar validação usando estados e manipuladores de eventos.

### Exemplo de Validação de Formulários

```
import React, { useState } from 'react';

function ValidatedForm() {
  const [username, setUsername] = useState('');
  const [error, setError] = useState('');

  const handleChange = (event) => {
    setUsername(event.target.value);
  };

  const handleSubmit = (event) => {
    event.preventDefault();
    if (username.length < 5) {
      setError('Username must be at least 5 characters long');
    } else {
      setError('');
      alert(`A username was submitted: ${username}`);
    }
  };

  return (
    <form onSubmit={handleSubmit}>
      <label>
        Username:
        <input type="text" value={username} onChange={handleChange} />
      </label>
      {error && <p style={{ color: 'red' }}>{error}</p>}
      <button type="submit">Submit</button>
    </form>
  );
}

export default ValidatedForm;
```

Neste exemplo, a validação é feita no `handleSubmit`, e uma mensagem de erro é exibida se a validação falhar.