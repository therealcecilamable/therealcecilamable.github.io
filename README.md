<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Dash — Project Whitepaper</title>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }
 
  body {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    background: #ffffff;
    color: #37352f;
    font-size: 16px;
    line-height: 1.6;
  }
 
  .page {
    max-width: 720px;
    margin: 0 auto;
    padding: 96px 96px 200px;
  }
 
  /* Cover */
  .cover {
    width: 100%;
    height: 220px;
    background: #0a0a0a;
    margin-bottom: 0;
    position: relative;
    overflow: hidden;
  }
 
  .cover::after {
    content: '';
    position: absolute;
    bottom: 0; right: 0;
    width: 300px; height: 220px;
    background: #ff3c1f;
    clip-path: polygon(40% 0%, 100% 0%, 100% 100%, 0% 100%);
  }
 
  .cover-text {
    position: absolute;
    bottom: 28px; left: 96px;
    font-size: 11px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: rgba(255,255,255,0.4);
    font-weight: 500;
    z-index: 2;
  }
 
  /* Page icon + title */
  .page-icon {
    font-size: 60px;
    margin-top: -30px;
    margin-bottom: 16px;
    display: block;
    position: relative;
    z-index: 3;
  }
 
  h1.page-title {
    font-size: 40px;
    font-weight: 700;
    color: #37352f;
    line-height: 1.2;
    letter-spacing: -0.02em;
    margin-bottom: 8px;
  }
 
  .page-subtitle {
    font-size: 16px;
    color: #9b9a97;
    margin-bottom: 32px;
    font-style: italic;
  }
 
  /* Properties table */
  .properties {
    border: 1px solid #e9e9e7;
    border-radius: 4px;
    margin-bottom: 40px;
    overflow: hidden;
  }
 
  .prop-row {
    display: grid;
    grid-template-columns: 160px 1fr;
    border-bottom: 1px solid #e9e9e7;
  }
 
  .prop-row:last-child { border-bottom: none; }
 
  .prop-key {
    padding: 8px 12px;
    font-size: 13px;
    color: #9b9a97;
    font-weight: 500;
    background: #f7f6f3;
    display: flex;
    align-items: center;
    gap: 6px;
  }
 
  .prop-val {
    padding: 8px 12px;
    font-size: 13px;
    color: #37352f;
    display: flex;
    align-items: center;
    gap: 6px;
  }
 
  .tag {
    display: inline-block;
    padding: 2px 8px;
    border-radius: 4px;
    font-size: 12px;
    font-weight: 500;
  }
 
  .tag-red   { background: #fbe4e2; color: #b85450; }
  .tag-gray  { background: #e3e2e0; color: #37352f; }
  .tag-green { background: #ddedea; color: #0f7b6c; }
 
  /* Divider */
  hr {
    border: none;
    border-top: 1px solid #e9e9e7;
    margin: 32px 0;
  }
 
  /* Headings */
  h2 {
    font-size: 20px;
    font-weight: 600;
    color: #37352f;
    margin: 40px 0 12px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
 
  h3 {
    font-size: 16px;
    font-weight: 600;
    color: #37352f;
    margin: 24px 0 8px;
  }
 
  p {
    color: #37352f;
    margin-bottom: 12px;
    font-size: 15px;
    line-height: 1.7;
  }
 
  /* Callout */
  .callout {
    display: flex;
    gap: 12px;
    background: #f1f1ef;
    border-radius: 4px;
    padding: 16px;
    margin: 16px 0;
    align-items: flex-start;
  }
 
  .callout.red   { background: #fbe4e2; }
  .callout.blue  { background: #e8f3fb; }
  .callout.green { background: #ddedea; }
  .callout.gold  { background: #fef3cd; }
 
  .callout-icon { font-size: 18px; flex-shrink: 0; margin-top: 1px; }
 
  .callout-body { font-size: 14px; color: #37352f; line-height: 1.6; }
  .callout-body strong { font-weight: 600; }
 
  /* Toggle-style section (visual only) */
  .toggle {
    border-left: 3px solid #ff3c1f;
    padding-left: 16px;
    margin: 16px 0;
  }
 
  .toggle-title {
    font-size: 13px;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    color: #ff3c1f;
    margin-bottom: 6px;
  }
 
  .toggle-body {
    font-size: 14px;
    color: #6b6b6b;
    line-height: 1.7;
  }
 
  /* Feature cards grid */
  .feature-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
    margin: 16px 0;
  }
 
  .feature-card {
    border: 1px solid #e9e9e7;
    border-radius: 6px;
    padding: 14px 16px;
    background: #fbfaf8;
    transition: background 0.15s;
  }
 
  .feature-card:hover { background: #f1f0ee; }
 
  .feature-card-label {
    font-size: 10px;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: #ff3c1f;
    margin-bottom: 4px;
  }
 
  .feature-card-title {
    font-size: 14px;
    font-weight: 600;
    color: #37352f;
    margin-bottom: 4px;
  }
 
  .feature-card-desc {
    font-size: 12px;
    color: #9b9a97;
    line-height: 1.5;
  }
 
  /* Numbered list */
  ol.notion-list {
    padding-left: 24px;
    margin: 8px 0 16px;
  }
 
  ol.notion-list li {
    font-size: 15px;
    color: #37352f;
    margin-bottom: 8px;
    line-height: 1.6;
    padding-left: 4px;
  }
 
  ol.notion-list li strong {
    font-weight: 600;
  }
 
  /* Quote block */
  blockquote {
    border-left: 3px solid #37352f;
    padding-left: 16px;
    margin: 20px 0;
    font-style: italic;
    color: #6b6b6b;
    font-size: 15px;
    line-height: 1.7;
  }
 
  /* Stat row */
  .stat-row {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 10px;
    margin: 16px 0;
  }
 
  .stat-card {
    background: #f7f6f3;
    border-radius: 6px;
    padding: 16px;
    text-align: center;
  }
 
  .stat-num {
    font-size: 28px;
    font-weight: 700;
    color: #ff3c1f;
    line-height: 1;
    margin-bottom: 4px;
  }
 
  .stat-label {
    font-size: 12px;
    color: #9b9a97;
    font-weight: 500;
  }
 
  /* Footer */
  .page-footer {
    margin-top: 64px;
    padding-top: 24px;
    border-top: 1px solid #e9e9e7;
    font-size: 12px;
    color: #c1c1be;
    text-align: center;
  }
 
  @media (max-width: 768px) {
    .page { padding: 48px 24px 120px; }
    .cover-text { left: 24px; }
    .feature-grid { grid-template-columns: 1fr; }
    .stat-row { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>
 
<div class="cover">
  <div class="cover-text">Project Whitepaper — Confidential</div>
</div>
 
<div class="page">
  
  <h1 class="page-title">Dash</h1>
  <p class="page-subtitle">Your Campus, Connected.</p>
 
  <div class="properties">
    <div class="prop-row">
      <div class="prop-key">Codename</div>
      <div class="prop-val"><span class="tag tag-gray">Dash</span></div>
    </div>
    <div class="prop-row">
      <div class="prop-key">Category</div>
      <div class="prop-val">P2P Web Marketplace & Campus Utility Platform</div>
    </div>
    <div class="prop-row">
      <div class="prop-key">Target</div>
      <div class="prop-val">Ghana Communication Technology University (GCTU)</div>
    </div>
    <div class="prop-row">
      <div class="prop-key">Competition</div>
      <div class="prop-val"><span class="tag tag-red">ATF AI Challenge 2026</span> &nbsp;<span class="tag tag-green">Finance Track</span></div>
    </div>
    <div class="prop-row">
      <div class="prop-key">Status</div>
      <div class="prop-val"><span class="tag tag-gray">Confidential</span></div>
    </div>
  </div>
 
  <hr>
 
  <!-- 1. EXECUTIVE SUMMARY -->
  <h2>1. Executive Summary</h2>
 
  <p>Dash is a hyper-local campus super-app designed to serve the student community at Ghana Communication Technology University (GCTU). It addresses a set of persistent, unmet needs in the daily lives of Ghanaian university students — needs that currently go unsolved or are handled through informal, unsafe, and inefficient channels.</p>
 
  <div class="callout blue">
    <div class="callout-body">The platform brings together several interconnected services under one trusted, verified ecosystem: peer-to-peer trade, academic resource sharing, student skill services, verified employment opportunities, accommodation listings, and a first-of-its-kind AI-assisted campus navigation layer.</div>
  </div>
 
  <p>Each component is designed around the real behaviour of Ghanaian university students and the constraints they operate under — including limited mobile data, reliance on Mobile Money, and the absence of formal institutional support structures for everyday commerce and opportunity.</p>
 
  <p>Dash is submitted under the Finance Track of the ATF AI Challenge 2026. The platform directly addresses financial exclusion at the student level — creating infrastructure for a campus economy that enables peer income, verified employment pathways, and structured micro-transactions for an underserved demographic.</p>
 
  <hr>
 
  <!-- 2. PROBLEM STATEMENT -->
  <h2>2. Problem Statement</h2>
 
  <p>University students in Ghana represent a digitally active, economically engaged demographic that is nonetheless excluded from formal commercial and financial infrastructure. The problems they face are not abstract — they manifest daily in the form of missed opportunities, unsafe transactions, and a lack of trusted platforms built for their specific context.</p>
 
  <h3>2.1 Fragmented, Untrustworthy Commerce</h3>
  <div class="toggle">
    <div class="toggle-title">The Problem</div>
    <div class="toggle-body">The dominant channel for student-to-student commerce at GCTU is WhatsApp. While accessible, this medium offers no searchability, no seller verification, no transaction history, and no recourse in the event of fraud. A student selling a laptop reaches only their immediate contacts. The informal nature of this system limits reach, erodes trust, and makes every transaction a matter of personal risk.</div>
  </div>
 
  <h3>2.2 The Accommodation Crisis</h3>
  <div class="toggle">
    <div class="toggle-title">The Problem</div>
    <div class="toggle-body">Finding housing near campus is one of the most stressful experiences for students, particularly first-year intake. There is no verified, centralised listing of hostels near GCTU. Students rely on word of mouth, physical scouting, or connections through older students — with no standardised way to compare options, verify legitimacy, or transfer bookings between students.</div>
  </div>
 
  <h3>2.3 Informal and Unverified Job Access</h3>
  <div class="toggle">
    <div class="toggle-title">The Problem</div>
    <div class="toggle-body">Internship and job opportunities reach GCTU students through informal channels — WhatsApp forwards, physical notice boards, or connections through lecturers. There is no platform where students can trust that a listed opportunity is real, relevant, and vetted. The SRC already plays an informal vetting role but without a structured platform, their reach and impact is limited.</div>
  </div>
 
  <h3>2.4 Campus Navigation Gaps</h3>
  <div class="toggle">
    <div class="toggle-title">The Problem</div>
    <div class="toggle-body">GCTU's physical campus is inadequately represented on existing mapping tools. For new students, navigating to buildings or meeting points is a genuine challenge. When students agree to meet for a trade, there is no standardised, safe way to coordinate a physical meetup — creating friction for every offline transaction and, in some cases, safety concerns.</div>
  </div>
 
  <hr>
 
  <!-- 3. PRODUCT OVERVIEW -->
  <h2>3. Product Overview</h2>
 
  <p>Dash is a mobile-first web platform that unifies the core commerce and utility needs of GCTU students into a single trusted ecosystem. Its scope, verification system, and feature set are deliberately tailored to the GCTU context, with a view to replication at other universities as the platform matures.</p>
 
  <blockquote>The platform is built around three principles: trust through verification, access through simplicity, and community through participation.</blockquote>
 
  <div class="stat-row">
    <div class="stat-card">
      <div class="stat-num">6</div>
      <div class="stat-label">Core Features</div>
    </div>
    <div class="stat-card">
      <div class="stat-num">3</div>
      <div class="stat-label">Account Types</div>
    </div>
    <div class="stat-card">
      <div class="stat-num">1</div>
      <div class="stat-label">Unified Platform</div>
    </div>
  </div>
 
  <h3>3.1 Core Service Areas</h3>
  <p>Dash addresses six distinct student needs through integrated platform features — from peer-to-peer trade and academic resources, to gigs, verified employment, accommodation, and AI-assisted campus navigation.</p>
 
  <h3>3.2 Account Structure</h3>
  <p>Three distinct account types operate within the platform, each with defined permissions and verification requirements. Student accounts form the core user base. Business accounts allow external entities to participate through a verified student affiliate. The SRC holds an institutional account with elevated trust permissions.</p>
 
  <h3>3.3 Trust and Safety Architecture</h3>
  <div class="callout gold">
    <div class="callout-body">Trust infrastructure includes: institutional email verification, a peer reputation system, an affiliate accountability model, SRC-backed employment verification, and physical Safe Zone meetup points surfaced through the mapping layer.</div>
  </div>
 
  <hr>
 
  <!-- 4. FEATURES -->
  <h2>4. Feature Summary</h2>
 
  <p>The following is a high-level summary of the six core platform features. Technical implementation details are withheld from this document.</p>
 
  <div class="feature-grid">
    <div class="feature-card">
      <div class="feature-card-label">Market</div>
      <div class="feature-card-title">Dash Market</div>
      <div class="feature-card-desc">Searchable, structured classifieds for student-to-student trade of physical goods. Replaces WhatsApp-based selling.</div>
    </div>
    <div class="feature-card">
      <div class="feature-card-label">Knowledge</div>
      <div class="feature-card-title">Dash Notes</div>
      <div class="feature-card-desc">Micro-transaction hub for academic resources — Pascos and exam summaries purchased via Mobile Money.</div>
    </div>
    <div class="feature-card">
      <div class="feature-card-label">Services</div>
      <div class="feature-card-title">Dash Gigs</div>
      <div class="feature-card-desc">Student services directory connecting skill providers with peers who need tasks done.</div>
    </div>
    <div class="feature-card">
      <div class="feature-card-label">Employment · SRC Verified</div>
      <div class="feature-card-title">Dash Jobs</div>
      <div class="feature-card-desc">Verified internship and job board — listings reviewed and approved by the SRC before going live.</div>
    </div>
    <div class="feature-card">
      <div class="feature-card-label">Accommodation</div>
      <div class="feature-card-title">Dash Hostels</div>
      <div class="feature-card-desc">Verified hostel listings through the student affiliate system. Room sublet and transfer supported.</div>
    </div>
    <div class="feature-card">
      <div class="feature-card-label">AI Core</div>
      <div class="feature-card-title">Dash Map</div>
      <div class="feature-card-desc">Crowd-sourced, AI-powered campus navigation layer built by student camera scans, with live arrow-based meetup directions.</div>
    </div>
  </div>
 
  <hr>
 
  <!-- 5. MARKET CONTEXT -->
  <h2>5. Market Context & Opportunity</h2>
 
  <p>GCTU is one of Ghana's foremost technology-focused public universities, with a student body that is digitally literate, mobile-first, and economically active. Students represent a captive, high-trust community with regular, repeated transactional needs.</p>
 
  <div class="callout green">
    <div class="callout-body"><strong>Mobile Money advantage:</strong> Ghana's MoMo penetration across MTN, Telecel, and AirtelTigo networks provides the payment infrastructure on which Dash is built. Frictionless in-app transactions are achievable without requiring bank accounts or formal financial identity.</div>
  </div>
 
  <p>The campus economy that Dash seeks to formalise already exists — it is simply unstructured and unsafe. Students already sell, hire, and trade with one another daily. Dash does not need to create behaviour; it needs to provide the infrastructure for behaviour that is already happening.</p>
 
  <blockquote>This is a significant product-market fit advantage. The demand is proven. The supply exists. The platform is the missing layer.</blockquote>
 
  <hr>
 
  <!-- 6. COMPETITION -->
  <h2>6. ATF AI Challenge — Competition Alignment</h2>
 
  <h3>6.1 Finance Track Fit</h3>
  <div class="callout red">
    <div class="callout-body">Dash addresses financial exclusion at the student level. It enables peer micro-transactions, creates student income streams through gig services and academic content, connects students to verified employment, and brings structure to an informal campus economy.</div>
  </div>
 
  <h3>6.2 AI Application</h3>
  <p>The AI component of Dash is the <strong>Dash Map</strong> — a crowd-sourced, computer vision-assisted campus navigation layer. Students contribute scan data through their phone cameras as they move around campus. This data is processed by an AI pipeline to construct and continuously refine a spatial map, powering live walking navigation for safe trade meetups.</p>
 
  <div class="callout">
    <div class="callout-body">The AI application is purposeful, not decorative. It solves a specific problem — campus navigation for safe commerce — and is deeply integrated with the financial activity taking place on the platform. The community-powered data model creates a network effect: more students scanning means a more valuable map for everyone.</div>
  </div>
 
  <h3>6.3 Innovation Positioning</h3>
  <p>The Dash Map represents a novel application of crowd-sourced spatial intelligence in a campus commerce context. No comparable product exists for Ghanaian university campuses. The combination of a peer marketplace with a community-built navigation layer — incentivised through a rewards system — is a distinct and defensible product position.</p>
 
  <hr>
 
  <!-- 7. ROADMAP -->
  <h2>7. Phased Rollout Plan</h2>
 
  <ol class="notion-list">
    <li><strong>Beta Launch</strong> — Focused 3-week pilot with BSc IT students. Dash Market and Dash Map scanning go live. Objective: validate core trade flows and begin accumulating map data.</li>
    <li><strong>SRC Integration</strong> — Formal onboarding of the SRC as institutional affiliate. Dash Jobs launches with the SRC verification pipeline active.</li>
    <li><strong>Full Platform Launch</strong> — All six features active for the GCTU student body. Business accounts open. Dash Hostels and Dash Gigs go live.</li>
    <li><strong>Map Completion</strong> — Dash Map scanning extended across the full GCTU Tesano campus. Safe Zone meetup points established platform-wide.</li>
    <li><strong>Scale</strong> — Rollout to additional technology-focused universities in Accra, replicating the SRC affiliate model at each new campus.</li>
  </ol>
 
  <hr>
 
  <!-- 8. CLOSING -->
  <h2>8. Closing Statement</h2>
 
  <p>Dash is not a speculative product. It addresses documented, daily problems experienced by thousands of students at GCTU — problems that existing platforms do not solve and that the informal workarounds in current use are inadequate to address.</p>
 
  <p>The platform is built on a clear understanding of its users, their constraints, and their existing behaviours. It is financially grounded — designed around payment infrastructure that already exists and commerce that already happens. Its AI component is applied to a real problem, not retrofitted for appearances.</p>
 
  <div class="callout blue">
    <div class="callout-body">Dash represents an opportunity to build foundational infrastructure for the campus economies of Ghanaian universities — starting at GCTU and expanding from a position of demonstrated trust and adoption.</div>
  </div>
 
  <div class="page-footer">
    Confidential — All rights reserved &nbsp;·&nbsp; GCTU &nbsp;·&nbsp; ATF AI Challenge 2026
  </div>
 
</div>
</body>
</html>
 
