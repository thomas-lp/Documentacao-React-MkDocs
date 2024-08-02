# Gerenciamento de Dados

## Fetch API e Axios

Para buscar dados de uma API externa, você pode usar a Fetch API ou Axios. Ambos são populares e amplamente usados para fazer solicitações HTTP em JavaScript.

### Fetch API

A Fetch API é uma interface nativa do JavaScript para fazer requisições HTTP. Aqui está um exemplo de como usar a Fetch API em um componente React:

```
import React, { useState, useEffect } from 'react';

function FetchData() {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    fetch('https://api.example.com/data')
      .then(response => response.json())
      .then(data => {
        setData(data);
        setLoading(false);
      });
  }, []);

  if (loading) {
    return <div>Loading...</div>;
  }

  return (
    <div>
      <h1>Data from API:</h1>
      <pre>{JSON.stringify(data, null, 2)}</pre>
    </div>
  );
}

export default FetchData;
```

### Axios

Axios é uma biblioteca baseada em Promises para fazer requisições HTTP. Ela oferece uma sintaxe mais simples e mais funcionalidades do que a Fetch API. Primeiro, você precisa instalar o Axios:

```
npm install axios
```

Aqui está um exemplo de como usar o Axios em um componente React:

```
import React, { useState, useEffect } from 'react';
import axios from 'axios';

function FetchData() {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    axios.get('https://api.example.com/data')
      .then(response => {
        setData(response.data);
        setLoading(false);
      });
  }, []);

  if (loading) {
    return <div>Loading...</div>;
  }

  return (
    <div>
      <h1>Data from API:</h1>
      <pre>{JSON.stringify(data, null, 2)}</pre>
    </div>
  );
}

export default FetchData;
```

## Consumindo APIs REST

Consumir APIs REST em React é uma prática comum, especialmente ao construir aplicações que dependem de dados externos.

### Exemplo de Consumo de API REST

Neste exemplo, vamos consumir uma API REST que retorna uma lista de usuários:

```
import React, { useState, useEffect } from 'react';
import axios from 'axios';

function UsersList() {
  const [users, setUsers] = useState([]);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    axios.get('https://jsonplaceholder.typicode.com/users')
      .then(response => {
        setUsers(response.data);
        setLoading(false);
      });
  }, []);

  if (loading) {
    return <div>Loading...</div>;
  }

  return (
    <div>
      <h1>Users List</h1>
      <ul>
        {users.map(user => (
          <li key={user.id}>{user.name}</li>
        ))}
      </ul>
    </div>
  );
}

export default UsersList;
```

Neste exemplo, usamos a API JSONPlaceholder, uma API REST pública que fornece dados fictícios para testes e prototipagem. A lista de usuários é renderizada em um `<ul>` com cada usuário representado por um `<li>`.