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

código de teste

```tsx
import { render, screen } from '@testing-library/react'

import Main from '.'

describe('<Main />', () => {
  it('should render the heading', () => {
    const { container } = render(<Main />)

    expect(
      screen.getByRole('heading', { name: /react avançado/i })
    ).toBeInTheDocument()

    expect(container.firstChild).toMatchSnapshot()
  })
})
//espera encontrar um h1 com react avançado sem ser case sensitive e que bata com o snapshot como segunda forma de segurança
```

## 15. Usando findRelatedTests para o hook

um detalhe atualizando o lint staged para 

```json
"lint-staged": {
    "src/**/*": ["eslint --cache --fix", "npm test --findRelatedTests --bail"]
  }
```

adicionado o find related tests para dizer para testar o que foi modificado

## 16. Instalando o Styled Components e configurando o SSR

instalação do @babel/styled-components e do babel-plugin-styled-components além do proprio styled components

## 17. Criando estilos globais com createGlobalStyle

```tsx
import { createGlobalStyle } from 'styled-components'

const GlobalStyles = createGlobalStyle `
    *{
        margin: 0;
        padding: 0;
        box-sizing: border-box;
      }
      html {
        font-size: 62.5%;
      }
      html, body, #__next {
        height: 100%;
      }
      body {
        font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif
      }
`

export default GlobalStyles
```



## 18. Criando estilos no primeiro componente

```tsx
import styled from 'styled-components'

export const Wrapper = styled.main`
  background-color: #06092b;
  color: #fff;
  width: 100%;
  height: 100%;
  padding: 3rem;
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
`

export const Logo = styled.img`
  width: 25rem;
  margin-bottom: 2rem;
`

export const Title = styled.h1`
  font-size: 2.5rem;
`

export const Description = styled.h2`
  font-size: 2rem;
  font-weight: 400;
`

export const Illustration = styled.img`
  margin-top: 3rem;
  width: min(30rem, 100%);
`
```

## 19. Melhorando snapshots com Jest-styled-components

`npm install --save-dev jest-styled-components`

## 20. Configurando o PWA

instalando PWA e configurando
