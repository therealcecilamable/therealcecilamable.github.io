<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Dash — Project Whitepaper</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

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
      padding: 0;
    }

    /* ============ COVER ============ */
    .cover {
      width: 100%;
      height: 180px;
      background: #0a0a0a;
      position: relative;
      overflow: hidden;
      display: flex;
      align-items: flex-end;
    }

    .cover::after {
      content: '';
      position: absolute;
      bottom: 0;
      right: 0;
      width: 50%;
      height: 100%;
      background: #ff3c1f;
      clip-path: polygon(30% 0%, 100% 0%, 100% 100%, 0% 100%);
    }

    .cover-text {
      position: relative;
      z-index: 2;
      font-size: 10px;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: rgba(255, 255, 255, 0.5);
      font-weight: 500;
      padding: 20px 20px;
    }

    /* ============ HEADER SECTION ============ */
    .header {
      padding: 32px 20px 24px;
      background: #ffffff;
    }

    .page-icon {
      font-size: 48px;
      margin-bottom: 12px;
      display: block;
    }

    h1.page-title {
      font-size: 32px;
      font-weight: 700;
      color: #37352f;
      line-height: 1.2;
      letter-spacing: -0.02em;
      margin-bottom: 4px;
    }

    .page-subtitle {
      font-size: 15px;
      color: #9b9a97;
      margin-bottom: 24px;
      font-style: italic;
    }

    /* ============ PROPERTIES TABLE ============ */
    .properties {
      margin: 0 0 24px;
      overflow: hidden;
    }

    .prop-row {
      display: grid;
      grid-template-columns: 1fr;
      padding: 12px 0;
      border-bottom: 1px solid #f0f0f0;
    }

    .prop-row:last-child {
      border-bottom: none;
    }

    .prop-key {
      padding: 0 0 6px 0;
      font-size: 11px;
      color: #9b9a97;
      font-weight: 600;
      text-transform: uppercase;
      letter-spacing: 0.08em;
    }

    .prop-val {
      padding: 4px 0 0 0;
      font-size: 14px;
      color: #37352f;
      display: flex;
      align-items: center;
      gap: 8px;
      flex-wrap: wrap;
    }

    .tag {
      display: inline-block;
      padding: 4px 10px;
      border-radius: 3px;
      font-size: 11px;
      font-weight: 600;
      white-space: nowrap;
    }

    .tag-red {
      background: #fbe4e2;
      color: #b85450;
    }

    .tag-gray {
      background: #e3e2e0;
      color: #37352f;
    }

    .tag-green {
      background: #ddedea;
      color: #0f7b6c;
    }

    /* ============ CONTENT SECTION ============ */
    .content {
      padding: 0 20px;
    }

    /* Divider */
    hr {
      border: none;
      border-top: 1px solid #f0f0f0;
      margin: 32px 0;
    }

    /* Headings */
    h2 {
      font-size: 22px;
      font-weight: 700;
      color: #37352f;
      margin: 36px 0 16px;
      line-height: 1.3;
    }

    h3 {
      font-size: 16px;
      font-weight: 600;
      color: #37352f;
      margin: 20px 0 10px;
    }

    p {
      color: #37352f;
      margin-bottom: 14px;
      font-size: 15px;
      line-height: 1.7;
    }

    /* ============ CALLOUT BLOCKS ============ */
    .callout {
      background: transparent;
      padding: 16px 0 16px 16px;
      margin: 20px 0;
      border-left: 3px solid #37352f;
      font-size: 14px;
      color: #37352f;
      line-height: 1.7;
    }

    .callout.red {
      border-left-color: #ff3c1f;
    }

    .callout.blue {
      border-left-color: #0066cc;
    }

    .callout.green {
      border-left-color: #0f7b6c;
    }

    .callout.gold {
      border-left-color: #d4a017;
    }

    .callout strong {
      font-weight: 600;
    }

    /* ============ TOGGLE BLOCKS ============ */
    .toggle {
      border-left: 3px solid #ff3c1f;
      padding-left: 16px;
      margin: 18px 0;
    }

    .toggle-title {
      font-size: 11px;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 0.1em;
      color: #ff3c1f;
      margin-bottom: 8px;
    }

    .toggle-body {
      font-size: 14px;
      color: #6b6b6b;
      line-height: 1.7;
    }

    /* ============ FEATURE GRID ============ */
    .feature-grid {
      display: grid;
      grid-template-columns: 1fr;
      gap: 16px;
      margin: 24px 0;
    }

    .feature-card {
      padding: 16px 0;
      background: transparent;
      transition: all 0.2s ease;
    }

    .feature-card-label {
      font-size: 11px;
      font-weight: 700;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: #ff3c1f;
      margin-bottom: 6px;
    }

    .feature-card-title {
      font-size: 15px;
      font-weight: 600;
      color: #37352f;
      margin-bottom: 6px;
    }

    .feature-card-desc {
      font-size: 13px;
      color: #9b9a97;
      line-height: 1.6;
    }

    /* ============ STAT CARDS ============ */
    .stat-row {
      display: grid;
      grid-template-columns: 1fr;
      gap: 16px;
      margin: 24px 0;
    }

    .stat-card {
      background: transparent;
      padding: 16px 0;
      text-align: left;
    }

    .stat-num {
      font-size: 32px;
      font-weight: 700;
      color: #ff3c1f;
      line-height: 1;
      margin-bottom: 6px;
    }

    .stat-label {
      font-size: 12px;
      color: #9b9a97;
      font-weight: 600;
      text-transform: uppercase;
      letter-spacing: 0.05em;
    }

    /* ============ LISTS ============ */
    ol.notion-list {
      padding-left: 20px;
      margin: 12px 0 18px;
    }

    ol.notion-list li {
      font-size: 15px;
      color: #37352f;
      margin-bottom: 12px;
      line-height: 1.7;
      padding-left: 8px;
    }

    ol.notion-list li strong {
      font-weight: 600;
      color: #37352f;
    }

    /* ============ BLOCKQUOTE ============ */
    blockquote {
      border-left: 3px solid #37352f;
      padding-left: 16px;
      margin: 20px 0;
      font-style: italic;
      color: #6b6b6b;
      font-size: 15px;
      line-height: 1.7;
    }

    /* ============ FOOTER ============ */
    .page-footer {
      margin-top: 48px;
      padding: 24px 0 40px;
      border-top: 1px solid #f0f0f0;
      font-size: 11px;
      color: #c1c1be;
      text-align: center;
      letter-spacing: 0.05em;
    }

    /* ============ TABLET BREAKPOINT ============ */
    @media (min-width: 640px) {
      .page {
        padding: 0;
      }

      .header {
        padding: 48px 40px 32px;
      }

      .content {
        padding: 0 40px;
      }

      .properties {
        margin: 0 0 32px;
      }

      .prop-row {
        grid-template-columns: 160px 1fr;
        gap: 16px;
        padding: 14px 0;
      }

      .prop-key {
        padding: 0;
      }

      .prop-val {
        padding: 0;
      }

      .feature-grid {
        grid-template-columns: 1fr 1fr;
        gap: 20px;
      }

      .stat-row {
        grid-template-columns: repeat(3, 1fr);
        gap: 20px;
      }

      .stat-card {
        text-align: center;
      }

      h2 {
        font-size: 24px;
        margin: 40px 0 18px;
      }

      .page-footer {
        padding: 32px 0 60px;
      }
    }

    /* ============ DESKTOP BREAKPOINT ============ */
    @media (min-width: 768px) {
      .page {
        max-width: 720px;
        margin: 0 auto;
      }

      .header {
        padding: 64px 40px 40px;
      }

      .content {
        padding: 0 40px;
      }

      .cover-text {
        padding: 28px 40px;
      }

      h1.page-title {
        font-size: 40px;
      }

      h2 {
        font-size: 26px;
        margin: 48px 0 20px;
      }

      .page-footer {
        padding: 40px 0 80px;
      }
    }
  </style>
