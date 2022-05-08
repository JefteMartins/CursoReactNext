# My Trips

## 21. Inicializando o projeto através do Boilerplate

- Atualizado o nome do projeto e descrição no `manifest.json` e no `_app.tsx`
- Atualizado o retorno do `index.tsx` para somente um h1 com o nome do projeto
- excluído os `styles.ts` e `test.tsx.snap` do projeto pois são referentes ao boilerplate

## 22. Adicionando CSS Variables

Definindo tema para o projeto criando variáveis de CSS ao inves do styled components.

```tsx
:root {
    --variavel: #e20e8d;
  }
	a {
      color: var(--variavel);
    }
```

## 23. Criando componente básico de Mapa com Leaflet

Lê-se "Lif-let"

o Leaflet é totalmente gratuito e mais leve, alem de ser open source

usaremos o React Leaflet que é um wrapper do leaflet

`npm i leaflet react-leaflet ` e `npm install -D @types/leaflet`

## 24. Utilizando dynamic import para scripts que só funcionam no browser

```tsx
import dynamic from 'next/dynamic'

const Map = dynamic(() => import('components/Map'), { ssr: false })
export default function Home() {
    return <Map />
}

```

## 25. Tornando o Mapa mais dinâmico usando testes com TDD



## 26. Criando componente de LinkWrapper com testes

Styled icons

## 27. Criando página de About (rota simples e estático)

https://github.com/JefteMartins/MyTrips/commit/0705b49d7c884944a82651385e9b6c563303a85f

## 28. Apresentando diferentes Headless CMS na Cloud

uso de CMS, no caso do projeto vai ser o GraphCMS

Se cadastrando no GraphCMS, criando a conta e iniciando o projeto

## 29. Criando a estrutura de Pages no CMS e página de about

criando a pagina no GraphCMS

## 30. Configurando GraphQL client

uso da `graphql-request`

`npm i graphql-request graphql`

## 31. Entendendo métodos de getStatic/getServerSide do NextJS e escrevendo queries

o next tem 3 funções importantes

//getStaticPaths => gera as url's em build time (/about - /exemplo)
//getStaticProps => serve para buscar dados da página - buildtime
//getServerSideProps => serve para buscar os dados da página - runtime

um menos usado

//gerInitialProps => é o mesmo do getServerSideProps mas o bundle também vem para o client ao inves de ficar so no server

## 32. Criando o método de getStaticPaths e fallback para a página gerada em runtime

```tsx
export async function getStaticPaths() {
  const { pages } = await client.request(GET_PAGES, { first: 3 })

  const paths = pages.map(({ slug }) => ({
    params: { slug }
  }))

  return { paths, fallback: true }
}
```

## 33. Criando N páginas genéricas dinâmicamente com getStaticPaths e getStaticProps



`https://github.com/JefteMartins/MyTrips/commit/3be13ebbd017a79fde008dc047401cba00d09ea7`

```tsx
import client from 'graphql/client'
import { GET_PAGES, GET_PAGE_BY_SLUG } from 'graphql/queries'
import { GetStaticProps } from 'next'
import { useRouter } from 'next/dist/client/router'
import PageTemplate, { PageTemplateProps } from 'templates/Pages'

export default function Page({ heading, body }: PageTemplateProps) {
  const router = useRouter()

  if (router.isFallback) return null

  return <PageTemplate heading={heading} body={body} />
}

export async function getStaticPaths() {
  const { pages } = await client.request(GET_PAGES, { first: 3 })

  const paths = pages.map(({ slug }) => ({
    params: { slug }
  }))

  return { paths, fallback: true }
}

export const getStaticProps: GetStaticProps = async ({ params }) => {
  const { page } = await client.request(GET_PAGE_BY_SLUG, {
    slug: `${params?.slug}`
  })

  if (!page) return { notFound: true }

  return {
    props: {
      heading: page.heading,
      body: page.body.html
    }
  }
}

```

