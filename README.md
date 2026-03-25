import { useState } from "react";

const styles = `
  @import url('https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap');
  
  * { box-sizing: border-box; margin: 0; padding: 0; }
  
  body { background: #0a0a0a; font-family: 'DM Sans', sans-serif; color: #f0ede6; }
  
  .app { min-height: 100vh; background: #0a0a0a; }
  
  .hero {
    background: linear-gradient(135deg, #0a0a0a 0%, #1a0a00 50%, #0a0a0a 100%);
    border-bottom: 1px solid #2a1500;
    padding: 40px 24px 32px;
    position: relative;
    overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute;
    top: -60px; right: -60px;
    width: 300px; height: 300px;
    background: radial-gradient(circle, #ff6b0022 0%, transparent 70%);
    pointer-events: none;
  }
  .hero::after {
    content: '';
    position: absolute;
    bottom: -40px; left: 10%;
    width: 200px; height: 200px;
    background: radial-gradient(circle, #ff990015 0%, transparent 70%);
    pointer-events: none;
  }
  
  .badge {
    display: inline-block;
    background: #ff6b00;
    color: #fff;
    font-family: 'Syne', sans-serif;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 2px;
    text-transform: uppercase;
    padding: 4px 12px;
    border-radius: 2px;
    margin-bottom: 16px;
  }
  
  .hero h1 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(28px, 6vw, 48px);
    font-weight: 800;
    line-height: 1.1;
    color: #fff;
    max-width: 700px;
  }
  .hero h1 span { color: #ff6b00; }
  
  .hero p {
    margin-top: 12px;
    color: #a09880;
    font-size: 15px;
    max-width: 560px;
    line-height: 1.6;
  }
  
  .hero-stats {
    display: flex;
    gap: 24px;
    margin-top: 28px;
    flex-wrap: wrap;
  }
  .stat {
    background: #141414;
    border: 1px solid #2a1500;
    border-radius: 8px;
    padding: 12px 20px;
  }
  .stat-value {
    font-family: 'Syne', sans-serif;
    font-size: 22px;
    font-weight: 800;
    color: #ff6b00;
  }
  .stat-label {
    font-size: 11px;
    color: #6b6050;
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-top: 2px;
  }
  
  .nav {
    display: flex;
    gap: 4px;
    padding: 16px 24px;
    border-bottom: 1px solid #1a1a1a;
    background: #0d0d0d;
    overflow-x: auto;
    scrollbar-width: none;
  }
  .nav::-webkit-scrollbar { display: none; }
  
  .nav-btn {
    background: none;
    border: none;
    color: #6b6050;
    font-family: 'DM Sans', sans-serif;
    font-size: 13px;
    font-weight: 500;
    padding: 8px 16px;
    border-radius: 6px;
    cursor: pointer;
    white-space: nowrap;
    transition: all 0.2s;
    display: flex;
    align-items: center;
    gap: 6px;
  }
  .nav-btn:hover { color: #f0ede6; background: #1a1a1a; }
  .nav-btn.active { color: #ff6b00; background: #1a0800; font-weight: 600; }
  
  .content { padding: 28px 24px; max-width: 900px; margin: 0 auto; }
  
  .section-title {
    font-family: 'Syne', sans-serif;
    font-size: 22px;
    font-weight: 700;
    color: #fff;
    margin-bottom: 6px;
  }
  .section-sub {
    color: #6b6050;
    font-size: 14px;
    margin-bottom: 24px;
  }
  
  .card {
    background: #111;
    border: 1px solid #1e1e1e;
    border-radius: 12px;
    padding: 20px;
    margin-bottom: 16px;
  }
  .card-orange { border-left: 3px solid #ff6b00; }
  .card-green { border-left: 3px solid #00c851; }
  .card-blue { border-left: 3px solid #007bff; }
  .card-yellow { border-left: 3px solid #ffd700; }
  
  .card h3 {
    font-family: 'Syne', sans-serif;
    font-size: 15px;
    font-weight: 700;
    color: #fff;
    margin-bottom: 10px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .card p { color: #8a8070; font-size: 14px; line-height: 1.6; }
  
  .grid-2 { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 16px; }
  .grid-3 { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 16px; }
  
  /* Timeline */
  .timeline { position: relative; padding-left: 32px; }
  .timeline::before {
    content: '';
    position: absolute;
    left: 10px; top: 0; bottom: 0;
    width: 2px;
    background: linear-gradient(to bottom, #ff6b00, #ff990060, transparent);
  }
  .timeline-item { position: relative; margin-bottom: 28px; }
  .timeline-dot {
    position: absolute;
    left: -27px; top: 4px;
    width: 14px; height: 14px;
    border-radius: 50%;
    background: #ff6b00;
    border: 2px solid #0a0a0a;
    box-shadow: 0 0 8px #ff6b0080;
  }
  .timeline-dot.done { background: #00c851; box-shadow: 0 0 8px #00c85180; }
  .timeline-dot.future { background: #333; box-shadow: none; }
  
  .timeline-week {
    font-family: 'Syne', sans-serif;
    font-size: 11px;
    font-weight: 700;
    color: #ff6b00;
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 4px;
  }
  .timeline-title {
    font-family: 'Syne', sans-serif;
    font-size: 15px;
    font-weight: 700;
    color: #fff;
    margin-bottom: 8px;
  }
  .timeline-tasks {
    display: flex;
    flex-direction: column;
    gap: 6px;
  }
  .task {
    display: flex;
    align-items: flex-start;
    gap: 8px;
    font-size: 13px;
    color: #8a8070;
    line-height: 1.4;
  }
  .task-icon { color: #ff6b00; flex-shrink: 0; margin-top: 1px; }
  
  /* Cost table */
  .cost-table { width: 100%; border-collapse: collapse; }
  .cost-table th {
    text-align: left;
    padding: 10px 14px;
    font-family: 'Syne', sans-serif;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    color: #6b6050;
    border-bottom: 1px solid #1e1e1e;
  }
  .cost-table td {
    padding: 10px 14px;
    font-size: 13px;
    color: #c0b8a8;
    border-bottom: 1px solid #151515;
  }
  .cost-table tr:last-child td { border-bottom: none; }
  .cost-free { color: #00c851 !important; font-weight: 600; }
  .cost-paid { color: #ff9944 !important; font-weight: 600; }
  .cost-total td { color: #fff !important; font-weight: 700; font-size: 14px; border-top: 2px solid #2a1500 !important; }
  
  /* Revenue bars */
  .revenue-bar-container { margin-bottom: 14px; }
  .revenue-bar-label {
    display: flex;
    justify-content: space-between;
    margin-bottom: 6px;
    font-size: 13px;
  }
  .revenue-bar-name { color: #c0b8a8; }
  .revenue-bar-value { color: #ff6b00; font-weight: 600; font-family: 'Syne', sans-serif; }
  .revenue-bar-track {
    height: 8px;
    background: #1e1e1e;
    border-radius: 4px;
    overflow: hidden;
  }
  .revenue-bar-fill {
    height: 100%;
    border-radius: 4px;
    background: linear-gradient(90deg, #ff6b00, #ff9944);
    transition: width 1s ease;
  }
  
  /* Step tutorial */
  .step-num {
    width: 32px; height: 32px;
    background: #ff6b00;
    color: #fff;
    font-family: 'Syne', sans-serif;
    font-weight: 800;
    font-size: 14px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
  }
  .step-content { flex: 1; }
  .step-title {
    font-family: 'Syne', sans-serif;
    font-size: 15px;
    font-weight: 700;
    color: #fff;
    margin-bottom: 6px;
  }
  .step-desc { font-size: 13px; color: #8a8070; line-height: 1.6; }
  .step-row { display: flex; gap: 14px; margin-bottom: 20px; align-items: flex-start; }
  
  .tip-box {
    background: #0f1a0a;
    border: 1px solid #1a3010;
    border-radius: 8px;
    padding: 14px 16px;
    margin-top: 12px;
  }
  .tip-box-title { font-size: 12px; font-weight: 600; color: #00c851; letter-spacing: 1px; text-transform: uppercase; margin-bottom: 6px; }
  .tip-box p { font-size: 13px; color: #6a8a60; line-height: 1.6; }
  
  .warning-box {
    background: #1a1000;
    border: 1px solid #3a2500;
    border-radius: 8px;
    padding: 14px 16px;
    margin-top: 12px;
  }
  .warning-box-title { font-size: 12px; font-weight: 600; color: #ffd700; letter-spacing: 1px; text-transform: uppercase; margin-bottom: 6px; }
  .warning-box p { font-size: 13px; color: #8a7040; line-height: 1.6; }
  
  .pill {
    display: inline-block;
    background: #1e1e1e;
    border: 1px solid #2a2a2a;
    border-radius: 20px;
    padding: 4px 12px;
    font-size: 12px;
    color: #8a8070;
    margin: 3px;
  }
  .pill-orange { background: #1a0800; border-color: #3a1800; color: #ff9944; }
  
  .platform-card {
    background: #111;
    border: 1px solid #1e1e1e;
    border-radius: 10px;
    padding: 16px;
    text-align: center;
  }
  .platform-icon { font-size: 28px; margin-bottom: 8px; }
  .platform-name { font-family: 'Syne', sans-serif; font-size: 13px; font-weight: 700; color: #fff; margin-bottom: 4px; }
  .platform-desc { font-size: 11px; color: #6b6050; line-height: 1.4; }
  
  .big-number {
    font-family: 'Syne', sans-serif;
    font-size: 36px;
    font-weight: 800;
    color: #ff6b00;
  }
  
  .divider { border: none; border-top: 1px solid #1a1a1a; margin: 24px 0; }
  
  .tag { 
    display: inline-block; 
    font-size: 11px; 
    font-weight: 600;
    padding: 3px 8px; 
    border-radius: 4px; 
    margin-right: 6px;
  }
  .tag-free { background: #00c85120; color: #00c851; }
  .tag-paid { background: #ff6b0020; color: #ff9944; }
  
  .checklist { list-style: none; }
  .checklist li {
    padding: 8px 0;
    font-size: 14px;
    color: #8a8070;
    border-bottom: 1px solid #151515;
    display: flex;
    align-items: flex-start;
    gap: 10px;
    line-height: 1.5;
  }
  .checklist li:last-child { border-bottom: none; }
  .check-icon { color: #ff6b00; flex-shrink: 0; font-size: 16px; }
  
  .scenario-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr)); gap: 12px; margin-top: 8px; }
  .scenario-card {
    background: #111;
    border: 1px solid #1e1e1e;
    border-radius: 10px;
    padding: 16px;
    text-align: center;
  }
  .scenario-label { font-size: 11px; color: #6b6050; text-transform: uppercase; letter-spacing: 1px; margin-bottom: 6px; }
  .scenario-value { font-family: 'Syne', sans-serif; font-size: 20px; font-weight: 800; }
  .scenario-note { font-size: 11px; color: #6b6050; margin-top: 4px; }
  .pessimista { color: #ff4444; }
  .realista { color: #ffd700; }
  .otimista { color: #00c851; }
`;

