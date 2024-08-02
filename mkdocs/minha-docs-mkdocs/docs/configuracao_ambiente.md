# Configuração do Ambiente

## Requisitos

Para começar a desenvolver com React, você precisará do seguinte:
- Node.js e npm instalados em sua máquina.

## Instalando Node.js e npm

Você pode baixar e instalar o Node.js a partir do site oficial [nodejs.org](https://nodejs.org/). A instalação do Node.js inclui o npm (Node Package Manager).

### Instalação no Windows

1. Baixe o instalador do Node.js a partir do [site oficial](https://nodejs.org/).
2. Execute o instalador e siga as instruções na tela.
3. Verifique a instalação abrindo o terminal e executando:

    ```bash
    node -v
    npm -v
    ```

### Instalação no macOS

1. Você pode instalar o Node.js usando um gerenciador de pacotes como Homebrew. Se você não tem o Homebrew instalado, pode instalá-lo seguindo as instruções no [site do Homebrew](https://brew.sh/).
2. Após instalar o Homebrew, execute:

    ```bash
    brew install node
    ```

3. Verifique a instalação executando:

    ```bash
    node -v
    npm -v
    ```

### Instalação no Linux

1. Para distribuições baseadas em Debian, como Ubuntu, execute:

    ```bash
    sudo apt update
    sudo apt install nodejs npm
    ```

2. Verifique a instalação executando:

    ```bash
    node -v
    npm -v
    ```

## Criando um Projeto React com Create React App

O Create React App é uma ferramenta oficial para criar projetos React. Ele configura um ambiente de desenvolvimento com as configurações necessárias e ferramentas modernas.

### Criando o Projeto

Para criar um novo projeto, execute o seguinte comando no terminal:

```bash
npx create-react-app my-app
cd my-app
npm start
```

Isso criará um novo projeto React e iniciará o servidor de desenvolvimento. Você verá a aplicação padrão do React rodando em http://localhost:3000.

### Estrutura do Projeto

Após criar o projeto, você verá a seguinte estrutura de diretórios:

```plaintext
my-app/
├── node_modules/
├── public/
│   ├── index.html
│   └── ...
├── src/
│   ├── App.css
│   ├── App.js
│   ├── App.test.js
│   ├── index.css
│   ├── index.js
│   └── ...
├── .gitignore
├── package.json
├── README.md
└── ...
```

* public/: Contém o arquivo index.html e outros ativos públicos.
* src/: Contém os arquivos de código-fonte do React.
* node_modules/: Contém as dependências do projeto.
* .gitignore: Lista de arquivos e diretórios a serem ignorados pelo Git.
* package.json: Arquivo de configuração que lista as dependências e scripts do projeto.

Agora você está pronto para começar a desenvolver com React!