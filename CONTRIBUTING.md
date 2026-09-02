# Contribuindo

Fluxo sugerido:

1. crie uma branch `feature/*` a partir de `develop`;
2. implemente a alteração mantendo responsabilidade única nos módulos;
3. execute `npm run check:js` e `npm run build`;
4. valide teclado, formulário, temas e responsividade;
5. utilize Conventional Commits;
6. abra Pull Request para `develop` com contexto, testes realizados e impactos.

Correções urgentes de produção devem usar `hotfix/*` a partir de `main` e ser integradas também em `develop`.