const tabs = [
  { id: "modelo", label: "🏗️ Modelo", title: "Modelo de Negócio" },
  { id: "cronograma", label: "📅 Cronograma", title: "Cronograma 90 Dias" },
  { id: "tutorial", label: "📖 Tutorial", title: "Passo a Passo" },
  { id: "plataformas", label: "🛒 Afiliados", title: "Programas de Afiliados" },
  { id: "custos", label: "💰 Custos", title: "Custos e Investimento" },
  { id: "faturamento", label: "📈 Faturamento", title: "Projeção de Faturamento" },
  { id: "conteudo", label: "🎬 Conteúdo", title: "Estratégia de Conteúdo" },
  { id: "ferramentas", label: "🔧 Ferramentas", title: "Ferramentas Essenciais" },
];

function ModeloTab() {
  return (
    <div>
      <p className="section-sub">Como funciona o funil completo do negócio de achadinhos</p>
      
      <div className="card card-orange" style={{marginBottom: 24}}>
        <h3>🎯 Conceito Central</h3>
        <p>Você age como um <strong style={{color:'#ff9944'}}>curador de promoções</strong>: encontra ofertas imperdíveis nos marketplaces, cria conteúdo atrativo nas redes sociais, e direciona sua audiência para o WhatsApp onde compartilha links de afiliados. A cada compra feita pelo seu link, você recebe comissão.</p>
      </div>
      
      <div className="section-title" style={{fontSize:16, marginBottom:16}}>🔄 O Funil de Conversão</div>
      
      <div style={{display:'flex', flexDirection:'column', gap:12, marginBottom:28}}>
        {[
          { icon: "📱", step: "1. ATRAÇÃO", title: "Redes Sociais (Instagram, TikTok, Facebook)", desc: "Posts de promoções, reels, stories com ofertas relâmpago. Você gera audiência orgânica e/ou paga.", color: "#ff6b00" },
          { icon: "📲", step: "2. DIRECIONAMENTO", title: "Link na Bio → WhatsApp", desc: "CTA nos posts direto para o WhatsApp ou grupo de WhatsApp. Use Linktree ou link direto.", color: "#ff9944" },
          { icon: "💬", step: "3. ENGAJAMENTO", title: "Grupo / Canal WhatsApp", desc: "Aqui você posta as promoções com seus links de afiliado. O cliente é aquecido e pronto para comprar.", color: "#ffd700" },
          { icon: "🛒", step: "4. CONVERSÃO", title: "Marketplace (Shopee, Amazon, ML, Magalu)", desc: "O cliente clica no seu link e compra no marketplace. Você ganha comissão de 3% a 15%.", color: "#00c851" },
          { icon: "💰", step: "5. COMISSÃO", title: "Pagamento via programa de afiliados", desc: "A comissão é creditada na sua conta 30-90 dias após a compra confirmada.", color: "#007bff" },
        ].map((f, i) => (
          <div key={i} style={{display:'flex', gap:14, alignItems:'flex-start', background:'#111', border:'1px solid #1e1e1e', borderRadius:10, padding:16}}>
            <div style={{fontSize:24, flexShrink:0}}>{f.icon}</div>
            <div>
              <div style={{fontSize:10, fontWeight:700, color:f.color, letterSpacing:2, marginBottom:4}}>{f.step}</div>
              <div style={{fontFamily:'Syne', fontWeight:700, fontSize:14, color:'#fff', marginBottom:4}}>{f.title}</div>
              <div style={{fontSize:13, color:'#8a8070'}}>{f.desc}</div>
            </div>
          </div>
        ))}
      </div>
      
      <div className="grid-2">
        <div className="card card-green">
          <h3>✅ Vantagens do Modelo</h3>
          <ul className="checklist">
            {["Custo inicial próximo de zero","Sem estoque, sem logística","Escalável sem limite","Renda passiva após criar audiência","Trabalha 24h no piloto automático","Pode começar sozinho, de casa"].map((v,i) => (
              <li key={i}><span className="check-icon">▸</span>{v}</li>
            ))}
          </ul>
        </div>
        <div className="card card-yellow">
          <h3>⚠️ Desafios a Superar</h3>
          <ul className="checklist">
            {["Leva tempo para construir audiência","Resultados demoram 2-3 meses","Concorrência alta no segmento","Depende de regularidade de posts","Comissões variam por temporada","Requer aprendizado contínuo"].map((v,i) => (
              <li key={i}><span style={{color:'#ffd700', flexShrink:0}}>▸</span>{v}</li>
            ))}
          </ul>
        </div>
      </div>
      
      <div className="card" style={{marginTop:16, background:'#0a0f1a', borderColor:'#0a1a2a'}}>
        <h3>💡 Fontes de Renda (Multi-stream)</h3>
        <div className="grid-3" style={{marginTop:8}}>
          {[
            {t:"Afiliados Marketplaces", d:"Shopee, Amazon, Mercado Livre — 3-12% por venda"},
            {t:"Grupo WhatsApp Pago", d:"Cobrança de R$9,90-29,90/mês para grupos premium"},
            {t:"Posts Patrocinados", d:"Marcas pagam para divulgar produtos para sua base"},
            {t:"Cursos e Mentorias", d:"Ensine outros a montar o mesmo negócio"},
            {t:"Dropshipping", d:"Venda produtos com margem maior em vez de só afiliar"},
          ].map((s, i) => (
            <div key={i} style={{background:'#111', border:'1px solid #1e1e1e', borderRadius:8, padding:14}}>
              <div style={{fontFamily:'Syne', fontWeight:700, fontSize:13, color:'#ff6b00', marginBottom:4}}>{s.t}</div>
              <div style={{fontSize:12, color:'#6b6050'}}>{s.d}</div>
            </div>
          ))}
        </div>
      </div>
    </div>
  );
}

