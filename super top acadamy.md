<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Super Top Academy | Academic · Cadet · Spoken English</title>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&family=Playfair+Display:ital,wght@0,600;0,700;0,800;0,900;1,700&display=swap" rel="stylesheet">
<style>
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box}
html{scroll-behavior:smooth}
body{font-family:'Inter',sans-serif;background:#0a0a0a;color:#e8e8e8;overflow-x:hidden}
img{display:block;max-width:100%}
a{text-decoration:none;color:inherit}
::-webkit-scrollbar{width:5px}
::-webkit-scrollbar-track{background:#0a0a0a}
::-webkit-scrollbar-thumb{background:#333;border-radius:3px}
:root{--bg:#0a0a0a;--bg2:#111;--bg3:#181818;--white:#fff;--gray:#999;--light:#ccc;--accent:#c8a45a;--accent2:#e0be78;--dark-accent:#8a6d2b;--card-bg:rgba(255,255,255,.03);--border:rgba(255,255,255,.06);--radius:16px;--shadow:0 20px 60px rgba(0,0,0,.5)}

/* DUST */
#dust-canvas{position:fixed;top:0;left:0;width:100%;height:100%;z-index:0;pointer-events:none}
nav,section,div.ticker,div.nums,footer,#stt,#fb-float{position:relative;z-index:1}

.wrap{max-width:1200px;margin:0 auto;padding:0 48px}
.sec{padding:120px 0}
.tag{display:inline-flex;align-items:center;gap:8px;font-size:.65rem;font-weight:700;letter-spacing:3px;text-transform:uppercase;color:var(--accent);margin-bottom:16px}
.tag::before{content:'';width:24px;height:1.5px;background:var(--accent)}
.sec-title{font-family:'Playfair Display',serif;font-size:clamp(2rem,4vw,3.2rem);font-weight:800;line-height:1.12;margin-bottom:16px;color:var(--white)}
.sec-title em{color:var(--accent);font-style:italic}
.sec-desc{font-size:.95rem;color:var(--gray);line-height:1.85;max-width:540px;font-weight:300}
.btn-primary{display:inline-flex;align-items:center;gap:8px;background:var(--accent);color:#0a0a0a;font-size:.82rem;font-weight:700;padding:14px 28px;border-radius:10px;border:none;cursor:pointer;transition:all .3s ease;letter-spacing:.3px}
.btn-primary:hover{background:var(--accent2);transform:translateY(-2px);box-shadow:0 8px 30px rgba(200,164,90,.25)}
.btn-outline{display:inline-flex;align-items:center;gap:8px;background:transparent;color:var(--white);font-size:.82rem;font-weight:600;padding:14px 28px;border-radius:10px;border:1px solid rgba(255,255,255,.15);cursor:pointer;transition:all .3s ease}
.btn-outline:hover{border-color:var(--accent);color:var(--accent);transform:translateY(-2px)}
.rv{opacity:0;transform:translateY(40px);transition:opacity .8s ease,transform .8s ease}
.rv.show{opacity:1;transform:none}
.rv-left{opacity:0;transform:translateX(-40px);transition:opacity .8s ease,transform .8s ease}
.rv-left.show{opacity:1;transform:none}
.rv-right{opacity:0;transform:translateX(40px);transition:opacity .8s ease,transform .8s ease}
.rv-right.show{opacity:1;transform:none}
.rv-scale{opacity:0;transform:scale(.92);transition:opacity .8s ease,transform .8s ease}
.rv-scale.show{opacity:1;transform:none}

/* NAV */
#nav{position:fixed;top:0;width:100%;z-index:1000;padding:0 48px;height:72px;display:flex;align-items:center;justify-content:space-between;background:transparent;transition:all .4s ease}
#nav.scrolled{background:rgba(10,10,10,.95);backdrop-filter:blur(20px);border-bottom:1px solid var(--border);height:64px}
.nav-brand{display:flex;align-items:center;gap:12px}
.nav-logo{width:40px;height:40px;border-radius:50%;object-fit:cover;border:2px solid var(--accent);transition:transform .3s;flex-shrink:0}
.nav-brand:hover .nav-logo{transform:scale(1.08)}
.nav-name{font-family:'Playfair Display',serif;font-size:.95rem;font-weight:700;color:var(--white)}
.nav-sub{font-size:.52rem;color:var(--accent);letter-spacing:2px;text-transform:uppercase;font-weight:600}
.nav-links{display:flex;align-items:center;gap:4px}
.nl{font-size:.76rem;font-weight:500;color:rgba(255,255,255,.5);padding:8px 14px;border-radius:8px;transition:all .25s}
.nl:hover,.nl.active{color:var(--white);background:rgba(255,255,255,.06)}
.nav-cta{margin-left:12px;font-size:.74rem;font-weight:700;padding:10px 20px;background:var(--accent);color:#0a0a0a;border-radius:8px;transition:all .3s}
.nav-cta:hover{background:var(--accent2);transform:translateY(-1px)}
.burger{display:none;flex-direction:column;gap:5px;cursor:pointer;padding:8px}
.burger span{display:block;width:22px;height:1.5px;background:var(--white);border-radius:1px;transition:.3s}

/* FACEBOOK FLOAT */
#fb-float{position:fixed;bottom:80px;right:24px;z-index:900;display:flex;align-items:center;gap:0;cursor:pointer}
#fb-float-btn{width:52px;height:52px;border-radius:14px;background:#1877f2;display:flex;align-items:center;justify-content:center;box-shadow:0 6px 24px rgba(24,119,242,.45);transition:all .3s;text-decoration:none;flex-shrink:0}
#fb-float-btn:hover{background:#1565d8;transform:translateY(-3px);box-shadow:0 10px 32px rgba(24,119,242,.6)}
#fb-float-btn svg{width:26px;height:26px;fill:#fff}
#fb-float-tip{background:rgba(10,10,10,.92);border:1px solid rgba(24,119,242,.25);color:#90bcff;font-size:.68rem;font-weight:700;padding:6px 12px;border-radius:8px;white-space:nowrap;margin-right:10px;letter-spacing:.3px;pointer-events:none;opacity:0;transform:translateX(6px);transition:all .25s}
#fb-float:hover #fb-float-tip{opacity:1;transform:translateX(0)}

/* SCROLL TOP */
#stt{position:fixed;bottom:24px;right:24px;z-index:900;width:44px;height:44px;border-radius:12px;background:var(--accent);display:flex;align-items:center;justify-content:center;font-size:1rem;color:var(--bg);font-weight:900;box-shadow:0 6px 20px rgba(200,164,90,.3);opacity:0;transform:translateY(14px);transition:opacity .3s,transform .3s;cursor:pointer;border:none}
#stt.show{opacity:1;transform:translateY(0)}
#stt:hover{background:var(--accent2);transform:translateY(-2px)}

/* HERO */
.hero{min-height:100vh;display:flex;align-items:center;position:relative;overflow:hidden;padding-top:72px}
.hero-bg{position:absolute;inset:0;z-index:0}
.hero-bg::before{content:'';position:absolute;inset:0;background:radial-gradient(ellipse at 20% 50%,rgba(200,164,90,.07) 0%,transparent 60%)}
.hero-bg::after{content:'';position:absolute;inset:0;background:linear-gradient(180deg,transparent 70%,var(--bg))}
.hero-grid{position:absolute;inset:0;background-image:linear-gradient(rgba(255,255,255,.015) 1px,transparent 1px),linear-gradient(90deg,rgba(255,255,255,.015) 1px,transparent 1px);background-size:60px 60px;animation:gridMove 40s linear infinite}
@keyframes gridMove{to{background-position:60px 60px}}
.hero-content{position:relative;z-index:2;display:grid;grid-template-columns:1fr 1fr;gap:80px;align-items:center;width:100%;max-width:1200px;margin:0 auto;padding:0 48px}
.hero-left{display:flex;flex-direction:column}
.hero-eyebrow{display:inline-flex;align-items:center;gap:8px;background:rgba(200,164,90,.08);border:1px solid rgba(200,164,90,.2);padding:6px 16px;border-radius:100px;margin-bottom:28px;width:fit-content;animation:fadeUp .8s ease .1s both}
.hero-eyebrow-dot{width:6px;height:6px;background:var(--accent);border-radius:50%;animation:pulse 2s ease-in-out infinite}
@keyframes pulse{0%,100%{opacity:1;transform:scale(1)}50%{opacity:.4;transform:scale(1.4)}}
.hero-eyebrow-text{font-size:.62rem;font-weight:700;letter-spacing:2.5px;text-transform:uppercase;color:var(--accent)}
.hero-h1{font-family:'Playfair Display',serif;font-size:clamp(2.4rem,4.5vw,4rem);font-weight:900;line-height:1.06;margin-bottom:20px;animation:fadeUp .8s ease .2s both}
.hero-h1 .gold{color:var(--accent)}
.hero-h1 .italic{font-style:italic}
.hero-desc{font-size:.95rem;color:rgba(255,255,255,.45);line-height:1.9;max-width:440px;margin-bottom:32px;font-weight:300;animation:fadeUp .8s ease .35s both}
.hero-btns{display:flex;gap:12px;flex-wrap:wrap;animation:fadeUp .8s ease .5s both}
.hero-stats{display:flex;gap:32px;margin-top:40px;animation:fadeUp .8s ease .65s both}
.hero-stat-num{font-family:'Playfair Display',serif;font-size:2.2rem;font-weight:800;color:var(--accent);line-height:1}
.hero-stat-label{font-size:.62rem;color:var(--gray);letter-spacing:1.5px;text-transform:uppercase;margin-top:4px;font-weight:500}
@keyframes fadeUp{from{opacity:0;transform:translateY(24px)}to{opacity:1;transform:translateY(0)}}
.hero-right{position:relative;animation:fadeUp .8s ease .4s both;perspective:1000px}
.hero-card{position:relative;border-radius:20px;overflow:hidden;transition:transform .6s ease;box-shadow:var(--shadow)}
.hero-card:hover{transform:rotateY(-4deg) rotateX(3deg) scale(1.02)}
.hero-card img{width:100%;height:500px;object-fit:cover;display:block}
.hero-card-overlay{position:absolute;inset:0;background:linear-gradient(to top,rgba(10,10,10,.85) 0%,transparent 50%);display:flex;align-items:flex-end;padding:28px}
.hero-card-info{color:var(--white)}
.hero-card-name{font-family:'Playfair Display',serif;font-size:1.3rem;font-weight:700}
.hero-card-role{font-size:.7rem;color:var(--accent);font-weight:600;letter-spacing:1px;text-transform:uppercase;margin-top:4px}
.hero-float-badge{position:absolute;top:20px;right:20px;background:rgba(10,10,10,.85);backdrop-filter:blur(16px);border:1px solid var(--border);border-radius:12px;padding:14px 18px;text-align:center;animation:floatBadge 4s ease-in-out infinite}
@keyframes floatBadge{0%,100%{transform:translateY(0)}50%{transform:translateY(-8px)}}
.hero-float-num{font-family:'Playfair Display',serif;font-size:1.8rem;font-weight:800;color:var(--accent);line-height:1}
.hero-float-lbl{font-size:.55rem;color:var(--gray);letter-spacing:1.5px;text-transform:uppercase;margin-top:2px}

/* TICKER */
.ticker{background:var(--accent);padding:12px 0;overflow:hidden}
.tick-track{display:flex;width:max-content;animation:tickScroll 30s linear infinite}
@keyframes tickScroll{from{transform:translateX(0)}to{transform:translateX(-50%)}}
.ti{display:inline-flex;align-items:center;font-size:.68rem;font-weight:800;letter-spacing:2px;text-transform:uppercase;color:var(--bg);padding:0 28px;white-space:nowrap}
.ti::after{content:'\2666';font-size:.35rem;opacity:.3;margin-left:10px}

/* ABOUT */
.about-sec{background:var(--bg)}
.about-grid{display:grid;grid-template-columns:1fr 1.1fr;gap:80px;align-items:center}
.about-img-wrap{position:relative;perspective:800px}
.about-img{width:100%;border-radius:var(--radius);box-shadow:var(--shadow);transition:transform .5s ease;transform-style:preserve-3d;display:block}
.about-img-wrap:hover .about-img{transform:rotateY(3deg) rotateX(-2deg)}
.about-img-frame{position:absolute;inset:-12px;border:1px solid rgba(200,164,90,.15);border-radius:calc(var(--radius)+6px);pointer-events:none}
.about-badge{position:absolute;bottom:-16px;left:50%;transform:translateX(-50%);background:var(--accent);color:var(--bg);font-size:.72rem;font-weight:800;padding:10px 24px;border-radius:10px;white-space:nowrap;box-shadow:0 8px 24px rgba(200,164,90,.25)}
.about-name{font-family:'Playfair Display',serif;font-size:1.8rem;font-weight:800;margin-bottom:6px;color:var(--white)}
.about-role{font-size:.65rem;font-weight:700;letter-spacing:2px;text-transform:uppercase;color:var(--accent);margin-bottom:20px}
.about-text{font-size:.9rem;color:var(--gray);line-height:1.95;margin-bottom:28px;font-weight:300}
.about-stats{display:grid;grid-template-columns:repeat(3,1fr);gap:14px}
.about-stat{background:var(--card-bg);border:1px solid var(--border);border-radius:12px;padding:20px 16px;text-align:center;transition:all .35s}
.about-stat:hover{background:rgba(200,164,90,.06);border-color:rgba(200,164,90,.2);transform:translateY(-4px)}
.about-stat-n{font-family:'Playfair Display',serif;font-size:2rem;font-weight:800;color:var(--accent);line-height:1}
.about-stat-l{font-size:.58rem;color:var(--gray);letter-spacing:1.5px;text-transform:uppercase;margin-top:5px;font-weight:500}
.fb-cta{display:inline-flex;align-items:center;gap:10px;background:#1877f2;color:#fff;font-size:.8rem;font-weight:700;padding:13px 24px;border-radius:10px;margin-top:22px;transition:all .3s;border:none;cursor:pointer;text-decoration:none}
.fb-cta:hover{background:#1565d8;transform:translateY(-2px);box-shadow:0 8px 28px rgba(24,119,242,.4)}
.fb-cta svg{width:18px;height:18px;fill:#fff;flex-shrink:0}

/* NUMBERS */
.nums{background:var(--bg2);border-top:1px solid var(--border);border-bottom:1px solid var(--border);padding:10px 0}
.nums-grid{display:grid;grid-template-columns:repeat(4,1fr);max-width:1200px;margin:0 auto;padding:0 48px}
.num-item{padding:44px 0;text-align:center;border-right:1px solid var(--border);position:relative}
.num-item:last-child{border-right:none}
.num-item::after{content:'';position:absolute;bottom:0;left:50%;transform:translateX(-50%);width:30px;height:1.5px;background:linear-gradient(90deg,transparent,var(--accent),transparent)}
.num-val{font-family:'Playfair Display',serif;font-size:3rem;font-weight:900;color:var(--accent);line-height:1}
.num-lbl{font-size:.62rem;color:var(--gray);letter-spacing:2px;text-transform:uppercase;margin-top:6px;font-weight:500}

/* PROGRAMS */
.programs-sec{background:var(--bg)}
.programs-head{text-align:center;margin-bottom:60px}
.programs-head .sec-desc{margin:0 auto}
.pgrid{display:grid;grid-template-columns:repeat(4,1fr);gap:18px}
.pcard{background:var(--card-bg);border:1px solid var(--border);border-radius:var(--radius);padding:34px 24px;position:relative;overflow:hidden;transition:all .4s ease}
.pcard::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,var(--accent),var(--accent2));transform:scaleX(0);transform-origin:left;transition:transform .5s ease}
.pcard:hover{transform:translateY(-8px);box-shadow:0 24px 60px rgba(0,0,0,.4);border-color:rgba(200,164,90,.15);background:rgba(200,164,90,.03)}
.pcard:hover::before{transform:scaleX(1)}
.pcard-num{position:absolute;top:18px;right:18px;font-family:'Playfair Display',serif;font-size:4rem;font-weight:800;color:rgba(255,255,255,.02);line-height:1}
.pcard-icon{width:52px;height:52px;border-radius:13px;background:rgba(200,164,90,.08);border:1px solid rgba(200,164,90,.15);display:flex;align-items:center;justify-content:center;font-size:1.3rem;margin-bottom:20px;transition:all .35s}
.pcard:hover .pcard-icon{background:var(--accent);border-color:transparent;box-shadow:0 6px 20px rgba(200,164,90,.3)}
.pcard-title{font-family:'Playfair Display',serif;font-size:1.1rem;font-weight:700;margin-bottom:10px;color:var(--white)}
.pcard-desc{font-size:.78rem;color:var(--gray);line-height:1.75;font-weight:300}
.pcard-list{list-style:none;display:flex;flex-direction:column;gap:7px;margin-top:16px}
.pcard-list li{font-size:.74rem;color:var(--gray);display:flex;align-items:center;gap:8px}
.pcard-list li::before{content:'\2713';color:var(--accent);font-weight:800;font-size:.7rem}

/* GALLERY */
.gallery-sec{background:linear-gradient(180deg,var(--bg2),var(--bg))}
.gallery-head{display:flex;justify-content:space-between;align-items:flex-end;margin-bottom:48px;gap:24px}
.ggrid{display:grid;grid-template-columns:1.4fr 1fr 1fr;grid-template-rows:280px 280px;gap:14px}
.gc{border-radius:var(--radius);overflow:hidden;position:relative;background:var(--bg3);transition:all .4s ease}
.gc:hover{transform:scale(1.02);box-shadow:0 24px 60px rgba(0,0,0,.5)}
.gc.tall{grid-row:span 2}
.gc img{width:100%;height:100%;object-fit:cover;display:block;transition:transform .6s ease}
.gc:hover img{transform:scale(1.06)}
.gc-overlay{position:absolute;inset:0;background:linear-gradient(to top,rgba(10,10,10,.9) 0%,transparent 50%);opacity:0;transition:opacity .35s;display:flex;align-items:flex-end;padding:18px}
.gc:hover .gc-overlay{opacity:1}
.gc-caption{font-size:.76rem;font-weight:600;color:var(--white);letter-spacing:.3px}
.gallery-strip{margin-top:20px;background:var(--card-bg);border:1px solid var(--border);border-radius:var(--radius);padding:22px 28px;display:flex;align-items:center;justify-content:space-between;gap:20px}
.gallery-strip-text{font-size:.85rem;color:var(--gray);line-height:1.7;font-weight:300}
.gallery-strip-text strong{color:var(--accent)}

/* ACHIEVEMENTS */
.achieve-sec{background:var(--bg)}
.achieve-grid{display:grid;grid-template-columns:1fr 1fr;gap:60px;align-items:center}
.achieve-img-wrap{position:relative;perspective:800px}
.achieve-img{width:100%;border-radius:var(--radius);box-shadow:var(--shadow);transition:transform .5s ease;display:block}
.achieve-img-wrap:hover .achieve-img{transform:rotateY(-3deg) rotateX(2deg)}
.achieve-list{display:flex;flex-direction:column;gap:18px;margin-top:28px}
.achieve-item{display:flex;align-items:flex-start;gap:16px;background:var(--card-bg);border:1px solid var(--border);border-radius:12px;padding:20px;transition:all .35s}
.achieve-item:hover{border-color:rgba(200,164,90,.2);transform:translateX(6px);background:rgba(200,164,90,.03)}
.achieve-icon{width:42px;height:42px;border-radius:10px;background:rgba(200,164,90,.1);border:1px solid rgba(200,164,90,.15);display:flex;align-items:center;justify-content:center;font-size:1.1rem;flex-shrink:0}
.achieve-title{font-size:.88rem;font-weight:700;color:var(--white);margin-bottom:4px}
.achieve-desc{font-size:.76rem;color:var(--gray);line-height:1.65;font-weight:300}

/* CLASSROOM */
.classroom-sec{background:linear-gradient(180deg,var(--bg),var(--bg2))}
.classroom-grid{display:grid;grid-template-columns:1.1fr 1fr;gap:60px;align-items:center}
.classroom-img{width:100%;border-radius:var(--radius);box-shadow:var(--shadow);transition:transform .5s ease;display:block}
.classroom-img:hover{transform:scale(1.02)}
.classroom-features{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-top:28px}
.cf-card{background:var(--card-bg);border:1px solid var(--border);border-radius:12px;padding:20px;transition:all .35s}
.cf-card:hover{border-color:rgba(200,164,90,.2);transform:translateY(-4px);background:rgba(200,164,90,.03)}
.cf-icon{font-size:1.4rem;margin-bottom:10px}
.cf-title{font-size:.82rem;font-weight:700;color:var(--white);margin-bottom:4px}
.cf-desc{font-size:.7rem;color:var(--gray);line-height:1.6}

/* QUOTE */
.quote-sec{background:var(--bg);position:relative;overflow:hidden}
.quote-sec::before{content:'';position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);width:600px;height:600px;border-radius:50%;background:radial-gradient(circle,rgba(200,164,90,.04),transparent 70%)}
.quote-inner{text-align:center;max-width:680px;margin:0 auto;position:relative;z-index:1}
.quote-mark{font-family:'Playfair Display',serif;font-size:6rem;color:rgba(200,164,90,.15);line-height:1;margin-bottom:-20px}
.quote-text{font-family:'Playfair Display',serif;font-size:1.6rem;font-weight:600;font-style:italic;line-height:1.65;color:var(--light);margin-bottom:28px}
.quote-author{font-size:.78rem;font-weight:700;color:var(--accent);letter-spacing:1px;text-transform:uppercase}
.quote-role{font-size:.68rem;color:var(--gray);margin-top:4px}

/* CONTACT */
.contact-sec{background:linear-gradient(180deg,var(--bg2),var(--bg))}
.contact-grid{display:grid;grid-template-columns:1fr 1fr;gap:60px}
.contact-info-list{display:flex;flex-direction:column;gap:18px;margin-top:28px}
.ci-card{display:flex;align-items:center;gap:16px;background:var(--card-bg);border:1px solid var(--border);border-radius:12px;padding:20px;transition:all .35s;text-decoration:none}
.ci-card:hover{border-color:rgba(200,164,90,.2);transform:translateX(4px)}
.ci-card.fb-card{background:rgba(24,119,242,.05);border-color:rgba(24,119,242,.18)}
.ci-card.fb-card:hover{background:rgba(24,119,242,.1);border-color:rgba(24,119,242,.4);transform:translateX(4px)}
.ci-icon{width:44px;height:44px;border-radius:10px;background:rgba(200,164,90,.1);border:1px solid rgba(200,164,90,.15);display:flex;align-items:center;justify-content:center;font-size:1.1rem;flex-shrink:0}
.ci-icon.fb{background:rgba(24,119,242,.15);border-color:rgba(24,119,242,.3)}
.ci-label{font-size:.6rem;font-weight:700;letter-spacing:2px;text-transform:uppercase;color:var(--accent);margin-bottom:2px}
.ci-label.fb{color:#6ba3f5}
.ci-value{font-size:.85rem;color:var(--light);font-weight:400}
.ci-value.fb{color:#90bcff}
.contact-map{border-radius:var(--radius);overflow:hidden;border:1px solid var(--border);min-height:400px;background:var(--bg3)}
.contact-map iframe{width:100%;height:100%;min-height:400px;border:none;filter:grayscale(.8) contrast(1.1) brightness(.7)}

/* FOOTER */
.footer{background:var(--bg);padding:60px 0 32px;border-top:1px solid var(--border)}
.footer-top{display:grid;grid-template-columns:1.8fr 1fr 1fr 1fr;gap:40px;padding-bottom:36px;border-bottom:1px solid var(--border);margin-bottom:24px}
.footer-brand{display:flex;align-items:center;gap:10px;margin-bottom:14px}
.footer-brand img{width:34px;height:34px;border-radius:50%;object-fit:cover;border:2px solid var(--accent)}
.footer-brand-name{font-family:'Playfair Display',serif;font-size:.95rem;font-weight:700}
.footer-desc{font-size:.76rem;color:rgba(255,255,255,.3);line-height:1.85;max-width:260px}
.footer-col-title{font-size:.58rem;font-weight:700;letter-spacing:2.5px;text-transform:uppercase;color:rgba(255,255,255,.25);margin-bottom:16px}
.footer-links{list-style:none;display:flex;flex-direction:column;gap:10px}
.footer-links a{font-size:.78rem;color:rgba(255,255,255,.4);transition:color .2s}
.footer-links a:hover{color:var(--accent)}
.footer-bottom{display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:12px}
.footer-copy{font-size:.66rem;color:rgba(255,255,255,.18)}
.footer-badges{display:flex;gap:8px}
.footer-badge{font-size:.58rem;color:rgba(255,255,255,.18);border:1px solid var(--border);padding:4px 10px;border-radius:100px}

@media(max-width:1024px){.hero-content{grid-template-columns:1fr;gap:48px}.hero-right{max-width:500px}.about-grid,.achieve-grid,.classroom-grid,.contact-grid{grid-template-columns:1fr;gap:48px}.pgrid{grid-template-columns:repeat(2,1fr)}.ggrid{grid-template-columns:1fr 1fr;grid-template-rows:auto}.gc.tall{grid-row:span 1}.footer-top{grid-template-columns:1fr 1fr;gap:28px}}
@media(max-width:768px){#nav{padding:0 20px}.nav-links{display:none;position:absolute;top:64px;left:0;right:0;background:rgba(10,10,10,.97);backdrop-filter:blur(20px);flex-direction:column;padding:20px;gap:6px;border-bottom:1px solid var(--border)}.nav-links.open{display:flex}.burger{display:flex}.wrap{padding:0 24px}.hero-content{padding:0 24px}.sec{padding:80px 0}.hero-stats{flex-wrap:wrap;gap:20px}.pgrid{grid-template-columns:1fr}.ggrid{grid-template-columns:1fr}.gc{height:220px}.gc.tall{grid-row:span 1;height:220px}.nums-grid{grid-template-columns:repeat(2,1fr)}.num-item:nth-child(2){border-right:none}.classroom-features{grid-template-columns:1fr}.footer-top{grid-template-columns:1fr}.gallery-head,.gallery-strip{flex-direction:column}.footer-bottom{flex-direction:column;text-align:center}}
</style>
</head>
<body>

<canvas id="dust-canvas"></canvas>

<!-- FACEBOOK FLOAT -->
<div id="fb-float">
  <span id="fb-float-tip">Visit our Facebook</span>
  <a id="fb-float-btn" href="https://www.facebook.com/profile.php?id=61575940540424" target="_blank" title="Facebook">
    <svg viewBox="0 0 24 24"><path d="M24 12.073C24 5.41 18.627 0 12 0S0 5.41 0 12.073C0 18.1 4.388 23.094 10.125 24v-8.437H7.078v-3.49h3.047V9.41c0-3.025 1.791-4.697 4.533-4.697 1.312 0 2.686.236 2.686.236v2.97h-1.513c-1.491 0-1.956.93-1.956 1.886v2.267h3.328l-.532 3.49h-2.796V24C19.612 23.094 24 18.1 24 12.073z"/></svg>
  </a>
</div>

<button id="stt" onclick="window.scrollTo({top:0,behavior:'smooth'})">↑</button>

<nav id="nav">
  <a href="#home" class="nav-brand">
    <img src="https://wassimustofa-glitch.github.io/super-top-academy/FB_IMG_1775901133064.jpg" alt="Logo" class="nav-logo">
    <div><div class="nav-name">Super Top Academy</div><div class="nav-sub">Academic · Cadet · Spoken</div></div>
  </a>
  <div class="nav-links" id="nav-links">
    <a href="#home" class="nl active">Home</a>
    <a href="#about" class="nl">About</a>
    <a href="#programs" class="nl">Programs</a>
    <a href="#gallery" class="nl">Gallery</a>
    <a href="#achievements" class="nl">Achievements</a>
    <a href="#contact" class="nl">Contact</a>
  </div>
  <a href="#contact" class="nav-cta">Enroll Now</a>
  <div class="burger" id="burger"><span></span><span></span><span></span></div>
</nav>

<section class="hero" id="home">
  <div class="hero-bg"><div class="hero-grid"></div></div>
  <div class="hero-content">
    <div class="hero-left">
      <div class="hero-eyebrow"><div class="hero-eyebrow-dot"></div><span class="hero-eyebrow-text">Now Enrolling — Limited Seats</span></div>
      <h1 class="hero-h1">Building <span class="gold">Future</span> Leaders Through <span class="italic">Excellence</span></h1>
      <p class="hero-desc">Super Top Academy provides world-class Academic coaching, rigorous Cadet College preparation, and professional Spoken English training in Dhaka, Bangladesh.</p>
      <div class="hero-btns">
        <a href="#programs" class="btn-primary">Explore Programs →</a>
        <a href="#about" class="btn-outline">Meet Our Founder</a>
      </div>
      <div class="hero-stats">
        <div><div class="hero-stat-num" data-target="500">500+</div><div class="hero-stat-label">Students Taught</div></div>
        <div><div class="hero-stat-num" data-target="10">10+</div><div class="hero-stat-label">Years Experience</div></div>
        <div><div class="hero-stat-num" data-target="99">99+</div><div class="hero-stat-label">Success Rate %</div></div>
      </div>
    </div>
    <div class="hero-right">
      <div class="hero-card">
        <img src="https://wassimustofa-glitch.github.io/super-top-academy/IMG-20260409-WA0000.jpg" alt="Founder">
        <div class="hero-card-overlay"><div class="hero-card-info"><div class="hero-card-name">Rakibuzzaman</div><div class="hero-card-role">Founding Director</div></div></div>
      </div>
      <div class="hero-float-badge"><div class="hero-float-num">500+</div><div class="hero-float-lbl">Students Taught</div></div>
    </div>
  </div>
</section>

<div class="ticker"><div class="tick-track" id="ticker"></div></div>

<div class="nums rv">
  <div class="nums-grid">
    <div class="num-item"><span class="num-val" data-target="500">0</span><div class="num-lbl">Students Taught</div></div>
    <div class="num-item"><span class="num-val" data-target="4">0</span><div class="num-lbl">Core Programs</div></div>
    <div class="num-item"><span class="num-val" data-target="10">0</span><div class="num-lbl">Years Experience</div></div>
    <div class="num-item"><span class="num-val" data-target="99">0</span><div class="num-lbl">Success Rate %</div></div>
  </div>
</div>

<section class="about-sec sec" id="about">
  <div class="wrap">
    <div class="about-grid">
      <div class="about-img-wrap rv-left">
        <div class="about-img-frame"></div>
        <img src="https://wassimustofa-glitch.github.io/super-top-academy/FB_IMG_1775994265124.jpg" alt="Founder" class="about-img">
        <div class="about-badge">Founding Director</div>
      </div>
      <div class="rv-right">
        <div class="tag">Meet Our Founder</div>
        <div class="about-name">Rakibuzzaman</div>
        <div class="about-role">Founding Director · Lead Educator</div>
        <p class="about-text">With over a decade of dedicated teaching experience, Rakibuzzaman founded Super Top Academy with a singular vision: to empower students with the knowledge, discipline, and confidence they need to excel.</p>
        <p class="about-text">From Grammar mastery to Cadet College admissions, every program is designed with care and a deep understanding of what students truly need to succeed in today's competitive world.</p>
        <div class="about-stats">
          <div class="about-stat"><div class="about-stat-n">500+</div><div class="about-stat-l">Students</div></div>
          <div class="about-stat"><div class="about-stat-n">10+</div><div class="about-stat-l">Years Exp.</div></div>
          <div class="about-stat"><div class="about-stat-n">99%</div><div class="about-stat-l">Success</div></div>
        </div>
        <a href="https://www.facebook.com/profile.php?id=61575940540424" target="_blank" class="fb-cta">
          <svg viewBox="0 0 24 24"><path d="M24 12.073C24 5.41 18.627 0 12 0S0 5.41 0 12.073C0 18.1 4.388 23.094 10.125 24v-8.437H7.078v-3.49h3.047V9.41c0-3.025 1.791-4.697 4.533-4.697 1.312 0 2.686.236 2.686.236v2.97h-1.513c-1.491 0-1.956.93-1.956 1.886v2.267h3.328l-.532 3.49h-2.796V24C19.612 23.094 24 18.1 24 12.073z"/></svg>
          Follow us on Facebook
        </a>
      </div>
    </div>
  </div>
</section>

<section class="programs-sec sec" id="programs">
  <div class="wrap">
    <div class="programs-head rv">
      <div class="tag" style="justify-content:center">What We Teach</div>
      <h2 class="sec-title" style="text-align:center">Programs Designed for <em>Excellence</em></h2>
      <p class="sec-desc" style="text-align:center">Comprehensive coaching that builds strong foundations and prepares students for every academic challenge ahead.</p>
    </div>
    <div class="pgrid">
      <div class="pcard rv"><div class="pcard-num">01</div><div class="pcard-icon"><span>📖</span></div><div class="pcard-title">English Grammar Mastery</div><p class="pcard-desc">From basic parts of speech to advanced syntax — we simplify English Grammar for every learner.</p><ul class="pcard-list"><li>Foundation to Advanced Grammar</li><li>Reading Comprehension</li><li>Essay &amp; Paragraph Writing</li><li>SSC &amp; HSC English Prep</li></ul></div>
      <div class="pcard rv"><div class="pcard-num">02</div><div class="pcard-icon"><span>🎖️</span></div><div class="pcard-title">Cadet Test Excellence</div><p class="pcard-desc">Intensive preparation giving students the edge to ace Cadet College admissions.</p><ul class="pcard-list"><li>Admission Test Drills</li><li>English &amp; Math Intensive</li><li>General Knowledge</li><li>Full Mock Examinations</li></ul></div>
      <div class="pcard rv"><div class="pcard-num">03</div><div class="pcard-icon"><span>🗣️</span></div><div class="pcard-title">Spoken English Fluency</div><p class="pcard-desc">Build real confidence and genuine fluency through our conversation-first approach.</p><ul class="pcard-list"><li>Conversational Practice</li><li>Pronunciation &amp; Fluency</li><li>Vocabulary Building</li><li>Public Speaking Basics</li></ul></div>
      <div class="pcard rv"><div class="pcard-num">04</div><div class="pcard-icon"><span>🔢</span></div><div class="pcard-title">General Academy</div><p class="pcard-desc">Physics, Chemistry, Mathematics, Bangla, and customised tutoring for all levels.</p><ul class="pcard-list"><li>Science &amp; Mathematics</li><li>Bangla Language</li><li>Personalised Tutoring</li><li>Board Exam Strategy</li></ul></div>
    </div>
  </div>
</section>

<section class="gallery-sec sec" id="gallery">
  <div class="wrap">
    <div class="gallery-head rv">
      <div><div class="tag">Gallery</div><h2 class="sec-title">Life at <em>Super Top Academy</em></h2></div>
      <p class="sec-desc" style="max-width:320px">Real moments — awards, achievements, competitions, and community.</p>
    </div>
    <div class="ggrid">
      <div class="gc tall rv-scale"><img src="https://wassimustofa-glitch.github.io/super-top-academy/FB_IMG_1775994416822.jpg" alt="Award Celebration"><div class="gc-overlay"><div class="gc-caption">Annual Award Celebration</div></div></div>
      <div class="gc rv-scale"><img src="https://wassimustofa-glitch.github.io/super-top-academy/FB_IMG_1775901151410.jpg" alt="Award ceremony"><div class="gc-overlay"><div class="gc-caption">Student Recognition Ceremony</div></div></div>
      <div class="gc rv-scale"><img src="https://wassimustofa-glitch.github.io/super-top-academy/FB_IMG_1775994376661.jpg" alt="Speech competition"><div class="gc-overlay"><div class="gc-caption">English Speech &amp; Debate Competition</div></div></div>
      <div class="gc rv-scale"><img src="https://wassimustofa-glitch.github.io/super-top-academy/FB_IMG_1775994332126.jpg" alt="Classroom"><div class="gc-overlay"><div class="gc-caption">Focused Learning Environment</div></div></div>
      <div class="gc rv-scale"><img src="https://wassimustofa-glitch.github.io/super-top-academy/FB_IMG_1775994409612.jpg" alt="Trophies"><div class="gc-overlay"><div class="gc-caption">Awards &amp; Trophies Collection</div></div></div>
    </div>
    <div class="gallery-strip rv">
      <div class="gallery-strip-text"><strong>Super Top Academy</strong> believes in celebrating every milestone. From monthly competitions to annual awards, we recognize the hard work and dedication of every student.</div>
      <a href="#contact" class="btn-primary" style="white-space:nowrap">Join Us →</a>
    </div>
  </div>
</section>

<section class="achieve-sec sec" id="achievements">
  <div class="wrap">
    <div class="achieve-grid">
      <div class="rv-left">
        <div class="tag">Achievements</div>
        <h2 class="sec-title">A Legacy of <em>Success</em></h2>
        <p class="sec-desc">Our students consistently outperform expectations, securing top positions in examinations and competitions across Bangladesh.</p>
        <div class="achieve-list">
          <div class="achieve-item"><div class="achieve-icon">🏆</div><div><div class="achieve-title">Monthly Speech &amp; Debate Competitions</div><div class="achieve-desc">Regular English speech and debate events building confidence, critical thinking, and public speaking skills.</div></div></div>
          <div class="achieve-item"><div class="achieve-icon">🎓</div><div><div class="achieve-title">Cadet College Admissions</div><div class="achieve-desc">Consistently producing students who secure admission to prestigious Cadet Colleges with top marks.</div></div></div>
          <div class="achieve-item"><div class="achieve-icon">⭐</div><div><div class="achieve-title">Board Exam Toppers</div><div class="achieve-desc">Our students routinely achieve GPA 5 in SSC and HSC board examinations.</div></div></div>
          <div class="achieve-item"><div class="achieve-icon">👥</div><div><div class="achieve-title">500+ Students &amp; Growing</div><div class="achieve-desc">A growing community of learners and alumni who carry Super Top Academy's values into their futures.</div></div></div>
        </div>
      </div>
      <div class="achieve-img-wrap rv-right">
        <img src="https://wassimustofa-glitch.github.io/super-top-academy/FB_IMG_1775901168391.jpg" alt="Students with trophies" class="achieve-img">
      </div>
    </div>
  </div>
</section>

<section class="classroom-sec sec" id="classroom">
  <div class="wrap">
    <div class="classroom-grid">
      <div class="rv-left"><img src="https://wassimustofa-glitch.github.io/super-top-academy/FB_IMG_1775994332126.jpg" alt="Classroom" class="classroom-img"></div>
      <div class="rv-right">
        <div class="tag">Our Environment</div>
        <h2 class="sec-title">Where Learning <em>Comes Alive</em></h2>
        <p class="sec-desc">Our classrooms are designed to foster focus, collaboration, and intellectual growth. Every session is structured for maximum engagement and real results.</p>
        <div class="classroom-features">
          <div class="cf-card"><div class="cf-icon">📚</div><div class="cf-title">Small Batch Sizes</div><div class="cf-desc">Personalised attention with limited students per batch.</div></div>
          <div class="cf-card"><div class="cf-icon">💻</div><div class="cf-title">Modern Resources</div><div class="cf-desc">Updated study materials, digital aids, and practice sets.</div></div>
          <div class="cf-card"><div class="cf-icon">📈</div><div class="cf-title">Progress Tracking</div><div class="cf-desc">Regular assessments and performance reports for parents.</div></div>
          <div class="cf-card"><div class="cf-icon">💪</div><div class="cf-title">Discipline &amp; Values</div><div class="cf-desc">Building character alongside academics for well-rounded development.</div></div>
        </div>
      </div>
    </div>
  </div>
</section>

<section class="quote-sec sec">
  <div class="wrap">
    <div class="quote-inner rv-scale">
      <div class="quote-mark">"</div>
      <p class="quote-text">Education is the most powerful weapon which you can use to change the world. At Super Top Academy, we don't just teach subjects — we build futures.</p>
      <div class="quote-author">Rakibuzzaman</div>
      <div class="quote-role">Founding Director, Super Top Academy</div>
    </div>
  </div>
</section>

<section class="contact-sec sec" id="contact">
  <div class="wrap">
    <div class="contact-grid">
      <div class="rv-left">
        <div class="tag">Get In Touch</div>
        <h2 class="sec-title">Begin Your <em>Journey</em></h2>
        <p class="sec-desc">Ready to take the first step? Reach out to us today and discover how Super Top Academy can shape your future.</p>
        <div class="contact-info-list">
          <div class="ci-card"><div class="ci-icon">📍</div><div><div class="ci-label">Location</div><div class="ci-value">491 North Shahjahanpur, Dhaka, Bangladesh</div></div></div>
          <a href="https://www.facebook.com/profile.php?id=61575940540424" target="_blank" class="ci-card fb-card">
            <div class="ci-icon fb"><svg width="20" height="20" viewBox="0 0 24 24" fill="#6ba3f5"><path d="M24 12.073C24 5.41 18.627 0 12 0S0 5.41 0 12.073C0 18.1 4.388 23.094 10.125 24v-8.437H7.078v-3.49h3.047V9.41c0-3.025 1.791-4.697 4.533-4.697 1.312 0 2.686.236 2.686.236v2.97h-1.513c-1.491 0-1.956.93-1.956 1.886v2.267h3.328l-.532 3.49h-2.796V24C19.612 23.094 24 18.1 24 12.073z"/></svg></div>
            <div><div class="ci-label fb">Facebook</div><div class="ci-value fb">Visit our Facebook Page →</div></div>
          </a>
          <div class="ci-card"><div class="ci-icon">📅</div><div><div class="ci-label">Operating Hours</div><div class="ci-value">Saturday – Thursday, 8:00 AM – 8:00 PM</div></div></div>
          <div class="ci-card"><div class="ci-icon">🌐</div><div><div class="ci-label">Programs</div><div class="ci-value">Academic · Cadet Prep · Spoken English · Admission</div></div></div>
        </div>
      </div>
      <div class="contact-map rv-right">
        <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3652.3!2d90.42!3d23.73!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x0!2zMjPCsDQzJzQ4LjAiTiA5MMKwMjUnMTIuMCJF!5e0!3m2!1sen!2sbd!4v1" loading="lazy"></iframe>
      </div>
    </div>
  </div>
</section>

<footer class="footer">
  <div class="wrap">
    <div class="footer-top">
      <div>
        <div class="footer-brand"><img src="https://wassimustofa-glitch.github.io/super-top-academy/FB_IMG_1775901133064.jpg" alt="Logo"><span class="footer-brand-name">Super Top Academy</span></div>
        <p class="footer-desc">Empowering students with world-class Academic coaching, Cadet College preparation, and Spoken English training since 2016.</p>
      </div>
      <div><div class="footer-col-title">Quick Links</div><ul class="footer-links"><li><a href="#home">Home</a></li><li><a href="#about">About</a></li><li><a href="#programs">Programs</a></li><li><a href="#gallery">Gallery</a></li></ul></div>
      <div><div class="footer-col-title">Programs</div><ul class="footer-links"><li><a href="#programs">English Grammar</a></li><li><a href="#programs">Cadet Prep</a></li><li><a href="#programs">Spoken English</a></li><li><a href="#programs">General Academy</a></li></ul></div>
      <div><div class="footer-col-title">Connect</div><ul class="footer-links"><li><a href="#contact">Contact Us</a></li><li><a href="https://www.facebook.com/profile.php?id=61575940540424" target="_blank">Facebook Page</a></li><li><a href="https://www.google.com/maps/search/491+North+Shahjahanpur+Dhaka+Bangladesh" target="_blank">Google Maps</a></li><li><a href="#contact">Enroll Now</a></li></ul></div>
    </div>
    <div class="footer-bottom">
      <div class="footer-copy">© 2026 Super Top Academy. All rights reserved.</div>
      <div class="footer-badges"><span class="footer-badge">Dhaka, BD</span><span class="footer-badge">Est. 2016</span><span class="footer-badge">500+ Students</span></div>
    </div>
  </div>
</footer>

<script>
/* ══ DUST ANIMATION ══ */
(function(){
  var c=document.getElementById('dust-canvas'),ctx=c.getContext('2d'),W,H,pts=[],mouse={x:-999,y:-999};
  function resize(){W=c.width=window.innerWidth;H=c.height=window.innerHeight;}
  resize();window.addEventListener('resize',resize);
  window.addEventListener('mousemove',function(e){mouse.x=e.clientX;mouse.y=e.clientY;});
  function r(a,b){return Math.random()*(b-a)+a;}
  function P(){this.reset(true);}
  P.prototype.reset=function(spread){
    this.x=r(0,W);this.y=spread?r(0,H):H+r(0,20);
    this.rad=r(0.5,2.4);this.vx=r(-0.25,0.25);this.vy=r(-0.7,-0.12);
    this.base=r(0.08,0.42);this.life=0;this.max=r(200,700);
    this.gold=Math.random()<0.6;this.tw=Math.random()<0.35;
    this.ts=r(0.025,0.07);this.to=r(0,Math.PI*2);
  };
  P.prototype.tick=function(){
    this.life++;
    var p=this.life/this.max,env=p<0.12?p/0.12:p>0.75?(1-p)/0.25:1;
    var tw=this.tw?0.45+0.55*Math.sin(this.life*this.ts+this.to):1;
    this.a=this.base*env*tw;
    this.x+=this.vx+Math.sin(this.life*0.013+this.to)*0.2;
    this.y+=this.vy;
    var dx=mouse.x-this.x,dy=mouse.y-this.y,d=Math.sqrt(dx*dx+dy*dy);
    if(d<180){this.x+=dx*0.0015;this.y+=dy*0.0015;}
    if(this.life>=this.max||this.y<-10)this.reset(false);
  };
  P.prototype.draw=function(){
    ctx.beginPath();
    ctx.fillStyle=this.gold?'rgba(200,164,90,'+this.a.toFixed(3)+')':'rgba(255,248,220,'+(this.a*0.5).toFixed(3)+')';
    ctx.arc(this.x,this.y,this.rad,0,Math.PI*2);ctx.fill();
  };
  for(var i=0;i<240;i++){var p=new P();p.life=Math.floor(r(0,p.max));pts.push(p);}
  (function loop(){ctx.clearRect(0,0,W,H);for(var i=0;i<pts.length;i++){pts[i].tick();pts[i].draw();}requestAnimationFrame(loop);})();
})();

/* ══ NAV SCROLL ══ */
(function(){var n=document.getElementById('nav');window.addEventListener('scroll',function(){n.classList.toggle('scrolled',window.scrollY>60);});})();

/* ══ BURGER ══ */
(function(){var b=document.getElementById('burger'),l=document.getElementById('nav-links');if(!b||!l)return;b.addEventListener('click',function(){l.classList.toggle('open');});l.querySelectorAll('.nl').forEach(function(a){a.addEventListener('click',function(){l.classList.remove('open');});});})();

/* ══ ACTIVE LINK ══ */
(function(){var ss=document.querySelectorAll('section[id]'),ls=document.querySelectorAll('.nl');window.addEventListener('scroll',function(){var y=window.scrollY+120;ss.forEach(function(s){var id=s.getAttribute('id');if(y>=s.offsetTop&&y<s.offsetTop+s.offsetHeight)ls.forEach(function(l){l.classList.remove('active');if(l.getAttribute('href')==='#'+id)l.classList.add('active');});});});})();

/* ══ SCROLL TOP ══ */
(function(){var s=document.getElementById('stt');window.addEventListener('scroll',function(){s.classList.toggle('show',window.scrollY>400);});})();

/* ══ SCROLL REVEAL ══ */
(function(){var els=document.querySelectorAll('.rv,.rv-left,.rv-right,.rv-scale');var obs=new IntersectionObserver(function(entries){entries.forEach(function(e){if(e.isIntersecting){e.target.classList.add('show');obs.unobserve(e.target);}});},{threshold:.12});els.forEach(function(el){obs.observe(el);});})();

/* ══ TICKER ══ */
(function(){var t=document.getElementById('ticker');var items=['English Grammar','Cadet Prep','Spoken English','Mathematics','Science','Public Speaking','Essay Writing','Board Exams','Vocabulary','HSC Prep','SSC Prep','Admission Coaching'];var h='';for(var i=0;i<items.length;i++)h+='<span class="ti">'+items[i]+'</span>';t.innerHTML=h+h;})();

/* ══ COUNTER ══ */
(function(){var vs=document.querySelectorAll('[data-target]'),done=new Set();var obs=new IntersectionObserver(function(entries){entries.forEach(function(e){if(!e.isIntersecting||done.has(e.target))return;done.add(e.target);var el=e.target,tgt=parseInt(el.getAttribute('data-target')),cur=0,step=Math.max(1,Math.floor(tgt/50));var t=setInterval(function(){cur+=step;if(cur>=tgt){cur=tgt;clearInterval(t);}el.textContent=cur+'+';},30);});},{threshold:.3});vs.forEach(function(v){v.textContent='0';obs.observe(v);});})();

/* ══ 3D TILT ══ */
(function(){document.querySelectorAll('.hero-card,.about-img-wrap,.achieve-img-wrap').forEach(function(c){c.addEventListener('mousemove',function(e){var r=c.getBoundingClientRect(),x=(e.clientX-r.left)/r.width-.5,y=(e.clientY-r.top)/r.height-.5,img=c.querySelector('img');if(img)img.style.transform='rotateY('+x*8+'deg) rotateX('+-y*8+'deg) scale(1.02)';});c.addEventListener('mouseleave',function(){var img=c.querySelector('img');if(img)img.style.transform='';});});})();
</script>
</body>
</html>