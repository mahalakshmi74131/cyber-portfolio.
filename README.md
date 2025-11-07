<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Srimahalakshmi Mekathoti — Cybersecurity Portfolio</title>

  <!-- Google Font -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800&display=swap" rel="stylesheet">

  <style>
    :root{
      --bg:#0f1724;
      --card:#0b1220;
      --muted:#9aa4b2;
      --accent:#00d1b2;
      --glass: rgba(255,255,255,0.04);
      --glass-2: rgba(255,255,255,0.02);
      --max-width:1100px;
      --radius:12px;
    }
    /* Light theme overrides (JS toggles body.light) */
    body.light { --bg:#f6f8fb; --card:#ffffff; --muted:#556071; --accent:#0066cc; --glass: rgba(0,0,0,0.03); --glass-2: rgba(0,0,0,0.02); color: #0b1220; }

    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family:Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      background: linear-gradient(180deg, var(--bg), #071020 120%);
      color: #e6eef6;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      line-height:1.5;
      padding:36px 18px;
      display:flex;
      justify-content:center;
    }

    .container{
      width:100%;
      max-width:var(--max-width);
      margin:0 auto;
    }

    header{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:16px;
      margin-bottom:28px;
    }

    .brand{
      display:flex;
      gap:14px;
      align-items:center;
    }
    .logo{
      width:54px;
      height:54px;
      border-radius:10px;
      background:linear-gradient(135deg,var(--accent), #8be5c8 140%);
      display:grid;
      place-items:center;
      color:#021019;
      font-weight:800;
      font-size:18px;
      box-shadow: 0 6px 18px rgba(0,0,0,0.45);
    }
    .brand h1{margin:0;font-size:18px}
    .brand p{margin:0;font-size:12px;color:var(--muted)}

    nav{
      display:flex;
      gap:10px;
      align-items:center;
      flex-wrap:wrap;
    }
    a.btn{
      text-decoration:none;
      color:inherit;
      background:var(--glass);
      padding:8px 12px;
      border-radius:10px;
      font-weight:600;
      font-size:13px;
      backdrop-filter: blur(6px);
    }
    a.btn:hover{transform:translateY(-2px)}

    main{
      display:grid;
      grid-template-columns: 1fr 360px;
      gap:28px;
      align-items:start;
    }

    /* Left column */
    .panel{
      background: linear-gradient(180deg,var(--card), rgba(255,255,255,0.02));
      border-radius: var(--radius);
      padding:20px;
      box-shadow: 0 12px 30px rgba(2,6,23,0.6);
    }

    .hero{
      display:flex;
      gap:18px;
      align-items:center;
    }
    .avatar{
      width:108px;height:108px;border-radius:14px;
      background:linear-gradient(135deg,#152235, #0f2b3a);
      display:grid;place-items:center;
      font-size:38px;font-weight:800;
      color:var(--accent);
      flex-shrink:0;
      border:2px solid rgba(255,255,255,0.03);
    }
    .hero h2{margin:0 0 6px 0}
    .hero p {margin:0;color:var(--muted)}

    .section{margin-top:18px}
    .section h3{margin:0 0 12px 0;font-size:16px}
    .tags{display:flex;flex-wrap:wrap;gap:8px}
    .tag{background:var(--glass-2);padding:8px 10px;border-radius:8px;font-weight:600;font-size:13px}

    /* Projects grid */
    .projects-grid{
      display:grid;
      grid-template-columns: repeat(auto-fit,minmax(240px,1fr));
      gap:12px;
    }
    .project-card{
      background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      padding:12px;border-radius:12px;
      border:1px solid rgba(255,255,255,0.03);
      min-height:120px;
      display:flex;flex-direction:column;gap:8px;
    }
    .project-card h4{margin:0;font-size:14px}
    .project-card p{margin:0;color:var(--muted);font-size:13px}
    .meta{margin-top:auto;display:flex;gap:8px;align-items:center;justify-content:space-between}
    .pill{font-size:12px;padding:6px 8px;border-radius:8px;background:var(--glass);font-weight:600}

    /* Right column */
    aside{position:relative}
    .card-side{position:sticky;top:36px}
    .contact-line{display:flex;align-items:center;gap:10px;padding:10px;border-radius:10px;background:var(--glass-2);margin-bottom:10px}
    .muted{color:var(--muted);font-size:13px}
    .socials{display:flex;gap:10px;margin-top:8px}
    .icon-btn{display:inline-grid;place-items:center;padding:8px;border-radius:8px;background:var(--glass);width:44px;height:44px;text-decoration:none;color:inherit}

    /* footer */
    footer{margin-top:26px;text-align:center;color:var(--muted);font-size:13px}

    /* small screens */
    @media (max-width:900px){
      main{grid-template-columns: 1fr}
      aside{order:2}
    }

    /* Project modal */
    .modal{
      position:fixed;inset:0;display:none;align-items:center;justify-content:center;background:rgba(2,6,23,0.6);z-index:60;
    }
    .modal.open{display:flex}
    .modal-card{width:min(920px,96%);background:var(--card);padding:20px;border-radius:12px}
    .modal-card h3{margin-top:0}
    .close{border-radius:8px;padding:6px 8px;background:var(--glass);border:none;cursor:pointer}

    /* small utilities */
    .row{display:flex;gap:12px;align-items:center}
    .spacer{flex:1}
    pre{white-space:pre-wrap;background:transparent;border-left:3px solid rgba(255,255,255,0.03);padding-left:10px;color:var(--muted)}
    .note{font-size:13px;color:var(--muted);padding:8px;background:var(--glass-2);border-radius:10px}

    /* subtle animations */
    .project-card, .panel {transition: transform .18s ease, box-shadow .18s ease}
    .project-card:hover{transform:translateY(-6px)}
  </style>
</head>
<body>
  <div class="container">
    <header>
      <div class="brand">
        <div class="logo">SM</div>
        <div>
          <h1>Srimahalakshmi Mekathoti</h1>
          <p>Cybersecurity Student • Web App & Network Security • Ethical Hacking</p>
        </div>
      </div>

      <nav>
        <a class="btn" href="#projects">Projects</a>
        <a class="btn" href="#skills">Skills</a>
        <a class="btn" href="#certs">Certifications</a>
        <a class="btn" href="#contact">Contact</a>
        <button id="themeToggle" class="btn" title="Toggle light / dark">Toggle Theme</button>
      </nav>
    </header>

    <main>
      <!-- LEFT: main content -->
      <div>
        <section class="panel hero">
          <div class="avatar">SM</div>
          <div>
            <h2>Hi — I'm <strong>Srimahalakshmi</strong></h2>
            <p>Cybersecurity student focused on web application security, network monitoring, and red-team fundamentals. I enjoy finding vulnerabilities and building defenses. This portfolio demonstrates sample projects and skills — edit these entries to reflect your real work.</p>
            <div style="margin-top:12px" class="row">
              <a class="btn" href="#projects">See Projects</a>
              <a class="btn" href="#contact">Get In Touch</a>
            </div>
          </div>
        </section>

        <section id="skills" class="panel section">
          <h3>Skills</h3>
          <div class="tags">
            <span class="tag">Web App Security (XSS, SQLi)</span>
            <span class="tag">Burp Suite</span>
            <span class="tag">Network Analysis (Wireshark)</span>
            <span class="tag">Linux & Bash</span>
            <span class="tag">Scripting (Python)</span>
            <span class="tag">CTF / Vulnerability Research</span>
            <span class="tag">Docker & Virtual Labs</span>
            <span class="tag">SIEM / Log Analysis</span>
          </div>
        </section>

        <section id="projects" class="panel section">
          <div style="display:flex;align-items:center;justify-content:space-between">
            <h3>Projects (Sample / Demo)</h3>
            <div class="note">These project descriptions are demo entries. Replace with your own work before sharing publicly.</div>
          </div>

          <div class="projects-grid" style="margin-top:12px">
            <!-- Project 1 -->
            <article class="project-card" data-title="DVWA Deep Dive — Web App Assessment" data-desc="Performed a simulated penetration test on DVWA (Damn Vulnerable Web App). Identified and exploited SQL injection and stored XSS vulnerabilities; documented proof-of-concept payloads and remediation recommendations. Tools used: Burp Suite, sqlmap, OWASP ZAP." data-tools="Burp Suite • sqlmap • OWASP ZAP" data-links="#">
              <h4>DVWA Deep Dive — Web App Assessment</h4>
              <p class="muted">Simulated pentest against DVWA. Demo report & POCs.</p>
              <div class="meta">
                <span class="pill">Web App Security</span>
                <button class="viewBtn btn" onclick="openModal(this)">View</button>
              </div>
            </article>

            <!-- Project 2 -->
            <article class="project-card" data-title="Internal Network Audit — Virtual Lab" data-desc="Conducted internal network audit in a lab environment. Mapped network using Nmap, enumerated services, and demonstrated lateral movement using misconfigured Samba shares. Generated hardening checklist for Linux servers." data-tools="Nmap • Metasploit • Wireshark" data-links="#">
              <h4>Internal Network Audit — Virtual Lab</h4>
              <p class="muted">Network discovery, service enumeration, and lateral movement simulation.</p>
              <div class="meta">
                <span class="pill">Network Security</span>
                <button class="viewBtn btn" onclick="openModal(this)">View</button>
              </div>
            </article>

            <!-- Project 3 -->
            <article class="project-card" data-title="CTF: Web Exploitation Writeups" data-desc="Collection of CTF-style web exploitation writeups covering XSS, CSRF, and insecure deserialization. For each challenge, I include steps, payloads, and mitigation guidance." data-tools="Custom Python Scripts • Burp Suite" data-links="#">
              <h4>CTF: Web Exploitation Writeups</h4>
              <p class="muted">Organized writeups for multiple CTF web challenges with POCs and fixes.</p>
              <div class="meta">
                <span class="pill">CTF / Research</span>
                <button class="viewBtn btn" onclick="openModal(this)">View</button>
              </div>
            </article>

            <!-- Project 4 -->
            <article class="project-card" data-title="SIEM Demo: Centralized Log Monitoring" data-desc="Built a small SIEM lab using open-source tools. Aggregated logs from multiple hosts, created correlation rules to detect brute-force and suspicious lateral-authentication attempts, and tested alerting with simulated attacks." data-tools="Elastic Stack • Wazuh • Logstash" data-links="#">
              <h4>SIEM Demo: Centralized Log Monitoring</h4>
              <p class="muted">Log ingestion, correlation rules, and alerting demo for common attack patterns.</p>
              <div class="meta">
                <span class="pill">Detection Engineering</span>
                <button class="viewBtn btn" onclick="openModal(this)">View</button>
              </div>
            </article>

            <!-- Project 5 -->
            <article class="project-card" data-title="Secure Dev: CI/CD Security Pipeline" data-desc="Prototype CI/CD pipeline with security gates: SAST scanning, dependency vulnerability checks, and container image scanning. Documented how to remediate critical findings and enforce policies on PRs." data-tools="GitHub Actions • Trivy • Bandit" data-links="#">
              <h4>Secure Dev: CI/CD Security Pipeline</h4>
              <p class="muted">Automated code checks and container scanning in CI to prevent vulnerabilities entering production.</p>
              <div class="meta">
                <span class="pill">DevSecOps</span>
                <button class="viewBtn btn" onclick="openModal(this)">View</button>
              </div>
            </article>
          </div>
        </section>

        <section id="certs" class="panel section">
          <h3>Certifications & Practice</h3>
          <div class="row" style="margin-bottom:8px">
            <div class="pill">TryHackMe • Active Learner</div>
            <div class="pill">Hack The Box • Intermediate</div>
            <div class="pill">CompTIA Security+ (Study)</div>
          </div>
          <p class="muted">Add any real certifications and links (PDF / verification links) here when you obtain them.</p>
        </section>

        <footer>
          <div class="muted">Want this template customized? Replace demo project entries with your real projects and update contact links.</div>
        </footer>
      </div>

      <!-- RIGHT: aside -->
      <aside>
        <div class="card-side panel">
          <h3>Contact</h3>
          <div class="contact-line"><strong>Email</strong><div class="spacer"></div><a href="mailto:youremail@example.com" style="color:var(--accent);font-weight:700">youremail@example.com</a></div>
          <div class="contact-line"><strong>Location</strong><div class="spacer"></div><span class="muted">India</span></div>

          <div class="section">
            <h3>Quick Links</h3>
            <div class="socials" style="margin-top:8px">
              <a class="icon-btn" href="#" title="GitHub" aria-label="GitHub">GH</a>
              <a class="icon-btn" href="#" title="LinkedIn" aria-label="LinkedIn">in</a>
              <a class="icon-btn" href="#" title="CTF/Platform" aria-label="CTF">CTF</a>
            </div>
          </div>

          <div class="section">
            <h3>Resume</h3>
            <p class="muted">Add a downloadable resume file under <code>/assets/resume.pdf</code> or link directly to your hosted PDF.</p>
            <a class="btn" href="#" download>Download Resume (PDF)</a>
          </div>

          <div class="section">
            <h3>Availability</h3>
            <p class="muted">Open to internships, bug bounty, and freelance security assessments.</p>
            <div style="margin-top:8px"><a class="btn" href="#contact">Message me</a></div>
          </div>
        </div>
      </aside>
    </main>
  </div>

  <!-- Modal for projects -->
  <div id="modal" class="modal" role="dialog" aria-modal="true" aria-hidden="true">
    <div class="modal-card">
      <div style="display:flex;justify-content:space-between;align-items:center">
        <h3 id="modalTitle"></h3>
        <div>
          <button class="close" onclick="closeModal()">Close</button>
        </div>
      </div>
      <p id="modalDesc" class="muted"></p>

      <div style="margin-top:12px">
        <strong>Tools / Technologies:</strong>
        <p id="modalTools" class="muted"></p>
      </div>

      <div style="margin-top:14px">
        <strong>Sample notes / highlights</strong>
        <pre id="modalNotes">
- Overview of approach
- Key findings (e.g. CVE-XXXX-YYYY style)
- Proof-of-concept (sanitized)
- Recommendations and mitigations
        </pre>
      </div>
    </div>
  </div>

  <script>
    // Theme toggle
    const btn = document.getElementById('themeToggle');
    btn.addEventListener('click', () => {
      document.body.classList.toggle('light');
      btn.textContent = document.body.classList.contains('light') ? 'Dark Theme' : 'Light Theme';
    });

    // Project modal UI
    function openModal(el){
      // traverse up to project-card
      let card = el.closest('.project-card');
      if(!card) return;
      const title = card.getAttribute('data-title') || card.querySelector('h4').innerText;
      const desc = card.getAttribute('data-desc') || card.querySelector('p').innerText;
      const tools = card.getAttribute('data-tools') || '';

      document.getElementById('modalTitle').innerText = title;
      document.getElementById('modalDesc').innerText = desc;
      document.getElementById('modalTools').innerText = tools;
      document.getElementById('modal').classList.add('open');
      document.getElementById('modal').setAttribute('aria-hidden','false');
    }
    function closeModal(){
      document.getElementById('modal').classList.remove('open');
      document.getElementById('modal').setAttribute('aria-hidden','true');
    }
    // close on outside click
    document.getElementById('modal').addEventListener('click', (e) => {
      if(e.target.id === 'modal') closeModal();
    });

    // keyboard support
    document.addEventListener('keydown', (e) => {
      if(e.key === 'Escape') closeModal();
    });
  </script>
</body>
</html>