function CronogramaTab() {
  const phases = [
    {
      phase: "FASE 1 — FUNDAÇÃO", weeks: "Semana 1 a 2", color: "#ff6b00",
      items: [
        "Definir nicho: celulares, casa/decoração, moda, bebê, tecnologia ou geral",
        "Criar contas no Instagram, TikTok e Facebook com nome e identidade visual",
        "Cadastrar em todos os programas de afiliados (Shopee, Amazon, Magalu)",
        "Criar grupo e canal no WhatsApp Business",
        "Instalar e aprender a usar o Canva para criar posts",
        "Montar link na bio com Linktree ou similar",
        "Criar identidade visual: logo, paleta de cores, template de posts",
      ]
    },
    {
      phase: "FASE 2 — CONTEÚDO", weeks: "Semana 3 a 4", color: "#ff9944",
      items: [
        "Criar os primeiros 9 posts para o feed do Instagram (feed curado)",
        "Gravar primeiros 3 Reels e TikToks de promoções",
        "Postar 2x por dia nos stories: promoções do dia",
        "Começar a construir os primeiros membros no WhatsApp (amigos, família)",
        "Estudar as melhores práticas de hashtag e SEO para cada plataforma",
        "Instalar app de encurtador de links com rastreamento",
      ]
    },
    {
      phase: "FASE 3 — TRAÇÃO", weeks: "Mês 2 (Semanas 5-8)", color: "#ffd700",
      items: [
        "Meta: 500 seguidores no Instagram, 300 no TikTok, 200 no WhatsApp",
        "Postar 1 Reel/TikTok por dia + 5 stories diários",
        "Iniciar campanha de tráfego pago com R$10/dia no Meta Ads",
        "Testar formatos: antes/depois de preço, timer de oferta relâmpago",
        "Criar primeiros 'drops' exclusivos de promoção para o grupo WhatsApp",
        "Analisar métricas e dobrar o que funciona melhor",
        "Começar parcerias com outros achadinhos (troca de divulgação)",
      ]
    },
    {
      phase: "FASE 4 — MONETIZAÇÃO", weeks: "Mês 3 (Semanas 9-12)", color: "#00c851",
      items: [
        "Meta: 2.000 seguidores no Instagram, 1.000 no TikTok, 500+ no WhatsApp",
        "Primeiras comissões de afiliados chegando na conta",
        "Criar grupo VIP pago no WhatsApp (R$19,90/mês)",
        "Negociar primeiro post patrocinado com marca pequena",
        "Automatizar parte do processo com bots de WhatsApp",
        "Documentar o que funciona e criar SOPs para escalar",
        "Projeção: R$500 a R$2.000/mês de comissões",
      ]
    },
    {
      phase: "FASE 5 — ESCALA", weeks: "Mês 4 a 6", color: "#007bff",
      items: [
        "Meta: 10k+ seguidores no Instagram, verificação TikTok",
        "Contratar editor de vídeo freelancer (R$300-600/mês)",
        "Criar segundo canal de nicho específico (ex: achadinhos pet, bebê)",
        "Lançar grupo premium com R$29,90/mês",
        "Investir R$500-1.000/mês em tráfego pago para acelerar crescimento",
        "Projeção: R$3.000 a R$8.000/mês receita total",
      ]
    },
  ];

  return (
    <div>
      <p className="section-sub">Roadmap detalhado do dia 1 ao mês 6</p>
      <div className="timeline">
        {phases.map((p, i) => (
          <div key={i} className="timeline-item">
            <div className="timeline-dot" style={{background: p.color, boxShadow: `0 0 8px ${p.color}80`}} />
            <div style={{fontFamily:'Syne', fontSize:10, fontWeight:700, color:p.color, letterSpacing:2, textTransform:'uppercase', marginBottom:4}}>{p.weeks}</div>
            <div style={{fontFamily:'Syne', fontSize:16, fontWeight:700, color:'#fff', marginBottom:10}}>{p.phase}</div>
            <div className="timeline-tasks">
              {p.items.map((item, j) => (
                <div key={j} className="task">
                  <span className="task-icon" style={{color:p.color}}>▸</span>
                  <span>{item}</span>
                </div>
              ))}
            </div>
          </div>
        ))}
      </div>
    </div>
  );
}

