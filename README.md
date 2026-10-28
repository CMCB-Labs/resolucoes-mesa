# Resoluções de Mesa - CMCB

Painel interativo de consulta e transparência das **Resoluções de Mesa** da Câmara Municipal de Coronel Barros/RS. Os dados são sincronizados em tempo real com a API do SAPL (Sistema de Apoio ao Processo Legislativo).

---

## 🌐 Acesso Direto
- **URL:** [https://cmcb-labs.github.io/resolucoes-mesa/](https://cmcb-labs.github.io/resolucoes-mesa/)

---

## 💻 Código para Incorporação (Embed / Iframe)

### Para o portal da Câmara (Plone / Janela ou HTML)
```html
<iframe 
  src="https://cmcb-labs.github.io/resolucoes-mesa/?embed=1&hide_header=1" 
  width="100%" 
  height="1200" 
  frameborder="0" 
  style="border: none; width: 100%; min-height: 800px;">
</iframe>
```

> **Parâmetros aceitos na URL:**
> - `?embed=1`: remove o rodapé e ativa layout compacto para iframe.
> - `&hide_header=1`: oculta o cabeçalho superior padrão.
> - `&page_size=6`: define a quantidade de itens por página (ex: 6 ou 12).