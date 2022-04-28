# Apresentação Teórica

## 1. Apresentação do Projeto.

Mostrando o que vai ser feito no curso, as tecnologias e como vai ser feito.

Links passados
`https://my-trips.willianjusten.com.br` - projeto no ar
`https://github.com/react-Avancado/boilerplate` - boilerplate
`https://github.com/willianjusten/my-trips` - Projeto final

## 2. Introdução ao NextJS

NextJS é um framework web desenvolvido com ReactJS

SSR - Server Side Rendering
SSG - Static Site Generation
Styled-JSX
Zero Configuration

Static Site | GatsbyJS, Hexo
Client Side Rendering (Single page Application - SPA) | Creat React App

**Static Site**

> Pega a REST api e o conteúdo estático e coloca na CDN que é um servidor. Quando for abrir o site, ele pega coisa da CDN ao inves de pegar da API.
>
> > **Vantagens**
> >
> > Uso baixo de servidor
> > Pode ser servida em uma CDN
> > Melhor Performance
> > Pode usar em qualquer servidor
> >
> > **Desvantagens**
> >
> > Tempo de build pode ser muito alto
> > Dificuldade para escalar em aplicações grandes
> > Dificuldade para realizar atualizações constantes
>
> **Quando usar**
>
> Site simples sem muita interação do usuário
> Conteúdo de desenvolvedor único
> Conteúdo que nao muda muito
> Simplicidade
> Quando performance for extremamente importante

**Client Side Rendering**

> O site pega html, css e js na CDN. Mas a página nao carrega pois as infos ele ainda vai puxar da REST API depois

**SSR**

> Ao abrir o site o server recebe a chamada e o servidor faz a chamada na API pelas infos. Quando o usuario abre a pagina ela ja vem tudo sem renderizar no client side
>
> > **Vantagens**
> >
> > Ótimo em SEO
> > Meta Tags com previews mais dequados
> > Melhor performance para o usuário
> > Código compartilhado com o backend em Node
> > Menor processamento no lado do usuário
> >
> > **Desvantagens**
> >
> > Time to first byte maior, pois ele vai ter que renderizar tudo antes de entregar algo
> > HTML maior
> > Reload completo nas mudanças de rota, sempre bater no servidor quando precisa de algo
>
> **Quando usar**
> Quando tem necessidade de um SPA mas precisa de um loading rapido
> Quando o conteúdo muda com frequência
> Quando trabalha com um número grande de páginas
> Quando precisa de uma boa indexação no Google
>
> Ex: Ecommerce e Sites de Notícia;

**SPA**

> **Vantagens**
>
> Permite paginas ricas em interações sem recarregar
> Site rápido após o load incial
> Ótimo paras  aplicações web
> possui diversas bibliotecas
>
> **Desvantagens**
>
> Load inicial pode ser muito alto
> performance imprevisível
> Dificuldade no SEO
> Maioria do conteúdo não é indexado
>
> **Quando usar**
>
> Quando nao tem necessidade de indexar informações ao google
> Quando o usuário faz muitas interações na página sem que vc queira refresh's
> Quando as informações vao ser diferentes para cada usuário (autenticação)

Links passados em aula para estudar

` https://nextjs.org/learn/basics/create-nextjs-app` (Tutorial oficial passo-a-passo)
`https://dev.to/kefranabg/demystifying-ssr-csr-universal-and-static-rendering-with-animations-m7d`
(animações vistas nos slides)
`https://marinaaisa.com/blog/cook-websites-based-on-your-needs/` (explicações sobre quando usar um ou outro)
`https://github.com/vercel/next.js/tree/canary/examples` (vários exemplos oficiais do NextJS com outras tecnologias)