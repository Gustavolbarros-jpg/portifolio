# Portfólio de Landing Pages

Vitrine de **8 landing pages de alta conversão**, cada uma em um nicho diferente, com identidade visual, tom de copy e estrutura próprios. O objetivo é demonstrar **versatilidade**: nenhuma página parece template da outra, mesmo sendo todas do mesmo profissional.

> ⚠️ **Todo o conteúdo é fictício** (nomes de negócios, depoimentos, números, telefones, registros profissionais e endereços). As imagens são placeholders carregados de [picsum.photos](https://picsum.photos). Nada representa pessoas, marcas ou resultados reais.

---

## Estrutura do projeto

```
/
├── index.html            → HUB (vitrine / índice dos 8 trabalhos)
├── 01-advocacia/         → Mendonça & Vale Advocacia (Jurídico)
├── 02-fitness/           → FORJA Personal Training (Fitness)
├── 03-estetica/          → Lumière (Harmonização Facial)
├── 04-imoveis/           → Horizonte Imóveis (Corretor)
├── 05-marketing/         → Tração Performance (Tráfego Pago)
├── 06-psicologia/        → Espaço Sereno (Psicologia)
├── 07-pet/               → AuMigo Pet & Vet (Pet Shop / Veterinária)
├── 08-arquitetura/       → Átrio Arquitetura (Arquitetura & Interiores)
└── README.md
```

Cada pasta numerada contém um único `index.html` **standalone** (HTML + CSS + JS embutidos, sem build, sem dependências). Cada página pode ser:

- aberta sozinha (clicando no arquivo ou via servidor local);
- **deployada de forma independente** (Vercel/Netlify), apontando a raiz do deploy para a pasta do nicho;
- ou hospedada **tudo junto**, mantendo a estrutura acima — o hub (`index.html` da raiz) linka para cada nicho via caminho relativo (`./01-advocacia/`, etc.).

> **Sobre o hub:** o meta-prompt original sugeria uma pasta `/hub`. Aqui o hub foi colocado como `index.html` na **raiz** — assim, ao publicar a pasta inteira, o endereço principal do site já abre a vitrine e todos os links relativos funcionam sem redirecionamento.

---

## Identidade de cada landing (resumo)

| # | Nicho | Negócio (fictício) | Tom | Visual |
|---|-------|--------------------|-----|--------|
| 01 | Advocacia | Mendonça & Vale | Sóbrio, institucional | Navy/petróleo + dourado, tipografia serifada (Playfair) |
| 02 | Fitness | FORJA Personal | Energético, motivacional | Escuro + verde-limão, condensada (Oswald), urgência/countdown |
| 03 | Estética | Lumière | Suave, emocional | Rosé/nude/dourado, serifada elegante (Cormorant) com itálicos |
| 04 | Imóveis | Horizonte | Direto, gerador de lead | Azul/laranja, clean, **formulário** de avaliação grátis |
| 05 | Marketing | Tração Performance | B2B, orientado a dados (AIDA) | Escuro + gradientes (roxo/rosa), dashboard animado |
| 06 | Psicologia | Espaço Sereno | Acolhedor, humano | Verde-sálvia/azul-claro, arredondada (Quicksand), muito respiro |
| 07 | Pet | AuMigo Pet & Vet | Afetuoso, caloroso | Azul/amarelo/verde, redonda (Baloo 2), patinhas |
| 08 | Arquitetura | Átrio | Premium, editorial | Neutra (preto/bege/pedra), grid assimétrico, serifada fina (Fraunces) |

---

## Requisitos técnicos atendidos

- **Mobile-first** e responsivo (menu hambúrguer + breakpoints em todas as páginas).
- **HTML semântico** + CSS moderno (grid/flexbox, `clamp()` para tipografia fluida).
- **Um CTA principal** claro e repetido por página (uma página, um objetivo).
- `<title>` e `meta description` únicos por página + **favicon SVG** próprio (inline, sem arquivos binários).
- Fontes via **Google Fonts** (carregadas por `<link>`, com `preconnect`).
- Imagens com **`loading="lazy"`** abaixo da dobra; heros carregam normalmente.
- WhatsApp como CTA recorrente (`wa.me`) + botão flutuante nas páginas de serviço.
- Disclaimer de conteúdo fictício no rodapé de cada página (a de advocacia inclui ressalva quanto às normas da OAB).

---

## Como rodar localmente

Por usarem fontes e imagens externas, o ideal é servir via HTTP (em vez de abrir o arquivo direto):

```bash
# A partir da raiz do projeto:
python3 -m http.server 8000
# Depois acesse:
#   http://localhost:8000/              → hub
#   http://localhost:8000/02-fitness/   → uma landing específica
```

Alternativas equivalentes: `npx serve`, extensão *Live Server* do VS Code, etc.

---

## Como publicar (deploy)

**Tudo junto (recomendado para a vitrine):**
- **Netlify:** arraste a pasta do projeto em [app.netlify.com/drop](https://app.netlify.com/drop), ou conecte o repositório (sem build; *publish directory* = raiz).
- **Vercel:** `vercel` na raiz, ou importe o repositório (framework: *Other*, sem build command).
- **GitHub Pages:** suba o repositório e ative o Pages na branch principal.

**Uma landing isolada como projeto próprio:**
- Aponte o *publish directory* para a pasta do nicho (ex.: `02-fitness`) — o `index.html` dela é autossuficiente.

---

## Personalização rápida (antes de mostrar a um cliente real)

Cada arquivo é editável diretamente. Os pontos mais comuns a trocar:

- **Número de WhatsApp:** procure por `5500000000000` e substitua pelo número real (formato `55DDDNUMERO`).
- **E-mails e telefones:** placeholders como `(00) 00000-0000` e `contato@...`.
- **Nome/marca do freelancer:** no hub (`index.html`), a marca "Vértice" e o contato no rodapé/CTA.
- **Imagens:** troque as URLs `https://picsum.photos/seed/...` por fotos reais (mantendo proporções) quando houver material do cliente.