function TutorialTab() {
  const [open, setOpen] = useState(null);
  
  const tutorials = [
    {
      title: "Como se cadastrar nos programas de afiliados",
      steps: [
        { t: "Shopee Afiliados", d: "Acesse affiliates.shopee.com.br → Clique em 'Cadastrar' → Preencha seus dados e redes sociais → Aguarde aprovação (1-3 dias) → Acesse o painel e gere links de produtos." },
        { t: "Amazon Afiliados (Associados)", d: "Acesse associados.amazon.com.br → Crie sua conta com seu CPF e dados bancários → Defina seu site/perfil social como 'canal' → Aprovação automática → Use o SiteStripe para gerar links." },
        { t: "Magalu Parceiros", d: "Acesse parceiros.magazineluiza.com.br → Cadastre como afiliado → Informe suas redes sociais → Após aprovação, use o painel para gerar links com sua tag." },
        { t: "Mercado Livre Afiliados", d: "Acesse afiliados.mercadolivre.com.br → Crie sua conta → Adicione seus canais de divulgação → Acesse o marketplace de ofertas → Gere links rastreáveis para qualquer produto." },
      ]
    },
    {
      title: "Como criar seu grupo/canal no WhatsApp",
      steps: [
        { t: "WhatsApp Business App", d: "Baixe o WhatsApp Business (gratuito) → Configure com CNPJ ou CPF → Crie catálogo, horários e mensagem automática de boas-vindas." },
        { t: "Canal WhatsApp (Recomendado)", d: "No WhatsApp, vá em 'Novidades' → 'Criar canal' → Coloque nome do seu achadinhos, foto e descrição → Compartilhe o link para as pessoas seguirem. Canal = você fala, seguidores não respondem (ideal para promoções)." },
        { t: "Grupo WhatsApp", d: "Crie grupos normais para comunidade. Limite de 1.024 membros. Use para o grupo premium pago, onde a interação é parte do valor. Configure regras na descrição do grupo." },
        { t: "Mensagem automática de boas-vindas", d: "No WhatsApp Business: Configurações → Ferramentas de negócios → Mensagem de saudação → Personalize dizendo 'Bem-vindo! Aqui você recebe as melhores promoções do dia. Ative as notificações! 🔔'" },
      ]
    },
    {
      title: "Como criar posts de alta conversão no Canva",
      steps: [
        { t: "Crie seu template base", d: "No Canva, crie um design de Post para Instagram (1080x1080). Use fundo escuro ou colorido chamativo. Reserve espaço para: foto do produto, preço DE e POR, nome da loja, badge 'OFERTA DO DIA'." },
        { t: "Elementos que convertem", d: "Badge vermelho/laranja de desconto (ex: '-60%'), timer de urgência, texto grande com o preço, antes e depois do preço tachado, emojis de fogo 🔥, alerta ⚡, dinheiro 💰." },
        { t: "Stories otimizados", d: "Use o formato 1080x1920. Adicione figurinha de link para redirecionar para o WhatsApp. Stories com 'Arrasta pra cima' ou link direto convertem muito melhor que só o feed." },
        { t: "Salvando templates", d: "Transforme seu design em template no Canva para reusar. Assim você só troca foto, preço e link — leva menos de 2 minutos criar um novo post." },
      ]
    },
    {
      title: "Como criar Reels e TikToks de promoções",
      steps: [
        { t: "Estrutura do vídeo de 15-30s", d: "0-3s: GANCHO — 'Essa promoção ABSURDA vai acabar hoje!' | 3-20s: PRODUTO — Mostre o produto, destaque o preço e desconto | 20-25s: CTA — 'Link no stories / bio / WhatsApp para garantir!'" },
        { t: "Apps gratuitos para editar", d: "CapCut (melhor para TikTok/Reels, gratuito e potente). InShot (mais simples e rápido). O próprio TikTok tem bons efeitos nativos. Use templates prontos do CapCut para economizar tempo." },
        { t: "Trilha sonora estratégica", d: "Use músicas em alta no TikTok/Instagram para maior alcance orgânico. O próprio TikTok mostra quais músicas estão em tendência. Sempre prefira músicas sem direitos autorais ou as sugeridas pela plataforma." },
        { t: "Hashtags para alcance", d: "Instagram: use 5-10 hashtags relevantes (#achadinhos #promoção #ofertadodia #shopee #amazon). TikTok: use 3-5 (#achadinhos #oferta #dica). Não exagere, foque na qualidade." },
      ]
    },
    {
      title: "Como configurar o tráfego pago (Meta Ads)",
      steps: [
        { t: "Criando a conta de anúncios", d: "Acesse business.facebook.com → Crie um Business Manager → Adicione sua conta de anúncios → Vincule ao seu perfil do Instagram → Adicione forma de pagamento (cartão de crédito)." },
        { t: "Campanha para crescimento de seguidores", d: "Objetivo: Engajamento ou Alcance → Público: Brasil, 18-45 anos, interesses em 'Promoções', 'Compras online', 'Shopee' → Budget: R$5-10/dia → Criativo: Reel ou imagem de promoção impactante." },
        { t: "Campanha para WhatsApp", d: "Objetivo: Mensagens → Plataforma: WhatsApp → Inclua botão 'Enviar mensagem' → Direcione para seu número/grupo → Mensagem pré-preenchida: 'Quero receber promoções!'" },
        { t: "Otimização das campanhas", d: "Deixe rodar 3-5 dias antes de julgar. Desligue anúncios com CPM/CPR muito alto. Duplique os vencedores com mais budget. Teste 2-3 criativos diferentes simultaneamente." },
      ]
    },
  ];

  return (
    <div>
      <p className="section-sub">Guias detalhados para cada etapa do negócio</p>
      {tutorials.map((t, i) => (
        <div key={i} className="card" style={{marginBottom:12, cursor:'pointer'}} onClick={() => setOpen(open===i ? null : i)}>
          <div style={{display:'flex', justifyContent:'space-between', alignItems:'center'}}>
            <h3 style={{marginBottom:0}}>
              <span style={{background:'#ff6b00', color:'#fff', borderRadius:'50%', width:24, height:24, display:'inline-flex', alignItems:'center', justifyContent:'center', fontSize:12, fontWeight:800, marginRight:10}}>{i+1}</span>
              {t.title}
            </h3>
            <span style={{color:'#ff6b00', fontSize:18}}>{open===i ? '−' : '+'}</span>
          </div>
          {open === i && (
            <div style={{marginTop:16}}>
              {t.steps.map((s, j) => (
                <div key={j} className="step-row">
                  <div className="step-num">{String.fromCharCode(65+j)}</div>
                  <div className="step-content">
                    <div className="step-title">{s.t}</div>
                    <div className="step-desc">{s.d}</div>
                  </div>
                </div>
              ))}
            </div>
          )}
        </div>
      ))}
      
      <div className="tip-box" style={{marginTop:8}}>
        <div className="tip-box-title">💡 Dica de Ouro</div>
        <p>Comece pelo WhatsApp e Instagram. São as plataformas com mais conversão para o modelo de achadinhos no Brasil. TikTok tem alcance orgânico maior mas converte menos diretamente. Facebook é ótimo para audiências 35+.</p>
      </div>
    </div>
  );
}

