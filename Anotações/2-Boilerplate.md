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

## 9. Configurando o .editorconfig

o que faz?

cria regras pro editor pra sempre que criar um arquivo ele formata o arquivo em questão

criando arquivo `.editorconfig` e populando com

```
# editorconfig.org
root = true

[*]
indent_style = space
indent_size = 2
end_of_line = lf
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true


```

## 10. Configurando o Eslint

ele vai apontar inconsistências no seu codigo alem de seguir boas práticas

`npx eslint --init`

**Como será usado:** escolher checar a sintaxe e encontrar problemas, ja que o pretier vai embelezar o código
**Tipos de módulo:** import / export
**Framework:**  React
**Typescript:** sim
**Browser ou node:** browser
**Formato do arquivo:** json

tem alguns plugins que vc vai colocando de acordo com a necessidade, mas ele começa ja colocando um que é o `eslint-plugin-react-hooks`

e customizado vc coloca o `"react-hooks"` nos plugins do `.eslintrc.json`
e os `"react-hooks/rules-of-hooks": "error","react-hooks/exhaustive-deps": "warn"` no `"rules"`

outra regra é o prop types, pra nao ficar dando erro ja que a gente nao vai usar por conta do TS `"react/prop-types": "off"` também no rules.

Também coloca o `"react/react-in-jsx-scope": "off"` para desabilitar o import do react ja que ele é setado globalmente

o `"@typescript-eslint/explicit-module-boundary-types": "off"` para desabilitar os pedidos de tipos quando já se tem por inferencia de tipos

outra informação seria o
```json
"settings": {
        "react": {
            "version": "detect"
        }
    }
```

para ele detectar a versão do react

## 11. Configurando o Prettier com o Eslint

`npm install --save-dev --save-exact prettier`

criar pasta `.prettierrc`

e usar o `eslint-plugin-prettier`

seguir o tutorial `https://github.com/prettier/eslint-plugin-prettier`

## 12. Configurando git hooks com Husky

`npx husky-init && npm install `

## 13. Instalando e configurando o Jest com TypeScript

## 14. Instalando e configurando React Testing Library

Melhor que o enzime pq vai renderizar de verdade seu componente 

`npm install --save-dev @testing-library/react` 