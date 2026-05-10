# Web Automação Santos

Site estático profissional para GitHub Pages.

## Estrutura

```txt
index.html
.nojekyll
assets/
  css/
    styles.css
  js/
    main.js
  img/
    pdv-legal-01.jpg
    pdv-legal-02.jpg
    ...
  favicon.svg
```

## Publicação no GitHub Pages

Envie todos os arquivos e pastas para a raiz do repositório.

A estrutura no GitHub deve ficar assim:

```txt
WebautomacaoSantos/
├── index.html
├── .nojekyll
├── README.md
└── assets/
    ├── css/
    ├── js/
    ├── img/
    └── favicon.svg
```

Depois vá em:

Settings → Pages → Deploy from a branch → main / root → Save

## Observações

- As imagens ficam na pasta `assets/img`.
- O CSS fica em `assets/css/styles.css`.
- O JavaScript fica em `assets/js/main.js`.
- O modal de ampliação das imagens abre na própria página.
- O vídeo do YouTube possui botão de fallback caso o navegador bloqueie o embed.


Atualização: cards de imagens da seção de equipamentos ajustados para ficarem com o mesmo tamanho visual.
