# THREE-STAR-GYM<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Three Star Gym & Fitness | Loktantrik Chowk, Kathmandu</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Inter:wght@300;400;500;600;700;900&family=Rajdhani:wght@500;600;700&display=swap');

*{margin:0;padding:0;box-sizing:border-box}
:root{
  --black:#080808;
  --dark:#0e0e0e;
  --card:#131313;
  --gold:#c9a84c;
  --gold2:#e8c96b;
  --red:#c0392b;
  --white:#f5f5f5;
  --grey:#888;
  --border:rgba(201,168,76,0.15);
  --border2:rgba(201,168,76,0.3);
  --radius:8px;
  --blue:#3b82f6;
  --green:#22c55e;
}
html{scroll-behavior:smooth}
body{background:var(--black);color:var(--white);font-family:'Inter',sans-serif;overflow-x:hidden}

/* SCROLLBAR */
::-webkit-scrollbar{width:4px}
::-webkit-scrollbar-thumb{background:var(--gold);border-radius:2px}

/* ===== LOADER ===== */
#loader{position:fixed;inset:0;z-index:9999;background:#000;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:20px}
.loader-star{font-size:60px;animation:starSpin 1.5s ease-in-out forwards}
@keyframes starSpin{0%{transform:scale(0) rotate(-180deg);opacity:0}60%{transform:scale(1.3) rotate(10deg);opacity:1}100%{transform:scale(1) rotate(0deg);opacity:1}}
.loader-bar{width:200px;height:2px;background:rgba(255,255,255,0.1);border-radius:1px;overflow:hidden;margin-top:10px}
.loader-bar-fill{height:100%;background:linear-gradient(90deg,var(--gold),var(--gold2));width:0%;animation:barFill 2s ease forwards 0.5s;border-radius:1px}
@keyframes barFill{to{width:100%}}
.loader-text{font-family:'Bebas Neue',sans-serif;font-size:28px;letter-spacing:6px;color:var(--gold);opacity:0;animation:fadeIn 0.5s ease forwards 0.3s}
#loader.out{animation:loaderOut 0.6s ease forwards}
@keyframes loaderOut{to{opacity:0;pointer-events:none}}
@keyframes fadeIn{to{opacity:1}}

