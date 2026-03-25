<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Plano de Negócios — Achadinhos da Internet</title>
  <meta name="description" content="Guia completo para montar seu negócio de achadinhos no Instagram, TikTok e WhatsApp com afiliados, cronograma e projeção de faturamento." />
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; }
    body { background: #0a0a0a; font-family: 'DM Sans', sans-serif; color: #f0ede6; min-height: 100vh; }
    #root { min-height: 100vh; }

    /* ── Hero ── */
    .hero {
      background: linear-gradient(135deg, #0a0a0a 0%, #1a0a00 50%, #0a0a0a 100%);
      border-bottom: 1px solid #2a1500;
      padding: 48px 24px 36px;
      position: relative; overflow: hidden;
    }
    .hero::before {
      content: ''; position: absolute; top: -80px; right: -80px;
      width: 380px; height: 380px;
      background: radial-gradient(circle, #ff6b0025 0%, transparent 70%);
      pointer-events: none;
    }
    .hero::after {
      content: ''; position: absolute; bottom: -60px; left: 8%;
      width: 240px; height: 240px;
      background: radial-gradient(circle, #ff990018 0%, transparent 70%);
      pointer-events: none;
    }
    .hero-inner { max-width: 900px; margin: 0 auto; position: relative; }
    .badge {
      display: inline-block; background: #ff6b00; color: #fff;
      font-family: 'Syne', sans-serif; font-size: 11px; font-weight: 700;
      letter-spacing: 2px; text-transform: uppercase;
      padding: 5px 14px; border-radius: 3px; margin-bottom: 18px;
    }
    .hero h1 {
      font-family: 'Syne', sans-serif;
      font-size: clamp(28px, 5.5vw, 52px);
      font-weight: 800; line-height: 1.08; color: #fff; max-width: 720px;
    }
    .hero h1 span { color: #ff6b00; }
    .hero-sub { margin-top: 14px; color: #a09880; font-size: 15px; max-width: 580px; line-height: 1.65; }
    .hero-stats { display: flex; gap: 16px; margin-top: 32px; flex-wrap: wrap; }
    .stat {
      background: #141414; border: 1px solid #2a1500; border-radius: 10px; padding: 14px 22px;
      transition: transform .2s, border-color .2s;
    }
    .stat:hover { transform: translateY(-2px); border-color: #ff6b0060; }
    .stat-value { font-family: 'Syne', sans-serif; font-size: 24px; font-weight: 800; color: #ff6b00; }
    .stat-label { font-size: 11px; color: #6b6050; text-transform: uppercase; letter-spacing: 1px; margin-top: 3px; }

    /* ── Nav ── */
    .nav-wrap { position: sticky; top: 0; z-index: 100; background: #0d0d0d; border-bottom: 1px solid #1a1a1a; }
    .nav {
      display: flex; gap: 4px; padding: 14px 24px;
      overflow-x: auto; scrollbar-width: none; max-width: 960px; margin: 0 auto;
    }
    .nav::-webkit-scrollbar { display: none; }
    .nav-btn {
      background: none; border: none; color: #6b6050;
      font-family: 'DM Sans', sans-serif; font-size: 13px; font-weight: 500;
      padding: 8px 16px; border-radius: 7px; cursor: pointer; white-space: nowrap;
      transition: all .2s; display: flex; align-items: center; gap: 6px;
    }
    .nav-btn:hover { color: #f0ede6; background: #1a1a1a; }
    .nav-btn.active { color: #ff6b00; background: #1a0800; font-weight: 600; }

    /* ── Layout ── */
    .content { padding: 32px 24px 64px; max-width: 900px; margin: 0 auto; }
    .section-title { font-family: 'Syne', sans-serif; font-size: 24px; font-weight: 700; color: #fff; margin-bottom: 6px; }
    .section-sub { color: #6b6050; font-size: 14px; margin-bottom: 26px; }

    /* ── Cards ── */
    .card { background: #111; border: 1px solid #1e1e1e; border-radius: 12px; padding: 20px; margin-bottom: 16px; transition: border-color .2s; }
    .card:hover { border-color: #2a2a2a; }
    .card-orange { border-left: 3px solid #ff6b00; }
    .card-green  { border-left: 3px solid #00c851; }
    .card-blue   { border-left: 3px solid #007bff; }
    .card-yellow { border-left: 3px solid #ffd700; }
    .card h3 { font-family: 'Syne', sans-serif; font-size: 15px; font-weight: 700; color: #fff; margin-bottom: 10px; }
    .card p  { color: #8a8070; font-size: 14px; line-height: 1.65; }

    .grid-2 { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 16px; }
    .grid-3 { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 16px; }

    /* ── Timeline ── */
    .timeline { position: relative; padding-left: 36px; }
    .timeline::before {
      content: ''; position: absolute; left: 12px; top: 0; bottom: 0; width: 2px;
      background: linear-gradient(to bottom, #ff6b00, #ff990050, transparent);
    }
    .timeline-item { position: relative; margin-bottom: 32px; }
    .tl-dot {
      position: absolute; left: -30px; top: 4px;
      width: 16px; height: 16px; border-radius: 50%;
      border: 2px solid #0a0a0a;
    }
    .tl-week { font-family: 'Syne', sans-serif; font-size: 10px; font-weight: 700; letter-spacing: 2px; text-transform: uppercase; margin-bottom: 4px; }
    .tl-title { font-family: 'Syne', sans-serif; font-size: 16px; font-weight: 700; color: #fff; margin-bottom: 10px; }
    .tl-task { display: flex; align-items: flex-start; gap: 8px; font-size: 13px; color: #8a8070; line-height: 1.5; margin-bottom: 6px; }
    .tl-arrow { flex-shrink: 0; margin-top: 1px; }

    /* ── Tables ── */
    .tbl-wrap { overflow-x: auto; border-radius: 10px; border: 1px solid #1e1e1e; margin-bottom: 20px; }
    table { width: 100%; border-collapse: collapse; }
    thead th { background: #1a0800; color: #ff9944; font-family: 'Syne', sans-serif; font-size: 11px; font-weight: 700; letter-spacing: 1.5px; text-transform: uppercase; padding: 12px 16px; text-align: left; }
    tbody td { padding: 10px 16px; font-size: 13px; color: #c0b8a8; border-bottom: 1px solid #151515; }
    tbody tr:last-child td { border-bottom: none; }
    tbody tr:hover td { background: #141414; }
    .td-free   { color: #00c851 !important; font-weight: 600; }
    .td-paid   { color: #ff9944 !important; font-weight: 600; }
    .td-orange { color: #ff6b00 !important; font-weight: 700; }
    .td-total  { color: #fff !important; font-weight: 700; font-size: 14px !important; background: #1a0800 !important; }

    /* ── Revenue bars ── */
    .rev-bar { margin-bottom: 16px; }
    .rev-bar-hd { display: flex; justify-content: space-between; margin-bottom: 7px; font-size: 13px; }
    .rev-bar-name { color: #c0b8a8; }
    .rev-bar-val  { color: #ff6b00; font-weight: 600; font-family: 'Syne', sans-serif; }
    .rev-track { height: 9px; background: #1e1e1e; border-radius: 5px; overflow: hidden; }
    .rev-fill  { height: 100%; border-radius: 5px; background: linear-gradient(90deg, #ff6b00, #ff9944); }

    /* ── Steps ── */
    .step-row { display: flex; gap: 14px; margin-bottom: 20px; align-items: flex-start; }
    .step-num {
      width: 32px; height: 32px; background: #ff6b00; color: #fff;
      font-family: 'Syne', sans-serif; font-weight: 800; font-size: 14px;
      border-radius: 50%; display: flex; align-items: center; justify-content: center; flex-shrink: 0;
    }
    .step-title { font-family: 'Syne', sans-serif; font-size: 15px; font-weight: 700; color: #fff; margin-bottom: 5px; }
    .step-desc  { font-size: 13px; color: #8a8070; line-height: 1.65; }

    /* ── Boxes ── */
    .tip-box { background: #0f1a0a; border: 1px solid #1a3010; border-radius: 9px; padding: 16px 18px; margin-top: 14px; }
    .tip-title { font-size: 12px; font-weight: 600; color: #00c851; letter-spacing: 1px; text-transform: uppercase; margin-bottom: 7px; }
    .tip-box p { font-size: 13px; color: #6a8a60; line-height: 1.65; }

    .warn-box { background: #1a1000; border: 1px solid #3a2500; border-radius: 9px; padding: 16px 18px; margin-top: 14px; }
    .warn-title { font-size: 12px; font-weight: 600; color: #ffd700; letter-spacing: 1px; text-transform: uppercase; margin-bottom: 7px; }
    .warn-box p { font-size: 13px; color: #8a7040; line-height: 1.65; }

    /* ── Scenario ── */
    .scenario-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(170px, 1fr)); gap: 12px; margin-top: 10px; }
    .scenario-card { background: #111; border: 1px solid #1e1e1e; border-radius: 10px; padding: 18px; text-align: center; }
    .sc-label { font-size: 11px; color: #6b6050; text-transform: uppercase; letter-spacing: 1px; margin-bottom: 7px; }
    .sc-value { font-family: 'Syne', sans-serif; font-size: 22px; font-weight: 800; }
    .sc-note  { font-size: 11px; color: #6b6050; margin-top: 5px; }
    .c-red    { color: #ff4444; }
    .c-yellow { color: #ffd700; }
    .c-green  { color: #00c851; }

    /* ── Checklist ── */
    .checklist { list-style: none; }
    .checklist li { padding: 8px 0; font-size: 14px; color: #8a8070; border-bottom: 1px solid #151515; display: flex; align-items: flex-start; gap: 10px; line-height: 1.5; }
    .checklist li:last-child { border-bottom: none; }

    /* ── Misc ── */
    .big-number { font-family: 'Syne', sans-serif; font-size: 38px; font-weight: 800; color: #ff6b00; }
    .divider    { border: none; border-top: 1px solid #1a1a1a; margin: 28px 0; }
    .pill       { display: inline-block; background: #1e1e1e; border: 1px solid #2a2a2a; border-radius: 20px; padding: 4px 13px; font-size: 12px; color: #8a8070; margin: 3px; }
    .pill-o     { background: #1a0800; border-color: #3a1800; color: #ff9944; }

    .platform-card { background: #111; border: 1px solid #1e1e1e; border-radius: 10px; padding: 16px; text-align: center; transition: border-color .2s, transform .2s; }
    .platform-card:hover { border-color: #ff6b0050; transform: translateY(-2px); }

    /* ── Accordion ── */
    .accordion { background: #111; border: 1px solid #1e1e1e; border-radius: 12px; margin-bottom: 12px; overflow: hidden; }
    .accordion-header { display: flex; justify-content: space-between; align-items: center; padding: 18px 20px; cursor: pointer; user-select: none; }
    .accordion-header:hover { background: #141414; }
    .accordion-title { font-family: 'Syne', sans-serif; font-size: 15px; font-weight: 700; color: #fff; display: flex; align-items: center; gap: 10px; }
    .accordion-icon { color: #ff6b00; font-size: 20px; font-weight: 300; transition: transform .2s; }
    .accordion-body { padding: 0 20px 20px; border-top: 1px solid #1a1a1a; padding-top: 18px; }

    /* ── Footer ── */
    .footer { border-top: 1px solid #1a1a1a; padding: 32px 24px; text-align: center; background: #080808; }
    .footer p { font-size: 13px; color: #6b6050; }
    .footer strong { color: #ff6b00; }

    /* ── Animations ── */
    @keyframes fadeUp { from { opacity: 0; transform: translateY(16px); } to { opacity: 1; transform: translateY(0); } }
    .fade-up { animation: fadeUp .4s ease both; }

    /* ── Responsive ── */
    @media (max-width: 600px) {
      .hero { padding: 32px 16px 28px; }
      .content { padding: 24px 16px 48px; }
      .hero-stats { gap: 10px; }
      .stat { padding: 10px 16px; }
    }
  </style>
</head>
<body>
  <div id="root"></div>

  <script src="https://cdnjs.cloudflare.com/ajax/libs/react/18.2.0/umd/react.production.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/react-dom/18.2.0/umd/react-dom.production.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-standalone/7.23.2/babel.min.js"></script>

  <script type="text/babel">
    const { useState } = React;

    const tabs = [
      { id:"modelo",       label:"🏗️ Modelo",      title:"Modelo de Negócio"       },
      { id:"cronograma",   label:"📅 Cronograma",   title:"Cronograma 90 Dias"      },
      { id:"tutorial",     label:"📖 Tutorial",     title:"Passo a Passo"           },
      { id:"plataformas",  label:"🛒 Afiliados",    title:"Programas de Afiliados"  },
      { id:"custos",       label:"💰 Custos",       title:"Custos e Investimento"   },
      { id:"faturamento",  label:"📈 Faturamento",  title:"Projeção de Faturamento" },
      { id:"conteudo",     label:"🎬 Conteúdo",     title:"Estratégia de Conteúdo"  },
      { id:"ferramentas",  label:"🔧 Ferramentas",  title:"Ferramentas Essenciais"  },
    ];

    /* ─── MODELO ─── */
    function ModeloTab() {
      return (
        <div className="fade-up">
          <div className="card card-orange">
            <h3>🎯 Conceito Central</h3>
            <p>Você age como um <strong style={{color:'#ff9944'}}>curador de promoções</strong>: encontra ofertas imperdíveis nos marketplaces, cria conteúdo atrativo nas redes sociais e direciona sua audiência para o WhatsApp onde compartilha links de afiliados. A cada compra feita pelo seu link, você recebe comissão.</p>
          </div>

          <div style={{fontFamily:'Syne',fontSize:16,fontWeight:700,color:'#fff',margin:'24px 0 14px'}}>🔄 O Funil de Conversão</div>
          {[
            {icon:"📱", step:"1. ATRAÇÃO",       title:"Redes Sociais (Instagram, TikTok, Facebook)",    desc:"Posts de promoções, reels, stories com ofertas relâmpago. Gere audiência orgânica e/ou paga.",         color:"#ff6b00"},
            {icon:"📲", step:"2. DIRECIONAMENTO", title:"Link na Bio → WhatsApp",                         desc:"CTA nos posts direto para o WhatsApp ou grupo de WhatsApp. Use Linktree ou link direto.",             color:"#ff9944"},
            {icon:"💬", step:"3. ENGAJAMENTO",    title:"Grupo / Canal WhatsApp",                         desc:"Aqui você posta promoções com seus links de afiliado. O cliente é aquecido e pronto para comprar.",   color:"#ffd700"},
            {icon:"🛒", step:"4. CONVERSÃO",      title:"Marketplace (Shopee, Amazon, ML, Magalu)",       desc:"O cliente clica no seu link e compra no marketplace. Você ganha comissão de 3% a 15%.",               color:"#00c851"},
            {icon:"💰", step:"5. COMISSÃO",       title:"Pagamento via programa de afiliados",            desc:"A comissão é creditada na sua conta 30–90 dias após a compra confirmada.",                           color:"#007bff"},
          ].map((f,i) => (
            <div key={i} style={{display:'flex',gap:14,alignItems:'flex-start',background:'#111',border:'1px solid #1e1e1e',borderRadius:10,padding:16,marginBottom:10}}>
              <div style={{fontSize:24,flexShrink:0}}>{f.icon}</div>
              <div>
                <div style={{fontSize:10,fontWeight:700,color:f.color,letterSpacing:2,marginBottom:4}}>{f.step}</div>
                <div style={{fontFamily:'Syne',fontWeight:700,fontSize:14,color:'#fff',marginBottom:4}}>{f.title}</div>
                <div style={{fontSize:13,color:'#8a8070'}}>{f.desc}</div>
              </div>
            </div>
          ))}

          <div className="grid-2" style={{marginTop:20}}>
            <div className="card card-green">
              <h3>✅ Vantagens do Modelo</h3>
              <ul className="checklist">
                {["Custo inicial próximo de zero","Sem estoque, sem logística","Escalável sem limite","Renda passiva após criar audiência","Trabalha 24h no piloto automático","Pode começar sozinho, de casa"].map((v,i)=>(
                  <li key={i}><span style={{color:'#00c851',flexShrink:0}}>▸</span>{v}</li>
                ))}
              </ul>
            </div>
            <div className="card card-yellow">
              <h3>⚠️ Desafios a Superar</h3>
              <ul className="checklist">
                {["Leva tempo para construir audiência","Resultados demoram 2–3 meses","Concorrência alta no segmento","Depende de regularidade de posts","Comissões variam por temporada","Requer aprendizado contínuo"].map((v,i)=>(
                  <li key={i}><span style={{color:'#ffd700',flexShrink:0}}>▸</span>{v}</li>
                ))}
              </ul>
            </div>
          </div>

          <div className="card" style={{marginTop:16,background:'#0a0f1a',borderColor:'#0a1a2a'}}>
            <h3>💡 Fontes de Renda (Multi-stream)</h3>
            <div className="grid-3" style={{marginTop:10}}>
              {[
                {t:"Afiliados Marketplaces",  d:"Shopee, Amazon, ML — 3–12% por venda"},
                {t:"Grupo WhatsApp Pago",     d:"Cobrança de R$9,90–29,90/mês para grupos premium"},
                {t:"Posts Patrocinados",      d:"Marcas pagam para divulgar produtos para sua base"},
                {t:"Cursos e Mentorias",      d:"Ensine outros a montar o mesmo negócio"},
                {t:"Dropshipping",            d:"Venda produtos com margem maior em vez de só afiliar"},
              ].map((s,i)=>(
                <div key={i} style={{background:'#111',border:'1px solid #1e1e1e',borderRadius:8,padding:14}}>
                  <div style={{fontFamily:'Syne',fontWeight:700,fontSize:13,color:'#ff6b00',marginBottom:4}}>{s.t}</div>
                  <div style={{fontSize:12,color:'#6b6050'}}>{s.d}</div>
                </div>
              ))}
            </div>
          </div>
        </div>
      );
    }

    /* ─── CRONOGRAMA ─── */
    function CronogramaTab() {
      const phases = [
        {phase:"FASE 1 — FUNDAÇÃO",   weeks:"Semana 1 a 2",         color:"#ff6b00",
          items:["Definir nicho: celulares, casa/decoração, moda, bebê, tecnologia ou geral","Criar contas no Instagram, TikTok e Facebook com nome e identidade visual","Cadastrar em todos os programas de afiliados (Shopee, Amazon, Magalu)","Criar grupo e canal no WhatsApp Business","Instalar e aprender a usar o Canva para criar posts","Montar link na bio com Linktree ou similar","Criar identidade visual: logo, paleta de cores, template de posts"]},
        {phase:"FASE 2 — CONTEÚDO",   weeks:"Semana 3 a 4",         color:"#ff9944",
          items:["Criar os primeiros 9 posts para o feed do Instagram (feed curado)","Gravar primeiros 3 Reels e TikToks de promoções","Postar 2x por dia nos stories: promoções do dia","Começar a construir os primeiros membros no WhatsApp (amigos, família)","Estudar as melhores práticas de hashtag e SEO para cada plataforma","Instalar app de encurtador de links com rastreamento"]},
        {phase:"FASE 3 — TRAÇÃO",     weeks:"Mês 2 (Semanas 5–8)",  color:"#ffd700",
          items:["Meta: 500 seguidores no Instagram, 300 no TikTok, 200 no WhatsApp","Postar 1 Reel/TikTok por dia + 5 stories diários","Iniciar campanha de tráfego pago com R$10/dia no Meta Ads","Testar formatos: antes/depois de preço, timer de oferta relâmpago","Criar primeiros 'drops' exclusivos de promoção para o grupo WhatsApp","Analisar métricas e dobrar o que funciona melhor","Começar parcerias com outros achadinhos (troca de divulgação)"]},
        {phase:"FASE 4 — MONETIZAÇÃO",weeks:"Mês 3 (Semanas 9–12)", color:"#00c851",
          items:["Meta: 2.000 seguidores no Instagram, 1.000 no TikTok, 500+ no WhatsApp","Primeiras comissões de afiliados chegando na conta","Criar grupo VIP pago no WhatsApp (R$19,90/mês)","Negociar primeiro post patrocinado com marca pequena","Automatizar parte do processo com bots de WhatsApp","Documentar o que funciona e criar SOPs para escalar","Projeção: R$500 a R$2.000/mês de comissões"]},
        {phase:"FASE 5 — ESCALA",     weeks:"Mês 4 a 6",            color:"#007bff",
          items:["Meta: 10k+ seguidores no Instagram, verificação TikTok","Contratar editor de vídeo freelancer (R$300–600/mês)","Criar segundo canal de nicho específico (ex: achadinhos pet, bebê)","Lançar grupo premium com R$29,90/mês","Investir R$500–1.000/mês em tráfego pago para acelerar crescimento","Projeção: R$3.000 a R$8.000/mês receita total"]},
      ];
      return (
        <div className="fade-up timeline">
          {phases.map((p,i)=>(
            <div key={i} className="timeline-item">
              <div className="tl-dot" style={{background:p.color,boxShadow:`0 0 8px ${p.color}80`}} />
              <div className="tl-week" style={{color:p.color}}>{p.weeks}</div>
              <div className="tl-title">{p.phase}</div>
              {p.items.map((item,j)=>(
                <div key={j} className="tl-task">
                  <span className="tl-arrow" style={{color:p.color}}>▸</span>
                  <span>{item}</span>
                </div>
              ))}
            </div>
          ))}
        </div>
      );
    }

    /* ─── TUTORIAL ─── */
    function TutorialTab() {
      const [open,setOpen] = useState(null);
      const tuts = [
        {title:"Como se cadastrar nos programas de afiliados",steps:[
          {t:"Shopee Afiliados",d:"Acesse affiliates.shopee.com.br → Clique em 'Cadastrar' → Preencha seus dados e redes sociais → Aguarde aprovação (1–3 dias) → Acesse o painel e gere links de produtos."},
          {t:"Amazon Afiliados (Associados)",d:"Acesse associados.amazon.com.br → Crie sua conta com CPF e dados bancários → Defina seu perfil social como 'canal' → Aprovação automática → Use o SiteStripe para gerar links."},
          {t:"Magalu Parceiros",d:"Acesse parceiros.magazineluiza.com.br → Cadastre como afiliado → Informe suas redes sociais → Após aprovação, use o painel para gerar links com sua tag."},
          {t:"Mercado Livre Afiliados",d:"Acesse afiliados.mercadolivre.com.br → Crie sua conta → Adicione seus canais → Acesse o marketplace de ofertas → Gere links rastreáveis para qualquer produto."},
        ]},
        {title:"Como criar seu grupo/canal no WhatsApp",steps:[
          {t:"WhatsApp Business App",d:"Baixe o WhatsApp Business (gratuito) → Configure com CNPJ ou CPF → Crie catálogo, horários e mensagem automática de boas-vindas."},
          {t:"Canal WhatsApp (Recomendado)",d:"No WhatsApp, vá em 'Novidades' → 'Criar canal' → Coloque nome do seu achadinhos, foto e descrição → Compartilhe o link para as pessoas seguirem. Canal = você fala, seguidores não respondem."},
          {t:"Grupo WhatsApp",d:"Crie grupos para comunidade. Limite de 1.024 membros. Use para o grupo premium pago. Configure regras na descrição do grupo."},
          {t:"Mensagem automática de boas-vindas",d:"No WhatsApp Business: Configurações → Ferramentas de negócios → Mensagem de saudação → 'Bem-vindo! Aqui você recebe as melhores promoções do dia. Ative as notificações! 🔔'"},
        ]},
        {title:"Como criar posts de alta conversão no Canva",steps:[
          {t:"Crie seu template base",d:"No Canva, crie um design de Post Instagram (1080×1080). Use fundo escuro ou colorido chamativo. Reserve espaço para: foto do produto, preço DE e POR, nome da loja, badge 'OFERTA DO DIA'."},
          {t:"Elementos que convertem",d:"Badge vermelho/laranja de desconto (ex: '-60%'), timer de urgência, texto grande com o preço, antes e depois do preço tachado, emojis de fogo 🔥, alerta ⚡, dinheiro 💰."},
          {t:"Stories otimizados",d:"Use o formato 1080×1920. Adicione figurinha de link para redirecionar para o WhatsApp. Stories com link direto convertem muito melhor que só o feed."},
          {t:"Salvando templates",d:"Transforme seu design em template no Canva para reusar. Assim você só troca foto, preço e link — leva menos de 2 minutos criar um novo post."},
        ]},
        {title:"Como criar Reels e TikToks de promoções",steps:[
          {t:"Estrutura do vídeo de 15–30s",d:"0–3s: GANCHO — 'Essa promoção ABSURDA vai acabar hoje!' | 3–20s: PRODUTO — Mostre o produto, destaque o preço e desconto | 20–25s: CTA — 'Link no stories/bio/WhatsApp para garantir!'"},
          {t:"Apps gratuitos para editar",d:"CapCut (melhor para TikTok/Reels, gratuito e potente). InShot (mais simples e rápido). O próprio TikTok tem bons efeitos nativos. Use templates prontos do CapCut para economizar tempo."},
          {t:"Trilha sonora estratégica",d:"Use músicas em alta no TikTok/Instagram para maior alcance orgânico. O próprio TikTok mostra quais músicas estão em tendência. Sempre prefira músicas sem direitos autorais."},
          {t:"Hashtags para alcance",d:"Instagram: use 5–10 hashtags relevantes (#achadinhos #promoção #ofertadodia #shopee #amazon). TikTok: use 3–5 hashtags. Não exagere, foque na qualidade."},
        ]},
        {title:"Como configurar o tráfego pago (Meta Ads)",steps:[
          {t:"Criando a conta de anúncios",d:"Acesse business.facebook.com → Crie um Business Manager → Adicione sua conta de anúncios → Vincule ao seu Instagram → Adicione forma de pagamento."},
          {t:"Campanha para crescimento de seguidores",d:"Objetivo: Engajamento ou Alcance → Público: Brasil, 18–45 anos, interesses em 'Promoções', 'Compras online', 'Shopee' → Budget: R$5–10/dia → Criativo: Reel ou imagem de promoção impactante."},
          {t:"Campanha para WhatsApp",d:"Objetivo: Mensagens → Plataforma: WhatsApp → Inclua botão 'Enviar mensagem' → Direcione para seu número/grupo → Mensagem pré-preenchida: 'Quero receber promoções!'"},
          {t:"Otimização das campanhas",d:"Deixe rodar 3–5 dias antes de julgar. Desligue anúncios com CPM alto. Duplique os vencedores com mais budget. Teste 2–3 criativos diferentes simultaneamente."},
        ]},
      ];
      return (
        <div className="fade-up">
          <p className="section-sub">Guias detalhados para cada etapa do negócio</p>
          {tuts.map((t,i)=>(
            <div key={i} className="accordion">
              <div className="accordion-header" onClick={()=>setOpen(open===i?null:i)}>
                <div className="accordion-title">
                  <span style={{background:'#ff6b00',color:'#fff',borderRadius:'50%',width:26,height:26,display:'inline-flex',alignItems:'center',justifyContent:'center',fontSize:12,fontWeight:800,flexShrink:0}}>{i+1}</span>
                  {t.title}
                </div>
                <span className="accordion-icon" style={{transform:open===i?'rotate(45deg)':'none'}}>+</span>
              </div>
              {open===i && (
                <div className="accordion-body">
                  {t.steps.map((s,j)=>(
                    <div key={j} className="step-row">
                      <div className="step-num">{String.fromCharCode(65+j)}</div>
                      <div>
                        <div className="step-title">{s.t}</div>
                        <div className="step-desc">{s.d}</div>
                      </div>
                    </div>
                  ))}
                </div>
              )}
            </div>
          ))}
          <div className="tip-box">
            <div className="tip-title">💡 Dica de Ouro</div>
            <p>Comece pelo WhatsApp e Instagram. São as plataformas com mais conversão para o modelo de achadinhos no Brasil. TikTok tem alcance orgânico maior mas converte menos diretamente. Facebook é ótimo para audiências 35+.</p>
          </div>
        </div>
      );
    }

    /* ─── PLATAFORMAS ─── */
    function PlataformasTab() {
      const plats = [
        {icon:"🛍️",name:"Shopee Afiliados",    url:"affiliates.shopee.com.br",         comissao:"Até 10%", cookie:"7–30 dias",       pros:"Enorme variedade, comissão alta, aprovação fácil", cons:"Ticket médio baixo",                  cor:"#ee4d2d"},
        {icon:"📦",name:"Amazon Associados",    url:"associados.amazon.com.br",          comissao:"Até 12%", cookie:"24h (carrinho 90d)",pros:"Marca forte, produtos premium, confiança alta",  cons:"Cookie de 24h é curto",               cor:"#ff9900"},
        {icon:"🏪",name:"Mercado Livre",        url:"afiliados.mercadolivre.com.br",     comissao:"Até 8%",  cookie:"30 dias",          pros:"Líder no Brasil, ticket médio bom",              cons:"Interface menos intuitiva",           cor:"#ffe600"},
        {icon:"🔵",name:"Magazine Luiza",       url:"parceiros.magazineluiza.com.br",    comissao:"Até 6%",  cookie:"30 dias",          pros:"Eletro e tecnologia, boas promoções sazonais",  cons:"Categorias mais limitadas",           cor:"#0086ff"},
        {icon:"🟠",name:"Americanas Afiliados", url:"afiliados.americanas.com.br",       comissao:"Até 7%",  cookie:"30 dias",          pros:"Variedade, boas ofertas no varejo",              cons:"Concorrência alta na categoria",      cor:"#f23005"},
        {icon:"🟣",name:"Hotmart / Monetizze",  url:"hotmart.com / monetizze.com.br",    comissao:"Até 50%", cookie:"30–60 dias",        pros:"Comissões altíssimas em infoprodutos e cursos",  cons:"Vende cursos, não produtos físicos",  cor:"#f04e23"},
      ];
      return (
        <div className="fade-up">
          <div className="warn-box" style={{marginBottom:20}}>
            <div className="warn-title">⚡ Estratégia Recomendada</div>
            <p>Cadastre em <strong>todos</strong> os programas. Para cada promoção, use o link do marketplace que paga a maior comissão naquela categoria. Compare sempre antes de postar.</p>
          </div>
          {plats.map((p,i)=>(
            <div key={i} className="card" style={{marginBottom:12}}>
              <div style={{display:'flex',gap:14,alignItems:'flex-start'}}>
                <div style={{fontSize:28,flexShrink:0}}>{p.icon}</div>
                <div style={{flex:1}}>
                  <div style={{display:'flex',justifyContent:'space-between',flexWrap:'wrap',gap:8}}>
                    <div style={{fontFamily:'Syne',fontWeight:700,fontSize:15,color:'#fff'}}>{p.name}</div>
                    <div style={{fontFamily:'Syne',fontWeight:800,fontSize:20,color:p.cor}}>{p.comissao}</div>
                  </div>
                  <div style={{fontSize:12,color:'#6b6050',marginBottom:8}}>{p.url}</div>
                  <div style={{display:'flex',gap:16,flexWrap:'wrap',marginBottom:8}}>
                    <div><span style={{fontSize:11,color:'#6b6050'}}>Cookie: </span><span style={{fontSize:12,color:'#c0b8a8'}}>{p.cookie}</span></div>
                  </div>
                  <div style={{display:'flex',gap:12,flexWrap:'wrap'}}>
                    <div style={{fontSize:12,color:'#00c851'}}>✓ {p.pros}</div>
                    <div style={{fontSize:12,color:'#ff6644'}}>✗ {p.cons}</div>
                  </div>
                </div>
              </div>
            </div>
          ))}
        </div>
      );
    }

    /* ─── CUSTOS ─── */
    function CustosTab() {
      return (
        <div className="fade-up">
          <div style={{display:'flex',gap:12,marginBottom:24,flexWrap:'wrap'}}>
            {[
              {v:"R$0",    l:"Para começar",         n:"Pode começar de graça"},
              {v:"R$55",   l:"Custo Mínimo/Mês",     n:"Apenas Canva Pro"},
              {v:"R$355",  l:"Custo Recomendado/Mês",n:"Com R$300 em tráfego"},
            ].map((s,i)=>(
              <div key={i} style={{background:'#111',border:'1px solid #1e1e1e',borderRadius:10,padding:20,flex:1,minWidth:150}}>
                <div style={{fontSize:11,color:'#6b6050',textTransform:'uppercase',letterSpacing:1}}>{s.l}</div>
                <div className="big-number">{s.v}</div>
                <div style={{fontSize:12,color:'#6b6050'}}>{s.n}</div>
              </div>
            ))}
          </div>

          <div style={{fontFamily:'Syne',fontSize:15,fontWeight:700,color:'#fff',marginBottom:10}}>📋 Ferramentas Gratuitas</div>
          <div className="tbl-wrap">
            <table>
              <thead><tr><th>Ferramenta</th><th>Uso</th><th>Custo</th></tr></thead>
              <tbody>
                {[
                  ["Instagram","Rede social principal"],
                  ["TikTok","Alcance orgânico viral"],
                  ["Facebook / Meta","Grupos e alcance 35+"],
                  ["WhatsApp Business","Grupo/Canal de promoções"],
                  ["Canva (free)","Criação de posts e stories"],
                  ["Linktree","Link na bio unificado"],
                  ["Bitly","Encurtar links de afiliado"],
                  ["CapCut","Edição de Reels e TikToks"],
                  ["Todos os programas de afiliados","Geração de links"],
                ].map(([a,b],i)=>(
                  <tr key={i}><td>{a}</td><td>{b}</td><td className="td-free">GRÁTIS</td></tr>
                ))}
              </tbody>
            </table>
          </div>

          <div style={{fontFamily:'Syne',fontSize:15,fontWeight:700,color:'#fff',margin:'20px 0 10px'}}>💳 Ferramentas Pagas (Recomendadas)</div>
          <div className="tbl-wrap">
            <table>
              <thead><tr><th>Ferramenta</th><th>Benefício</th><th>Custo/Mês</th></tr></thead>
              <tbody>
                {[
                  ["Canva Pro","Remove fundo, templates premium","R$54,99"],
                  ["Meta Ads","Acelera crescimento de seguidores","R$10/dia recomendado"],
                  ["ChatGPT Plus","Cria legendas, copies e ideias","R$100"],
                  ["Automação WA","Bots para mensagens automáticas","R$49–99"],
                  ["TOTAL RECOMENDADO","Com R$300 em anúncios","~R$355/mês"],
                ].map(([a,b,c],i)=>(
                  <tr key={i} className={i===4?"":""}><td style={i===4?{fontWeight:700,color:'#fff'}:{}}>{a}</td><td>{b}</td><td className={i===4?"td-total":"td-paid"}>{c}</td></tr>
                ))}
              </tbody>
            </table>
          </div>

          <div className="grid-2">
            <div className="tip-box">
              <div className="tip-title">💡 Comece Gratuito</div>
              <p>Nos primeiros 30 dias, use tudo gratuito. Só invista em anúncios quando tiver conteúdo funcionando organicamente. Não gaste antes de validar.</p>
            </div>
            <div className="warn-box">
              <div className="warn-title">⚠️ Atenção com CNPJ</div>
              <p>Para receber comissões acima de R$1.500/mês, considere abrir um MEI (R$70/mês). Facilita recebimento e profissionaliza o negócio.</p>
            </div>
          </div>
        </div>
      );
    }

    /* ─── FATURAMENTO ─── */
    function FaturamentoTab() {
      const bars = [
        {label:"Mês 1",  range:"R$0 – R$200",          pct:1},
        {label:"Mês 3",  range:"R$200 – R$800",         pct:4},
        {label:"Mês 6",  range:"R$2.500 – R$6.000",     pct:30},
        {label:"Mês 12", range:"R$6.000 – R$20.000+",   pct:100},
      ];
      return (
        <div className="fade-up">
          <div className="warn-box" style={{marginBottom:20}}>
            <div className="warn-title">📊 Base das Projeções</div>
            <p>Valores baseados em achadinhos reais do Brasil. Considera: postagem consistente 2×/dia, crescimento orgânico + R$300/mês em ads a partir do mês 3. Resultados variam por nicho, dedicação e consistência.</p>
          </div>

          <div style={{fontFamily:'Syne',fontSize:15,fontWeight:700,color:'#fff',marginBottom:12}}>📊 Cenários no Mês 6</div>
          <div className="scenario-grid" style={{marginBottom:24}}>
            {[
              {label:"Pessimista",value:"R$1.200/mês",note:"Pouca consistência, sem ads",cls:"c-red"},
              {label:"Realista",  value:"R$4.000/mês",note:"Consistente, R$300/mês ads", cls:"c-yellow"},
              {label:"Otimista",  value:"R$8.000/mês",note:"Viral, nicho quente, ads",   cls:"c-green"},
            ].map((s,i)=>(
              <div key={i} className="scenario-card">
                <div className="sc-label">{s.label}</div>
                <div className={`sc-value ${s.cls}`}>{s.value}</div>
                <div className="sc-note">{s.note}</div>
              </div>
            ))}
          </div>

          <div style={{fontFamily:'Syne',fontSize:15,fontWeight:700,color:'#fff',marginBottom:12}}>📈 Evolução do Faturamento</div>
          <div className="card" style={{marginBottom:20}}>
            {bars.map((b,i)=>(
              <div key={i} className="rev-bar">
                <div className="rev-bar-hd">
                  <span className="rev-bar-name">{b.label}</span>
                  <span className="rev-bar-val">{b.range}</span>
                </div>
                <div className="rev-track">
                  <div className="rev-fill" style={{width:`${b.pct}%`,minWidth:'4px'}} />
                </div>
              </div>
            ))}
          </div>

          <div style={{fontFamily:'Syne',fontSize:15,fontWeight:700,color:'#fff',marginBottom:12}}>📋 Projeção Detalhada</div>
          <div className="tbl-wrap">
            <table>
              <thead><tr><th>Período</th><th>Audiência</th><th>WhatsApp</th><th>Comissões</th><th>Renda Total*</th></tr></thead>
              <tbody>
                {[
                  ["Mês 1–2","0–500 seg.","0–100 membros","R$0–R$200","R$0–R$200"],
                  ["Mês 3","500–2k seg.","100–300 membros","R$200–R$800","R$200–R$800"],
                  ["Mês 4–5","2k–8k seg.","300–600 membros","R$800–R$2.500","R$800–R$3.000"],
                  ["Mês 6","8k–20k seg.","600–1k membros","R$2.000–R$5.000","R$2.500–R$6.000"],
                  ["Mês 12","20k–50k seg.","1k–3k membros","R$5.000–R$15.000","R$6.000–R$20.000+"],
                ].map((r,i)=>(
                  <tr key={i}>
                    <td className="td-orange">{r[0]}</td>
                    <td>{r[1]}</td><td>{r[2]}</td>
                    <td style={{color:'#ff9944'}}>{r[3]}</td>
                    <td style={{color:'#00c851',fontWeight:600}}>{r[4]}</td>
                  </tr>
                ))}
              </tbody>
            </table>
          </div>
          <p style={{fontSize:11,color:'#6b6050',marginBottom:20}}>*Renda Total inclui: comissões + grupo pago + posts patrocinados</p>

          <div className="grid-2">
            {[
              {title:"Exemplo Shopee — R$1.920/mês",items:["500 membros ativos no WhatsApp","20% clicam nas promoções = 100 cliques/dia","10% dos que clicam compram = 10 vendas/dia","Ticket médio R$80 × comissão 8% = R$6,40","10 vendas × R$6,40 = R$64/dia","R$64 × 30 dias = R$1.920/mês"]},
              {title:"Exemplo Grupo VIP Pago",       items:["200 membros no grupo pago","Mensalidade: R$19,90","200 × R$19,90 = R$3.980/mês","+ comissões extras dos membros VIP","ROI: pagou R$300 em ads para gerar R$4k"]},
            ].map((e,i)=>(
              <div key={i} className="card card-orange">
                <h3>📐 {e.title}</h3>
                <ul className="checklist">
                  {e.items.map((it,j)=>(
                    <li key={j}><span style={{color:'#ff6b00',flexShrink:0}}>▸</span>{it}</li>
                  ))}
                </ul>
              </div>
            ))}
          </div>
        </div>
      );
    }

    /* ─── CONTEÚDO ─── */
    function ConteudoTab() {
      return (
        <div className="fade-up">
          <div style={{fontFamily:'Syne',fontSize:15,fontWeight:700,color:'#fff',marginBottom:10}}>📅 Calendário Semanal Ideal</div>
          <div className="card" style={{marginBottom:20}}>
            {[
              {dia:"Seg",posts:["📱 Reel: Top 5 promoções da semana","📲 WhatsApp: 3–5 achados do dia","📸 Stories: Votação 'qual produto você queria?'"]},
              {dia:"Ter",posts:["⚡ Story urgência: oferta relâmpago 24h","📲 WhatsApp: promoção específica com link","💬 Post carrossel: 'Como economizar em X'"]},
              {dia:"Qua",posts:["🔥 Reel: Achado da semana (melhor oferta)","📲 WhatsApp: 3–5 promoções do dia","📸 Stories: bastidores, como você busca promoções"]},
              {dia:"Qui",posts:["📸 Post: comparativo de preços (antes/depois)","📲 WhatsApp: cupons e códigos do dia","💬 Enquete: 'Qual categoria você quer amanhã?'"]},
              {dia:"Sex",posts:["🛍️ Reel: 'Promoções de fim de semana'","📲 WhatsApp: promoções de sexta","⚡ Stories: contagem regressiva ofertas"]},
              {dia:"Sáb",posts:["🎬 TikTok: melhores achadinhos da semana","📲 WhatsApp: resumo das melhores da semana","📸 Stories: feirão de achadinhos"]},
              {dia:"Dom",posts:["🔄 Repost dos melhores conteúdos da semana","📲 WhatsApp: teaser da próxima semana","📸 Stories: planejamento da semana"]},
            ].map((d,i)=>(
              <div key={i} style={{display:'flex',gap:14,padding:'12px 0',borderBottom:i<6?'1px solid #151515':'none'}}>
                <div style={{width:36,height:36,background:'#1a0800',border:'1px solid #3a1800',borderRadius:8,display:'flex',alignItems:'center',justifyContent:'center',fontFamily:'Syne',fontWeight:700,fontSize:12,color:'#ff6b00',flexShrink:0}}>{d.dia}</div>
                <div>{d.posts.map((p,j)=><div key={j} style={{fontSize:13,color:'#8a8070',marginBottom:3}}>{p}</div>)}</div>
              </div>
            ))}
          </div>

          <div style={{fontFamily:'Syne',fontSize:15,fontWeight:700,color:'#fff',marginBottom:12}}>🎯 Tipos de Conteúdo que Mais Convertem</div>
          <div className="grid-2">
            {[
              {icon:"🔥",t:"Oferta Relâmpago",       d:"'Só até meia-noite!' — urgência e escassez são os gatilhos mais poderosos."},
              {icon:"⚖️",t:"Antes × Depois de Preço", d:"Mostre o preço riscado e o novo. Ex: ~~R$299~~ → R$89. Impacto visual imediato."},
              {icon:"🏆",t:"Top N Achados",           d:"'Top 5 produtos mais baratos da semana' — formato lista sempre gera engajamento."},
              {icon:"🎁",t:"Cupom Exclusivo",         d:"Cupons exclusivos para o grupo WhatsApp criam senso de comunidade VIP."},
              {icon:"📱",t:"Unboxing de Achados",     d:"Mostre recebendo e usando o produto — prova social que o produto é bom."},
              {icon:"🤔",t:"Comparativo de Lojas",    d:"'O mesmo produto em 3 lojas: qual é mais barato?' — educa e entretém."},
            ].map((c,i)=>(
              <div key={i} className="card" style={{marginBottom:10}}>
                <div style={{display:'flex',gap:10,alignItems:'flex-start'}}>
                  <span style={{fontSize:22,flexShrink:0}}>{c.icon}</span>
                  <div>
                    <div style={{fontFamily:'Syne',fontWeight:700,fontSize:14,color:'#fff',marginBottom:4}}>{c.t}</div>
                    <div style={{fontSize:13,color:'#8a8070'}}>{c.d}</div>
                  </div>
                </div>
              </div>
            ))}
          </div>

          <div className="tip-box" style={{marginTop:8}}>
            <div className="tip-title">🕐 Melhores Horários para Postar</div>
            <p><strong style={{color:'#00c851'}}>Instagram:</strong> 18h–21h (seg–sex) e 10h–12h (fim de semana).<br/><strong style={{color:'#00c851'}}>TikTok:</strong> 19h–22h qualquer dia.<br/><strong style={{color:'#00c851'}}>WhatsApp:</strong> 7h–9h (acordar), 12h–13h (almoço), 19h–21h (após trabalho).</p>
          </div>
        </div>
      );
    }

    /* ─── FERRAMENTAS ─── */
    function FerramentasTab() {
      const cats = [
        {cat:"📱 Redes Sociais e Comunicação",items:[
          {n:"Instagram Business",d:"Perfil profissional com métricas e acesso a anúncios",tag:"free"},
          {n:"TikTok Creator",d:"Acesse o TikTok Studio para métricas e tendências",tag:"free"},
          {n:"WhatsApp Business",d:"Mensagens automáticas, catálogo e múltiplos atendentes",tag:"free"},
          {n:"Meta Business Suite",d:"Gerencie Instagram e Facebook + agende posts",tag:"free"},
        ]},
        {cat:"🎨 Criação de Conteúdo",items:[
          {n:"Canva",d:"Posts, stories, logos, banners — tudo num lugar",tag:"free"},
          {n:"CapCut",d:"Edição de vídeo mais usada no Brasil para Reels/TikTok",tag:"free"},
          {n:"Remove.bg",d:"Remove fundo de imagens de produtos automaticamente",tag:"free"},
          {n:"ChatGPT",d:"Gera legendas, copies de venda e ideias de conteúdo",tag:"free"},
        ]},
        {cat:"🔗 Links e Rastreamento",items:[
          {n:"Linktree",d:"Link único na bio com todos os seus canais e grupos",tag:"free"},
          {n:"Bitly",d:"Encurta links de afiliado e rastreia cliques",tag:"free"},
          {n:"Amazon SiteStripe",d:"Extensão do Chrome para gerar links Amazon diretamente",tag:"free"},
          {n:"Shopee Painel Afiliados",d:"Gere links de qualquer produto em segundos",tag:"free"},
        ]},
        {cat:"🔍 Encontrar Promoções",items:[
          {n:"Promobit",d:"Maior agregador de promoções do Brasil",tag:"free"},
          {n:"Pelando",d:"Comunidade de achadinhos — veja o que está quente",tag:"free"},
          {n:"Keepa",d:"Histórico de preços da Amazon — detecte promoções reais",tag:"free"},
          {n:"Grupos Telegram",d:"Entre em grupos de achadinhos para se inspirar",tag:"free"},
        ]},
      ];
      return (
        <div className="fade-up">
          {cats.map((cat,i)=>(
            <div key={i} style={{marginBottom:22}}>
              <div style={{fontFamily:'Syne',fontSize:14,fontWeight:700,color:'#fff',marginBottom:10}}>{cat.cat}</div>
              <div className="grid-2">
                {cat.items.map((f,j)=>(
                  <div key={j} style={{background:'#111',border:'1px solid #1e1e1e',borderRadius:8,padding:14,transition:'border-color .2s'}}
                       onMouseEnter={e=>e.currentTarget.style.borderColor='#3a3a3a'}
                       onMouseLeave={e=>e.currentTarget.style.borderColor='#1e1e1e'}>
                    <div style={{display:'flex',justifyContent:'space-between',alignItems:'center',marginBottom:5}}>
                      <div style={{fontFamily:'Syne',fontWeight:700,fontSize:13,color:'#fff'}}>{f.n}</div>
                      <span style={{background:'#003c20',color:'#00c851',fontSize:10,padding:'2px 8px',borderRadius:4,fontWeight:600}}>GRÁTIS</span>
                    </div>
                    <div style={{fontSize:12,color:'#6b6050'}}>{f.d}</div>
                  </div>
                ))}
              </div>
            </div>
          ))}
          <div className="card card-orange">
            <h3>🌟 Stack Mínima para Começar HOJE</h3>
            <div style={{display:'flex',flexWrap:'wrap',gap:6,marginTop:10}}>
              {["Instagram Business","WhatsApp Business","Canva (free)","CapCut","Linktree","Shopee Afiliados","Amazon Afiliados","ML Afiliados","Promobit","Pelando"].map((t,i)=>(
                <span key={i} className="pill pill-o">{t}</span>
              ))}
            </div>
            <p style={{marginTop:14}}>Com essas 10 ferramentas você tem tudo para começar a operar hoje sem gastar nada. Adicione as demais conforme o negócio crescer.</p>
          </div>
        </div>
      );
    }

    /* ─── APP ─── */
    function App() {
      const [active, setActive] = useState("modelo");
      const tab = tabs.find(t => t.id === active);

      const content = {
        modelo:      <ModeloTab />,
        cronograma:  <CronogramaTab />,
        tutorial:    <TutorialTab />,
        plataformas: <PlataformasTab />,
        custos:      <CustosTab />,
        faturamento: <FaturamentoTab />,
        conteudo:    <ConteudoTab />,
        ferramentas: <FerramentasTab />,
      };

      return (
        <div>
          <div className="hero">
            <div className="hero-inner">
              <div className="badge">Plano de Negócios Completo</div>
              <h1>Negócio de <span>Achadinhos</span><br/>do Zero ao Faturamento</h1>
              <p className="hero-sub">Guia completo para montar seu canal de promoções no Instagram, TikTok e WhatsApp — com afiliados, cronograma, custos e projeção de faturamento.</p>
              <div className="hero-stats">
                {[
                  {v:"R$0",       l:"Para começar"},
                  {v:"90 dias",   l:"Para resultados"},
                  {v:"R$4k+",     l:"Potencial mês 6"},
                  {v:"4 afiliados",l:"Plataformas"},
                ].map((s,i)=>(
                  <div key={i} className="stat">
                    <div className="stat-value">{s.v}</div>
                    <div className="stat-label">{s.l}</div>
                  </div>
                ))}
              </div>
            </div>
          </div>

          <div className="nav-wrap">
            <nav className="nav">
              {tabs.map(t => (
                <button key={t.id} className={`nav-btn ${active===t.id?"active":""}`} onClick={()=>setActive(t.id)}>
                  {t.label}
                </button>
              ))}
            </nav>
          </div>

          <div className="content">
            <h2 className="section-title">{tab?.title}</h2>
            {content[active]}
          </div>

          <footer className="footer">
            <p>Plano de Negócios <strong>Achadinhos da Internet</strong> · Gerado com Claude · {new Date().getFullYear()}</p>
            <p style={{marginTop:8,fontSize:12}}>Instagram · TikTok · Facebook · WhatsApp · Shopee · Amazon · Mercado Livre</p>
          </footer>
        </div>
      );
    }

    ReactDOM.createRoot(document.getElementById("root")).render(<App />);
  </script>
</body>
</html>
