# Aula de Documentação com MkDocs

<p align="center">
  <a href="#">
    <img src="https://img.shields.io/badge/Aula-Documentação-brightgreen.svg" alt="Documentação">
  </a>
  <a href="#">
    <img src="https://img.shields.io/badge/Aula-MkDocs-blue.svg" alt="MkDocs">
  </a>
</p>

## Índice

* [Introdução](#introdução)
* [Recursos Utilizados](#recursos-utilizados)
* [Objetivo da Aula](#objetivo-da-aula)
* [Desenvolvimento do Projeto](#desenvolvimento-do-projeto)
* [Próximas Etapas](#próximas-etapas)
* [Créditos e Referências](#créditos-e-referências)

## Introdução

Aula de documentação técnica com MkDocs. Projeto usado para o ensino de documentação técnica com MkDocs para ser desenvolvido na Aula da disciplina GAC116 - Programação Web da UFLA.

O objetivo desse projeto é criar uma página web de documentação técnica sobre o próprio MkDocs utilizando a ferramenta MkDocs. Os principais recursos disponíveis no MkDocs serão apresentados e, por fim, a página gerada será publicada no Github.

A aula está estruturada em forma de tutorial, de forma que cada estudante vá replicando em seu computador os conceitos e recursos aqui mostrados. A aula mostra a evolução do código para que os estudantes possa compreender como as coisas se conectam.

## Recursos Utilizados

A seguir estão listados os principais recursos utilizados no desenvolvimento desta aula.

### Linguagens

* Markdown - Linguagem de Marcação Simples - [link](https://www.markdownguide.org/)
* MkDocs - MkDocs é um Gerador de Sites Estáticos com Markdown - [link](https://www.mkdocs.org)
* Mermaid - Ferramenta de Diagramação e Gráficos - [link](https://mermaid.js.org/intro/)

### Bibliotecas

* mkdocs - [link](https://www.mkdocs.org/)
* mkdocs-material - [link](https://squidfunk.github.io/mkdocs-material/)

### Ferramentas

* Visual Studio Code - IDE - [link](https://code.visualstudio.com/)
* Python - [link](https://www.python.org/)
* Pip - Gerenciador de Pacotes do Python - [link](https://pypi.org/project/pip/)
* Venv - Ambiente Virtual do Python - [link](https://docs.python.org/pt-br/3/library/venv.html)
* Git - Sistema de Controle de Versão - [link](https://git-scm.com/)
* Github - Plataforma de Hospedagem de Códigos - [link](https://github.com/)

## Objetivo da Aula

O objetivo da aula é apresentar uma introdução a documentação técnica com o MkDocs. Assim, os fundamentos para construção de documentação em formato de página web com essa ferramenta será abordado.

A animação abaixo mostra de forma visual o resultado esperado nesta aula.

![Objetivo da Aula](./recursos/objetivo_mkdocs.gif)

## Desenvolvimento do Projeto

### Clonando o Repositório

Inicialmente, clone o repositório da seguinte forma:

```bash
git clone https://github.com/ufla-prog-web/aula-mkdocs.git
```

### Baixando o Repositório

Caso deseje ao invês de clonar o repositório (método acima), baixe o repositório do [link](https://github.com/ufla-prog-web/aula-mkdocs) clicando em `Code` e `Download ZIP`.

### Abrindo o Visual Studio Code

Abra o IDE Visual Studio Code na pasta `aula-mkdocs`.

**Dica:** Abra o arquivo `README.md` e clique em `Open Preview to the Side` para facilitar a construção da aplicação.

### Instalando o Python

Se necessário, instale o Python (testado na versão 3.10.12) [link](https://www.python.org/downloads/)

Verifique a versão instalada do Python (para ter certeza que tudo ocorreu bem):

```bash
python3 --version
```

### Instalando o Pip

Se necessário, instale o pip (testado na versão 22.0.2):

```bash
sudo apt install python3-pip
```

Verifique a versão instalada do pip (para ter certeza que tudo ocorreu bem):

```bash
pip3 --version
```

### Criando a Pasta do Projeto

Inicialmente, crie uma pasta do projeto (dentro da pasta `aula-mkdocs`):

```bash
mkdir mkdocs
```

A ideia desta pasta é armazenar o projeto em Python do MkDocs.

### Abrindo a Pasta do Projeto

Navegue até a pasta `mkdocs`.

```bash
cd mkdocs
```

### Criando o Ambiente Virtual

Crie o ambiente virtual com o `venv` para isolar a instalação de dependências do Python:

Unix/macOS

```bash
python3 -m venv venv
```

Windows

```bash
py -m venv venv
```

Ative o ambiente virtual no seu computador utilizando o comando abaixo:

Unix/macOS

```bash
source venv/bin/activate
```

Windows

```bash
.\venv\Scripts\activate
```

Quando desejar sair do ambiente virtual, basta digitar:

```bash
deactivate
```

### Criando um Arquivo com as Dependências da Aplicação

Crie um arquivo `requirements.txt` dentro da pasta `mkdocs` com o seguinte conteúdo:

```
mkdocs==1.5.2
mkdocs-autorefs==0.5.0
mkdocs-material==9.2.7
mkdocs-material-extensions==1.1.1
```

### Instalando as Dependências da Aplicação

Utilize os comandos abaixo para instalar as dependências da aplicação dentro do ambiente virtual criado:

```shell script
pip3 install -r requirements.txt
```

### Criando o Projeto da Documentação

O desenvolvimento da documentação inicia-se com a criação do projeto com o mkdocs utilizando o comando abaixo:

```bash
mkdocs new minha-docs-mkdocs
cd minha-docs-mkdocs
```

A ideia desse comando é criar a aplicação com o MkDocs. Essa aplicação possui o nome `minha-docs-mkdocs`.

Analise a pasta `minha-docs-mkdocs` criada, repare que possui uma pasta chamada `docs` e um arquivo chamado `mkdocs.yml`.

### Construindo a Documentação

Utilize o comando abaixo para construir a documentação do projeto:

```bash
mkdocs build
```

**OBS:** É necessário executar esse comando todas as vezes que houver modificação nos arquivos markdown da documentação.

Esse comando cria uma pasta chamada `site` com todo o conteúdo do site dentro do projeto chamado `minha-docs-mkdocs`.

Analise a estrutura de arquivos e diretórios da pasta `site`.

### Executando a Aplicação

Utilize o comando abaixo para executar a aplicação:

```bash
mkdocs serve
```

Após executar esse comando, acesso o endereço utilizando o navegador [http://127.0.0.1:8000/](http://127.0.0.1:8000/). Com essa forma de execução, atualizações na documentação são refletidas instantaneamente no site.

Para alterar a porta em que a documentação ficará disponível, utilize o comando abaixo:

```shell script
mkdocs serve -a localhost:9000
```

ou

```shell script
cd site
python3 -m http.server -b localhost 9000
```

Após executar esse comando, acesse o endereço utilizando o navegador [http://localhost:9000/](http://localhost:9000/). Com essa forma de execução, apenas o site estático é acessado pelo navegador.

### Personalizando a Documentação

As configurações principais do projeto de documentação utilizam a linguagem de descrição YAML e ficam no arquivo chamado `mkdocs.yml`. Esse arquivo possui a seguinte estrutura geral:

```yml
site_name: My Docs
```

Abra esse arquivo é escreva o seguinte conteúdo:

```yml
site_name: Documentação do MkDocs
```

Repare que existe uma pasta chamada `docs` e que dentro dessa pasta existe um arquivo chamado `index.md`. Abra esse arquivo, e analise o conteúdo do mesmo.

Substitua o conteúdo desse arquivo pelo conteúdo abaixo.

```markdown
# Bem-Vindo a Documentação do MkDocs

Para acessar a documentação completa acesse [mkdocs.org](https://www.mkdocs.org).

![Logo Mkdocs](./imgs/logo-mkdocs.png)

## Resumo dos Comandos

* `mkdocs new [nome-diretorio]` - Cria um novo projeto.
* `mkdocs serve` - Inicie o servidor de documentos.
* `mkdocs build` - Constroi o site de documentação.
* `mkdocs -h` - Imprime uma mensagem de ajuda e sai.

## Layout do Projeto

O projeto em Mkdocs está organizado da seguiente maneira:

    mkdocs.yml    # Arquivo de configuração
    docs/
        index.md  # Página inicial da documentação.
        ...       # Outras páginas em markdown, imagens e outros arquivos.
```

Crie dentro da pasta `docs` uma pasta chamada `imgs`. Copie o arquivo `logo-mkdocs.png` da pasta `recursos` para a pasta `imgs` criada.

Execute o comando abaixo para executar novamente a aplicação:

```bash
mkdocs serve
```

Acesse a URL [http://127.0.0.1:8000/](http://127.0.0.1:8000/).

### Criando uma Nova Página

Agora, iremos criar uma nova página na nossa documentação. Para isso faça o seguinte. Crie um arquivo chamado `introducao.md` dentro da pasta `docs`. Nesse arquivo, coloque o seguinte conteúdo:

```markdown
# Introdução

## O Que é o MkDocs?

O MkDocs é uma ferramenta de código aberto escrita em Python, usada para criar documentação estática para projetos. Ele permite que os desenvolvedores criem documentações elegantes e responsivas usando arquivos de texto simples formatados em Markdown. O MkDocs gera um site estático a partir desses arquivos Markdown, facilitando a criação e a manutenção de documentação para projetos de software, bibliotecas, APIs e muito mais. É uma ferramenta popular entre desenvolvedores por sua simplicidade e flexibilidade.

## Principais Vantagens

**Simplicidade**: MkDocs é extremamente simples de configurar e usar. Ele utiliza Markdown para escrever conteúdo, o que é muito mais fácil e intuitivo do que escrever HTML ou LaTeX, por exemplo. Isso torna a curva de aprendizado suave para novos usuários.

**Facilidade de Personalização**: Embora MkDocs seja simples de usar, ele oferece muitas opções de personalização. Você pode escolher entre vários temas, configurar a estrutura da sua documentação e até mesmo estender as funcionalidades do MkDocs com plugins.

**Integração com Controle de Versão**: MkDocs se integra bem com sistemas de controle de versão como Git. Isso permite que você mantenha sua documentação junto com o código-fonte do seu projeto e aproveite os recursos de colaboração e controle de versão oferecidos pelo Git.

**Responsivo e Estilo Moderno**: As documentações criadas com MkDocs geralmente têm um design limpo, moderno e responsivo, o que as torna adequadas para visualização em uma variedade de dispositivos, desde desktops até smartphones.

## Principais Desvantagens

**Limitações de Formatação**: Embora Markdown seja fácil de usar, ele tem algumas limitações em termos de formatação quando comparado a linguagens de marcação mais complexas, como HTML. Isso pode ser um problema se você precisar de um controle preciso sobre a aparência da sua documentação.

**Menos Recursos Avançados**: MkDocs pode ser menos adequado para documentações muito complexas que exigem recursos avançados, como suporte completo a LaTeX para equações matemáticas complexas ou funcionalidades específicas de gerenciamento de API.

**Dependência de Python**: MkDocs é construído em Python, o que significa que você precisa ter Python instalado em seu sistema para usá-lo. Isso pode ser uma desvantagem se você não estiver familiarizado com Python ou se estiver trabalhando em um ambiente onde Python não é uma opção viável.

**Gestão de Imagens**: A gestão de imagens pode ser um pouco mais complicada em comparação com outras ferramentas de documentação, especialmente se você precisar de um controle mais granular sobre o posicionamento e o redimensionamento das imagens.

## Ferramentas para Markdown

O site [markdown live preview](https://markdownlivepreview.com/) é uma boa ferramenta para testar e visualizar a saída gerada por determinado código escrito em Markdown.

O site [markdown guide](https://www.markdownguide.org/tools/) lista um conjunto de outros sites e ferramentas que suportam a linguagem Markdown.
```

### Atualizando o Arquivo mkdocs.yml

Agora, iremos atualizar o arquivo `mkdocs.yml`.

```yml
site_name: Documentação do MkDocs

site_url: https://example.com/
site_description: Documentação do MkDocs.
site_author: Prof. Jesimar Arantes

repo_name: ufla-prog-web/aula-mkdocs
repo_url: https://github.com/ufla-prog-web/aula-mkdocs

nav:
  - Início: index.md
  - Introdução: introducao.md

copyright: Copyright &copy; GAC116 - 2024

theme: readthedocs
```

**Explicação:**

* **site_name**: Este campo define o nome do site de documentação. Ele aparecerá no título da página e pode ser usado em outros lugares para identificar o site.

* **site_url**: Este campo define a URL base do site de documentação. Ele é útil quando você deseja vincular recursos externos, como imagens ou links, no site.

* **site_description**: Este campo fornece uma descrição breve do site de documentação. Ele geralmente aparece em metadados e pode ser usado para melhorar a acessibilidade e a indexação pelos mecanismos de busca.

* **site_author**: Este campo especifica o autor ou autores do site de documentação. Ele pode ser usado para identificar quem é responsável pela criação e manutenção da documentação.

* **repo_name**: Este campo define o nome do repositório onde está armazenado o código-fonte do projeto. Ele pode ser usado para gerar links para o repositório no site de documentação.

* **repo_url**: Este campo especifica a URL do repositório onde está armazenado o código-fonte do projeto. Ele é usado em conjunto com o repo_name para gerar links para o repositório no site de documentação.

* **nav**: Este campo define a estrutura da navegação do site de documentação. Ele permite que você especifique os links para as diferentes páginas da documentação e como elas devem ser organizadas na barra de navegação do site. Geralmente, você fornece uma lista de pares chave-valor, onde a chave é o texto do link e o valor é o caminho para a página correspondente.

* **copyright**: Este campo define os direitos autorais ou qualquer outra informação de direitos autorais que você deseja exibir no rodapé do site de documentação. Você pode usar este campo para fornecer informações sobre quem possui os direitos autorais do conteúdo ou especificar uma licença para o uso do conteúdo.

* **theme**: Este campo especifica o tema (aparência) a ser usado para o site de documentação. O MkDocs suporta vários temas pré-construídos, como "mkdocs" (o tema padrão), "readthedocs", "material", entre outros. Você pode escolher o tema que melhor se adapta ao estilo e às necessidades do seu projeto.

Acesse a URL [http://127.0.0.1:8000/](http://127.0.0.1:8000/).

### Estilizando a Página

Agora, iremos estilizar/personalizar ainda mais a página da documentação, para isso no final do arquivo `mkdocs.yml` adicione o seguinte conteúdo:

```yml
...

#theme: readthedocs  # comente essa linha

theme:
  name: material
  language: pt-BR
  palette: 
    # Paleta quando esta no modo light
    - scheme: default
      primary: blue       # cor dos menus principais
      accent: indigo      # cor dos links 
      toggle:
        icon: material/brightness-7 # icone para troca de modo
        name: Trocar para modo escuro
    # Paleta quando esta no modo dark
    - scheme: slate 
      primary: brown
      accent: orange
      toggle:
        icon: material/brightness-4 # icone para troca de modo (escuro)
        name: Trocar para modo claro
  favicon: imgs/favicon.ico         # adiciona um favicon no site
  features:
    - content.tabs.link             # habilita o vinculo de guias de conteúdo
    - content.code.copy             # hbilita a cópia de códigos da página
```

Copie o arquivo `favicon.ico` da pasta `recursos` para a pasta `imgs`.

Acesse a URL [http://127.0.0.1:8000/](http://127.0.0.1:8000/).

Para mais informações sobre cores e modo de exibição (claro - escuro) consulte [cores](https://squidfunk.github.io/mkdocs-material/setup/changing-the-colors/).

Para mais informações sobre favicon, consulte [favicon](https://squidfunk.github.io/mkdocs-material/setup/changing-the-logo-and-icons/#favicon).

### Criando uma Página de Recursos

Agora, iremos criar uma nova página na nossa documentação. Para isso faça o seguinte. Copie o arquivo chamado `recursos.md` da pasta `recursos` para dentro da pasta `docs`.

Em seguida, no arquivo `mkdocs.yml` atualize o seguinte conteúdo:

```yaml
...

nav:
  - Início: index.md
  - Introdução: introducao.md
  - Recursos: recursos.md

...
```

Para que todos os exemplos funcionem, é necessário incluir as seguintes extensões no arquivo `mkdocs.yml`:

```yaml
...
markdown_extensions:
  - tables
  - abbr                        # usado para definir abreviaturas
  - admonition                  # usado para definir advertências 
  - pymdownx.details            # usada para recolher conteúdo
  - pymdownx.superfences:
      custom_fences:
        - name: mermaid
          class: mermaid
          format: !!python/name:pymdownx.superfences.fence_code_format
  - pymdownx.highlight:         # usada para colorir as tags dos códigos json, python, etc.
      anchor_linenums: true     # usado para blocos de código
      line_spans: __span        # usado para blocos de código
      pygments_lang_class: true # usado para blocos de código
  - pymdownx.inlinehilite       # usado para blocos de código
  - pymdownx.snippets           # usado para blocos de código
  - pymdownx.tabbed:            # usado para guias de conteúdo
      alternate_style: true     # usado para guias de conteúdo
  - attr_list

extra_javascript:
  - https://unpkg.com/tablesort@5.3.0/dist/tablesort.min.js
  - javascripts/tablesort.js
```

Acesse a URL [http://127.0.0.1:8000/](http://127.0.0.1:8000/).

### Analisando o Conteúdo de Recursos

Analise o conteúdo do arquivo `recursos.md` para entender os exemplos.

Em seguida, altere os exemplos lá existentes.

## Próximas Etapas

Agora que você sabe como construir uma documentação de técnica, utilize os conhecimentos e exemplos aqui apresentados para fazer o seu trabalho sobre tecnologia. Nesse trabalho, os aspectos mais importantes da tecnologia escolhida deverão ser documentados. Por fim, o relatório em forma de site deverá ser postado publicamente no github.

## Créditos e Referências

Este tutorial foi inspirado nos seguintes recursos:

* [Documentação oficial do MkDocs](https://www.mkdocs.org)
* [Documentação oficial do MkDocs Material](https://squidfunk.github.io/mkdocs-material/)
* [Documentação oficial do Mermaid](https://mermaid.js.org/intro/)
