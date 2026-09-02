# Deploy e CI/CD

## Produção

- Plataforma: Vercel
- Projeto: `projeto-ong`
- Repositório conectado: `Gmerick/projeto-ong`
- Branch de produção: `main`
- Framework: Vite
- Build: `npm run build`
- Diretório de saída: `dist`
- URL pública: https://projeto-ong-bice.vercel.app

## Fluxo de entrega

1. alterações são desenvolvidas em branches `feature/*` derivadas de `develop`;
2. um Pull Request integra a feature em `develop` após revisão;
3. o GitHub Actions executa instalação, verificação da sintaxe JavaScript e build;
4. uma release é promovida de `develop` para `main` por Pull Request;
5. a integração Git da Vercel detecta o commit em `main` e cria um novo deployment de produção;
6. branches e Pull Requests podem gerar Preview Deployments para validação antes da publicação.

## GitHub Actions

O workflow `Frontend CI` executa:

```text
npm install
npm run check:js
npm run build
```

A pipeline utiliza Node.js 22 e um `package-lock.json` versionado para garantir instalação reprodutível.

## Deploy Hooks

Não são necessários para o fluxo normal, pois o projeto utiliza integração Git nativa entre GitHub e Vercel. Deploy Hooks ficam reservados para integrações externas que precisem disparar uma build sem criar commit no repositório.
