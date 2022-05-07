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

