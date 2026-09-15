# 🎮 G3 Gamer Store

![React](https://img.shields.io/badge/React-18.3-61DAFB?logo=react&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5.8-3178C6?logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-5.4-646CFF?logo=vite&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.4-06B6D4?logo=tailwindcss&logoColor=white)
![Vitest](https://img.shields.io/badge/Vitest-3.2-6E9F18?logo=vitest&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green.svg)

Landing page de e-commerce gamer desenvolvida com React e TypeScript, com foco em apresentação de produtos, navegação responsiva e uma experiência interativa para montagem de PCs.

## Visão geral

O G3 Gamer Store foi desenvolvido como uma experiência web para uma loja especializada em produtos e componentes gamer.

O projeto combina uma landing page comercial com seções de produtos, ofertas, categorias, marcas e um fluxo interativo para montagem de computadores.

## O problema

Uma loja de hardware gamer precisa apresentar diferentes categorias de produtos de forma visual, organizada e fácil de navegar, além de oferecer uma experiência mais interativa para quem deseja montar um PC.

O desafio foi transformar essa apresentação em uma interface moderna, responsiva e orientada à experiência do usuário.

## Solução

A aplicação organiza a experiência em seções reutilizáveis e componentes independentes, incluindo:

- Hero e apresentação principal
- Destaques e benefícios
- Ofertas
- Categorias de produtos
- Marcas
- Newsletter
- Contato via WhatsApp
- Fluxo interativo de montagem de PC
- Navegação entre páginas
- Componentes de interface reutilizáveis

A página principal é composta por componentes independentes, enquanto a rota `/monte-seu-pc` concentra a experiência de configuração de hardware.

## Stack

### Frontend

- **React 18** — construção da interface
- **TypeScript** — tipagem estática e organização do código
- **Vite** — desenvolvimento e build
- **React Router DOM** — navegação entre páginas

### UI e experiência

- **Tailwind CSS** — estilização utility-first
- **shadcn/ui + Radix UI** — componentes e primitivas de interface reutilizáveis
- **Framer Motion** — animações e interações
- **Lucide React** — ícones
- **Embla Carousel** — carrosséis
- **Sonner** — notificações

### Formulários e validação

- **React Hook Form** — gerenciamento de formulários
- **Zod** — validação baseada em schemas
- **@hookform/resolvers** — integração entre formulário e validação

### Estado e dados

- **TanStack Query** — gerenciamento de estado assíncrono e cache

### Qualidade

- **ESLint** — análise estática
- **Vitest** — framework de testes
- **Testing Library** — utilitários para testes React
- **jsdom** — ambiente DOM para testes

## Estrutura

```text
src/
├── assets/
├── components/
│   ├── ui/
│   ├── BrandsSection.tsx
│   ├── BuildPCWizard.tsx
│   ├── CategoriesSection.tsx
│   ├── FeaturesSection.tsx
│   ├── Header.tsx
│   ├── Hero.tsx
│   ├── OffersSection.tsx
│   ├── ProductCard.tsx
│   └── ...
├── pages/
│   ├── Index.tsx
│   ├── BuildPC.tsx
│   └── NotFound.tsx
├── test/
│   ├── example.test.ts
│   └── setup.ts
├── App.tsx
├── App.css
├── index.css
└── main.tsx
```

## Qualidade e engenharia

O projeto possui uma base configurada para desenvolvimento em React com TypeScript, ESLint, Vitest, Testing Library e jsdom.

### Testes

A infraestrutura do Vitest está configurada para arquivos `.test.ts`, `.test.tsx`, `.spec.ts` e `.spec.tsx`, com ambiente `jsdom` e setup do Testing Library.

Atualmente existe **1 arquivo de teste**:

```text
src/test/example.test.ts
```

O teste atual é um smoke test que verifica uma asserção básica. Portanto, existe infraestrutura de testes configurada, mas **não há cobertura funcional comprovada de componentes, páginas ou regras de negócio**.

Não é apresentado percentual de cobertura nem badge de testes passando.

## Deploy

O projeto possui configuração para deploy na Vercel através de `vercel.json`, utilizando Vite, build para `dist` e rewrite para `index.html`.

Deploy configurado/documentado no repositório:

**https://g3-gamer-store.vercel.app**

A disponibilidade atual dessa URL não foi confirmada de forma independente.

## Como rodar localmente

### Pré-requisitos

- Node.js
- npm

### Instalação

```bash
git clone https://github.com/KayohanCosta/G3-Gamer-Store.git
cd G3-Gamer-Store
npm install
```

### Desenvolvimento

```bash
npm run dev
```

### Build

```bash
npm run build
```

### Preview

```bash
npm run preview
```

### Testes

```bash
npm run test
```

### Testes em modo watch

```bash
npm run test:watch
```

### Lint

```bash
npm run lint
```

## Resultado

O projeto demonstra uma implementação de interface moderna para e-commerce gamer, combinando componentes reutilizáveis, navegação por rotas, animações, UI baseada em Radix/shadcn e uma experiência interativa de montagem de PC.

A arquitetura técnica detalhada, as decisões de implementação e o fluxo das principais funcionalidades estão documentados em [`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md).

## Licença

Este projeto está sob a licença MIT. Consulte o arquivo [`LICENSE`](LICENSE) para o texto completo da licença.

---

Desenvolvido por [Kayohan Costa](https://github.com/KayohanCosta)
