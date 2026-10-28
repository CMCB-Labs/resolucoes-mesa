# Painel de Resoluções de Mesa - Câmara Municipal de Coronel Barros (RS)

Página web responsiva (HTML com CSS e JavaScript incorporados em arquivo único) para consulta pública das **Resoluções da Mesa Diretora** da Câmara Municipal de Coronel Barros - RS.

O painel foi projetado para ser hospedado no **GitHub Pages** e incorporado via **`<iframe>` (embed)** no portal oficial da Câmara Municipal ou consultado diretamente de forma independente.

---

## 🏛️ Características e Funcionalidades

- **Zero dependências externas**: Tudo em um único arquivo `index.html` (CSS e JavaScript nativos, sem bibliotecas pesadas).
- **Integração em tempo real com o SAPL**: Conecta-se diretamente aos endpoints públicos da API do SAPL da Câmara (`/api/norma/normajuridica/?tipo=8`).
- **Resiliência e Carregamento Instantâneo (0ms)**: Possui snapshot inicial dos dados embutido, garantindo exibição instantânea mesmo se a API estiver lenta ou temporariamente instável. Em seguida, busca atualizações silenciosamente em segundo plano.
- **Filtro dinâmico por Ano**: Abas com contagem exata de resoluções cadastradas por exercício (ex: 2026, 2025, 2024, 2023).
- **Busca Rápida com Destaque**: Pesquisa por número da resolução (ex: `10`, `10/2026`), ano ou termos na ementa (com suporte a busca insensível a acentos, ex: pesquisar "diarias" encontra "diárias").
- **Modos de Visualização**:
  - **Grade (Cards)**: Visual moderno com resumo, badges de data, links para download e botão de cópia de link.
  - **Tabela**: Visual compacto e denso, ideal para computadores e telas maiores.
- **Download e Acesso Direto**: Botões com identificação visual do formato original (`PDF` ou `DOCX`) e atalho para a página de detalhes no SAPL.
- **Otimizado para Embed (Iframe)**: Detecta automaticamente quando está dentro de um iframe e ajusta margens, fundo e espaçamentos. Suporta redimensionamento automático via `postMessage`.

---

## 🚀 Como Publicar no GitHub Pages

1. Crie um repositório no seu GitHub (exemplo: `resolucoes-mesa-coronel-barros`).
2. Faça o upload do arquivo `index.html` para a raiz (`main` ou `master`) do repositório:
   - Pode subir diretamente pela interface web do GitHub ("Add file" -> "Upload files") ou via `git`:
     ```bash
     git init
     git add index.html README.md
     git commit -m "Publicação inicial do painel de resoluções de mesa"
     git branch -M main
     git remote add origin https://github.com/SEU-USUARIO/SEU-REPOSITORIO.git
     git push -u origin main
     ```
3. No seu repositório no GitHub:
   - Acesse a aba **Settings** (Configurações).
   - No menu lateral esquerdo, clique em **Pages**.
   - Em **Build and deployment > Source**, selecione **Deploy from a branch**.
   - Em **Branch**, selecione `main` (ou `master`) e pasta `/(root)`.
   - Clique em **Save**.
4. Em cerca de 1 minuto, sua página estará online no endereço:
   `https://cmcb-labs.github.io/resolucoes-mesa/`

---

## 🌐 Como Incorporar (Embed) no Site da Câmara

Para adicionar o painel dentro de uma página ou notícia no site da Câmara (WordPress, Joomla, HTML ou portal institucional), basta colar o código `<iframe>` abaixo:

### Opção 1: Padrão (com cabeçalho institucional)
```html
<iframe 
  src="https://cmcb-labs.github.io/resolucoes-mesa/?embed=1" 
  width="100%" 
  height="750" 
  style="border: none; width: 100%; min-height: 600px; border-radius: 8px;" 
  title="Resoluções da Mesa Diretora - Câmara Municipal de Coronel Barros"
  loading="lazy"
  allowfullscreen>
</iframe>
```

### Opção 2: Modo Compacto (Sem o cabeçalho superior)
Ideal se a página do site da Câmara já tiver o seu próprio título:
```html
<iframe 
  src="https://cmcb-labs.github.io/resolucoes-mesa/?embed=1&hide_header=1" 
  width="100%" 
  height="700" 
  style="border: none; width: 100%; min-height: 550px;" 
  title="Resoluções da Mesa Diretora"
  loading="lazy">
</iframe>
```

---

## ⚙️ Parâmetros de URL Disponíveis

| Parâmetro | Valores | Descrição |
| :--- | :--- | :--- |
| `embed` | `1` ou `true` | Ativa o modo de incorporação (fundo transparente e margens reduzidas). |
| `hide_header` | `1` ou `true` | Oculta o banner superior institucional. |

---

## 🔗 Informações Técnicas da API

- **Swagger Oficial**: [https://sapl.coronelbarros.rs.leg.br/api/schema/swagger-ui/](https://sapl.coronelbarros.rs.leg.br/api/schema/swagger-ui/)
- **Endpoint Utilizado**: `https://sapl.coronelbarros.rs.leg.br/api/norma/normajuridica/?tipo=8&format=json`
- **Tipo de Norma no SAPL**: `tipo=8` corresponde especificamente às **Resoluções de Mesa (RM)** da Câmara de Coronel Barros.
