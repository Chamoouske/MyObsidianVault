---
tag: ajuda
---
#  Vite+Tailwind
## Extenções para instalar no VSCode
1. React Snippets
2. Tailwind CSS IntelliSense
3. PostCSS Language Support
4. Autoprefixer

## Criação de projetos
```bash
npm create vite@latest tiktok-feed -- --template react-ts
```

## Instalação Tailwind
```bash
yarn add -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```
Usar o passo a passo do site oficial do [Tailwind](https://tailwindcss.com/docs/guides/vite)

## Alguns comandos de cmd pra criar pastas
```bash
"src/components", "src/pages" |%{mkdir $_}
```

## Criar arquivos e várias pastas ao mesmo tempo
```bash
"src/components/FeedGrid" |%{mkdir $_; ni\index.tsx}
```

## Outras extenções
1. Glassit

## Ler depois
- [Vite + Electron](https://dev.to/rafaelberaldo/como-criar-um-app-electron-usando-vite-52d6)