function PlataformasTab() {
  const plataformas = [
    { icon:"🛍️", name:"Shopee Afiliados", url:"affiliates.shopee.com.br", comissao:"Até 10%", cookie:"7-30 dias", pago:"Mensal via PIX", pros:"Enorme variedade, comissão alta, aprovação fácil", cons:"Ticket médio baixo", cor:"#ee4d2d" },
    { icon:"📦", name:"Amazon Associados", url:"associados.amazon.com.br", comissao:"Até 12%", cookie:"24h (carrinhos 90 dias)", pago:"Vale-presente ou transferência", pros:"Marca forte, produtos premium, confiança alta", cons:"Cookie de 24h é curto", cor:"#ff9900" },
    { icon:"🏪", name:"Mercado Livre", url:"afiliados.mercadolivre.com.br", comissao:"Até 8%", cookie:"30 dias", pago:"Mensal", pros:"Líder no Brasil, ticket médio bom, eletrodomésticos", cons:"Interface do painel menos intuitiva", cor:"#ffe600" },
    { icon:"🔵", name:"Magazine Luiza", url:"parceiros.magazineluiza.com.br", comissao:"Até 6%", cookie:"30 dias", pago:"Mensal", pros:"Eletro e tecnologia, boas promoções sazonais", cons:"Categorias mais limitadas", cor:"#0086ff" },
    { icon:"🟠", name:"Americanas Afiliados", url:"afiliados.americanas.com.br", comissao:"Até 7%", cookie:"30 dias", pago:"Mensal", pros:"Variedade, boas ofertas no varejo", cons:"Concorrência alta na categoria", cor:"#f23005" },
    { icon:"🟣", name:"Hotmart / Monetizze", url:"hotmart.com / monetizze.com.br", comissao:"Até 50%!", cookie:"30-60 dias", pago:"Semanal/quinzenal", pros:"Comissões altíssimas em infoprodutos, cursos", cons:"Diferente — vende cursos, não produtos físicos", cor:"#f04e23" },
  ];

  return (
    <div>
      <p className="section-sub">Todos os programas de afiliados que você deve cadastrar</p>
      
      <div className="warning-box" style={{marginBottom:20}}>
        <div className="warning-box-title">⚡ Estratégia Recomendada</div>
        <p>Cadastre em <strong>todos</strong> os programas. Para cada promoção, use o link do marketplace que paga a maior comissão naquela categoria. Compare sempre antes de postar.</p>
      </div>
      
      {plataformas.map((p, i) => (
        <div key={i} className="card" style={{marginBottom:12}}>
          <div style={{display:'flex', gap:14, alignItems:'flex-start'}}>
            <div style={{fontSize:28, flexShrink:0}}>{p.icon}</div>
            <div style={{flex:1}}>
              <div style={{display:'flex', justifyContent:'space-between', flexWrap:'wrap', gap:8}}>
                <div style={{fontFamily:'Syne', fontWeight:700, fontSize:15, color:'#fff'}}>{p.name}</div>
                <div style={{fontFamily:'Syne', fontWeight:800, fontSize:18, color:p.cor}}>{p.comissao}</div>
              </div>
              <div style={{fontSize:12, color:'#6b6050', marginBottom:8}}>{p.url}</div>
              <div style={{display:'flex', gap:16, flexWrap:'wrap', marginBottom:8}}>
                <div><span style={{fontSize:11, color:'#6b6050'}}>Cookie: </span><span style={{fontSize:12, color:'#c0b8a8'}}>{p.cookie}</span></div>
                <div><span style={{fontSize:11, color:'#6b6050'}}>Pagamento: </span><span style={{fontSize:12, color:'#c0b8a8'}}>{p.pago}</span></div>
              </div>
              <div style={{display:'flex', gap:10, flexWrap:'wrap'}}>
                <div style={{fontSize:12, color:'#00c851'}}>✓ {p.pros}</div>
                <div style={{fontSize:12, color:'#ff6644'}}>✗ {p.cons}</div>
              </div>
            </div>
          </div>
        </div>
      ))}
      
      <div className="card card-green" style={{marginTop:8}}>
        <h3>🔗 Como gerar links de afiliado</h3>
        <div className="step-row" style={{marginBottom:10}}>
          <div className="step-num" style={{width:24, height:24, fontSize:12}}>1</div>
          <div className="step-content">
            <div className="step-desc">Encontre o produto em promoção no marketplace</div>
          </div>
        </div>
        <div className="step-row" style={{marginBottom:10}}>
          <div className="step-num" style={{width:24, height:24, fontSize:12}}>2</div>
          <div className="step-content">
            <div className="step-desc">Copie o link do produto e cole no painel do afiliado, ou use a extensão do navegador</div>
          </div>
        </div>
        <div className="step-row" style={{marginBottom:10}}>
          <div className="step-num" style={{width:24, height:24, fontSize:12}}>3</div>
          <div className="step-content">
            <div className="step-desc">O sistema gera um link rastreado com sua ID de afiliado</div>
          </div>
        </div>
        <div className="step-row" style={{marginBottom:0}}>
          <div className="step-num" style={{width:24, height:24, fontSize:12}}>4</div>
          <div className="step-content">
            <div className="step-desc">Encurte o link com Bitly ou similar e poste no WhatsApp/redes sociais</div>
          </div>
        </div>
      </div>
    </div>
  );
}

