# Instituto Conecta Esperança

Projeto acadêmico desenvolvido ao longo das Experiências Práticas I–IV da disciplina de Desenvolvimento Front-end. A aplicação simula a presença digital de uma organização do terceiro setor e consolida HTML5 semântico, CSS3 responsivo, JavaScript modular, SPA, acessibilidade, versionamento e preparação para produção.

## Visão geral

A plataforma apresenta a ONG, seus projetos sociais e um fluxo de cadastro de apoiadores e voluntários. A navegação funciona como uma Single Page Application baseada em hash, sem recarregar o documento principal.

## Tecnologias

- HTML5 semântico
- CSS3 com Design System, Grid de 12 colunas e Flexbox
- JavaScript ES6+ com módulos
- Vite
- Day.js
- Web Storage (`localStorage`)
- Git e GitHub
- Vercel para deploy

## Funcionalidades

- SPA com navegação dinâmica e histórico do navegador
- Templates HTML carregados como recursos `raw` pelo Vite
- Cards de projetos gerados dinamicamente
- Filtro de projetos
- Formulário com máscaras de CPF, telefone e CEP
- Validação nativa + feedback visual acessível
- Persistência de dados não sensíveis no `localStorage`
- Tema claro, escuro e alto contraste
- Menu responsivo com dropdown e modo hambúrguer
- Modal acessível com gestão de foco e tecla `Esc`
- Toasts com região `aria-live`
- Respeito a `prefers-reduced-motion`

## Estrutura

```text
projeto-ong/
├── index.html
├── html/
│   ├── home.html
│   ├── projetos.html
│   └── cadastro.html
├── css/
│   └── style.css
├── js/
│   ├── app.js
│   ├── navigation.js
│   ├── templates.js
│   ├── form.js
│   ├── storage.js
│   └── ui.js
├── imagens/
├── .github/workflows/ci.yml
├── .gitignore
├── CHANGELOG.md
├── package.json
├── vercel.json
└── README.md
```

## Instalação local

Pré-requisito: Node.js 20.19+.

```bash
git clone https://github.com/Gmerick/projeto-ong.git
cd projeto-ong
npm install
npm run dev
```

Abra o endereço informado pelo Vite no navegador.

## Build e preview

```bash
npm run build
npm run preview
```

A build é gerada na pasta `dist/`. O Vite minifica JavaScript e CSS e empacota os templates importados pela aplicação.

## Acessibilidade

O projeto foi estruturado com foco nas diretrizes WCAG 2.1 nível AA:

- landmarks semânticos (`header`, `nav`, `main`, `footer`)
- link para saltar ao conteúdo principal
- foco visível
- navegação por teclado
- associação entre `label` e controles
- `aria-expanded`, `aria-controls`, `aria-live`, `aria-invalid`, `role="dialog"` e `aria-modal`
- textos alternativos em imagens
- modo de alto contraste
- suporte a movimento reduzido
- mensagens de validação que não dependem exclusivamente de cor

## Privacidade da demonstração

CPF, telefone e CEP são utilizados somente para demonstrar máscaras e validação. Esses campos não são persistidos no `localStorage`. O armazenamento local mantém apenas dados necessários para demonstrar continuidade da experiência acadêmica.

## Versionamento

Fluxo baseado em GitFlow:

- `main`: versão estável
- `develop`: integração de desenvolvimento
- `feature/*`: funcionalidades isoladas
- `hotfix/*`: correções urgentes

Mensagens seguem Conventional Commits, por exemplo:

```text
feat: implementa navegação SPA
fix: corrige validação do formulário
a11y: melhora navegação por teclado
docs: atualiza documentação
perf: otimiza recursos para produção
```

Releases seguem Semantic Versioning (`MAJOR.MINOR.PATCH`). A primeira versão estável é `v1.0.0`.

## CI/CD

O workflow do GitHub Actions valida a sintaxe JavaScript e executa a build em pushes e pull requests. Na Vercel, a branch `main` é utilizada para produção e branches/PRs podem gerar previews.

## Manutenção

Antes de integrar alterações:

1. criar uma branch `feature/*` a partir de `develop`;
2. executar `npm run check:js`;
3. executar `npm run build`;
4. testar navegação, formulário, localStorage, teclado e temas;
5. abrir Pull Request para revisão.

## Licença e contexto

Projeto acadêmico demonstrativo. As informações institucionais e de contacto utilizadas na interface são fictícias.
