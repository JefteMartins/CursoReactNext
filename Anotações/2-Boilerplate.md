# Boilerplate

## 6. Requisitos para o projeto

um requisito é node versão 10+

no projeto será usando o yarn, mas eu vou ficar com o npm mesmo pelo costume

versionador asdf ou nvm pra nao ter problema com linux

## 7. Criando o boilerplate com create-next-app

`npm create nexp-app` - ja baixa as dependencias
comandos disponíveis

- npm run dev - Starts the development server
- npm run build - builds the app for production
- npm start - Runs the built app in production mode

abrir o projeto com vs code basta ir na pasta do projeto no terminal e executar o comando `code .`

**Visão geral das pastas**

**Pages** - Onde vao ficar as estruturas das páginas
**Public** - Onde vai ficar os arquivos estáticos, os Assets
**Styles**- Tem por pad~rao suporte ao CSS Modules, mas será usado o CSS in JS

Começou removendo a pasta `api` do pages
O `_app.js` é importantíssimo pois vai encapsular todos os componentes em nível de página. Mas vai deletar também para construir depois com mais detalhes

Deletou o `global `do `styles `pq nao vai usar mas o `home.modules` ta usando entao vai deletar depois

## 8. Configurando o TypeScript no NextJS

cria o `tsconfig.json` e roda o `npm run dev` ele vai dar o comando para instalar o TS no projeto `npm install --save-dev @types/react @types/node`

com isso populou o `tsconfig.json` e criou o `next-env.d.ts`

Declaration file - d.ts

Declara uns tipos para o projeto para ter os autocompletes 

o `tsconfig` serve para configurar o projeto e o mudar vai ser o `strict`

vai ser mais restrito na análise de tipos do projeto, nao permitindo any's

criado uma pasta `src` e colocado o `pages dentro`
Apíos isso o arquivo index foi renomeado para index.tsx para ser um arquivo typescript com suporte a jsx