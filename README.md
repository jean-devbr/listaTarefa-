# Lista de Tarefas com Vue 3

Este projeto é uma aplicação simples de lista de tarefas desenvolvida com Vue 3.

Ele serve para organizar tarefas do dia a dia, permitindo:

- adicionar novas tarefas;
- marcar tarefas como concluídas;
- remover tarefas da lista;
- manter os dados salvos no navegador usando `localStorage`.

## Tecnologias usadas

- Vue 3
- Vite
- JavaScript
- CSS

## Como rodar o projeto localmente

### Pré-requisitos

- Node.js instalado
- npm instalado

### Instalação

No diretório do projeto, execute:

```bash
npm install
```

### Ambiente de desenvolvimento

Para iniciar o servidor local:

```bash
npm run dev
```

Depois, abra no navegador o endereço exibido no terminal. Normalmente será algo como:

```bash
http://localhost:5173
```

## Build para produção

Para gerar a versão de produção:

```bash
npm run build
```

Para visualizar localmente a build gerada:

```bash
npm run preview
```

## Estrutura principal

- `src/App.vue`: contém a lógica e a interface da lista de tarefas
- `src/main.js`: inicializa a aplicação Vue
- `src/style.css`: estilos globais do projeto
