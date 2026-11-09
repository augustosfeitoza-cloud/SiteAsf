# SiteAsf — site institucional da ASF Contabilidade

Site institucional da ASF Contabilidade. O site é estático (um `index.html` e a pasta `assets/`). Não precisa de servidor, banco de dados nem mensalidade de hospedagem.

## Arquivos

```
SiteAsf/
├── index.html          ← o site inteiro (textos, cores, formulário)
└── assets/
    ├── logo.png    ← logo oficial (fundo transparente)
    └── favicon.png ← ícone da aba do navegador
```

## 1. Publicar (opção recomendada: Netlify, gratuito)

1. Crie uma conta em https://app.netlify.com (pode entrar com a conta do GitHub).
2. **Jeito mais rápido:** acesse https://app.netlify.com/drop e arraste a pasta do site inteira. Em segundos o site fica no ar num endereço `algumacoisa.netlify.app`.
3. **Jeito com atualização automática:** em *Add new site → Import from GitHub*, escolha o repositório `SiteAsf`, branch `main`, deixe *Base directory* e *Build command* vazios e *Publish directory* = `.`. Cada alteração enviada ao GitHub atualiza o site.

Alternativas equivalentes e gratuitas: Vercel, Cloudflare Pages ou GitHub Pages. Se o seu domínio veio com hospedagem (Hostinger, Locaweb, HostGator…), também dá para enviar os arquivos pelo Gerenciador de Arquivos para a pasta `public_html`.

## 2. Ligar o seu domínio

No Netlify: *Site configuration → Domain management → Add a domain* → digite `asfcontabil.com.br`. O Netlify mostra os registros a criar. No painel onde o domínio está registrado (Registro.br, GoDaddy, Hostinger…), na área de **DNS**:

| Tipo  | Nome | Valor                        |
|-------|------|------------------------------|
| A     | @    | 75.2.60.5                    |
| CNAME | www  | `seu-site.netlify.app`       |

(Confirme os valores exibidos pelo Netlify — eles prevalecem.) A propagação leva de minutos até 24 h. O HTTPS (cadeado) é ativado automaticamente.

> **Atenção ao e-mail:** se o e-mail `@asfcontabil.com.br` já funciona, **não apague os registros MX** do DNS. Altere apenas os registros A/CNAME do site.

## 3. Ativar o formulário por e-mail (uma vez só)

O botão **Enviar por e-mail** usa o FormSubmit (gratuito, sem cadastro). Depois de publicar:

1. Abra o site e envie um contato de teste.
2. Chegará em `asfcontabil@asfcontabil.com.br` um e-mail do FormSubmit pedindo confirmação — clique em **Activate Form**.
3. Pronto: os próximos contatos chegam direto na caixa de entrada (confira também a pasta de spam no começo).

O botão **Enviar pelo WhatsApp** funciona desde o primeiro minuto: abre o WhatsApp com nome, e-mail, telefone e interesse já escritos para o número (11) 97875-7407.

## 4. Alterar número, e-mail ou textos

No `index.html`, procure o bloco `CONFIGURAÇÃO` no final do arquivo:

```js
const WHATSAPP = '5511978757407';                 // 55 + DDD + número
const EMAIL    = 'asfcontabil@asfcontabil.com.br';
const MSG_PADRAO = 'Olá, ASF Contabilidade! ...';
```

Ao mudar essas duas linhas, o número e o e-mail mudam em todo o site (botões, faixa verde, contato e rodapé). Textos dos serviços e da seção "Sobre" podem ser editados diretamente no HTML.

## Identidade visual

- Fonte única: **Montserrat** (Google Fonts), pesos 400 a 800.
- Cores tiradas do logo oficial: verde ASF `#006553`, verde-escuro `#00352B` (faixas e contato), grafite `#373738` e verde-claro `#EEF5F3` para fundos.
- Logo oficial da pasta *LOGO* do Drive. Nenhuma imagem dos posts do Instagram é usada; o painel ilustrativo do topo é feito em HTML.
