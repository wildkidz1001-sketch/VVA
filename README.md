# VVA
Officail audition form 
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>WILDKIDZ — Official Application Portal | WOWLD Entertainment</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@500;600;700&family=Cormorant+Garamond:ital,wght@0,500;0,600;1,500&family=Plus+Jakarta+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
  <style>
    :root {
      --silver-deep: #4A5058;
      --silver-mid: #68707A;
      --silver-soft: #8A929E;
      --silver-whisper: #A3AAB5;
      --silver-line: rgba(154, 162, 174, 0.30);
    }
    * { box-sizing: border-box; -webkit-tap-highlight-color: transparent; }
    body {
      margin: 0;
      font-family: 'Plus Jakarta Sans', sans-serif;
      color: var(--silver-mid);
      background: radial-gradient(circle at 50% 0%, #FFFFFF 0%, #F7F9FC 55%, #EEF1F6 100%);
      min-height: 100vh;
      overflow-x: hidden;
    }
    .font-angelic { font-family: 'Cinzel', serif; }
    .font-editorial { font-family: 'Cormorant Garamond', serif; }

    /* Brushed Liquid Silver Text (Zero Black) */
    .silver-chrome-text {
      background: linear-gradient(135deg, #4B525B 0%, #8E96A2 34%, #525963 68%, #9AA2AE 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }
    .silver-ink { color: var(--silver-deep); }
    .silver-body { color: var(--silver-mid); }
    .silver-muted { color: var(--silver-soft); }
    .silver-hairline { border-color: var(--silver-line); }

    /* Frosted White iOS Liquid Glass */
    .liquid-glass {
      background: linear-gradient(155deg, rgba(255, 255, 255, 0.90) 0%, rgba(250, 252, 255, 0.72) 100%);
      backdrop-filter: blur(24px) saturate(145%);
      -webkit-backdrop-filter: blur(24px) saturate(145%);
      border: 1px solid rgba(255, 255, 255, 0.98);
      box-shadow:
        0 20px 48px rgba(110, 118, 130, 0.08),
        0 1px 3px rgba(110, 118, 130, 0.05),
        inset 0 1px 0 rgba(255, 255, 255, 1);
    }

    /* Silver Inputs */
    .silver-input {
      width: 100%;
      background: rgba(255, 255, 255, 0.82);
      border: 1px solid rgba(164, 172, 184, 0.36);
      border-radius: 14px;
      padding: 11px 14px;
      font-size: 13.5px;
      color: var(--silver-deep);
      transition: all 0.2s ease;
    }
    .silver-input::placeholder { color: var(--silver-whisper); }
    .silver-input:focus {
      outline: none;
      background: #FFFFFF;
      border-color: #7D8591;
      box-shadow: 0 0 0 3px rgba(154, 162, 174, 0.16);
    }

    /* Silver Pills & Buttons (Zero Black) */
    .silver-pill {
      background: rgba(255, 255, 255, 0.78);
      border: 1px solid rgba(164, 172, 184, 0.36);
      color: var(--silver-mid);
      transition: all 0.2s ease;
    }
    .silver-pill:hover { background: #FFFFFF; border-color: #828A96; color: var(--silver-deep); }
    .silver-pill.active {
      background: linear-gradient(135deg, #58606B 0%, #7C8592 100%);
      color: #FFFFFF;
      border-color: #6B7380;
      box-shadow: 0 8px 20px rgba(104, 112, 122, 0.20);
    }

    .btn-silver-primary {
      background: linear-gradient(135deg, #565E69 0%, #838C99 52%, #5F6773 100%);
      color: #FFFFFF;
      border: 1px solid rgba(255, 255, 255, 0.65);
      box-shadow: 0 10px 24px rgba(104, 112, 122, 0.22);
      transition: transform 0.18s ease, opacity 0.18s ease;
    }
    .btn-silver-primary:hover { opacity: 0.94; transform: translateY(-1px); }
    .btn-silver-primary:active { transform: scale(0.985); }

    .btn-silver-ghost {
      background: rgba(255, 255, 255, 0.86);
      color: var(--silver-deep);
      border: 1px solid rgba(164, 172, 184, 0.40);
      transition: all 0.18s ease;
    }
    .btn-silver-ghost:hover { background: #FFFFFF; border-color: #7A828E; }

    .studio-white-ai {
      background: #FFFFFF !important;
      filter: brightness(1.07) contrast(1.03);
    }

    @keyframes slowSpin { from { transform: rotate(0deg); } to { transform: rotate(360deg); } }
    @keyframes floatSoft { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-5px); } }
    @keyframes revealUp { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: translateY(0); } }
    .animate-slow-spin { animation: slowSpin 28s linear infinite; }
    .animate-float-soft { animation: floatSoft 4.6s ease-in-out infinite; }
    .stage-enter { animation: revealUp 0.32s cubic-bezier(0.22, 1, 0.36, 1) forwards; }
  </style>
</head>
<body class="antialiased selection:bg-slate-200">

  <!-- Slow-Motion Cherry-Blossom Falling Silver Stars -->
  <canvas id="blossomStars" class="fixed inset-0 pointer-events-none z-0"></canvas>

  <!-- Floating Silver Validation Toast -->
  <div id="toast" class="fixed top-4 left-1/2 -translate-x-1/2 z-50 pointer-events-none opacity-0 transition-all duration-300 w-[90%] max-w-xs">
    <div class="liquid-glass rounded-full px-4 py-2.5 flex items-center justify-center gap-2 text-xs font-medium silver-ink">
      <span class="w-1.5 h-1.5 rounded-full bg-[#68707A]"></span>
      <span id="toastMsg"></span>
    </div>
  </div>

  <!-- Minimal Header -->
  <header class="sticky top-0 z-30 px-4 pt-3 pb-2">
    <div class="max-w-[620px] mx-auto liquid-glass rounded-2xl px-4 py-3">
      <div class="flex items-center justify-between gap-2">
        <button type="button" onclick="goStage(0)" class="flex items-center gap-2.5 text-left">
          <svg class="w-4 h-4 text-[#68707A]" viewBox="0 0 24 24" fill="currentColor">
            <path d="M12 0L14.3 9.7L24 12L14.3 14.3L12 24L9.7 14.3L0 12L9.7 9.7L12 0Z"/>
          </svg>
          <div>
            <span class="font-angelic text-sm font-bold tracking-[0.16em] silver-chrome-text block leading-none">WILDKIDZ</span>
            <span class="text-[9px] tracking-[0.22em] silver-muted uppercase block mt-0.5">WOWLD ENTERTAINMENT</span>
          </div>
        </button>

        <div class="flex items-center gap-2">
          <span id="stepBadge" class="text-[11px] font-medium tracking-widest silver-muted">00 / 05</span>
          <button type="button" onclick="toggleDirectory()" class="btn-silver-ghost px-3 py-1 rounded-full text-[10px] font-medium tracking-[0.16em] uppercase">
            STAGES ▾
          </button>
        </div>
      </div>

      <!-- Brushed Silver Progress Bar -->
      <div class="mt-2.5 h-[2px] w-full bg-[#E5E8EE] rounded-full overflow-hidden">
        <div id="progressLine" class="h-full transition-all duration-500" style="width:0%; background: linear-gradient(90deg, #B2B9C4, #68707A, #9AA2AE);"></div>
      </div>
    </div>

    <!-- Compact Stage Jumper -->
    <div id="stageDrawer" class="hidden max-w-[620px] mx-auto mt-2 liquid-glass rounded-2xl p-3.5">
      <div class="flex items-center justify-between pb-2 mb-2 border-b silver-hairline text-[10px] tracking-[0.2em] silver-muted uppercase">
        <span>PORTAL STAGES</span>
        <button type="button" onclick="toggleDirectory()" class="silver-ink">CLOSE ✕</button>
      </div>
      <div id="drawerList" class="grid grid-cols-1 sm:grid-cols-2 gap-1"></div>
    </div>
  </header>

  <!-- Main Single-Column Seraphic Viewport -->
  <main id="app" class="relative z-10 max-w-[620px] mx-auto px-4 pt-3 pb-28"></main>

  <!-- Bottom Navigation -->
  <footer id="navBar" class="hidden fixed bottom-0 inset-x-0 z-30 px-4 pb-4 pt-2 pointer-events-none">
    <div class="max-w-[620px] mx-auto liquid-glass rounded-2xl p-2.5 flex items-center justify-between gap-3 pointer-events-auto">
      <button type="button" onclick="prevStage()" class="btn-silver-ghost px-4 py-2.5 rounded-xl text-[11px] font-medium tracking-[0.14em] uppercase">
        ← PREVIOUS
      </button>
      <span id="navTitle" class="text-[10px] tracking-[0.16em] silver-muted uppercase truncate">01 — PROFILE</span>
      <button id="nextBtn" type="button" onclick="nextStage()" class="btn-silver-primary px-5 py-2.5 rounded-xl text-[11px] font-medium tracking-[0.14em] uppercase">
        NEXT →
      </button>
    </div>
  </footer>

  <script>
    // =========================================================================
    // 1. STREAMLINED 5-STAGE SCHEMA + REVIEW
    // =========================================================================
    const STAGES = [
      { id: 0, code: '00', title: 'PORTAL ENTRY' },
      { id: 1, code: '01', title: 'PROFILE', desc: 'Candidate identity and contact details.' },
      { id: 2, code: '02', title: 'CATEGORY & SKILLS', desc: 'Select your artistic roles and performance background.' },
      { id: 3, code: '03', title: 'ABOUT YOU & INTERESTS', desc: 'Your individuality, musical taste, and creative passions.' },
      { id: 4, code: '04', title: 'AUDITION & VISUAL', desc: 'Optional performance sample and studio headshot.' },
      { id: 5, code: '05', title: 'AVAILABILITY & WHY WILDKIDZ?', desc: 'Motivation, commitment, and guardian permission.' },
      { id: 6, code: '06', title: 'REVIEW & SUBMIT', desc: 'Verify your answers, edit any stage, and confirm.' }
    ];

    const ROLES = ['Vocalist', 'Rapper', 'All-rounder', 'Dancer', 'Visual', 'Lead vocalist', 'Leader'];

    const FIELDS = {
      1: [
        { k: 'fullName', l: 'Full name', p: 'Legal full name', req: true },
        { k: 'preferredName', l: 'Preferred name', p: 'Stage or preferred name', req: true },
        { k: 'age', l: 'Age', p: 'e.g. 19', t: 'number', req: true, half: true },
        { k: 'dob', l: 'Date of birth', t: 'date', req: true, half: true },
        { k: 'email', l: 'Email address', p: 'you@example.com', t: 'email', req: true },
        { k: 'country', l: 'Country of residence', p: 'Country where you live', req: true, half: true },
        { k: 'languages', l: 'Languages spoken', p: 'e.g. English, Korean', req: true, half: true }
      ],
      2: [
        { k: 'prevExperience', l: 'Previous performance experience', opts: ['Extensive Experience', 'Some Experience', 'Beginner / Self-Taught'], req: true },
        { k: 'practiceDuration', l: 'Main talent practice duration', p: 'e.g. 3 years of vocal & dance training', req: true }
      ],
      3: [
        { k: 'introduceYourself', l: 'Introduce yourself', p: 'Share who you are as an artist and individual...', area: 3, req: true },
        { k: 'whatMakesUnique', l: 'What makes you unique?', p: 'What sets your tone, style, or presence apart...', area: 2, req: true },
        { k: 'favMusic', l: 'Favourite music genres & artists', p: 'e.g. R&B, Pop, Hip-Hop — inspired by...', req: true },
        { k: 'creativePassions', l: 'Creative passions', p: 'Songwriting, choreography, acting, fashion, instruments...', area: 2 }
      ],
      5: [
        { k: 'whyApply', l: 'Why did you apply for WILDKIDZ?', p: 'Share your motivation for joining WILDKIDZ...', area: 3, req: true },
        { k: 'whatContribute', l: 'What can you contribute to the team?', p: 'Describe the talent, energy, or creativity you bring...', area: 3, req: true },
        { k: 'timeDedication', l: 'Weekly time dedication', p: 'e.g. 10–15 hours per week', req: true, half: true },
        { k: 'onlineReady', l: 'Reliable internet & online meetings?', opts: ['Yes — Ready', 'Limited'], req: true, half: true },
        { k: 'parentalPermission', l: 'Parental / guardian permission (if under 18)', opts: ['Yes — Confirmed', 'Not Applicable (18+)', 'Not Yet'], req: true }
      ]
    };

    // =========================================================================
    // 2. LOCAL STATE (ZERO EXTERNAL EMAIL DELIVERY)
    // =========================================================================
    const STORE_KEY = 'wildkidz_seraphic_5stage_v1';
    const defaultState = {
      stage: 0, submitted: false, refCode: '',
      categories: [], auditionLink: '', aiWhiteBg: false,
      confirmAccuracy: false, confirmMinor: false
    };

    let state = (() => {
      try {
        const s = JSON.parse(localStorage.getItem(STORE_KEY) || 'null');
        return s ? { ...defaultState, ...s } : structuredClone(defaultState);
      } catch { return structuredClone(defaultState); }
    })();

    const files = { audition: null, photo: null };
    const save = () => { try { localStorage.setItem(STORE_KEY, JSON.stringify(state)); } catch {} };
    const setVal = (k, v) => { state[k] = v; save(); };

    let toastTimer;
    function notify(msg) {
      const box = document.getElementById('toast');
      document.getElementById('toastMsg').textContent = msg;
      box.classList.remove('opacity-0', '-translate-y-2');
      box.classList.add('opacity-100', 'translate-y-0');
      clearTimeout(toastTimer);
      toastTimer = setTimeout(() => {
        box.classList.add('opacity-0', '-translate-y-2');
        box.classList.remove('opacity-100', 'translate-y-0');
      }, 2600);
    }

    // =========================================================================
    // 3. NAVIGATION & VALIDATION
    // =========================================================================
    function toggleDirectory() {
      const el = document.getElementById('stageDrawer');
      el.classList.toggle('hidden');
      if (!el.classList.contains('hidden')) {
        document.getElementById('drawerList').innerHTML = STAGES.map(s => `
          <button type="button" onclick="goStage(${s.id}); toggleDirectory();"
            class="text-left px-3 py-2 rounded-xl text-xs flex items-center justify-between transition ${state.stage === s.id ? 'bg-[#68707A] text-white font-medium' : 'silver-body hover:bg-white'}">
            <span><span class="opacity-60 mr-2">${s.code}</span>${s.title}</span>
            ${state.stage === s.id ? '<span>✦</span>' : ''}
          </button>
        `).join('');
      }
    }

    function goStage(n) {
      if (n < 0 || n > 6) return;
      state.stage = n;
      save(); render();
      window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    const prevStage = () => state.stage > 0 && goStage(state.stage - 1);
    const nextStage = () => validate(state.stage) && state.stage < 6 && goStage(state.stage + 1);
    const isEmail = v => /^[^\s@]+@[^\s@]+\.[^\s@]{2,}$/.test((v || '').trim());
    const err = m => { notify(m); return false; };

    function validate(s) {
      if (s === 1) {
        if (!(state.fullName || '').trim()) return err('Please enter your full name.');
        if (!(state.preferredName || '').trim()) return err('Please enter your preferred name.');
        if (!state.age || Number(state.age) < 8 || Number(state.age) > 99) return err('Please enter a valid age.');
        if (!state.dob) return err('Please select your date of birth.');
        if (!isEmail(state.email)) return err('Please enter a valid email address.');
        if (!(state.country || '').trim()) return err('Please enter your country.');
        if (!(state.languages || '').trim()) return err('Please enter languages spoken.');
      }
      if (s === 2) {
        if (!state.categories.length) return err('Please select at least one category.');
        if (!state.prevExperience || !(state.practiceDuration || '').trim()) return err('Please complete your experience & practice duration.');
      }
      if (s === 3) {
        if (!(state.introduceYourself || '').trim() || !(state.whatMakesUnique || '').trim() || !(state.favMusic || '').trim()) {
          return err('Please complete your introduction, uniqueness, and favourite music.');
        }
      }
      if (s === 5) {
        if (!(state.whyApply || '').trim() || !(state.whatContribute || '').trim() || !(state.timeDedication || '').trim() || !state.onlineReady || !state.parentalPermission) {
          return err('Please complete all Stage 05 fields.');
        }
        if (Number(state.age) < 18 && state.parentalPermission !== 'Yes — Confirmed') {
          return err('Parental / guardian permission is required for applicants under 18.');
        }
      }
      return true;
    }

    function toggleRole(r) {
      const idx = state.categories.indexOf(r);
      idx > -1 ? state.categories.splice(idx, 1) : state.categories.push(r);
      save(); render();
    }

    function handleUpload(slot, input) {
      const f = input.files?.[0];
      if (!f) return;
      if (files[slot]?.url) URL.revokeObjectURL(files[slot].url);
      files[slot] = { name: f.name, type: f.type, url: URL.createObjectURL(f) };
      notify(`Uploaded ${f.name}`);
      render();
    }

    function removeUpload(slot) {
      if (files[slot]?.url) URL.revokeObjectURL(files[slot].url);
      files[slot] = null;
      if (slot === 'photo') state.aiWhiteBg = false;
      save(); render();
    }

    function finalizeApplication() {
      if (!validate(1) || !validate(2) || !validate(3) || !validate(5)) return;
      if (!state.confirmAccuracy) return err('Please confirm your application information.');
      if (Number(state.age) < 18 && !state.confirmMinor) return err('Please confirm parental / guardian permission.');

      state.refCode = 'WKZ-' + Math.random().toString(36).substring(2, 8).toUpperCase();
      state.submitted = true;
      save(); render();
      window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    function resetHome() {
      state = structuredClone(defaultState);
      save(); render();
      window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    // =========================================================================
    // 4. RENDER ENGINE (ALL SILVER TYPOGRAPHY)
    // =========================================================================
    const starIcon = (cls = 'w-4 h-4') => `
      <svg class="${cls}" viewBox="0 0 24 24" fill="currentColor">
        <path d="M12 0L14.4 9.6L24 12L14.4 14.4L12 24L9.6 14.4L0 12L9.6 9.6L12 0Z"/>
      </svg>`;

    function renderFields(list) {
      return `<div class="grid grid-cols-1 sm:grid-cols-2 gap-4">${list.map(f => {
        const val = (state[f.k] ?? '').toString().replace(/"/g, '&quot;');
        const span = f.half ? '' : 'sm:col-span-2';
        if (f.opts) {
          return `
            <div class="${span} space-y-2">
              <label class="block text-xs font-medium silver-ink">${f.l} ${f.req ? '<span class="silver-muted">*</span>' : ''}</label>
              <div class="flex flex-wrap gap-2">
                ${f.opts.map(o => `
                  <button type="button" onclick="setVal('${f.k}', '${o}'); render();"
                    class="silver-pill px-3.5 py-2 rounded-xl text-xs font-medium ${state[f.k] === o ? 'active' : ''}">${o}</button>
                `).join('')}
              </div>
            </div>`;
        }
        if (f.area) {
          return `
            <div class="${span} space-y-1.5">
              <label class="block text-xs font-medium silver-ink">${f.l} ${f.req ? '<span class="silver-muted">*</span>' : ''}</label>
              <textarea rows="${f.area}" placeholder="${f.p || ''}" oninput="setVal('${f.k}', this.value)"
                class="silver-input leading-relaxed">${state[f.k] ?? ''}</textarea>
            </div>`;
        }
        return `
          <div class="${span} space-y-1.5">
            <label class="block text-xs font-medium silver-ink">${f.l} ${f.req ? '<span class="silver-muted">*</span>' : ''}</label>
            <input type="${f.t || 'text'}" value="${val}" placeholder="${f.p || ''}" oninput="setVal('${f.k}', this.value)" class="silver-input" />
          </div>`;
      }).join('')}</div>`;
    }

    function renderView() {
      if (state.submitted) {
        return `
          <section class="stage-enter liquid-glass rounded-3xl px-6 py-12 sm:px-10 text-center space-y-6 my-3">
            <div class="relative w-20 h-20 mx-auto flex items-center justify-center">
              <div class="absolute inset-0 rounded-full border border-[#B8BFC9] animate-slow-spin"></div>
              <div class="text-[#68707A] animate-float-soft drop-shadow-[0_4px_14px_rgba(148,156,170,0.5)]">
                ${starIcon('w-10 h-10')}
              </div>
            </div>
            <div class="space-y-1.5">
              <span class="text-[10px] tracking-[0.26em] silver-muted uppercase block">CONFIRMATION // ${state.refCode}</span>
              <h2 class="font-angelic text-2xl sm:text-4xl font-bold tracking-wider silver-chrome-text">APPLICATION RECEIVED.</h2>
            </div>
            <div class="max-w-md mx-auto space-y-2.5 text-sm silver-body leading-relaxed">
              <p class="font-semibold silver-ink">Thank you for your interest in WILDKIDZ.</p>
              <p>Your application has been successfully submitted. WOWLD Entertainment will review your application and contact you using the email provided.</p>
            </div>
            <div class="pt-3">
              <button type="button" onclick="resetHome()" class="btn-silver-primary px-8 py-3.5 rounded-2xl text-xs font-medium tracking-[0.2em] uppercase">
                RETURN TO HOME
              </button>
            </div>
          </section>`;
      }

      const s = state.stage;
      const meta = STAGES[s];

      if (s === 0) {
        return `
          <section class="stage-enter pt-2">
            <div class="liquid-glass rounded-3xl px-6 py-12 sm:px-12 sm:py-16 text-center relative overflow-hidden">
              <div class="inline-flex items-center gap-2 px-3.5 py-1 rounded-full bg-white/90 border silver-hairline text-[10px] tracking-[0.24em] silver-muted uppercase mb-8">
                <span>✦</span>
                <span>WOWLD ENTERTAINMENT PRESENTS</span>
              </div>

              <div class="relative w-20 h-20 mx-auto mb-6 flex items-center justify-center">
                <svg class="absolute inset-0 w-full h-full animate-slow-spin opacity-60" viewBox="0 0 100 100" fill="none">
                  <circle cx="50" cy="50" r="44" stroke="#9AA2AE" stroke-width="0.75" stroke-dasharray="2 5"/>
                  <ellipse cx="50" cy="50" rx="47" ry="16" transform="rotate(-24 50 50)" stroke="#7D8591" stroke-width="0.75"/>
                </svg>
                <div class="text-[#68707A] animate-float-soft">${starIcon('w-10 h-10')}</div>
              </div>

              <h1 class="font-angelic text-4xl sm:text-6xl font-bold tracking-[0.15em] silver-chrome-text leading-none">
                WILDKIDZ
              </h1>
              <p class="text-[11px] tracking-[0.28em] silver-muted uppercase mt-3">
                OFFICIAL APPLICATION PORTAL
              </p>

              <p class="font-editorial italic text-lg sm:text-xl silver-body max-w-md mx-auto mt-6 leading-relaxed">
                An international entertainment project uniting distinctive voices, movement, and individuality under WOWLD Entertainment.
              </p>

              <div class="mt-9 flex justify-center">
                <button type="button" onclick="goStage(1)" class="btn-silver-primary w-full sm:w-auto px-9 py-3.5 rounded-2xl text-xs font-medium tracking-[0.2em] uppercase">
                  BEGIN APPLICATION →
                </button>
              </div>
            </div>
          </section>`;
      }

      const header = `
        <div class="mb-6 pb-4 border-b silver-hairline">
          <div class="flex items-center justify-between text-[10px] tracking-[0.22em] silver-muted uppercase mb-1.5">
            <span>STAGE ${meta.code} OF 05</span>
            <span>WILDKIDZ // WOWLD</span>
          </div>
          <h2 class="font-angelic text-xl sm:text-2xl font-bold tracking-wider silver-chrome-text">${meta.code} — ${meta.title}</h2>
          ${meta.desc ? `<p class="text-xs silver-muted mt-1.5 leading-relaxed">${meta.desc}</p>` : ''}
        </div>`;

      if (s === 1 || s === 3 || s === 5) {
        const minorNote = (s === 5 && Number(state.age) > 0 && Number(state.age) < 18) ? `
          <div class="mt-4 p-3.5 rounded-2xl bg-white/80 border silver-hairline text-xs silver-body">
            <strong class="silver-ink">Minor Safeguard:</strong> Applicants under 18 require verified parent or legal guardian permission.
          </div>` : '';
        return `<section class="stage-enter liquid-glass rounded-3xl p-6 sm:p-9">${header}${renderFields(FIELDS[s])}${minorNote}</section>`;
      }

      if (s === 2) {
        return `
          <section class="stage-enter liquid-glass rounded-3xl p-6 sm:p-9 space-y-6">
            ${header}
            <div class="space-y-2">
              <label class="block text-xs font-medium silver-ink">Select Categories (Multiple allowed) <span class="silver-muted">*</span></label>
              <div class="grid grid-cols-1 sm:grid-cols-2 gap-2.5">
                ${ROLES.map(r => {
                  const on = state.categories.includes(r);
                  return `
                    <button type="button" onclick="toggleRole('${r}')"
                      class="silver-pill p-3.5 rounded-2xl flex items-center justify-between text-left ${on ? 'active' : ''}">
                      <span class="flex items-center gap-2.5">
                        ${starIcon(`w-3.5 h-3.5 ${on ? 'text-white' : 'text-[#8A929E]'}`)}
                        <span class="text-xs font-semibold tracking-wide uppercase">${r}</span>
                      </span>
                      <span class="text-xs">${on ? '✓' : '+'}</span>
                    </button>`;
                }).join('')}
              </div>
            </div>
            ${renderFields(FIELDS[2])}
          </section>`;
      }

      if (s === 4) {
        const aud = files.audition;
        const p = files.photo;
        return `
          <section class="stage-enter liquid-glass rounded-3xl p-6 sm:p-9 space-y-6">
            ${header}

            <!-- Optional Audition Sample -->
            <div class="p-4 rounded-2xl bg-white/70 border silver-hairline space-y-3">
              <div class="flex items-center justify-between">
                <span class="text-xs font-semibold silver-ink">Audition Recording or Link</span>
                <span class="text-[9px] tracking-widest silver-muted uppercase">OPTIONAL</span>
              </div>
              ${aud ? `
                <div class="p-2.5 rounded-xl bg-white border silver-hairline space-y-2">
                  ${aud.type.startsWith('video')
                    ? `<video src="${aud.url}" controls class="w-full h-36 rounded-lg object-cover bg-slate-100"></video>`
                    : `<audio src="${aud.url}" controls class="w-full h-8"></audio>`}
                  <div class="flex items-center justify-between text-[11px]">
                    <span class="truncate silver-body max-w-[180px]">${aud.name}</span>
                    <div class="flex gap-3 font-medium">
                      <label class="silver-ink underline cursor-pointer">Replace<input type="file" accept="audio/*,video/*" class="hidden" onchange="handleUpload('audition', this)" /></label>
                      <button type="button" onclick="removeUpload('audition')" class="silver-muted hover:silver-ink">Remove</button>
                    </div>
                  </div>
                </div>
              ` : `
                <label class="block rounded-xl border border-dashed border-[#B2B9C4] hover:border-[#68707A] py-3 text-center cursor-pointer transition bg-white/60">
                  <span class="text-xs font-medium silver-ink">+ Upload Audio or Video Sample</span>
                  <input type="file" accept="audio/*,video/*" class="hidden" onchange="handleUpload('audition', this)" />
                </label>
              `}
              <input type="url" value="${(state.auditionLink || '').replace(/"/g, '&quot;')}" placeholder="Or paste YouTube / Drive / SoundCloud link..."
                oninput="setVal('auditionLink', this.value)" class="silver-input !text-xs" />
            </div>

            <!-- Optional Profile Photograph -->
            <div class="p-4 rounded-2xl bg-white/70 border silver-hairline space-y-3">
              <div class="flex items-center justify-between">
                <span class="text-xs font-semibold silver-ink">Profile Photograph (White Background, Clear Lighting)</span>
                <span class="text-[9px] tracking-widest silver-muted uppercase">OPTIONAL</span>
              </div>
              ${p ? `
                <div class="space-y-3">
                  <div class="max-w-[220px] mx-auto rounded-2xl overflow-hidden border silver-hairline p-2 transition ${state.aiWhiteBg ? 'studio-white-ai' : 'bg-white/60'}">
                    <img src="${p.url}" alt="Applicant Portrait" class="w-full h-56 object-cover rounded-xl ${state.aiWhiteBg ? 'mix-blend-multiply' : ''}" />
                  </div>
                  <div class="flex flex-wrap justify-center gap-2">
                    <label class="btn-silver-ghost px-3 py-1.5 rounded-xl text-[11px] font-medium cursor-pointer">
                      Replace<input type="file" accept="image/*" class="hidden" onchange="handleUpload('photo', this)" />
                    </label>
                    <button type="button" onclick="removeUpload('photo')" class="btn-silver-ghost px-3 py-1.5 rounded-xl text-[11px] font-medium">Remove</button>
                    <button type="button" onclick="setVal('aiWhiteBg', !state.aiWhiteBg); render();"
                      class="silver-pill px-3 py-1.5 rounded-xl text-[11px] font-medium ${state.aiWhiteBg ? 'active' : ''}">
                      ✦ AI Clean White Backdrop
                    </button>
                  </div>
                </div>
              ` : `
                <label class="block rounded-xl border border-dashed border-[#B2B9C4] hover:border-[#68707A] py-5 text-center cursor-pointer transition bg-white/60">
                  <span class="font-angelic text-xs font-bold silver-ink block">UPLOAD PHOTOGRAPH</span>
                  <span class="text-[11px] silver-muted mt-0.5 block">Face visible • No heavy filters</span>
                  <input type="file" accept="image/*" class="hidden" onchange="handleUpload('photo', this)" />
                </label>
              `}
            </div>

            <div class="pt-2 flex justify-center">
              <button type="button" onclick="goStage(5)" class="btn-silver-ghost px-8 py-2.5 rounded-xl text-xs font-medium tracking-[0.2em] uppercase">
                SKIP →
              </button>
            </div>
          </section>`;
      }

      if (s === 6) {
        const isMinor = Number(state.age) > 0 && Number(state.age) < 18;
        const row = (num, title, pairs) => `
          <div class="p-3.5 rounded-2xl bg-white/80 border silver-hairline space-y-1.5">
            <div class="flex items-center justify-between pb-1.5 border-b silver-hairline">
              <span class="text-[11px] font-semibold silver-ink">${num} — ${title}</span>
              <button type="button" onclick="goStage(${Number(num)})" class="text-[10px] px-2.5 py-0.5 rounded-lg bg-[#F1F4F8] hover:bg-[#E4E8EF] silver-ink font-medium">Edit</button>
            </div>
            ${pairs.map(([k, v]) => `
              <div class="flex flex-col sm:flex-row sm:justify-between text-xs gap-0.5">
                <span class="silver-muted">${k}</span>
                <span class="silver-ink sm:text-right max-w-sm break-words">${v || '—'}</span>
              </div>
            `).join('')}
          </div>`;

        return `
          <section class="stage-enter liquid-glass rounded-3xl p-6 sm:p-9 space-y-5">
            ${header}
            <div class="space-y-2.5">
              ${row('01', 'PROFILE', [['Full / Preferred Name', `${state.fullName || ''} (${state.preferredName || ''})`], ['Age / DOB', `${state.age || ''} • ${state.dob || ''}`], ['Email', state.email], ['Country / Languages', `${state.country || ''} • ${state.languages || ''}`]])}
              ${row('02', 'CATEGORY & SKILLS', [['Categories', state.categories.join(', ')], ['Experience / Practice', `${state.prevExperience || '—'} • ${state.practiceDuration || '—'}`]])}
              ${row('03', 'ABOUT YOU & INTERESTS', [['Introduction', state.introduceYourself], ['Uniqueness', state.whatMakesUnique], ['Favourite Music', state.favMusic]])}
              ${row('04', 'AUDITION & VISUAL', [['Audition', files.audition ? files.audition.name : (state.auditionLink || 'Skipped')], ['Photograph', files.photo ? `${files.photo.name}${state.aiWhiteBg ? ' (AI White BG)' : ''}` : 'Skipped']])}
              ${row('05', 'AVAILABILITY & WHY WILDKIDZ?', [['Why WILDKIDZ', state.whyApply], ['Contribution', state.whatContribute], ['Dedication / Ready', `${state.timeDedication || '—'} • ${state.onlineReady || '—'}`], ['Parental Permission', state.parentalPermission]])}
            </div>

            <div class="p-4 rounded-2xl bg-white/85 border silver-hairline space-y-2.5 text-xs silver-body">
              <label class="flex items-start gap-2.5 cursor-pointer">
                <input type="checkbox" ${state.confirmAccuracy ? 'checked' : ''} onchange="setVal('confirmAccuracy', this.checked)" class="mt-0.5 accent-[#68707A] w-4 h-4" />
                <span>I confirm that all information provided in this application is accurate and complete.</span>
              </label>
              ${isMinor ? `
                <label class="flex items-start gap-2.5 cursor-pointer">
                  <input type="checkbox" ${state.confirmMinor ? 'checked' : ''} onchange="setVal('confirmMinor', this.checked)" class="mt-0.5 accent-[#68707A] w-4 h-4" />
                  <span>I confirm verified parent or legal guardian permission as an applicant under 18.</span>
                </label>` : ''}
            </div>

            <button type="button" onclick="finalizeApplication()" class="btn-silver-primary w-full py-3.5 rounded-2xl text-xs font-medium tracking-[0.22em] uppercase">
              SUBMIT APPLICATION →
            </button>
          </section>`;
      }
    }

    function render() {
      const m = STAGES[state.stage] || STAGES[0];
      const pct = state.submitted ? 100 : Math.min(100, Math.round((state.stage / 6) * 100));
      document.getElementById('stepBadge').textContent = state.submitted ? 'COMPLETE' : (state.stage === 6 ? 'REVIEW' : `${m.code} / 05`);
      document.getElementById('progressLine').style.width = `${pct}%`;

      const nav = document.getElementById('navBar');
      const next = document.getElementById('nextBtn');
      if (state.stage === 0 || state.submitted) {
        nav.classList.add('hidden');
      } else {
        nav.classList.remove('hidden');
        document.getElementById('navTitle').textContent = `${m.code} — ${m.title}`;
        next.classList.toggle('hidden', state.stage === 6);
      }
      document.getElementById('app').innerHTML = renderView();
    }

    // =========================================================================
    // 5. SLOW-MOTION CHERRY-BLOSSOM FALLING SILVER STARS
    // =========================================================================
    function initBlossomStars() {
      const c = document.getElementById('blossomStars');
      const ctx = c.getContext('2d');
      let w, h;
      const resize = () => { w = c.width = window.innerWidth; h = c.height = window.innerHeight; };
      window.addEventListener('resize', resize);
      resize();

      const petals = Array.from({ length: 36 }, () => ({
        x: Math.random() * w,
        y: Math.random() * h,
        r: Math.random() * 5 + 3.2,
        vy: Math.random() * 0.25 + 0.12,
        swayAmp: Math.random() * 0.45 + 0.18,
        swayFreq: Math.random() * 0.011 + 0.005,
        phase: Math.random() * Math.PI * 2,
        rot: Math.random() * Math.PI,
        vRot: (Math.random() - 0.5) * 0.007,
        alpha: Math.random() * 0.35 + 0.22
      }));

      function drawSilverStar(p) {
        ctx.save();
        ctx.translate(p.x, p.y);
        ctx.rotate(p.rot);
        ctx.globalAlpha = p.alpha;

        const grad = ctx.createLinearGradient(-p.r, -p.r, p.r, p.r);
        grad.addColorStop(0, '#FFFFFF');
        grad.addColorStop(0.5, '#A3AAB5');
        grad.addColorStop(1, '#68707A');

        ctx.fillStyle = grad;
        ctx.beginPath();
        for (let i = 0; i < 8; i++) {
          const rad = i % 2 === 0 ? p.r : p.r * 0.25;
          const a = (i * Math.PI) / 4;
          ctx[i === 0 ? 'moveTo' : 'lineTo'](Math.cos(a) * rad, Math.sin(a) * rad);
        }
        ctx.closePath();
        ctx.fill();
        ctx.restore();
      }

      (function loop() {
        ctx.clearRect(0, 0, w, h);
        for (const p of petals) {
          p.phase += p.swayFreq;
          p.x += Math.sin(p.phase) * p.swayAmp;
          p.y += p.vy;
          p.rot += p.vRot;

          if (p.y > h + 16) { p.y = -16; p.x = Math.random() * w; }
          if (p.x > w + 16) p.x = -16;
          if (p.x < -16) p.x = w + 16;
          drawSilverStar(p);
        }
        requestAnimationFrame(loop);
      })();
    }

    window.addEventListener('DOMContentLoaded', () => { initBlossomStars(); render(); });
  </script>
</body>
</html>
```