function CustosTab() {
  return (
    <div>
      <p className="section-sub">Investimento inicial e custos mensais para operar</p>
      
      <div style={{display:'flex', gap:12, marginBottom:24, flexWrap:'wrap'}}>
        <div style={{background:'#111', border:'1px solid #1e1e1e', borderRadius:10, padding:20, flex:1, minWidth:160}}>
          <div style={{fontSize:11, color:'#6b6050', textTransform:'uppercase', letterSpacing:1}}>Investimento Inicial</div>
          <div className="big-number">R$0</div>
          <div style={{fontSize:12, color:'#6b6050'}}>Pode começar de graça</div>
        </div>
        <div style={{background:'#111', border:'1px solid #1e1e1e', borderRadius:10, padding:20, flex:1, minWidth:160}}>
          <div style={{fontSize:11, color:'#6b6050', textTransform:'uppercase', letterSpacing:1}}>Custo Mínimo/Mês</div>
          <div className="big-number">R$55</div>
          <div style={{fontSize:12, color:'#6b6050'}}>Apenas Canva Pro</div>
        </div>
        <div style={{background:'#111', border:'1px solid #1e1e1e', borderRadius:10, padding:20, flex:1, minWidth:160}}>
          <div style={{fontSize:11, color:'#6b6050', textTransform:'uppercase', letterSpacing:1}}>Custo Recomendado/Mês</div>
          <div className="big-number">R$355</div>
          <div style={{fontSize:12, color:'#6b6050'}}>Com R$300 em tráfego</div>
        </div>
      </div>
      
      <div className="section-title" style={{fontSize:16, marginBottom:12}}>📋 Ferramentas — Plano Gratuito</div>
      <div className="card" style={{marginBottom:20, padding:0, overflow:'hidden'}}>
        <table className="cost-table" style={{width:'100%'}}>
          <thead>
            <tr><th>Ferramenta</th><th>Uso</th><th>Custo</th></tr>
          </thead>
          <tbody>
            {[
              ["Instagram", "Rede social principal", "GRÁTIS"],
              ["TikTok", "Alcance orgânico viral", "GRÁTIS"],
              ["Facebook / Meta", "Grupos e alcance 35+", "GRÁTIS"],
              ["WhatsApp Business", "Grupo/Canal de promoções", "GRÁTIS"],
              ["Canva (versão free)", "Criação de posts e stories", "GRÁTIS"],
              ["Linktree", "Link na bio unificado", "GRÁTIS"],
              ["Bitly", "Encurtar links de afiliado", "GRÁTIS"],
              ["CapCut", "Edição de Reels e TikToks", "GRÁTIS"],
              ["Todos os programas de afiliados", "Geração de links", "GRÁTIS"],
            ].map(([a,b,c], i) => (
              <tr key={i}><td>{a}</td><td>{b}</td><td className="cost-free">{c}</td></tr>
            ))}
          </tbody>
        </table>
      </div>
      
      <div className="section-title" style={{fontSize:16, marginBottom:12}}>💳 Ferramentas Pagas (Recomendadas)</div>
      <div className="card" style={{marginBottom:20, padding:0, overflow:'hidden'}}>
        <table className="cost-table" style={{width:'100%'}}>
          <thead>
            <tr><th>Ferramenta</th><th>Benefício</th><th>Custo/Mês</th></tr>
          </thead>
          <tbody>
            {[
              ["Canva Pro", "Remove fundo, +templates premium, marca d'água off", "R$54,99"],
              ["Meta Ads (tráfego pago)", "Acelera crescimento de seguidores e WhatsApp", "R$10/dia recomendado"],
              ["ChatGPT Plus (opcional)", "Cria legendas, ideias de post e copy de venda", "R$100"],
              ["Notion (opcional)", "Organiza o calendário editorial e tarefas", "GRÁTIS"],
              ["WA Marketing / ZAP (opcional)", "Automação de mensagens WhatsApp Business API", "R$49-99"],
            ].map(([a,b,c], i) => (
              <tr key={i}><td>{a}</td><td>{b}</td><td className="cost-paid">{c}</td></tr>
            ))}
            <tr className="cost-total">
              <td colSpan={2}><strong>TOTAL RECOMENDADO (com R$300 ads)</strong></td>
              <td><strong>~R$355/mês</strong></td>
            </tr>
          </tbody>
        </table>
      </div>
      
      <div className="grid-2">
        <div className="tip-box">
          <div className="tip-box-title">💡 Comece Gratuito</div>
          <p>Nos primeiros 30 dias, use tudo gratuito. Só invista em anúncios quando tiver conteúdo funcionando organicamente. Não gaste antes de validar.</p>
        </div>
        <div className="warning-box">
          <div className="warning-box-title">⚠️ Atenção com CNPJ</div>
          <p>Para receber comissões acima de R$1.500/mês, considere abrir um MEI (R$70/mês). Facilita recebimento, diminui impostos e profissionaliza o negócio.</p>
        </div>
      </div>
    </div>
  );
}

function FaturamentoTab() {
  const projecoes = [
    { mes: "Mês 1-2", seguidores: "0-500 seg.", whatsapp: "0-100 membros", comissao: "R$0 – R$200", renda: "R$0 – R$200", fase: "Construção" },
    { mes: "Mês 3", seguidores: "500-2k seg.", whatsapp: "100-300 membros", comissao: "R$200 – R$800", renda: "R$200 – R$800", fase: "Validação" },
    { mes: "Mês 4-5", seguidores: "2k-8k seg.", whatsapp: "300-600 membros", comissao: "R$800 – R$2.500", renda: "R$800 – R$3.000", fase: "Crescimento" },
    { mes: "Mês 6", seguidores: "8k-20k seg.", whatsapp: "600-1k membros", comissao: "R$2.000 – R$5.000", renda: "R$2.500 – R$6.000", fase: "Escala" },
    { mes: "Mês 12", seguidores: "20k-50k seg.", whatsapp: "1k-3k membros", comissao: "R$5.000 – R$15.000", renda: "R$6.000 – R$20.000+", fase: "Profissional" },
  ];

  const bars = [
    { label: "Mês 1", min: 0, max: 200, max_scale: 15000 },
    { label: "Mês 3", min: 200, max: 800, max_scale: 15000 },
    { label: "Mês 6", min: 2500, max: 6000, max_scale: 15000 },
    { label: "Mês 12", min: 6000, max: 20000, max_scale: 20000 },
  ];

  return (
    <div>
      <p className="section-sub">Projeções realistas baseadas em casos reais do mercado</p>
      
      <div className="warning-box" style={{marginBottom:20}}>
        <div className="warning-box-title">📊 Base das Projeções</div>
        <p>Valores baseados em achadinhos reais do Brasil. Considera: postagem consistente 2x/dia, crescimento orgânico + R$300/mês em ads a partir do mês 3. Resultados variam por nicho, dedicação e consistência.</p>
      </div>
      
      <div className="section-title" style={{fontSize:16, marginBottom:16}}>📊 Cenários no Mês 6</div>
      <div className="scenario-grid" style={{marginBottom:24}}>
        {[
          { label: "Pessimista", value: "R$1.200/mês", note: "Pouca consistência, sem ads", cls: "pessimista" },
          { label: "Realista", value: "R$4.000/mês", note: "Consistente, R$300/mês ads", cls: "realista" },
          { label: "Otimista", value: "R$8.000/mês", note: "Viral, nicho quente, ads", cls: "otimista" },
        ].map((s,i) => (
          <div key={i} className="scenario-card">
            <div className="scenario-label">{s.label}</div>
            <div className={`scenario-value ${s.cls}`}>{s.value}</div>
            <div className="scenario-note">{s.note}</div>
          </div>
        ))}
      </div>

      <div className="section-title" style={{fontSize:16, marginBottom:12}}>📈 Evolução do Faturamento</div>
      <div className="card" style={{marginBottom:20}}>
        {bars.map((b, i) => (
          <div key={i} className="revenue-bar-container">
            <div className="revenue-bar-label">
              <span className="revenue-bar-name">{b.label}</span>
              <span className="revenue-bar-value">R${b.min.toLocaleString()} – R${b.max.toLocaleString()}</span>
            </div>
            <div className="revenue-bar-track">
              <div className="revenue-bar-fill" style={{width:`${(b.max/b.max_scale)*100}%`}} />
            </div>
          </div>
        ))}
      </div>
      
      <div className="section-title" style={{fontSize:16, marginBottom:12}}>📋 Tabela de Projeção Detalhada</div>
      <div className="card" style={{padding:0, overflow:'auto'}}>
        <table className="cost-table" style={{width:'100%'}}>
          <thead>
            <tr>
              <th>Período</th>
              <th>Audiência</th>
              <th>WhatsApp</th>
              <th>Comissões</th>
              <th>Renda Total*</th>
            </tr>
          </thead>
          <tbody>
            {projecoes.map((p, i) => (
              <tr key={i}>
                <td><span style={{color:'#ff6b00', fontWeight:600}}>{p.mes}</span><br/><span style={{fontSize:11, color:'#6b6050'}}>{p.fase}</span></td>
                <td>{p.seguidores}</td>
                <td>{p.whatsapp}</td>
                <td style={{color:'#ff9944'}}>{p.comissao}</td>
                <td style={{color:'#00c851', fontWeight:600}}>{p.renda}</td>
              </tr>
            ))}
          </tbody>
        </table>
      </div>
      <p style={{fontSize:11, color:'#6b6050', marginTop:8}}>*Renda Total inclui: comissões de afiliados + grupo pago + posts patrocinados</p>
      
      <div className="section-title" style={{fontSize:16, marginBottom:12, marginTop:24}}>💰 Como a Matemática Funciona</div>
      <div className="grid-2">
        {[
          { title: "Exemplo Shopee — R$1.000/mês", items: ["500 membros ativos no WhatsApp","20% clicam nas promoções = 100 cliques/dia","10% dos que clicam compram = 10 vendas/dia","Ticket médio R$80 × comissão 8% = R$6,40","10 vendas × R$6,40 = R$64/dia","R$64 × 30 dias = R$1.920/mês"] },
          { title: "Exemplo Grupo VIP Pago", items: ["200 membros no grupo pago","Mensalidade: R$19,90","200 × R$19,90 = R$3.980/mês","+ comissões extras dos membros VIP","ROI: pagou R$300 em ads para gerar R$4k"] },
        ].map((e, i) => (
          <div key={i} className="card card-orange">
            <h3>📐 {e.title}</h3>
            <ul className="checklist">
              {e.items.map((it, j) => (
                <li key={j}><span style={{color:'#ff6b00', flexShrink:0}}>▸</span>{it}</li>
              ))}
            </ul>
          </div>
        ))}
      </div>
    </div>
  );
}

