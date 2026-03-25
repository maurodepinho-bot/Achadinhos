# 🛍️ Plano de Negócios — Achadinhos da Internet

Página web interativa com o plano de negócios completo para montar um negócio de achadinhos no Instagram, TikTok e WhatsApp com programas de afiliados.

## ✅ O que está incluído

| Seção | Conteúdo |
|-------|----------|
| 🏗️ Modelo | Funil de conversão completo, 5 fontes de renda |
| 📅 Cronograma | Roadmap de 6 meses em 5 fases |
| 📖 Tutorial | 5 guias detalhados (afiliados, WhatsApp, Canva, Reels, Ads) |
| 🛒 Afiliados | Comparativo de Shopee, Amazon, ML, Magalu e Hotmart |
| 💰 Custos | Ferramentas gratuitas e pagas detalhadas |
| 📈 Faturamento | Projeções com cenários pessimista/realista/otimista |
| 🎬 Conteúdo | Calendário editorial semanal + tipos de post que convertem |
| 🔧 Ferramentas | Stack completa de ferramentas, quase 100% gratuita |

---

## 🚀 Como publicar no GitHub Pages (passo a passo)

### Pré-requisito
Ter uma conta no [GitHub](https://github.com). É grátis.

---

### Opção A — Pelo site do GitHub (mais fácil, sem instalar nada)

1. **Faça login** em [github.com](https://github.com)

2. **Crie um repositório novo:**
   - Clique no `+` no canto superior direito → **New repository**
   - Nome: `achadinhos` (ou qualquer nome)
   - Marque **Public** (obrigatório para GitHub Pages grátis)
   - Clique em **Create repository**

3. **Faça upload do arquivo:**
   - Na página do repositório vazio, clique em **uploading an existing file**
   - Arraste o arquivo `index.html` para a área de upload
   - Escreva uma mensagem como `Adicionar site achadinhos` no campo de commit
   - Clique em **Commit changes**

4. **Ative o GitHub Pages:**
   - Vá em **Settings** (aba no topo do repositório)
   - No menu lateral, clique em **Pages**
   - Em *Source*, selecione **Deploy from a branch**
   - Em *Branch*, selecione **main** e pasta **/ (root)**
   - Clique em **Save**

5. **Aguarde 1–2 minutos** e acesse seu site em:
   ```
   https://SEU_USUARIO.github.io/achadinhos/
   ```

---

### Opção B — Pelo terminal (para quem conhece Git)

```bash
# Clone ou crie o repositório
git init achadinhos
cd achadinhos

# Copie o index.html para esta pasta, depois:
git add index.html
git commit -m "Adicionar plano de negócios achadinhos"

# Conecte ao repositório remoto (substitua pelo seu usuário)
git remote add origin https://github.com/SEU_USUARIO/achadinhos.git

# Envie para o GitHub
git push -u origin main
```

Depois ative o GitHub Pages nas **Settings** do repositório conforme o passo 4 da Opção A.

---

## 🔗 Compartilhando o link

Após publicar, seu link será:
```
https://SEU_USUARIO.github.io/achadinhos/
```

Você pode:
- Colocar no **Linktree** da sua bio do Instagram
- Enviar no **grupo do WhatsApp** para sua audiência
- Compartilhar no **TikTok** e **Facebook**

---

## 📁 Estrutura do projeto

```
achadinhos/
└── index.html      ← site completo (único arquivo necessário)
└── README.md       ← este arquivo de instruções
```

O site é 100% **autocontido** — funciona com apenas o `index.html`.  
Não precisa de servidor, build ou instalação de dependências.

---

## 🛠️ Tecnologias

- **React 18** (via CDN)
- **Babel Standalone** (para processar JSX no browser)
- **Google Fonts** (Syne + DM Sans)
- HTML/CSS puro para os estilos

---

## 📄 Licença

Uso pessoal e comercial livre. Modifique à vontade.
