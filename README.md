portal-app/
├── www/                         → o PWA (isto é o que você hospeda online)
│   ├── index.html               → o portal (já preparado como PWA)
│   ├── manifest.webmanifest     → identidade do app (nome, cores, ícones)
│   ├── service-worker.js        → cache + offline
│   ├── offline.html             → tela exibida sem conexão
│   ├── icons/                   → ícones 192, 512, maskable, favicon
│   └── .well-known/
│       └── assetlinks.json      → verifica que o app pertence ao seu domínio
├── android/
│   └── twa-manifest.json        → configuração do Bubblewrap (gera o AAB)
├── store/
│   ├── ficha-google-play.md     → títulos e descrições prontos
│   ├── politica-de-privacidade.html → hospede e use a URL na loja (obrigatório)
│   ├── feature-graphic-1024x500.png → gráfico de destaque
│   └── play-icon-512.png        → ícone da loja
└── README.md