function ConteudoTab() {
  return (
    <div>
      <p className="section-sub">O que postar, quando postar e como criar conteúdo de alta conversão</p>
      
      <div className="section-title" style={{fontSize:16, marginBottom:12}}>📅 Calendário Semanal Ideal</div>
      <div className="card" style={{marginBottom:20}}>
        {[
          { dia: "Seg", posts: ["📱 Reel: Top 5 promoções da semana", "📲 WhatsApp: 3-5 achados do dia", "📸 Stories: Votação 'qual produto você queria?'"] },
          { dia: "Ter", posts: ["⚡ Story urgência: oferta relâmpago 24h", "📲 WhatsApp: promoção específica com link", "💬 Post carrossel: 'Como economizar em X'"] },
          { dia: "Qua", posts: ["🔥 Reel: Achado da semana (melhor oferta)", "📲 WhatsApp: 3-5 promoções do dia", "📸 Stories: bastidores, como você busca promoções"] },
          { dia: "Qui", posts: ["📸 Post: comparativo de preços (antes/depois)", "📲 WhatsApp: cupons e códigos do dia", "💬 Enquete: 'Qual categoria você quer amanhã?'"] },
          { dia: "Sex", posts: ["🛍️ Reel: 'Promoções de fim de semana'", "📲 WhatsApp: Black Friday antecipada / promoções sexta", "⚡ Stories: contagem regressiva ofertas"] },
          { dia: "Sáb", posts: ["🎬 TikTok: vídeo longo 'melhores achadinhos da semana'", "📲 WhatsApp: resumo das melhores da semana", "📸 Stories: feirão de achadinhos"] },
          { dia: "Dom", posts: ["🔄 Repost dos melhores conteúdos da semana", "📲 WhatsApp: preparando a semana (teaser)", "📸 Stories: bastidores, planejamento"] },
        ].map((d, i) => (
          <div key={i} style={{display:'flex', gap:14, padding:'12px 0', borderBottom: i<6 ? '1px solid #151515' : 'none'}}>
            <div style={{width:36, height:36, background:'#1a0800', border:'1px solid #3a1800', borderRadius:8, display:'flex', alignItems:'center', justifyContent:'center', fontFamily:'Syne', fontWeight:700, fontSize:12, color:'#ff6b00', flexShrink:0}}>{d.dia}</div>
            <div>
              {d.posts.map((p, j) => (
                <div key={j} style={{fontSize:13, color:'#8a8070', marginBottom:3}}>{p}</div>
              ))}
            </div>
          </div>
        ))}
      </div>
      
      <div className="section-title" style={{fontSize:16, marginBottom:12}}>🎯 Tipos de Conteúdo que Mais Convertem</div>
      <div className="grid-2">
        {[
          { icon:"🔥", t:"Oferta Relâmpago", d:"'Só até meia-noite!' — urgência e escassez são os gatilhos mais poderosos. Use timer visual.", tag:"Alta conversão" },
          { icon:"⚖️", t:"Antes × Depois de Preço", d:"Mostre o preço riscado e o novo preço. Ex: ~~R$299~~ → R$89. Impacto visual imediato.", tag:"Alta viralização" },
          { icon:"🏆", t:"Top N Achados", d:"'Top 5 produtos mais baratos da semana' — formato de lista sempre gera engajamento.", tag:"Salva e compartilha" },
          { icon:"🎁", t:"Cupom Exclusivo", d:"Cupons exclusivos para o seu grupo WhatsApp criam senso de comunidade e VIP.", tag:"Retém membros" },
          { icon:"📱", t:"Unboxing de Achados", d:"Mostre recebendo e usando o produto. Prova social que o produto chegou e é bom.", tag:"Confiança" },
          { icon:"🤔", t:"Comparativo de Lojas", d:"'O mesmo produto em 3 lojas: qual é mais barato?' — educa e entretém.", tag:"Educativo" },
        ].map((c, i) => (
          <div key={i} className="card" style={{marginBottom:10}}>
            <div style={{display:'flex', gap:10, alignItems:'flex-start'}}>
              <span style={{fontSize:24, flexShrink:0}}>{c.icon}</span>
              <div>
                <div style={{fontFamily:'Syne', fontWeight:700, fontSize:14, color:'#fff', marginBottom:4}}>{c.t} <span style={{background:'#1a0800', color:'#ff9944', fontSize:10, padding:'2px 8px', borderRadius:4}}>{c.tag}</span></div>
                <div style={{fontSize:13, color:'#8a8070'}}>{c.d}</div>
              </div>
            </div>
          </div>
        ))}
      </div>
      
      <div className="tip-box" style={{marginTop:8}}>
        <div className="tip-box-title">🕐 Melhores Horários para Postar</div>
        <p><strong style={{color:'#00c851'}}>Instagram:</strong> 18h-21h (seg-sex) e 10h-12h (fim de semana). <strong style={{color:'#00c851'}}>TikTok:</strong> 19h-22h qualquer dia. <strong style={{color:'#00c851'}}>WhatsApp:</strong> 7h-9h (pessoas acordando), 12h-13h (almoço), 19h-21h (após trabalho).</p>
      </div>
    </div>
  );
}