/* ===== NAV ===== */
nav{position:fixed;top:0;left:0;right:0;z-index:500;padding:0 40px;height:70px;display:flex;align-items:center;justify-content:space-between;transition:all 0.4s}
nav.scrolled{background:rgba(8,8,8,0.95);backdrop-filter:blur(20px);border-bottom:1px solid var(--border)}
.nav-logo{font-family:'Bebas Neue',sans-serif;font-size:26px;letter-spacing:3px;background:linear-gradient(135deg,var(--gold),var(--gold2));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text}
.nav-logo span{color:var(--red);-webkit-text-fill-color:var(--red)}
.nav-links{display:flex;gap:32px;list-style:none}
.nav-links a{font-size:13px;font-weight:500;letter-spacing:2px;text-transform:uppercase;color:rgba(255,255,255,0.6);text-decoration:none;transition:color 0.3s;position:relative}
.nav-links a::after{content:'';position:absolute;bottom:-4px;left:0;width:0;height:1px;background:var(--gold);transition:width 0.3s}
.nav-links a:hover{color:var(--gold)}
.nav-links a:hover::after{width:100%}
.nav-cta{padding:10px 24px;border:1px solid var(--gold);color:var(--gold);font-size:12px;font-weight:600;letter-spacing:2px;text-transform:uppercase;text-decoration:none;transition:all 0.3s;cursor:pointer;background:transparent}
.nav-cta:hover{background:var(--gold);color:#000}
.hamburger{display:none;flex-direction:column;gap:5px;cursor:pointer;padding:4px}
.hamburger span{width:24px;height:2px;background:var(--white);transition:all 0.3s;display:block}

/* ===== HERO ===== */
.hero{height:100vh;position:relative;display:flex;align-items:center;justify-content:center;overflow:hidden}
.hero-bg{position:absolute;inset:0;z-index:0;display:flex;align-items:center;justify-content:center}
.hero-gradient{position:absolute;inset:0;background:radial-gradient(ellipse 80% 60% at 50% 50%,rgba(201,168,76,0.08) 0%,transparent 70%);z-index:1}
.hero-vignette{position:absolute;inset:0;background:radial-gradient(ellipse at center,transparent 30%,rgba(0,0,0,0.9) 100%);z-index:1}
.particles{position:absolute;inset:0;overflow:hidden;z-index:2}
.particle{position:absolute;width:2px;height:2px;background:var(--gold);border-radius:50%;opacity:0;animation:particleFloat linear infinite}
@keyframes particleFloat{0%{transform:translateY(100vh) translateX(0);opacity:0}10%{opacity:0.6}90%{opacity:0.2}100%{transform:translateY(-100px) translateX(30px);opacity:0}}

.hero-content{position:relative;z-index:3;text-align:center;max-width:900px;padding:0 20px}
.hero-eyebrow{font-size:11px;letter-spacing:6px;text-transform:uppercase;color:var(--gold);margin-bottom:20px;opacity:0;animation:slideUp 0.8s ease forwards 2.8s;display:flex;align-items:center;justify-content:center;gap:16px}
.hero-eyebrow::before,.hero-eyebrow::after{content:'';width:40px;height:1px;background:var(--gold);opacity:0.5}
.hero-title{font-family:'Bebas Neue',sans-serif;font-size:clamp(60px,12vw,130px);line-height:0.9;letter-spacing:2px;opacity:0;animation:slideUp 0.9s ease forwards 3s}
.hero-title .star{color:var(--gold)}
.hero-title .outline{-webkit-text-stroke:1px rgba(255,255,255,0.3);-webkit-text-fill-color:transparent;color:transparent}
.hero-sub{font-size:clamp(13px,2vw,16px);color:rgba(255,255,255,0.5);letter-spacing:3px;text-transform:uppercase;margin-top:16px;opacity:0;animation:slideUp 0.8s ease forwards 3.2s}
.hero-divider{width:60px;height:2px;background:linear-gradient(90deg,transparent,var(--gold),transparent);margin:28px auto;opacity:0;animation:slideUp 0.8s ease forwards 3.3s}
.hero-btns{display:flex;gap:16px;justify-content:center;flex-wrap:wrap;opacity:0;animation:slideUp 0.8s ease forwards 3.4s}
.btn-primary{padding:14px 36px;background:var(--gold);color:#000;font-size:13px;font-weight:700;letter-spacing:2px;text-transform:uppercase;text-decoration:none;transition:all 0.3s;display:inline-block;border:none;cursor:pointer}
.btn-primary:hover{background:var(--gold2);transform:translateY(-2px);box-shadow:0 8px 30px rgba(201,168,76,0.4)}
.btn-ghost{padding:14px 36px;border:1px solid rgba(255,255,255,0.2);color:var(--white);font-size:13px;font-weight:600;letter-spacing:2px;text-transform:uppercase;text-decoration:none;transition:all 0.3s;display:inline-block;background:transparent;cursor:pointer}
.btn-ghost:hover{border-color:var(--gold);color:var(--gold)}

@keyframes slideUp{from{transform:translateY(30px);opacity:0}to{transform:translateY(0);opacity:1}}

/* ===== SECTIONS ===== */
section{padding:100px 40px}
.container{max-width:1200px;margin:0 auto}
.section-label{font-size:10px;letter-spacing:6px;text-transform:uppercase;color:var(--gold);margin-bottom:12px;display:flex;align-items:center;gap:12px}
.section-label::before{content:'';width:30px;height:1px;background:var(--gold)}
.section-title{font-family:'Bebas Neue',sans-serif;font-size:clamp(40px,6vw,72px);line-height:1;margin-bottom:8px}
.section-sub{color:rgba(255,255,255,0.4);font-size:15px;max-width:500px;line-height:1.7;margin-bottom:60px}

/* reveal animation */
.reveal{opacity:0;transform:translateY(40px);transition:all 0.8s cubic-bezier(0.16,1,0.3,1)}
.reveal.visible{opacity:1;transform:translateY(0)}

/* ===== INTEL LITE CSS ===== */
.intel-tabs{display:flex;gap:8px;background:var(--dark);padding:6px;border-radius:var(--radius);margin-bottom:30px;border:1px solid var(--border);flex-wrap:wrap}
.intel-tab{flex:1;min-width:140px;padding:12px;background:transparent;border:none;color:rgba(255,255,255,0.6);font-family:'Rajdhani',sans-serif;font-weight:700;font-size:14px;letter-spacing:1px;text-transform:uppercase;cursor:pointer;transition:all 0.3s;text-align:center;border-radius:4px}
.intel-tab:hover{color:var(--gold);background:rgba(201,168,76,0.05)}
.intel-tab.active{background:var(--gold);color:#000}
.intel-page{display:none}
.intel-page.active{display:block;animation:fadeIn 0.5s ease forwards}

.intel-grid{display:grid;grid-template-columns:1fr 1fr;gap:30px}
@media(max-width:768px){.intel-grid{grid-template-columns:1fr}}

.intel-card{background:var(--card);border:1px solid var(--border);padding:24px;border-radius:var(--radius);position:relative}
.intel-card-title{font-family:'Rajdhani',sans-serif;font-size:18px;font-weight:700;color:var(--gold);margin-bottom:16px;text-transform:uppercase;letter-spacing:1px;display:flex;align-items:center;gap:8px}

.intel-field{margin-bottom:16px}
.intel-label{display:block;font-size:12px;color:rgba(255,255,255,0.5);margin-bottom:6px;text-transform:uppercase;letter-spacing:1px}
.intel-input, .intel-select{width:100%;background:var(--dark);border:1px solid var(--border);padding:12px;color:#fff;font-family:'Inter',sans-serif;font-size:14px;border-radius:4px;outline:none;transition:all 0.3s}
.intel-input:focus, .intel-select:focus{border-color:var(--gold)}
.intel-input[type="range"]{padding:0;accent-color:var(--gold)}

.intel-btn{width:100%;padding:14px;background:transparent;border:1px solid var(--gold);color:var(--gold);font-family:'Rajdhani',sans-serif;font-weight:700;letter-spacing:2px;text-transform:uppercase;cursor:pointer;transition:all 0.3s}
.intel-btn:hover{background:var(--gold);color:#000}

.intel-results{background:var(--dark);border:1px solid var(--border2);border-radius:4px;padding:20px;margin-top:16px}
.intel-res-row{display:flex;justify-content:space-between;padding:10px 0;border-bottom:1px solid rgba(255,255,255,0.05)}
.intel-res-row:last-child{border-bottom:none}
.intel-res-val{font-weight:700;color:var(--gold)}

/* WATER DISP */
.glass-grid{display:flex;gap:8px;flex-wrap:wrap;margin-top:12px}
.glass{width:35px;height:45px;border:2px solid var(--blue);border-top:none;border-radius:0 0 8px 8px;position:relative;cursor:pointer;transition:all 0.2s}
.glass.filled::after{content:'';position:absolute;bottom:0;left:0;right:0;height:85%;background:var(--blue);opacity:0.7}

/* MEMBERSHIP & TRAINERS FROM SOURCE HTML */
.plans-grid, .trainers-grid, .why-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:24px}
.why-grid{grid-template-columns:repeat(4,1fr)}
@media(max-width:992px){.plans-grid, .trainers-grid{grid-template-columns:repeat(2,1fr)} .why-grid{grid-template-columns:repeat(2,1fr)}}
@media(max-width:600px){.plans-grid, .trainers-grid, .why-grid{grid-template-columns:1fr}}

.plan-card, .trainer-card, .why-card{background:var(--card);border:1px solid var(--border);padding:40px 32px;position:relative;overflow:hidden;transition:all 0.4s}
.plan-card.featured{border-color:var(--gold);background:rgba(201,168,76,0.04)}
.plan-name{font-family:'Bebas Neue',sans-serif;font-size:32px;letter-spacing:2px;margin-bottom:8px}
.plan-price{font-family:'Rajdhani',sans-serif;font-size:28px;font-weight:700;color:var(--gold)}
.plan-price span{font-size:14px;color:#fff;font-weight:400}
.plan-features{list-style:none;margin:24px 0;font-size:14px;color:rgba(255,255,255,0.6)}
.plan-features li{margin-bottom:10px}
.plan-btn{display:block;text-align:center;padding:12px;border:1px solid var(--gold);color:var(--gold);text-decoration:none;font-weight:600;font-size:13px;letter-spacing:1px;transition:all 0.3s}
.plan-btn:hover{background:var(--gold);color:#000}

.trainer-img{font-size:50px;margin-bottom:16px;text-align:center}
.trainer-name{font-family:'Bebas Neue',sans-serif;font-size:24px;letter-spacing:1px}
.trainer-role{color:var(--gold);font-size:12px;text-transform:uppercase;margin-bottom:12px;font-weight:600}
.trainer-desc{font-size:13px;color:rgba(255,255,255,0.5);line-height:1.6}

.why-card{padding:30px 20px}
.why-num{position:absolute;top:10px;right:15px;font-size:40px;font-family:'Bebas Neue',sans-serif;color:rgba(201,168,76,0.05)}
.why-icon{font-size:32px;margin-bottom:16px;display:block}
.why-title{font-family:'Rajdhani',sans-serif;font-size:20px;font-weight:700;margin-bottom:8px}
.why-text{font-size:13px;color:rgba(255,255,255,0.5);line-height:1.6}

.contact-grid{display:grid;grid-template-columns:1fr 1fr;gap:4px;margin-top:40px}
@media(max-width:768px){.contact-grid{grid-template-columns:1fr}}
.contact-info{background:var(--card);padding:40px;display:flex;flex-direction:column;gap:24px;border:1px solid var(--border)}
.contact-item{display:flex;gap:16px}
.contact-icon{font-size:24px}
.contact-label{font-size:12px;text-transform:uppercase;color:var(--gold);letter-spacing:1px}
.contact-value, .contact-value a{color:rgba(255,255,255,0.7);text-decoration:none;font-size:14px;line-height:1.6}
.map-embed iframe{width:100%;height:100%;min-height:350px;border:none}

footer{background:#040404;padding:80px 40px 20px;border-top:1px solid var(--border)}
.footer-grid{max-width:1200px;margin:0 auto;display:grid;grid-template-columns:2fr 1fr 1fr;gap:60px;padding-bottom:60px}
@media(max-width:768px){.footer-grid{grid-template-columns:1fr;gap:4px}}
.footer-logo{font-family:'Bebas Neue',sans-serif;font-size:28px;color:var(--gold);margin-bottom:16px}
.footer-desc{font-size:13px;color:rgba(255,255,255,0.5);line-height:1.7}
.footer-title{font-family:'Rajdhani',sans-serif;font-size:16px;font-weight:700;text-transform:uppercase;color:#fff;margin-bottom:20px;letter-spacing:1px}
.footer-links{list-style:none}
.footer-links li{margin-bottom:12px}
.footer-links a{color:rgba(255,255,255,0.5);text-decoration:none;font-size:13px;transition:color 0.3s}
.footer-links a:hover{color:var(--gold)}
.footer-bottom{max-width:1200px;margin:0 auto;padding-top:20px;border-top:1px solid rgba(255,255,255,0.05);display:flex;justify-content:space-between;font-size:11px;color:rgba(255,255,255,0.3)}

#btt{position:fixed;bottom:30px;right:30px;width:40px;height:40px;background:var(--gold);border:none;color:#000;font-weight:700;cursor:pointer;opacity:0;transition:0.3s;z-index:99}
#btt.visible{opacity:1}
</style>
</head>
<body>

<div id="loader">
  <div class="loader-star">★</div>
  <div class="loader-text">THREE STAR GYM</div>
  <div class="loader-bar"><div class="loader-bar-fill"></div></div>
</div>

<nav id="navbar">
  <div class="nav-logo">THREE <span>★</span> GYM</div>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#intelligence">Fitness Intelligence</a></li>
    <li><a href="#membership">Membership</a></li>
    <li><a href="#trainers">Trainers</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a href="tel:9841078384" class="nav-cta">Call Now</a>
  <div class="hamburger" id="hamburger"><span></span><span></span><span></span></div>
</nav>

<section class="hero">
  <div class="hero-bg">
    <div class="hero-gradient"></div>
    <div class="hero-vignette"></div>
    <div class="particles" id="particles"></div>
  </div>
  <div class="hero-content">
    <div class="hero-eyebrow">Premium Fitness Destination</div>
    <h1 class="hero-title">SHAPE YOUR <span class="star">DESTINY</span></h1>
    <p class="hero-sub">Loktantrik Chowk, Manamaiju, Kathmandu</p>
    <div class="hero-divider"></div>
    <div class="hero-btns">
      <a href="#intelligence" class="btn-primary">Start AI Assessment</a>
      <a href="#membership" class="btn-ghost">View Memberships</a>
    </div>
  </div>
</section>

<section id="intelligence" style="background: var(--dark);">
  <div class="container">
    <div class="reveal">
      <div class="section-label">AI Fitness Companion</div>
      <h2 class="section-title">FITNESS INTELLIGENCE PRO</h2>
      <p class="section-sub">Calculate your custom metrics, optimize macro nutrition ratios, explore meal templates, and track vital statistics in real-time.</p>
    </div>

    <div class="intel-tabs reveal">
      <button class="intel-tab active" onclick="switchIntelTab('calc')">🧮 Calculators</button>
      <button class="intel-tab" onclick="switchIntelTab('nutri')">🥗 Nutrition Plan</button>
      <button class="intel-tab" onclick="switchIntelTab('meals')">🍽️ Meal Matrix</button>
      <button class="intel-tab" onclick="switchIntelTab('work')">💪 Workout Engine</button>
      <button class="intel-tab" onclick="switchIntelTab('track')">📈 Smart Tracker</button>
    </div>

    <div id="intel-calc" class="intel-page active reveal">
      <div class="intel-grid">
        <div class="intel-card">
          <div class="intel-card-title">🔬 Body Mass & Metabolic Metrics</div>
          <div class="intel-field">
            <label class="intel-label" id="lbl-weight">Weight: 70 kg</label>
            <input type="range" class="intel-input" id="inp-weight" min="40" max="150" value="70" oninput="runCalculations()">
          </div>
          <div class="intel-field">
            <label class="intel-label" id="lbl-height">Height: 175 cm</label>
            <input type="range" class="intel-input" id="inp-height" min="130" max="210" value="175" oninput="runCalculations()">
          </div>
          <div class="intel-field">
            <label class="intel-label" id="lbl-age">Age: 25 years</label>
            <input type="range" class="intel-input" id="inp-age" min="15" max="80" value="25" oninput="runCalculations()">
          </div>
          <div class="intel-field">
            <label class="intel-label">Biological Gender</label>
            <select class="intel-select" id="inp-gender" onchange="runCalculations()">
              <option value="male">Male</option>
              <option value="female">Female</option>
            </select>
          </div>
          <div class="intel-field">
            <label class="intel-label">Weekly Activity Coefficient</label>
            <select class="intel-select" id="inp-activity" onchange="runCalculations()">
              <option value="1.2">Sedentary (Office job, minimal exercise)</option>
              <option value="1.375">Lightly Active (1-3 days gym/week)</option>
              <option value="1.55" selected>Moderately Active (3-5 days intense gym/week)</option>
              <option value="1.725">Very Active (6-7 days hard training/week)</option>
            </select>
          </div>
        </div>

        <div class="intel-card">
          <div class="intel-card-title">📈 Computed System Outputs</div>
          <div class="intel-results">
            <div class="intel-res-row">
              <span>Body Mass Index (BMI)</span>
              <span class="intel-res-val" id="res-bmi">22.9 (Normal)</span>
            </div>
            <div class="intel-res-row">
              <span>Basal Metabolic Rate (BMR)</span>
              <span class="intel-res-val" id="res-bmr">1650 kcal</span>
            </div>
            <div class="intel-res-row">
              <span>Total Daily Energy Expenditure (TDEE)</span>
              <span class="intel-res-val" id="res-tdee">2557 kcal</span>
            </div>
          </div>
          <div style="margin-top: 20px; font-size: 13px; color: rgba(255,255,255,0.4); line-height: 1.5;">
            💡 <strong>Three Star Engine Note:</strong> Use your calculated TDEE in the next tab to configure targeted muscle architecture or fat loss programs safely.
          </div>
        </div>
      </div>
    </div>

    <div id="intel-nutri" class="intel-page reveal">
      <div class="intel-grid">
        <div class="intel-card">
          <div class="intel-card-title">🎯 Set Fitness Architecture Strategy</div>
          <div class="intel-field">
            <label class="intel-label">Primary Objective Goal</label>
            <select class="intel-select" id="nutri-goal" onchange="calculateMacros()">
              <option value="fat-loss">Fat Loss Cutting (-500 kcal deficit)</option>
              <option value="maintain" selected>Maintain Energy Homeostasis (Balanced)</option>
              <option value="clean-bulk">Clean Muscle Bulk (+300 kcal surplus)</option>
            </select>
          </div>
          <div class="intel-field">
            <label class="intel-label">Macro Distribution Strategy</label>
            <select class="intel-select" id="macro-split" onchange="calculateMacros()">
              <option value="balanced" selected>Balanced Split (40% Carbs, 30% Protein, 30% Fat)</option>
              <option value="high-protein">High Protein Strength (35% Carbs, 40% Protein, 25% Fat)</option>
              <option value="low-carb">Low Carb Shredding (20% Carbs, 45% Protein, 35% Fat)</option>
            </select>
          </div>
        </div>

        <div class="intel-card">
          <div class="intel-card-title">📊 Calculated Target Macronutrient Distribution</div>
          <div class="intel-results">
            <div class="intel-res-row">
              <span>Target Daily Intake Calories</span>
              <span class="intel-res-val" id="nutri-target-cal">2557 kcal/day</span>
            </div>
            <div class="intel-res-row">
              <span>Proteins Allocation</span>
              <span class="intel-res-val" id="nutri-prot">192g (768 kcal)</span>
            </div>
            <div class="intel-res-row">
              <span>Carbohydrates Allocation</span>
              <span class="intel-res-val" id="nutri-carb">256g (1024 kcal)</span>
            </div>
            <div class="intel-res-row">
              <span>Dietary Lipids (Fats)</span>
              <span class="intel-res-val" id="nutri-fat">85g (765 kcal)</span>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div id="intel-meals" class="intel-page reveal">
      <div class="intel-card">
        <div class="intel-card-title">🍽️ Recommended Kathmandu-Friendly Performance Meal Templates</div>
        <div class="intel-grid" style="margin-top:20px;">
          <div style="background:var(--dark); padding:16px; border-left:3px solid var(--gold);">
            <h4 style="color:var(--gold); margin-bottom:8px;">Meal 1: Breakfast Booster</h4>
            <p style="font-size:13px; color:rgba(255,255,255,0.6);">4 Egg Whites + 2 Whole Eggs scrambled, 70g rolled oats cooked with water, 1 sliced medium banana.</p>
            <p style="font-size:12px; margin-top:8px; color:var(--gold2);">~520 kcal | 35g Protein</p>
          </div>
          <div style="background:var(--dark); padding:16px; border-left:3px solid var(--gold);">
            <h4 style="color:var(--gold); margin-bottom:8px;">Meal 2: Standard Gym Fuel Lunch</h4>
            <p style="font-size:13px; color:rgba(255,255,255,0.6);">180g grilled or boiled lean chicken breast, 150g cooked Jasmine brown rice, 100g steamed seasonal broccoli/cauliflower.</p>
            <p style="font-size:12px; margin-top:8px; color:var(--gold2);">~610 kcal | 48g Protein</p>
          </div>
          <div style="background:var(--dark); padding:16px; border-left:3px solid var(--gold);">
            <h4 style="color:var(--gold); margin-bottom:8px;">Meal 3: Pure Local Option Veg</h4>
            <p style="font-size:13px; color:rgba(255,255,255,0.6);">200g Fresh cottage Paneer sauteed, 1 bowl black lentils (Mahi ko Daal), mixed green salad with a drop of olive oil.</p>
            <p style="font-size:12px; margin-top:8px; color:var(--gold2);">~490 kcal | 28g Protein</p>
          </div>
          <div style="background:var(--dark); padding:16px; border-left:3px solid var(--gold);">
            <h4 style="color:var(--gold); margin-bottom:8px;">Meal 4: Pre-Workout Power Snack</h4>
            <p style="font-size:13px; color:rgba(255,255,255,0.6);">2 slices whole wheat brown bread toasted, 2 tablespoons sugar-free peanut butter, 1 scoop Whey isolated protein block.</p>
            <p style="font-size:12px; margin-top:8px; color:var(--gold2);">~410 kcal | 32g Protein</p>
          </div>
        </div>
      </div>
    </div>

    <div id="intel-work" class="intel-page reveal">
      <div class="intel-card">
        <div class="intel-card-title">💪 Target Split Protocol Routine Selector</div>
        <div class="intel-field">
          <label class="intel-label">Select Dynamic Split System</label>
          <select class="intel-select" id="workout-select" onchange="renderWorkoutSplit()">
            <option value="ppl">3-Day Classic Push / Pull / Legs protocol</option>
            <option value="arnold">4-Day High Efficiency Arnold Split architecture</option>
          </select>
        </div>
        <div id="workout-container" style="margin-top:20px;"></div>
      </div>
    </div>

    <div id="intel-track" class="intel-page reveal">
      <div class="intel-grid">
        <div class="intel-card">
          <div class="intel-card-title">💧 Realtime Hydration Tracker Engine</div>
          <p style="font-size:13px; color:rgba(255,255,255,0.6); margin-bottom:12px;">Track your hydration levels. Click on each glass to log 250ml water consumption.</p>
          <div class="glass-grid" id="water-grid"></div>
          <p style="margin-top:12px; font-weight:700; color:var(--blue);" id="water-total">Total logged water: 0 mL / 3000 mL</p>
        </div>
        <div class="intel-card">
          <div class="intel-card-title">📝 Quick Progress Notes Cache</div>
          <textarea id="track-notes" class="intel-input" style="height:100px; resize:none;" placeholder="Write daily workout notes, e.g., Squat 100kg PR hit today..."></textarea>
          <button class="intel-btn" style="margin-top:12px;" onclick="saveTrackNotes()">Save Data Locally</button>
        </div>
      </div>
    </div>

  </div>
</section>

<section id="membership">
  <div class="container">
    <div class="reveal" style="text-align:center">
      <div class="section-label" style="justify-content:center">Choose Your Plan</div>
      <h2 class="section-title">MEMBERSHIP PACKAGES</h2>
      <p class="section-sub" style="margin:0 auto 60px">Affordable elite membership architectures tailored to support long-term metabolic health and athletic performance objectives.</p>
    </div>
    <div class="plans-grid reveal">
      <div class="plan-card">
        <div class="plan-name">Walk-in</div>
        <div class="plan-price">Pay Per <span>Visit</span></div>
        <ul class="plan-features">
          <li>Full gym access</li>
          <li>All structural iron equipment</li>
          <li>Locker locker amenities</li>
          <li>Zero long-term commitment</li>
        </ul>
        <a href="tel:9841078384" class="plan-btn">Call for Pricing</a>
      </div>
      <div class="plan-card featured">
        <div class="plan-name">Monthly</div>
        <div class="plan-price">Best <span>Value</span></div>
        <ul class="plan-features">
          <li>Unlimited gym floor access</li>
          <li>All studio group classes</li>
          <li>High-energy Zumba integration</li>
          <li>Routine body assessment checks</li>
        </ul>
        <a href="tel:9841078384" class="plan-btn">Call for Pricing</a>
      </div>
      <div class="plan-card">
        <div class="plan-name">Yearly</div>
        <div class="plan-price">Max <span>Savings</span></div>
        <ul class="plan-features">
          <li>Everything included in monthly plan</li>
          <li>Priority scheduling setup</li>
          <li>Personalized dietary design</li>
          <li>Best cost-per-day optimization</li>
        </ul>
        <a href="tel:9841078384" class="plan-btn">Call for Pricing</a>
      </div>
    </div>
  </div>
</section>

<section id="trainers" style="background:var(--dark);">
  <div class="container">
    <div class="reveal" style="text-align:center">
      <div class="section-label" style="justify-content:center">Certified Instructors</div>
      <h2 class="section-title">EXPERT COACHING STAFF</h2>
    </div>
    <div class="trainers-grid reveal" style="margin-top:40px;">
      <div class="trainer-card">
        <div class="trainer-img">💪</div>
        <div class="trainer-name">Head Trainer</div>
        <div class="trainer-role">Strength Conditioning Expert</div>
        <div class="trainer-desc">Master programmer specializing in hypertrophy transformations and biomechanics execution protocols.</div>
      </div>
      <div class="trainer-card">
        <div class="trainer-img">💃</div>
        <div class="trainer-name">Zumba Specialist</div>
        <div class="trainer-role">Aerobic Movement Coach</div>
        <div class="trainer-desc">High intensity fitness leader bringing dynamic calorie burn split designs weekly.</div>
      </div>
      <div class="trainer-card">
        <div class="trainer-img">🥗</div>
        <div class="trainer-name">Nutrition Guide</div>
        <div class="trainer-role">Metabolic Health Consultant</div>
        <div class="trainer-desc">Designs individual lifestyle meal setups matching client functional energy architectures perfectly.</div>
      </div>
    </div>
  </div>
</section>

<section id="contact">
  <div class="container">
    <div class="reveal">
      <div class="section-label">Find Us</div>
      <h2 class="section-title">GET IN TOUCH</h2>
    </div>
    <div class="contact-grid">
      <div class="contact-info reveal">
        <div class="contact-item">
          <div class="contact-icon">📍</div>
          <div>
            <div class="contact-label">Address</div>
            <div class="contact-value">Loktantrik Chowk, Manamaiju<br>Kathmandu, Nepal 44660</div>
          </div>
        </div>
        <div class="contact-item">
          <div class="contact-icon">📞</div>
          <div>
            <div class="contact-label">Phone Enquiries</div>
            <div class="contact-value"><a href="tel:9841078384">984-1078384</a> | <a href="tel:9851069255">985-1069255</a></div>
          </div>
        </div>
        <div class="contact-item">
          <div class="contact-icon">⏰</div>
          <div>
            <div class="contact-label">Facility Hours</div>
            <div class="contact-value">Mon – Sat: 5:00 AM – 9:00 PM<br><span style="color:var(--red)">Sunday: Closed</span></div>
          </div>
        </div>
      </div>
      <div class="map-embed reveal">
        <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3531.7!2d85.3134!3d27.7432!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x39eb196dc0000001%3A0x0!2sThree+Star+Gym!5e0!3m2!1sen!2snp!4v1" allowfullscreen="" loading="lazy"></iframe>
      </div>
    </div>
  </div>
</section>

<footer>
  <div class="footer-grid">
    <div>
      <div class="footer-logo">THREE ★ GYM</div>
      <p class="footer-desc">Your ultimate physique transformation center inside Kathmandu. Professional environment built around community health elevation.</p>
    </div>
    <div>
      <div class="footer-title">Navigation Links</div>
      <ul class="footer-links">
        <li><a href="#about">About</a></li>
        <li><a href="#services">Services</a></li>
        <li><a href="#intelligence">Fitness Intelligence</a></li>
        <li><a href="#membership">Packages</a></li>
      </ul>
    </div>
    <div>
      <div class="footer-title">Emergency Reach</div>
      <ul class="footer-links">
        <li><a href="tel:9841078384">📞 984-1078384</a></li>
        <li><a href="tel:9851069255">📞 985-1069255</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <span>© 2026 Three Star Gym & Fitness · All Rights Reserved</span>
    <span>Loktantrik Chowk, Kathmandu</span>
  </div>
</footer>

<button id="btt" onclick="window.scrollTo({top:0,behavior:'smooth'})">↑</button>

<script>
// ---- SYSTEM LOADER INITIALIZATION ----
window.addEventListener('load',()=>{
  setTimeout(()=>{
    const l=document.getElementById('loader');
    l.classList.add('out');
    setTimeout(()=>l.style.display='none',700);
  },2000);
  runCalculations();
  renderWorkoutSplit();
  buildWaterGrid();
  loadSavedNotes();
});

// ---- NAVIGATION RESPONSE EVENTS ----
const nav=document.getElementById('navbar');
window.addEventListener('scroll',()=>{
  if(window.scrollY>50) nav.classList.add('scrolled');
  else nav.classList.remove('scrolled');
  if(window.scrollY>400) document.getElementById('btt').classList.add('visible');
  else document.getElementById('btt').classList.remove('visible');
});

// HAMBURGER TOGGLES
document.getElementById('hamburger').addEventListener('click', function() {
  const links = document.querySelector('.nav-links');
  if(links.style.display === 'flex') { links.style.display = 'none'; }
  else { links.style.cssText = 'display:flex; flex-direction:column; position:fixed; top:70px; left:0; right:0; background:#080808; padding:20px; gap:16px; border-bottom:1px solid var(--border);'; }
});

// ---- INTERACTIVE TAB MANAGER ENGINE ----
function switchIntelTab(tabName) {
  document.querySelectorAll('.intel-tab').forEach(btn => btn.classList.remove('active'));
  document.querySelectorAll('.intel-page').forEach(page => page.classList.remove('active'));
  
  event.target.classList.add('active');
  document.getElementById('intel-' + tabName).classList.add('active');
}

// ---- METABOLIC COMPUTATION CORE MATHEMATICS ----
function runCalculations() {
  let w = parseFloat(document.getElementById('inp-weight').value);
  let h = parseFloat(document.getElementById('inp-height').value);
  let a = parseFloat(document.getElementById('inp-age').value);
  let gender = document.getElementById('inp-gender').value;
  let act = parseFloat(document.getElementById('inp-activity').value);

  document.getElementById('lbl-weight').innerText = `Weight: ${w} kg`;
  document.getElementById('lbl-height').innerText = `Height: ${h} cm`;
  document.getElementById('lbl-age').innerText = `Age: ${a} years`;

  // BMI Formula
  let bmi = w / ((h/100)*(h/100));
  let bmiDesc = "Normal";
  if(bmi < 18.5) bmiDesc = "Underweight";
  else if(bmi >= 25 && bmi < 29.9) bmiDesc = "Overweight";
  else if(bmi >= 29.9) bmiDesc = "Obese";
  document.getElementById('res-bmi').innerText = `${bmi.toFixed(1)} (${bmiDesc})`;

  // BMR Formula (Mifflin-St Jeor Equation)
  let bmr = (10 * w) + (6.25 * h) - (5 * a);
  if(gender === 'male') bmr += 5;
  else bmr -= 161;
  document.getElementById('res-bmr').innerText = `${Math.round(bmr)} kcal`;

  // TDEE Calculation
  let tdee = bmr * act;
  document.getElementById('res-tdee').innerText = `${Math.round(tdee)} kcal`;

  // Update adjacent nutrition models automatically
  calculateMacros();
}

// ---- MACRONUTRIENT DISTRIBUTION CORE ENGINE ----
function calculateMacros() {
  let tdeeStr = document.getElementById('res-tdee').innerText;
  let tdee = parseInt(tdeeStr) || 2500;
  let goal = document.getElementById('nutri-goal').value;
  let split = document.getElementById('macro-split').value;

  let targetCal = tdee;
  if(goal === 'fat-loss') targetCal = tdee - 500;
  else if(goal === 'clean-bulk') targetCal = tdee + 300;

  document.getElementById('nutri-target-cal').innerText = `${Math.round(targetCal)} kcal/day`;

  // Distribution Ratios mapping
  let pPct = 0.3, cPct = 0.4, fPct = 0.3;
  if(split === 'high-protein') { pPct = 0.4; cPct = 0.35; fPct = 0.25; }
  else if(split === 'low-carb') { pPct = 0.45; cPct = 0.20; fPct = 0.35; }

  let pGrams = (targetCal * pPct) / 4;
  let cGrams = (targetCal * cPct) / 4;
  let fGrams = (targetCal * fPct) / 9;

  document.getElementById('nutri-prot').innerText = `${Math.round(pGrams)}g (${Math.round(targetCal*pPct)} kcal)`;
  document.getElementById('nutri-carb').innerText = `${Math.round(cGrams)}g (${Math.round(targetCal*cPct)} kcal)`;
  document.getElementById('nutri-fat').innerText = `${Math.round(fGrams)}g (${Math.round(targetCal*fPct)} kcal)`;
}

// ---- ROUTINE ENGINE SPLIT RENDERER ----
const splitData = {
  ppl: `
    <div style="margin-bottom:12px;"><strong>Day 1: Push System</strong> - Benchpress (4x8), Overhead Shoulder Press (3x10), Incline Dumbbell Flyes (3x12), Tricep Cable Extensions (4x12)</div>
    <div style="margin-bottom:12px;"><strong>Day 2: Pull System</strong> - Barbell Deadlifts (3x5), Lat Pulldowns (4x10), Seated Cable Rows (3x12), Hammer Bicep Curls (4x12)</div>
    <div><strong>Day 3: Legs/Core</strong> - Barbell Back Squats (4x6), Romanian Deadlifts (3x10), Leg Extensions (3x15), Standing Calf Raises (4x20)</div>`,
  arnold: `
    <div style="margin-bottom:12px;"><strong>Day 1: Chest & Back Architecture</strong> - Incline Press super-set with Pullups (4 sets x 10 reps)</div>
    <div style="margin-bottom:12px;"><strong>Day 2: Shoulders & Arms Split</strong> - Standing Military Dumbbell Press with Barbell Bicep Curls (4x12)</div>
    <div style="margin-bottom:12px;"><strong>Day 3: Leg Hypertrophy Focus</strong> - Leg Press (4x12), Lying Leg Curls (3x15)</div>
    <div><strong>Day 4: Core Isolation Protocol</strong> - Weighted Cable Crunches (4x20), Russian Twist sets</div>`
};

function renderWorkoutSplit() {
  let val = document.getElementById('workout-select').value;
  document.getElementById('workout-container').innerHTML = splitData[val];
}

// ---- TRACKER WATER ARCHITECTURE INTEGRATION ----
let waterCount = 0;
function buildWaterGrid() {
  const container = document.getElementById('water-grid');
  container.innerHTML = '';
  for(let i=1; i<=12; i++) {
    let div = document.createElement('div');
    div.classList.add('glass');
    div.onclick = function() {
      this.classList.toggle('filled');
      let filledGlasses = document.querySelectorAll('.glass.filled').length;
      waterCount = filledGlasses * 250;
      document.getElementById('water-total').innerText = `Total logged water: ${waterCount} mL / 3000 mL`;
    };
    container.appendChild(div);
  }
}

// ---- LOCAL CACHE MANAGEMENT ENGINE ----
function saveTrackNotes() {
  let txt = document.getElementById('track-notes').value;
  localStorage.setItem('threestar_notes', txt);
  alert('Data securely saved to your local browser storage cache!');
}
function loadSavedNotes() {
  let saved = localStorage.getItem('threestar_notes');
  if(saved) document.getElementById('track-notes').value = saved;
}

// ---- BACKGROUND DECORATIVE ANIMATED PARTICLES ----
const pc=document.getElementById('particles');
for(let i=0;i<25;i++){
  const p=document.createElement('div');
  p.classList.add('particle');
  const size=Math.random()*3+1;
  p.style.cssText=`left:${Math.random()*100}%; width:${size}px; height:${size}px; animation-duration:${8+Math.random()*12}s; animation-delay:${Math.random()*8}s; opacity:${0.3+Math.random()*0.4}`;
  pc.appendChild(p);
}
</script>
</body>
</html>