</head>
<body>

  <div class="cover">
    <div class="cover-text">Project Whitepaper — Confidential</div>
  </div>

  <div class="page">
    <div class="header">
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
          <div class="prop-val"><span class="tag tag-red">ATF AI Challenge 2026</span> <span class="tag tag-green">Finance Track</span></div>
        </div>
        <div class="prop-row">
          <div class="prop-key">Status</div>
          <div class="prop-val"><span class="tag tag-gray">Confidential</span></div>
        </div>
      </div>
    </div>

    <div class="content">
      <hr>

      <!-- 1. EXECUTIVE SUMMARY -->
      <h2>1. Executive Summary</h2>

      <p>Dash is a hyper-local campus super-app designed to serve the student community at Ghana Communication Technology University (GCTU). It addresses a set of persistent, unmet needs in the daily lives of Ghanaian university students — needs that currently go unsolved or are handled through informal, unsafe, and inefficient channels.</p>

      <div class="callout blue">
        The platform brings together several interconnected services under one trusted, verified ecosystem: peer-to-peer trade, academic resource sharing, student skill services, verified employment opportunities, accommodation listings, and a first-of-its-kind AI-assisted campus navigation layer.
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
        Trust infrastructure includes: institutional email verification, a peer reputation system, an affiliate accountability model, SRC-backed employment verification, and physical Safe Zone meetup points surfaced through the mapping layer.
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
        <strong>Mobile Money advantage:</strong> Ghana's MoMo penetration across MTN, Telecel, and AirtelTigo networks provides the payment infrastructure on which Dash is built. Frictionless in-app transactions are achievable without requiring bank accounts or formal financial identity.
      </div>

      <p>The campus economy that Dash seeks to formalise already exists — it is simply unstructured and unsafe. Students already sell, hire, and trade with one another daily. Dash does not need to create behaviour; it needs to provide the infrastructure for behaviour that is already happening.</p>

      <blockquote>This is a significant product-market fit advantage. The demand is proven. The supply exists. The platform is the missing layer.</blockquote>

      <hr>

      <!-- 6. COMPETITION -->
      <h2>6. ATF AI Challenge — Competition Alignment</h2>

      <h3>6.1 Finance Track Fit</h3>
      <div class="callout red">
        Dash addresses financial exclusion at the student level. It enables peer micro-transactions, creates student income streams through gig services and academic content, connects students to verified employment, and brings structure to an informal campus economy.
      </div>

      <h3>6.2 AI Application</h3>
      <p>The AI component of Dash is the <strong>Dash Map</strong> — a crowd-sourced, computer vision-assisted campus navigation layer. Students contribute scan data through their phone cameras as they move around campus. This data is processed by an AI pipeline to construct and continuously refine a spatial map, powering live walking navigation for safe trade meetups.</p>

      <div class="callout">
        The AI application is purposeful, not decorative. It solves a specific problem — campus navigation for safe commerce — and is deeply integrated with the financial activity taking place on the platform. The community-powered data model creates a network effect: more students scanning means a more valuable map for everyone.
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
        Dash represents an opportunity to build foundational infrastructure for the campus economies of Ghanaian universities — starting at GCTU and expanding from a position of demonstrated trust and adoption.
      </div>

      <div class="page-footer">
        Confidential — All rights reserved · GCTU · ATF AI Challenge 2026
      </div>
    </div>
  </div>

</body>
</html>