function FerramentasTab() {
  const ferramentas = [
    {
      cat: "📱 Redes Sociais e Comunicação", items: [
        { n:"Instagram Business", d:"Perfil profissional com métricas e acesso a anúncios", tag:"free" },
        { n:"TikTok Creator", d:"Acesse o TikTok Studio para métricas e tendências", tag:"free" },
        { n:"WhatsApp Business", d:"Mensagens automáticas, catálogo e múltiplos atendentes", tag:"free" },
        { n:"Meta Business Suite", d:"Gerencie Instagram e Facebook num só lugar + agende posts", tag:"free" },
      ]
    },
    {
      cat: "🎨 Criação de Conteúdo", items: [
        { n:"Canva", d:"Posts, stories, logos, banners — tudo num lugar", tag:"free" },
        { n:"CapCut", d:"Edição de vídeo mais usada no Brasil para Reels/TikTok", tag:"free" },
        { n:"Remove.bg", d:"Remove fundo de imagens de produtos automaticamente", tag:"free" },
        { n:"ChatGPT", d:"Gera legendas, copies de venda e ideias de conteúdo", tag:"free" },
      ]
    },
    {
      cat: "🔗 Links e Rastreamento", items: [
        { n:"Linktree", d:"Link único na bio com todos os seus canais e grupos", tag:"free" },
        { n:"Bitly", d:"Encurta links de afiliado e rastreia cliques", tag:"free" },
        { n:"Shopeegee / Gerador Shopee", d:"Extensão para gerar link de afiliado Shopee com um clique", tag:"free" },
        { n:"Amazon SiteStripe", d:"Extensão do Chrome para gerar links Amazon direto na página", tag:"free" },
      ]
    },
    {
      cat: "📊 Análise e Organização", items: [
        { n:"Notion", d:"Crie seu calendário editorial e organize as tarefas", tag:"free" },
        { n:"Google Sheets", d:"Planilha para acompanhar faturamento e comissões", tag:"free" },
        { n:"Later / Buffer", d:"Agendamento antecipado de posts para Instagram", tag:"free" },
        { n:"Google Alerts", d:"Alertas de email quando uma palavra-chave (ex: 'promoção') aparece online", tag:"free" },
      ]
    },
    {
      cat: "🔍 Encontrar Promoções", items: [
        { n:"Promobit", d:"Maior agregador de promoções do Brasil — fonte diária de conteúdo", tag:"free" },
        { n:"Pelando", d:"Comunidade de achadinhos, ideal para descobrir o que está quente", tag:"free" },
        { n:"Telegram de Achadinhos", d:"Entre em grupos do Telegram de achadinhos para se inspirar", tag:"free" },
        { n:"Keepa", d:"Histórico de preços da Amazon para identificar quando é promo real", tag:"free" },
      ]
    },
  ];
  
  return (
    <div>
      <p className="section-sub">Stack completa de ferramentas — praticamente 100% gratuita</p>
      {ferramentas.map((cat, i) => (
        <div key={i} style={{marginBottom:20}}>
          <div style={{fontFamily:'Syne', fontSize:14, fontWeight:700, color:'#fff', marginBottom:10}}>{cat.cat}</div>
          <div className="grid-2">
            {cat.items.map((f, j) => (
              <div key={j} style={{background:'#111', border:'1px solid #1e1e1e', borderRadius:8, padding:14}}>
                <div style={{display:'flex', justifyContent:'space-between', alignItems:'center', marginBottom:4}}>
                  <div style={{fontFamily:'Syne', fontWeight:700, fontSize:13, color:'#fff'}}>{f.n}</div>
                  <span className={`tag tag-${f.tag}`}>{f.tag === 'free' ? 'GRÁTIS' : 'PAGO'}</span>
                </div>
                <div style={{fontSize:12, color:'#6b6050'}}>{f.d}</div>
              </div>
            ))}
          </div>
        </div>
      ))}
      
      <div className="card card-orange">
        <h3>🌟 Stack Mínima para Começar HOJE</h3>
        <div style={{display:'flex', flexWrap:'wrap', gap:6, marginTop:8}}>
          {["Instagram Business", "WhatsApp Business", "Canva (free)", "CapCut", "Linktree", "Shopee Afiliados", "Amazon Afiliados", "Mercado Livre Afiliados", "Promobit", "Pelando"].map((t, i) => (
            <span key={i} className="pill pill-orange">{t}</span>
          ))}
        </div>
        <p style={{marginTop:12}}>Com essas 10 ferramentas, você tem tudo para começar a operar hoje sem gastar nada. Adicione as demais conforme o negócio crescer.</p>
      </div>
    </div>
  );
}

export default function App() {
  const [activeTab, setActiveTab] = useState("modelo");
  
  const tabContent = {
    modelo: <ModeloTab />,
    cronograma: <CronogramaTab />,
    tutorial: <TutorialTab />,
    plataformas: <PlataformasTab />,
    custos: <CustosTab />,
    faturamento: <FaturamentoTab />,
    conteudo: <ConteudoTab />,
    ferramentas: <FerramentasTab />,
  };
  
  const current = tabs.find(t => t.id === activeTab);

  return (
    <>
      <style>{styles}</style>
      <div className="app">
        <div className="hero">
          <div className="badge">Plano de Negócios Completo</div>
          <h1>Negócio de <span>Achadinhos</span><br/>do Zero ao Faturamento</h1>
          <p>Guia completo para montar seu canal de promoções no Instagram, TikTok e WhatsApp — com afiliados, cronograma, custos e projeção de faturamento.</p>
          <div className="hero-stats">
            <div className="stat"><div className="stat-value">R$0</div><div className="stat-label">Para começar</div></div>
            <div className="stat"><div className="stat-value">90 dias</div><div className="stat-label">Para resultados</div></div>
            <div className="stat"><div className="stat-value">R$4k+</div><div className="stat-label">Potencial mês 6</div></div>
            <div className="stat"><div className="stat-value">4 plataformas</div><div className="stat-label">De afiliados</div></div>
          </div>
        </div>
        
        <div className="nav">
          {tabs.map(t => (
            <button key={t.id} className={`nav-btn ${activeTab === t.id ? 'active' : ''}`} onClick={() => setActiveTab(t.id)}>
              {t.label}
            </button>
          ))}
        </div>
        
        <div className="content">
          <div className="section-title">{current?.title}</div>
          {tabContent[activeTab]}
        </div>
      </div>
    </>
  );
}
