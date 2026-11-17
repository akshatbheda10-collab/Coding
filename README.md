<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta name="description" content="A friendly, searchable starter guide to Python, HTML, CSS, and JavaScript.">
  <title>Code Club | Beginner Cheat Sheet</title>
  <style>
    :root {
      color-scheme: light;
      --ink: #18233b; --muted: #52617a; --paper: #f5f7fb; --card: #fff;
      --line: #dce3ef; --blue: #3157d5; --blue-pale: #eaf0ff;
      --purple: #7352ce; --green: #19835f; --orange: #b95918;
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    }
    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; scroll-padding-top: 100px; }
    body { margin: 0; color: var(--ink); background: var(--paper); line-height: 1.6; }
    a { color: inherit; }
    button, input { font: inherit; }
    button:focus-visible, a:focus-visible, input:focus-visible { outline: 3px solid #f1ae43; outline-offset: 3px; }
.app-view[hidden] { display: none !important; }

    .view-switcher { position: sticky; top: 0; z-index: 30; display: flex; gap: 8px; overflow-x: auto; padding: 9px max(12px, calc((100vw - 1080px) / 2)); background: #fffffff5; border-bottom: 1px solid var(--line); backdrop-filter: blur(12px); }
    .view-switcher button { flex: 0 0 auto; padding: 8px 13px; border: 1px solid var(--line); border-radius: 999px; color: var(--muted); background: white; font-weight: 750; cursor: pointer; }
    .view-switcher button[aria-pressed="true"] { color: white; background: var(--blue); border-color: var(--blue); }
    .view-switcher button:hover { border-color: var(--blue); }
    .app-view[hidden] { display: none !important; }
    .planner-section { width: min(1080px, 100% - 36px); margin: 28px auto; padding: 18px; border: 1px solid var(--line); border-radius: 16px; background: white; }
    .planner-section h2 { margin: 0 0 6px; font-size: 1.5rem; }
    .planner-section p { margin: 0 0 14px; color: var(--muted); }
    .planner-frame { display: block; width: 100%; height: min(88vh, 1000px); min-height: 620px; border: 1px solid var(--line); border-radius: 12px; background: #f6f6fa; }
    nav a.planner-link { color: var(--blue); background: var(--blue-pale); border: 1px solid #d8e2ff; }
    nav a.planner-link:hover { background: #dce6ff; }
.hero { color: white; background: radial-gradient(ellipse at 88% 10%, #788cf2 0, transparent 34%), linear-gradient(125deg, #182d67, #3157d5 72%, #5669d4); padding: 42px 20px 38px; }
    .hero-inner, main, .nav-inner { width: min(1080px, 100% - 36px); margin-inline: auto; }
    .eyebrow { margin: 0 0 8px; font-size: .78rem; font-weight: 800; letter-spacing: .14em; text-transform: uppercase; opacity: .85; }
    h1 { margin: 0; font-size: clamp(2rem, 5vw, 3.3rem); line-height: 1.08; letter-spacing: -.04em; }
    .hero p:last-child { max-width: 660px; margin: 15px 0 0; color: #e4eaff; font-size: 1.08rem; }
    .sticky { position: sticky; z-index: 5; top: 52px; background: #fffffff2; border-bottom: 1px solid var(--line); backdrop-filter: blur(12px); }
    .nav-inner { display: flex; align-items: center; gap: 10px; padding-block: 10px; }
    .nav-label { flex: none; font-size: .82rem; font-weight: 800; color: var(--muted); }
    nav { display: flex; gap: 6px; overflow-x: auto; flex: 1; }
    nav a { flex: 0 0 auto; text-decoration: none; padding: 8px 12px; border-radius: 999px; font-size: .9rem; font-weight: 750; color: var(--muted); }
    nav a:hover, nav a:focus-visible, nav a[aria-current="location"] { color: var(--blue); background: var(--blue-pale); }
    .search { width: min(230px, 38vw); padding: 9px 12px; border: 1px solid var(--line); border-radius: 10px; background: white; }
    main { padding: 28px 0 64px; }
    .big-idea { display: grid; grid-template-columns: repeat(3, 1fr); gap: 12px; margin-bottom: 36px; }
    .idea { padding: 16px; border: 1px solid var(--line); border-radius: 14px; background: var(--card); }
    .idea strong { display: block; margin-bottom: 3px; }
    .idea span { color: var(--muted); font-size: .91rem; }

    .reference-topics { display: grid; grid-template-columns: repeat(auto-fit, minmax(min(100%, 230px), 1fr)); gap: 10px; margin: 14px 0; }
    .reference-topic { border: 1px solid var(--line); border-radius: 10px; padding: 12px; background: #f8faff; }
    .reference-topic h3 { color: var(--blue); font-size: .95rem; }
    .reference-topic p { padding: 5px 0 0; margin: 0; color: var(--muted); font-size: .86rem; }
    .topic-detail { margin: 8px 0; border: 1px solid var(--line); border-radius: 9px; background: white; }
    .topic-detail summary { cursor: pointer; padding: 10px 12px; color: var(--blue); font-weight: 750; }
    .topic-detail .source-text { max-height: 55vh; }
    .source-reference { margin-top: 18px; border: 1px solid var(--line); border-radius: 14px; background: #fff; padding: 14px; }
    .source-reference summary { cursor: pointer; color: var(--blue); font-weight: 800; }
    .source-reference > p { margin-top: 12px; }
    .source-text { max-height: 70vh; overflow: auto; white-space: pre-wrap; overflow-wrap: anywhere; font-size: .78rem; }
    .full-reference { margin-top: 18px; border: 1px solid var(--line); border-radius: 14px; background: #fff; padding: 14px; }
    .full-reference summary { cursor: pointer; color: var(--blue); font-weight: 800; }
    .full-reference > p { margin-top: 12px; }
    .ref-group { padding: 0 !important; margin: 0 0 3px !important; color: var(--purple) !important; font-size: .72rem !important; font-weight: 800; letter-spacing: .06em; text-transform: uppercase; }
.section { padding-top: 12px; margin-top: 34px; scroll-margin-top: 84px; }
    .section-heading { display: flex; align-items: center; gap: 12px; margin-bottom: 7px; }
    .badge { display: grid; place-items: center; flex: 0 0 46px; height: 46px; border-radius: 14px; background: var(--blue-pale); color: var(--blue); font-weight: 900; font-size: 1.1rem; }
    h2 { margin: 0; font-size: clamp(1.5rem, 3vw, 2rem); letter-spacing: -.025em; }
    .section-intro { color: var(--muted); margin: 0 0 16px; }
    .cards { display: grid; grid-template-columns: repeat(auto-fit, minmax(min(100%, 310px), 1fr)); gap: 14px; align-items: start; }
    .card { overflow: hidden; background: var(--card); border: 1px solid var(--line); border-radius: 15px; box-shadow: 0 5px 18px #17264a08; }
    .card-top { display: flex; align-items: flex-start; justify-content: space-between; gap: 12px; padding: 16px 17px 9px; }
    h3 { margin: 0; font-size: 1.03rem; }
    .card p { margin: 0; padding: 0 17px 12px; color: var(--muted); font-size: .92rem; }
    pre { margin: 0; overflow-x: auto; padding: 14px 17px; background: #f1f4fa; color: #203050; border-top: 1px solid #e5eaf3; font: .86rem/1.65 ui-monospace, SFMono-Regular, Menlo, Consolas, monospace; tab-size: 2; }
    code { font-family: ui-monospace, SFMono-Regular, Menlo, Consolas, monospace; }
    .copy { border: 1px solid var(--line); background: white; border-radius: 8px; color: var(--blue); padding: 5px 9px; font-size: .78rem; font-weight: 750; cursor: pointer; }
    .copy:hover { background: var(--blue-pale); }
    .tip { margin-top: 14px; padding: 14px 16px; border-left: 4px solid #f0ad42; background: #fff7e7; border-radius: 0 10px 10px 0; color: #59420f; }
    .tip strong { color: #4c3606; }
    .empty { display: none; padding: 20px; color: var(--muted); text-align: center; }
    footer { padding: 22px; border-top: 1px solid var(--line); color: var(--muted); text-align: center; font-size: .88rem; }
    @media (max-width: 650px) {
      .hero { padding: 32px 0; }
      .hero-inner, main, .nav-inner { width: min(100% - 24px, 1080px); }
      .nav-inner { flex-wrap: wrap; }
      nav { order: 2; width: 100%; }
      .search { width: 100%; }
      .big-idea { grid-template-columns: 1fr; }
      .planner-section { width: min(100% - 24px, 1080px); padding: 10px; }
      .planner-frame { min-height: 70vh; }
      html { scroll-padding-top: 118px; }
    }
    @media (prefers-reduced-motion: reduce) { html { scroll-behavior: auto; } }
  
    /* Personal notebook: shared layout, individual saved pages */
    .planner-section {
      width: min(1120px, calc(100% - 32px));
      margin: 28px auto;
      padding: clamp(14px, 2.5vw, 28px);
      border: 1px solid #dce4f2;
      border-radius: 24px;
      background: linear-gradient(145deg, #f9fbff 0%, #fff 52%, #f5f7ff 100%);
      box-shadow: 0 18px 55px rgba(31, 53, 102, .08);
    }
    .planner-section > h2 { margin: 0 0 8px; font-size: clamp(1.4rem, 3vw, 2rem); }
    .planner-section > p { margin: 8px 0 18px; color: #63728b; }
    .notebook { display: grid; gap: 18px; min-width: 0; }
    .notebook-head {
      display: flex; align-items: center; justify-content: space-between;
      gap: 20px; flex-wrap: wrap; padding: 5px 2px;
    }
    .notebook-head h3 { margin: 0; color: #182542; font-size: clamp(1.35rem, 2.3vw, 1.8rem); letter-spacing: -.025em; }
    .notebook-head p { margin: 5px 0 0; color: #63728b; font-size: .95rem; }
    .notebook-kicker { margin-bottom: 4px; color: #385bd6; font-size: .7rem; font-weight: 850; letter-spacing: .14em; text-transform: uppercase; }
    .notebook-actions { display: flex; align-items: end; gap: 9px; flex-wrap: wrap; }
    .notebook-actions label { display: grid; gap: 5px; color: #586781; font-size: .76rem; font-weight: 750; }
    .notebook-actions select, .notebook-actions button {
      min-height: 40px; border: 1px solid #d7e0ef; border-radius: 11px;
      background: #fff; color: #253551; padding: 8px 12px;
      font: 600 .88rem/1.2 system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    }
    .notebook-actions select { max-width: min(270px, 52vw); }
    .notebook-actions button { cursor: pointer; transition: transform .15s ease, box-shadow .15s ease, background .15s ease; }
    .notebook-actions button[data-new-page] { border-color: #3157d5; background: #3157d5; color: #fff; }
    .notebook-actions button[data-delete-page] { color: #8b3c4a; }
    .notebook-actions button:hover { transform: translateY(-1px); box-shadow: 0 5px 14px rgba(31, 53, 102, .12); }
    .notebook-sheet {
      min-width: 0; padding: clamp(14px, 2.4vw, 26px);
      border: 1px solid #dce5f4; border-radius: 23px;
      background: #fff; box-shadow: 0 12px 38px rgba(31, 53, 102, .07);
    }
    .notebook-meta { display: grid; grid-template-columns: minmax(0, 1.2fr) minmax(100px, .55fr) minmax(0, 1fr); gap: 13px; margin-bottom: 18px; }
    .notebook-meta label { display: grid; gap: 6px; min-width: 0; color: #51617d; font-size: .8rem; font-weight: 750; }
    .notebook-meta input {
      width: 100%; min-width: 0; min-height: 44px; border: 1px solid #d7e0ef;
      border-radius: 11px; padding: 10px 12px; background: #fbfcff; color: #1c2945;
      font: 500 .95rem/1.3 system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      transition: border-color .15s ease, box-shadow .15s ease, background .15s ease;
    }
    .notebook-meta input:focus { border-color: #6482e7; background: #fff; outline: 0; box-shadow: 0 0 0 4px rgba(67, 97, 223, .12); }
    .editor-grid { display: block; min-width: 0; }
    .lesson-notes {
      min-width: 0; overflow: hidden; border: 1px solid #dce3ef;
      border-radius: 17px; background: #fff; box-shadow: 0 8px 28px rgba(30, 48, 88, .06);
    }
    .document-titlebar {
      display: flex; align-items: center; gap: 8px; flex-wrap: wrap;
      padding: 10px 14px 6px; background: #fff;
    }
    .doc-icon { display: grid; place-items: center; width: 32px; height: 34px; flex: none; border-radius: 8px; background: #eaf0ff; color: #3157d5; font-size: 21px; }
    .document-title {
      width: min(245px, 34%); min-width: 130px; border: 1px solid transparent; border-radius: 6px;
      padding: 6px 8px; color: #303b50; font: 550 14px system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    }
    .document-title:hover, .document-title:focus { border-color: #dce3ef; outline: 0; }
    .star-document { border: 0; border-radius: 7px; padding: 3px 7px; background: transparent; color: #7b879b; font-size: 21px; cursor: pointer; }
    .star-document[aria-pressed="true"] { color: #e2a329; }
    .document-menu { padding: 4px 5px; border-radius: 5px; color: #46536a; font-size: 11px; cursor: default; }
    .format-toolbar {
      display: flex; align-items: center; gap: 4px; flex-wrap: wrap;
      min-height: 44px; padding: 6px 11px; border-block: 1px solid #e3e8f0; background: #f7f8fa;
    }
    .format-toolbar button, .format-toolbar select {
      height: 30px; border: 1px solid transparent; border-radius: 6px;
      background: transparent; color: #39465d; font: 12px system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    }
    .format-toolbar button { min-width: 30px; padding: 4px 8px; cursor: pointer; }
    .format-toolbar button:hover, .format-toolbar select:hover { border-color: #dfe5ef; background: #eaf0f8; }
    .format-toolbar select { padding: 4px 7px; border-color: #e0e5ed; background: #fff; }
    .toolbar-divider { height: 21px; margin: 0 3px; border-left: 1px solid #d9dee7; }
    .format-toolbar .editing-pill { margin-left: auto; border-color: #dce3ef; background: #fff; color: #60708b; font-size: 10px; cursor: default; }
    .format-toolbar .insert-code-line { border-color: #cddaf9; background: #eaf0ff; color: #3157d5; font-weight: 750; white-space: nowrap; }
    .format-toolbar .insert-code-line:hover { background: #dce6ff; }
    .document-notes {
      min-height: 520px; max-height: 780px; overflow: auto; padding: 30px clamp(20px, 4vw, 58px);
      outline: none; color: #273650;
      background: repeating-linear-gradient(to bottom, #fff 0, #fff 35px, #f1f3f8 36px);
      font: 15px/2.25 Arial, system-ui, sans-serif;
    }
    .document-notes:focus { box-shadow: inset 0 0 0 2px #d8e3ff; }
    .document-notes:empty::before { content: attr(data-placeholder); white-space: pre-wrap; color: #929bad; pointer-events: none; }
    .document-notes h2 { margin: .45em 0; color: #182542; font-size: 1.5em; line-height: 1.3; }
    .document-notes h3 { margin: .45em 0; color: #30456d; font-size: 1.2em; line-height: 1.4; }
    .document-notes ul, .document-notes ol { padding-left: 1.6em; }
    .document-notes pre {
      margin: 14px 0; padding: 13px 16px; border: 1px solid #dce4f1; border-left: 4px solid #3157d5;
      border-radius: 9px; background: #f1f4fa; color: #203050; white-space: pre-wrap; overflow-wrap: anywhere;
      font: 14px/1.75 ui-monospace, SFMono-Regular, Menlo, Consolas, monospace;
    }
    .document-notes pre code { font: inherit; color: inherit; }
    .notebook-status { margin-top: 12px; padding: 9px 13px; border: 1px solid #e1e8f2; border-radius: 10px; background: #f9fbff; color: #61718a; font-size: 12px; }
    .planner-frame { display: block; width: 100%; height: min(88vh, 1000px); min-height: 620px; border: 1px solid #dce3ef; border-radius: 14px; background: #f6f6fa; }
    button:focus-visible, input:focus-visible, select:focus-visible, [contenteditable="true"]:focus-visible { outline: 3px solid #f1ae43; outline-offset: 2px; }
    @media (max-width: 760px) {
      .planner-section { width: min(100% - 20px, 1120px); padding: 12px; border-radius: 18px; }
      .notebook-head { align-items: stretch; }
      .notebook-actions { display: grid; grid-template-columns: minmax(0, 1fr) auto auto; align-items: end; }
      .notebook-actions label { grid-column: 1 / -1; }
      .notebook-actions select { width: 100%; max-width: none; }
      .notebook-meta { grid-template-columns: minmax(0, 1fr) minmax(84px, .55fr); }
      .notebook-meta .filename { grid-column: 1 / -1; }
      .document-titlebar { gap: 5px; padding-inline: 9px; }
      .document-title { flex: 1; width: auto; }
      .document-menu { font-size: 10px; }
      .document-notes { min-height: 400px; padding: 22px 20px; }
      .format-toolbar .editing-pill { margin-left: 0; }
    }
    @media (max-width: 480px) {
      .notebook-actions { grid-template-columns: 1fr 1fr; }
      .notebook-actions label { grid-column: 1 / -1; }
      .notebook-actions button { min-width: 0; padding-inline: 8px; font-size: .78rem; }
      .document-menu { padding-inline: 3px; font-size: 9px; }
      .document-notes { min-height: 340px; font-size: 14px; }
      .format-toolbar { gap: 2px; padding-inline: 7px; }
      .format-toolbar button { min-width: 27px; padding-inline: 5px; }
    }
    @media (prefers-reduced-motion: reduce) { .notebook-actions button { transition: none; } }


    .docs-workspace-frame{display:block;width:100%;height:min(94vh,1120px);min-height:760px;border:1px solid #d9e1ee;border-radius:18px;background:#f9fbfd;box-shadow:0 10px 34px rgba(24,43,83,.08)}
    @media(max-width:760px){.docs-workspace-frame{height:88vh;min-height:620px;border-radius:12px}.course-planner-intro{margin-top:22px!important}}

  </style>
</head>
<body>
  <nav class="view-switcher" aria-label="Choose a section">
    <button type="button" data-view="cheatsheet-view" aria-pressed="true">📚 Cheat Sheet</button>
    <button type="button" data-view="nikhil-planner" aria-pressed="false">📓 Nikhil’s Notebook</button>
    <button type="button" data-view="akshat-planner" aria-pressed="false">📓 Akshat’s Notebook</button>
  </nav>
  <div class="app-view" id="cheatsheet-view">
  <header class="hero">
    <div class="hero-inner">
      <p class="eyebrow">A friendly starter guide</p>
      <h1>Code Club Cheat Sheet</h1>
      <p>Four coding tools, explained in small steps. Read an example, change it, and see what happens. You do not have to memorize everything.</p>
    </div>
  </header>
  <div class="sticky">
    <div class="nav-inner">
      <span class="nav-label">Jump to a language:</span>
      <nav aria-label="Jump to a language">
        <a href="#python">🐍 Python</a><a href="#html">🧱 HTML</a><a href="#css">🎨 CSS</a><a href="#javascript">⚡ JavaScript</a>
        <a class="planner-link" href="#nikhil-planner" data-view="nikhil-planner">Nikhil’s Notebook</a>
        <a class="planner-link" href="#akshat-planner" data-view="akshat-planner">Akshat’s Notebook</a>
      </nav>
      <input class="search" id="search" type="search" aria-label="Search examples" placeholder="Search examples…">
    </div>
  </div>
  <main>
    <div class="big-idea" aria-label="What each language does">
      <div class="idea"><strong>🐍 Python: give instructions</strong><span>Make a computer do a task, solve a problem, or play a game.</span></div>
      <div class="idea"><strong>🧱 HTML: build the page</strong><span>Add the words, pictures, links, and buttons on a website.</span></div>
      <div class="idea"><strong>🎨 CSS + ⚡ JavaScript</strong><span>CSS styles the page. JavaScript makes it respond when people use it.</span></div>
    </div>
    <p class="tip"><strong>How to read the examples:</strong> Words in quotes are text. Names like <code>score</code> are labels that hold information. Try changing one small part at a time.</p>

    <section class="section" id="python">
      <div class="section-heading"><span class="badge">🐍</span><div><h2>Python</h2></div></div>
      <p class="section-intro">Python is a language for giving the computer clear instructions. Spaces at the start of a line matter in Python!</p>
      <div class="cards">
        <article class="card"><div class="card-top"><h3>Show a message</h3><button class="copy" type="button">Copy</button></div><p><code>print()</code> puts words or a result on the screen.</p><pre><code>print("Hello, world!")</code></pre></article>
        <article class="card"><div class="card-top"><h3>Save information in a variable</h3><button class="copy" type="button">Copy</button></div><p>A variable is a labeled box that holds a value.</p><pre><code>name = "Maya"
print(f"Hi, {name}!")</code></pre></article>
        <article class="card"><div class="card-top"><h3>Make a choice with if</h3><button class="copy" type="button">Copy</button></div><p>The computer checks a question. It runs the matching part.</p><pre><code>score = 8
if score &gt;= 5:
    print("You passed!")
else:
    print("Try again!")</code></pre></article>
        <article class="card"><div class="card-top"><h3>Repeat with a loop</h3><button class="copy" type="button">Copy</button></div><p>A <code>for</code> loop repeats its indented lines for each item.</p><pre><code>pets = ["cat", "dog", "fish"]
for pet in pets:
    print(pet)</code></pre></article>
        <article class="card"><div class="card-top"><h3>Make a reusable function</h3><button class="copy" type="button">Copy</button></div><p>A function is a set of instructions you can use by its name.</p><pre><code>def say_hello(name):
    print(f"Hello, {name}!")

say_hello("Sam")</code></pre></article>
        <article class="card"><div class="card-top"><h3>Ask the user a question</h3><button class="copy" type="button">Copy</button></div><p><code>input()</code> waits for someone to type. It gives back text.</p><pre><code>favorite = input("Favorite color? ")
print(f"I like {favorite}, too!")</code></pre></article>
      </div>

      <div class="tip"><strong>Python reminder:</strong> <code>=</code> saves a value. <code>==</code> asks whether two values are equal.</div>

      <details class="full-reference" open><summary>Open the full Python reference (336 examples)</summary>
        <p class="section-intro">These are the examples from the original Python sheet. Some cover more advanced topics, so start with the examples above and explore these when you are ready.</p>
        <div class="cards">
<article class="card"><div class="card-top"><div><p class="ref-group">Variables and Strings</p><h3>Hello world</h3></div><button class="copy" type="button">Copy</button></div><p>print() shows text on the screen. Strings go in single or double quotes.</p><pre><code>print(&quot;Hello world!&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Variables and Strings</p><h3>Hello world with a variable</h3></div><button class="copy" type="button">Copy</button></div><p>A variable is a label attached to a value.</p><pre><code>msg = &quot;Hello world!&quot;
print(msg)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Variables and Strings</p><h3>f-strings (using variables in strings)</h3></div><button class="copy" type="button">Copy</button></div><p>Put an f before the quotes, then put variables inside curly braces.</p><pre><code>first_name = &#x27;albert&#x27;
last_name = &#x27;einstein&#x27;
full_name = f&quot;{first_name} {last_name}&quot;
print(full_name)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">User input</p><h3>Prompting for a value</h3></div><button class="copy" type="button">Copy</button></div><p>All input is stored as a string.</p><pre><code>name = input(&quot;What&#x27;s your name? &quot;)
print(f&quot;Hello, {name}!&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">User input</p><h3>Prompting for numerical input (int)</h3></div><button class="copy" type="button">Copy</button></div><p>Convert the string to a whole number with int().</p><pre><code>age = input(&quot;How old are you? &quot;)
age = int(age)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">User input</p><h3>Prompting for numerical input (float)</h3></div><button class="copy" type="button">Copy</button></div><p>Use float() when the number can have decimals.</p><pre><code>pi = input(&quot;What&#x27;s the value of pi? &quot;)
pi = float(pi)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">User input</p><h3>Accepting input and using it</h3></div><button class="copy" type="button">Copy</button></div><pre><code>age = input(&quot;How old are you? &quot;)
age = int(age)

if age &gt;= 18:
    print(&quot;\nYou can vote!&quot;)
else:
    print(&quot;\nSorry, you can&#x27;t vote yet.&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">User input</p><h3>Accepting a tip as a float</h3></div><button class="copy" type="button">Copy</button></div><pre><code>tip = input(&quot;How much do you want to tip? &quot;)
tip = float(tip)
print(f&quot;Tipped ${tip}.&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Make a list</h3></div><button class="copy" type="button">Copy</button></div><p>Square brackets and commas. Use plural names for lists.</p><pre><code>bikes = [&#x27;trek&#x27;, &#x27;redline&#x27;, &#x27;giant&#x27;]</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Make a list of users</h3></div><button class="copy" type="button">Copy</button></div><pre><code>users = [&#x27;val&#x27;, &#x27;bob&#x27;, &#x27;mia&#x27;, &#x27;ron&#x27;, &#x27;ned&#x27;]</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Get the first item in a list</h3></div><button class="copy" type="button">Copy</button></div><p>Indexes start at 0.</p><pre><code>first_bike = bikes[0]</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Get the first element</h3></div><button class="copy" type="button">Copy</button></div><pre><code>first_user = users[0]</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Get the second item</h3></div><button class="copy" type="button">Copy</button></div><pre><code>second_user = users[1]</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Get the last item in a list</h3></div><button class="copy" type="button">Copy</button></div><p>Negative indexes count from the end.</p><pre><code>last_bike = bikes[-1]</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Changing an element</h3></div><button class="copy" type="button">Copy</button></div><p>Assign to an index to replace that item.</p><pre><code>users[0] = &#x27;valerie&#x27;
users[1] = &#x27;robert&#x27;
users[-2] = &#x27;ronald&#x27;</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Looping through a list</h3></div><button class="copy" type="button">Copy</button></div><p>Use the singular name of the list for the loop variable.</p><pre><code>for bike in bikes:
    print(bike)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Printing a message for each item, then one at the end</h3></div><button class="copy" type="button">Copy</button></div><p>Indented lines run for every item. Unindented lines run after the loop.</p><pre><code>for user in users:
    print(f&quot;\nWelcome, {user}!&quot;)
    print(&quot;We&#x27;re so glad you joined!&quot;)

print(&quot;\nWelcome, we&#x27;re glad to see you all!&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Adding an item to the end</h3></div><button class="copy" type="button">Copy</button></div><pre><code>users.append(&#x27;amy&#x27;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Starting with an empty list</h3></div><button class="copy" type="button">Copy</button></div><pre><code>users = []
users.append(&#x27;amy&#x27;)
users.append(&#x27;val&#x27;)
users.append(&#x27;bob&#x27;)
users.append(&#x27;mia&#x27;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Inserting at a particular position</h3></div><button class="copy" type="button">Copy</button></div><pre><code>users.insert(0, &#x27;joe&#x27;)
users.insert(3, &#x27;bea&#x27;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Deleting an element by its position</h3></div><button class="copy" type="button">Copy</button></div><pre><code>del users[-1]</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Removing an item by its value</h3></div><button class="copy" type="button">Copy</button></div><p>Removes only the first item with that value.</p><pre><code>users.remove(&#x27;mia&#x27;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Pop the last item</h3></div><button class="copy" type="button">Copy</button></div><p>pop() removes the item and gives it back to you.</p><pre><code>most_recent_user = users.pop()
print(most_recent_user)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Pop the first item</h3></div><button class="copy" type="button">Copy</button></div><pre><code>first_user = users.pop(0)
print(first_user)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Find the length of a list</h3></div><button class="copy" type="button">Copy</button></div><pre><code>num_users = len(users)
print(f&quot;We have {num_users} users.&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Sorting a list permanently</h3></div><button class="copy" type="button">Copy</button></div><p>sort() changes the original list.</p><pre><code>users.sort()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Sorting in reverse alphabetical order</h3></div><button class="copy" type="button">Copy</button></div><pre><code>users.sort(reverse=True)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Sorting a list temporarily</h3></div><button class="copy" type="button">Copy</button></div><p>sorted() returns a sorted copy and leaves the original alone.</p><pre><code>print(sorted(users))
print(sorted(users, reverse=True))</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Reversing the order of a list</h3></div><button class="copy" type="button">Copy</button></div><pre><code>users.reverse()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Making numerical lists</h3></div><button class="copy" type="button">Copy</button></div><pre><code>squares = []
for x in range(1, 11):
    squares.append(x**2)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>The range() function: 0 to 1000</h3></div><button class="copy" type="button">Copy</button></div><p>range() stops one number before the number you pass.</p><pre><code>for number in range(1001):
    print(number)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>The range() function: 1 to 1000</h3></div><button class="copy" type="button">Copy</button></div><pre><code>for number in range(1, 1001):
    print(number)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>A list of numbers from 1 to a million</h3></div><button class="copy" type="button">Copy</button></div><pre><code>numbers = list(range(1, 1_000_001))</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Finding the minimum value</h3></div><button class="copy" type="button">Copy</button></div><pre><code>ages = [93, 99, 66, 17, 85, 1, 35, 82, 2, 77]
youngest = min(ages)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Finding the maximum value</h3></div><button class="copy" type="button">Copy</button></div><pre><code>ages = [93, 99, 66, 17, 85, 1, 35, 82, 2, 77]
oldest = max(ages)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Finding the sum of all values</h3></div><button class="copy" type="button">Copy</button></div><pre><code>ages = [93, 99, 66, 17, 85, 1, 35, 82, 2, 77]
total_years = sum(ages)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Slicing a list</h3></div><button class="copy" type="button">Copy</button></div><p>A slice is a portion of a list. [:2] means from the start up to, but not including, index 2.</p><pre><code>finishers = [&#x27;sam&#x27;, &#x27;bob&#x27;, &#x27;ada&#x27;, &#x27;bea&#x27;]
first_two = finishers[:2]</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Slicing: first three items</h3></div><button class="copy" type="button">Copy</button></div><pre><code>finishers = [&#x27;kai&#x27;, &#x27;abe&#x27;, &#x27;ada&#x27;, &#x27;gus&#x27;, &#x27;zoe&#x27;]
first_three = finishers[:3]</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Slicing: middle three items</h3></div><button class="copy" type="button">Copy</button></div><pre><code>middle_three = finishers[1:4]</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Slicing: last three items</h3></div><button class="copy" type="button">Copy</button></div><pre><code>last_three = finishers[-3:]</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Copying a list (bikes)</h3></div><button class="copy" type="button">Copy</button></div><pre><code>copy_of_bikes = bikes[:]</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Copying a list</h3></div><button class="copy" type="button">Copy</button></div><p>A full slice makes an independent copy.</p><pre><code>finishers = [&#x27;kai&#x27;, &#x27;abe&#x27;, &#x27;ada&#x27;, &#x27;gus&#x27;, &#x27;zoe&#x27;]
copy_of_finishers = finishers[:]</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>List comprehension: squares</h3></div><button class="copy" type="button">Copy</button></div><p>One line that builds a list from a loop.</p><pre><code>squares = [x**2 for x in range(1, 11)]</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Loop vs comprehension: squares</h3></div><button class="copy" type="button">Copy</button></div><pre><code>squares = []
for x in range(1, 11):
    square = x**2
    squares.append(square)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Loop vs comprehension: upper case names (loop)</h3></div><button class="copy" type="button">Copy</button></div><pre><code>names = [&#x27;kai&#x27;, &#x27;abe&#x27;, &#x27;ada&#x27;, &#x27;gus&#x27;, &#x27;zoe&#x27;]

upper_names = []
for name in names:
    upper_names.append(name.upper())</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Loop vs comprehension: upper case names (comprehension)</h3></div><button class="copy" type="button">Copy</button></div><pre><code>names = [&#x27;kai&#x27;, &#x27;abe&#x27;, &#x27;ada&#x27;, &#x27;gus&#x27;, &#x27;zoe&#x27;]

upper_names = [name.upper() for name in names]</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Lists</p><h3>Build a list and print the items</h3></div><button class="copy" type="button">Copy</button></div><p>Try this one on pythontutor.com to watch the list change step by step.</p><pre><code>dogs = []
dogs.append(&#x27;willie&#x27;)
dogs.append(&#x27;hootz&#x27;)
dogs.append(&#x27;peso&#x27;)
dogs.append(&#x27;goblin&#x27;)

for dog in dogs:
    print(f&quot;Hello {dog}!&quot;)
print(&quot;I love these dogs!&quot;)

print(&quot;\nThese were my first two dogs:&quot;)
old_dogs = dogs[:2]
for old_dog in old_dogs:
    print(old_dog)

del dogs[0]
dogs.remove(&#x27;peso&#x27;)
print(dogs)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Tuples</p><h3>Making a tuple</h3></div><button class="copy" type="button">Copy</button></div><p>Tuples use parentheses. Their items can&#x27;t be changed.</p><pre><code>dimensions = (1920, 1080)
resolutions = (&#x27;720p&#x27;, &#x27;1080p&#x27;, &#x27;4K&#x27;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Tuples</p><h3>Defining a tuple</h3></div><button class="copy" type="button">Copy</button></div><pre><code>dimensions = (800, 600)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Tuples</p><h3>Looping through a tuple</h3></div><button class="copy" type="button">Copy</button></div><pre><code>for dimension in dimensions:
    print(dimension)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Tuples</p><h3>Overwriting a tuple</h3></div><button class="copy" type="button">Copy</button></div><p>You can replace the whole tuple, but not individual items.</p><pre><code>dimensions = (800, 600)
print(dimensions)

dimensions = (1200, 900)
print(dimensions)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">If statements</p><h3>Conditional tests: comparison operators</h3></div><button class="copy" type="button">Copy</button></div><p>A single = assigns a value. A double == checks equality.</p><pre><code>equal            x == 42
not equal        x != 42
greater than     x &gt; 42
  or equal to    x &gt;= 42
less than        x &lt; 42
  or equal to    x &lt;= 42</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">If statements</p><h3>Checking for equality</h3></div><button class="copy" type="button">Copy</button></div><pre><code>&gt;&gt;&gt; car = &#x27;bmw&#x27;
&gt;&gt;&gt; car == &#x27;bmw&#x27;
True
&gt;&gt;&gt; car = &#x27;audi&#x27;
&gt;&gt;&gt; car == &#x27;bmw&#x27;
False</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">If statements</p><h3>Ignoring case when making a comparison</h3></div><button class="copy" type="button">Copy</button></div><pre><code>&gt;&gt;&gt; car = &#x27;Audi&#x27;
&gt;&gt;&gt; car.lower() == &#x27;audi&#x27;
True</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">If statements</p><h3>Checking for inequality</h3></div><button class="copy" type="button">Copy</button></div><pre><code>&gt;&gt;&gt; topping = &#x27;mushrooms&#x27;
&gt;&gt;&gt; topping != &#x27;anchovies&#x27;
True</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">If statements</p><h3>Testing equality and inequality</h3></div><button class="copy" type="button">Copy</button></div><pre><code>&gt;&gt;&gt; age = 18
&gt;&gt;&gt; age == 18
True
&gt;&gt;&gt; age != 18
False</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">If statements</p><h3>Comparison operators (numerical)</h3></div><button class="copy" type="button">Copy</button></div><pre><code>&gt;&gt;&gt; age = 19
&gt;&gt;&gt; age &lt; 21
True
&gt;&gt;&gt; age &lt;= 21
True
&gt;&gt;&gt; age &gt; 21
False
&gt;&gt;&gt; age &gt;= 21
False</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">If statements</p><h3>Using and to check multiple conditions</h3></div><button class="copy" type="button">Copy</button></div><p>and is True only if every condition is True.</p><pre><code>&gt;&gt;&gt; age_0 = 22
&gt;&gt;&gt; age_1 = 18
&gt;&gt;&gt; age_0 &gt;= 21 and age_1 &gt;= 21
False
&gt;&gt;&gt; age_1 = 23
&gt;&gt;&gt; age_0 &gt;= 21 and age_1 &gt;= 21
True</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">If statements</p><h3>Using or to check multiple conditions</h3></div><button class="copy" type="button">Copy</button></div><p>or is True if any condition is True.</p><pre><code>&gt;&gt;&gt; age_0 = 22
&gt;&gt;&gt; age_1 = 18
&gt;&gt;&gt; age_0 &gt;= 21 or age_1 &gt;= 21
True
&gt;&gt;&gt; age_0 = 18
&gt;&gt;&gt; age_0 &gt;= 21 or age_1 &gt;= 21
False</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">If statements</p><h3>Conditional tests with lists</h3></div><button class="copy" type="button">Copy</button></div><p>in and not in check whether a value is in a list.</p><pre><code>&#x27;trek&#x27; in bikes
&#x27;surly&#x27; not in bikes</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">If statements</p><h3>Testing if a value is in a list</h3></div><button class="copy" type="button">Copy</button></div><pre><code>&gt;&gt;&gt; players = [&#x27;al&#x27;, &#x27;bea&#x27;, &#x27;cyn&#x27;, &#x27;dale&#x27;]
&gt;&gt;&gt; &#x27;al&#x27; in players
True
&gt;&gt;&gt; &#x27;eric&#x27; in players
False</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">If statements</p><h3>Testing if two values are in a list</h3></div><button class="copy" type="button">Copy</button></div><pre><code>&gt;&gt;&gt; &#x27;al&#x27; in players and &#x27;cyn&#x27; in players</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">If statements</p><h3>Testing if a value is not in a list</h3></div><button class="copy" type="button">Copy</button></div><pre><code>banned_users = [&#x27;ann&#x27;, &#x27;chad&#x27;, &#x27;dee&#x27;]
user = &#x27;erin&#x27;

if user not in banned_users:
    print(&quot;You can play!&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">If statements</p><h3>Assigning boolean values</h3></div><button class="copy" type="button">Copy</button></div><pre><code>game_active = True
is_valid = True
can_edit = False</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">If statements</p><h3>A simple if test</h3></div><button class="copy" type="button">Copy</button></div><pre><code>if age &gt;= 18:
    print(&quot;You can vote!&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">If statements</p><h3>If-else statements</h3></div><button class="copy" type="button">Copy</button></div><pre><code>age = 17

if age &gt;= 18:
    print(&quot;You&#x27;re old enough to vote!&quot;)
else:
    print(&quot;You can&#x27;t vote yet.&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">If statements</p><h3>If-elif-else statements</h3></div><button class="copy" type="button">Copy</button></div><p>Python runs the first block whose test is True, then skips the rest.</p><pre><code>if age &lt; 4:
    ticket_price = 0
elif age &lt; 18:
    ticket_price = 10
elif age &lt; 65:
    ticket_price = 40
else:
    ticket_price = 15</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">If statements</p><h3>The if-elif-else chain with a message</h3></div><button class="copy" type="button">Copy</button></div><pre><code>age = 12

if age &lt; 4:
    price = 0
elif age &lt; 18:
    price = 25
else:
    price = 40

print(f&quot;Your cost is ${price}.&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">If statements</p><h3>Checking if a list is empty</h3></div><button class="copy" type="button">Copy</button></div><p>An empty list counts as False in an if statement.</p><pre><code>players = []

if players:
    for player in players:
        print(f&quot;Player: {player.title()}&quot;)
else:
    print(&quot;We have no players yet!&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">While loops</p><h3>A simple while loop</h3></div><button class="copy" type="button">Copy</button></div><p>Runs as long as the condition is True.</p><pre><code>current_value = 1
while current_value &lt;= 5:
    print(current_value)
    current_value += 1</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">While loops</p><h3>Counting to 5</h3></div><button class="copy" type="button">Copy</button></div><pre><code>current_number = 1

while current_number &lt;= 5:
    print(current_number)
    current_number += 1</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">While loops</p><h3>Letting the user choose when to quit</h3></div><button class="copy" type="button">Copy</button></div><pre><code>msg = &#x27;&#x27;
while msg != &#x27;quit&#x27;:
    msg = input(&quot;What&#x27;s your message? &quot;)

    if msg != &#x27;quit&#x27;:
        print(msg)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">While loops</p><h3>Letting the user choose when to quit (with a prompt)</h3></div><button class="copy" type="button">Copy</button></div><pre><code>prompt = &quot;\nTell me something, and I&#x27;ll &quot;
prompt += &quot;repeat it back to you.&quot;
prompt += &quot;\nEnter &#x27;quit&#x27; to end the program. &quot;

message = &quot;&quot;
while message != &#x27;quit&#x27;:
    message = input(prompt)

    if message != &#x27;quit&#x27;:
        print(message)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">While loops</p><h3>Using a flag</h3></div><button class="copy" type="button">Copy</button></div><p>A flag is a True/False variable that controls when the loop ends.</p><pre><code>prompt = &quot;\nTell me something, and I&#x27;ll &quot;
prompt += &quot;repeat it back to you.&quot;
prompt += &quot;\nEnter &#x27;quit&#x27; to end the program. &quot;

active = True
while active:
    message = input(prompt)

    if message == &#x27;quit&#x27;:
        active = False
    else:
        print(message)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">While loops</p><h3>Using break to exit a loop</h3></div><button class="copy" type="button">Copy</button></div><p>break leaves the loop immediately.</p><pre><code>prompt = &quot;\nWhat cities have you visited?&quot;
prompt += &quot;\nEnter &#x27;quit&#x27; when you&#x27;re done. &quot;

while True:
    city = input(prompt)

    if city == &#x27;quit&#x27;:
        break
    else:
        print(f&quot;I&#x27;ve been to {city}!&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">While loops</p><h3>Using continue in a loop</h3></div><button class="copy" type="button">Copy</button></div><p>continue skips the rest of this pass and goes back to the top of the loop.</p><pre><code>banned_users = [&#x27;eve&#x27;, &#x27;fred&#x27;, &#x27;gary&#x27;, &#x27;helen&#x27;]

prompt = &quot;\nAdd a player to your team.&quot;
prompt += &quot;\nEnter &#x27;quit&#x27; when you&#x27;re done. &quot;

players = []
while True:
    player = input(prompt)

    if player == &#x27;quit&#x27;:
        break
    elif player in banned_users:
        print(f&quot;{player} is banned!&quot;)
        continue
    else:
        players.append(player)

print(&quot;\nYour team:&quot;)
for player in players:
    print(player)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">While loops</p><h3>An infinite loop</h3></div><button class="copy" type="button">Copy</button></div><p>Every while loop needs a way to stop. Press Ctrl-C to stop this one.</p><pre><code>while True:
    name = input(&quot;\nWho are you? &quot;)
    print(f&quot;Nice to meet you, {name}!&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">While loops</p><h3>Removing all instances of a value from a list</h3></div><button class="copy" type="button">Copy</button></div><p>remove() only removes the first match, so a while loop repeats it.</p><pre><code>pets = [&#x27;dog&#x27;, &#x27;cat&#x27;, &#x27;dog&#x27;, &#x27;fish&#x27;, &#x27;cat&#x27;, &#x27;rabbit&#x27;, &#x27;cat&#x27;]
print(pets)

while &#x27;cat&#x27; in pets:
    pets.remove(&#x27;cat&#x27;)

print(pets)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Dictionaries</p><h3>A simple dictionary</h3></div><button class="copy" type="button">Copy</button></div><p>Curly braces, with key: value pairs separated by commas.</p><pre><code>alien = {&#x27;color&#x27;: &#x27;green&#x27;, &#x27;points&#x27;: 5}</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Dictionaries</p><h3>Accessing a value</h3></div><button class="copy" type="button">Copy</button></div><pre><code>print(f&quot;The alien&#x27;s color is {alien[&#x27;color&#x27;]}.&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Dictionaries</p><h3>Getting the value associated with a key</h3></div><button class="copy" type="button">Copy</button></div><p>A missing key causes an error.</p><pre><code>alien_0 = {&#x27;color&#x27;: &#x27;green&#x27;, &#x27;points&#x27;: 5}

print(alien_0[&#x27;color&#x27;])
print(alien_0[&#x27;points&#x27;])</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Dictionaries</p><h3>Getting the value with get()</h3></div><button class="copy" type="button">Copy</button></div><p>get() returns None, or a default you choose, instead of an error.</p><pre><code>alien_0 = {&#x27;color&#x27;: &#x27;green&#x27;}

alien_color = alien_0.get(&#x27;color&#x27;)
alien_points = alien_0.get(&#x27;points&#x27;, 0)
alien_speed = alien_0.get(&#x27;speed&#x27;)

print(alien_color)
print(alien_points)
print(alien_speed)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Dictionaries</p><h3>Adding a new key-value pair</h3></div><button class="copy" type="button">Copy</button></div><pre><code>alien[&#x27;x_position&#x27;] = 0</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Dictionaries</p><h3>Adding several pairs</h3></div><button class="copy" type="button">Copy</button></div><pre><code>alien_0 = {&#x27;color&#x27;: &#x27;green&#x27;, &#x27;points&#x27;: 5}

alien_0[&#x27;x&#x27;] = 0
alien_0[&#x27;y&#x27;] = 25
alien_0[&#x27;speed&#x27;] = 1.5</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Dictionaries</p><h3>Starting with an empty dictionary</h3></div><button class="copy" type="button">Copy</button></div><pre><code>alien_0 = {}
alien_0[&#x27;color&#x27;] = &#x27;green&#x27;
alien_0[&#x27;points&#x27;] = 5</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Dictionaries</p><h3>Modifying values in a dictionary</h3></div><button class="copy" type="button">Copy</button></div><pre><code>alien_0 = {&#x27;color&#x27;: &#x27;green&#x27;, &#x27;points&#x27;: 5}
print(alien_0)

# Change the alien&#x27;s color and point value.
alien_0[&#x27;color&#x27;] = &#x27;yellow&#x27;
alien_0[&#x27;points&#x27;] = 10
print(alien_0)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Dictionaries</p><h3>Deleting a key-value pair</h3></div><button class="copy" type="button">Copy</button></div><pre><code>alien_0 = {&#x27;color&#x27;: &#x27;green&#x27;, &#x27;points&#x27;: 5}
print(alien_0)

del alien_0[&#x27;points&#x27;]
print(alien_0)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Dictionaries</p><h3>Looping through all key-value pairs</h3></div><button class="copy" type="button">Copy</button></div><pre><code>fav_numbers = {&#x27;eric&#x27;: 7, &#x27;ever&#x27;: 4, &#x27;erin&#x27;: 47}

for name, number in fav_numbers.items():
    print(f&quot;{name} loves {number}.&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Dictionaries</p><h3>Looping through all key-value pairs (languages)</h3></div><button class="copy" type="button">Copy</button></div><pre><code># Store people&#x27;s favorite languages.
fav_languages = {
    &#x27;jen&#x27;: &#x27;python&#x27;,
    &#x27;sarah&#x27;: &#x27;c&#x27;,
    &#x27;edward&#x27;: &#x27;ruby&#x27;,
    &#x27;phil&#x27;: &#x27;python&#x27;,
    }

# Show each person&#x27;s favorite language.
for name, language in fav_languages.items():
    print(f&quot;{name}: {language}&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Dictionaries</p><h3>Looping through all the keys</h3></div><button class="copy" type="button">Copy</button></div><pre><code>fav_numbers = {&#x27;eric&#x27;: 7, &#x27;ever&#x27;: 4, &#x27;erin&#x27;: 47}

for name in fav_numbers.keys():
    print(f&quot;{name} loves a number.&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Dictionaries</p><h3>Looping through all the values</h3></div><button class="copy" type="button">Copy</button></div><pre><code>fav_numbers = {&#x27;eric&#x27;: 7, &#x27;ever&#x27;: 4, &#x27;erin&#x27;: 47}

for number in fav_numbers.values():
    print(f&quot;{number} is a favorite.&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Dictionaries</p><h3>Looping through the keys in reverse order</h3></div><button class="copy" type="button">Copy</button></div><p>Dictionaries remember insertion order. Use sorted() to process them in another order.</p><pre><code># Show each person&#x27;s favorite language,
#   in reverse order by the person&#x27;s name.
for name in sorted(fav_languages.keys(),
        reverse=True):
    language = fav_languages[name]
    print(f&quot;{name}: {language}&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Dictionaries</p><h3>Finding a dictionary&#x27;s length</h3></div><button class="copy" type="button">Copy</button></div><pre><code>num_responses = len(fav_languages)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Dictionaries</p><h3>Nesting: storing dictionaries in a list</h3></div><button class="copy" type="button">Copy</button></div><pre><code># Start with an empty list.
users = []

# Make a new user, and add them to the list.
new_user = {
    &#x27;last&#x27;: &#x27;fermi&#x27;,
    &#x27;first&#x27;: &#x27;enrico&#x27;,
    &#x27;username&#x27;: &#x27;efermi&#x27;,
    }
users.append(new_user)

# Make another new user, and add them as well.
new_user = {
    &#x27;last&#x27;: &#x27;curie&#x27;,
    &#x27;first&#x27;: &#x27;marie&#x27;,
    &#x27;username&#x27;: &#x27;mcurie&#x27;,
    }
users.append(new_user)

# Show all information about each user.
print(&quot;User summary:&quot;)
for user_dict in users:
    for k, v in user_dict.items():
        print(f&quot;{k}: {v}&quot;)
    print(&quot;\n&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Dictionaries</p><h3>Nesting: define a list of dictionaries directly</h3></div><button class="copy" type="button">Copy</button></div><pre><code># Define a list of users, where each user
#   is represented by a dictionary.
users = [
    {
        &#x27;last&#x27;: &#x27;fermi&#x27;,
        &#x27;first&#x27;: &#x27;enrico&#x27;,
        &#x27;username&#x27;: &#x27;efermi&#x27;,
    },
    {
        &#x27;last&#x27;: &#x27;curie&#x27;,
        &#x27;first&#x27;: &#x27;marie&#x27;,
        &#x27;username&#x27;: &#x27;mcurie&#x27;,
    },
]</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Dictionaries</p><h3>Nesting: lists in a dictionary</h3></div><button class="copy" type="button">Copy</button></div><pre><code># Store multiple languages for each person.
fav_languages = {
    &#x27;jen&#x27;: [&#x27;python&#x27;, &#x27;ruby&#x27;],
    &#x27;sarah&#x27;: [&#x27;c&#x27;],
    &#x27;edward&#x27;: [&#x27;ruby&#x27;, &#x27;go&#x27;],
    &#x27;phil&#x27;: [&#x27;python&#x27;, &#x27;haskell&#x27;],
}

# Show all responses for each person.
for name, langs in fav_languages.items():
    print(f&quot;{name}: &quot;)
    for lang in langs:
        print(f&quot;- {lang}&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Dictionaries</p><h3>Nesting: a dictionary of dictionaries</h3></div><button class="copy" type="button">Copy</button></div><p>If you nest much deeper than this, a class is probably simpler.</p><pre><code>users = {
    &#x27;aeinstein&#x27;: {
        &#x27;first&#x27;: &#x27;albert&#x27;,
        &#x27;last&#x27;: &#x27;einstein&#x27;,
        &#x27;location&#x27;: &#x27;princeton&#x27;,
        },

    &#x27;mcurie&#x27;: {
        &#x27;first&#x27;: &#x27;marie&#x27;,
        &#x27;last&#x27;: &#x27;curie&#x27;,
        &#x27;location&#x27;: &#x27;paris&#x27;,
        },
}

for username, user_dict in users.items():
    full_name = f&quot;{user_dict[&#x27;first&#x27;]} &quot;
    full_name += user_dict[&#x27;last&#x27;]

    location = user_dict[&#x27;location&#x27;]

    print(f&quot;\nUsername: {username}&quot;)
    print(f&quot;\tFull name: {full_name.title()}&quot;)
    print(f&quot;\tLocation: {location.title()}&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Dictionaries</p><h3>Dictionary comprehension</h3></div><button class="copy" type="button">Copy</button></div><pre><code>squares = {x:x**2 for x in range(5)}</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Dictionaries</p><h3>Using a loop to make a dictionary</h3></div><button class="copy" type="button">Copy</button></div><pre><code>squares = {}
for x in range(5):
    squares[x] = x**2</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Dictionaries</p><h3>Using zip() to make a dictionary</h3></div><button class="copy" type="button">Copy</button></div><p>zip() matches each item in one list with the item in the other.</p><pre><code>group_1 = [&#x27;kai&#x27;, &#x27;abe&#x27;, &#x27;ada&#x27;, &#x27;gus&#x27;, &#x27;zoe&#x27;]
group_2 = [&#x27;jen&#x27;, &#x27;eva&#x27;, &#x27;dan&#x27;, &#x27;isa&#x27;, &#x27;meg&#x27;]

pairings = {name:name_2
    for name, name_2 in zip(group_1, group_2)}</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Dictionaries</p><h3>A million aliens</h3></div><button class="copy" type="button">Copy</button></div><pre><code>aliens = []

# Make a million green aliens, worth 5 points
#   each. Have them all start in one row.
for alien_num in range(1_000_000):
    new_alien = {
        &#x27;color&#x27;: &#x27;green&#x27;,
        &#x27;points&#x27;: 5,
        &#x27;x&#x27;: 20 * alien_num,
        &#x27;y&#x27;: 0
    }

    aliens.append(new_alien)

# Prove the list contains a million aliens.
num_aliens = len(aliens)

print(&quot;Number of aliens created:&quot;)
print(num_aliens)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Functions</p><h3>A simple function</h3></div><button class="copy" type="button">Copy</button></div><p>def starts a function. The triple-quoted docstring says what it does.</p><pre><code>def greet_user():
    &quot;&quot;&quot;Display a simple greeting.&quot;&quot;&quot;
    print(&quot;Hello!&quot;)

greet_user()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Functions</p><h3>Passing an argument</h3></div><button class="copy" type="button">Copy</button></div><p>The value you pass in is an argument. The name in the definition is a parameter.</p><pre><code>def greet_user(username):
    &quot;&quot;&quot;Display a personalized greeting.&quot;&quot;&quot;
    print(f&quot;Hello, {username}!&quot;)

greet_user(&#x27;jesse&#x27;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Functions</p><h3>Passing a simple argument several times</h3></div><button class="copy" type="button">Copy</button></div><pre><code>def greet_user(username):
    &quot;&quot;&quot;Display a simple greeting.&quot;&quot;&quot;
    print(f&quot;Hello, {username}!&quot;)

greet_user(&#x27;jesse&#x27;)
greet_user(&#x27;diana&#x27;)
greet_user(&#x27;brandon&#x27;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Functions</p><h3>Positional arguments</h3></div><button class="copy" type="button">Copy</button></div><p>Python matches arguments to parameters by position.</p><pre><code>def describe_pet(animal, name):
    &quot;&quot;&quot;Display information about a pet.&quot;&quot;&quot;
    print(f&quot;\nI have a {animal}.&quot;)
    print(f&quot;Its name is {name}.&quot;)

describe_pet(&#x27;hamster&#x27;, &#x27;harry&#x27;)
describe_pet(&#x27;dog&#x27;, &#x27;willie&#x27;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Functions</p><h3>Keyword arguments</h3></div><button class="copy" type="button">Copy</button></div><p>With keywords, the order doesn&#x27;t matter.</p><pre><code>def describe_pet(animal, name):
    &quot;&quot;&quot;Display information about a pet.&quot;&quot;&quot;
    print(f&quot;\nI have a {animal}.&quot;)
    print(f&quot;Its name is {name}.&quot;)

describe_pet(animal=&#x27;hamster&#x27;, name=&#x27;harry&#x27;)
describe_pet(name=&#x27;willie&#x27;, animal=&#x27;dog&#x27;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Functions</p><h3>Default values for parameters</h3></div><button class="copy" type="button">Copy</button></div><pre><code>def make_pizza(topping=&#x27;pineapple&#x27;):
    &quot;&quot;&quot;Make a single-topping pizza.&quot;&quot;&quot;
    print(f&quot;Have a {topping} pizza!&quot;)

make_pizza()
make_pizza(&#x27;mushroom&#x27;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Functions</p><h3>Using a default value</h3></div><button class="copy" type="button">Copy</button></div><p>Parameters with defaults must come after parameters without them.</p><pre><code>def describe_pet(name, animal=&#x27;dog&#x27;):
    &quot;&quot;&quot;Display information about a pet.&quot;&quot;&quot;
    print(f&quot;\nI have a {animal}.&quot;)
    print(f&quot;Its name is {name}.&quot;)

describe_pet(&#x27;harry&#x27;, &#x27;hamster&#x27;)
describe_pet(&#x27;willie&#x27;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Functions</p><h3>Using None to make an argument optional</h3></div><button class="copy" type="button">Copy</button></div><pre><code>def describe_pet(animal, name=None):
    &quot;&quot;&quot;Display information about a pet.&quot;&quot;&quot;
    print(f&quot;\nI have a {animal}.&quot;)
    if name:
        print(f&quot;Its name is {name}.&quot;)

describe_pet(&#x27;hamster&#x27;, &#x27;harry&#x27;)
describe_pet(&#x27;snake&#x27;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Functions</p><h3>Returning a value</h3></div><button class="copy" type="button">Copy</button></div><pre><code>def add_numbers(x, y):
    &quot;&quot;&quot;Add two numbers and return the sum.&quot;&quot;&quot;
    return x + y

sum = add_numbers(3, 5)
print(sum)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Functions</p><h3>Returning a single value (formatted name)</h3></div><button class="copy" type="button">Copy</button></div><pre><code>def get_full_name(first, last):
    &quot;&quot;&quot;Return a neatly formatted full name.&quot;&quot;&quot;
    full_name = f&quot;{first} {last}&quot;
    return full_name.title()

musician = get_full_name(&#x27;jimi&#x27;, &#x27;hendrix&#x27;)
print(musician)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Functions</p><h3>Returning a dictionary</h3></div><button class="copy" type="button">Copy</button></div><pre><code>def build_person(first, last):
    &quot;&quot;&quot;Return a dictionary of information
    about a person.
    &quot;&quot;&quot;
    person = {&#x27;first&#x27;: first, &#x27;last&#x27;: last}
    return person

musician = build_person(&#x27;jimi&#x27;, &#x27;hendrix&#x27;)
print(musician)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Functions</p><h3>Returning a dictionary with optional values</h3></div><button class="copy" type="button">Copy</button></div><pre><code>def build_person(first, last, age=None):
    &quot;&quot;&quot;Return a dictionary of information
    about a person.
    &quot;&quot;&quot;
    person = {&#x27;first&#x27;: first, &#x27;last&#x27;: last}
    if age:
        person[&#x27;age&#x27;] = age

    return person

musician = build_person(&#x27;jimi&#x27;, &#x27;hendrix&#x27;, 27)
print(musician)

musician = build_person(&#x27;janis&#x27;, &#x27;joplin&#x27;)
print(musician)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Functions</p><h3>Passing a list as an argument</h3></div><button class="copy" type="button">Copy</button></div><pre><code>def greet_users(names):
    &quot;&quot;&quot;Print a simple greeting to everyone.&quot;&quot;&quot;
    for name in names:
        msg = f&quot;Hello, {name}!&quot;
        print(msg)

usernames = [&#x27;hannah&#x27;, &#x27;ty&#x27;, &#x27;margot&#x27;]
greet_users(usernames)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Functions</p><h3>Allowing a function to modify a list</h3></div><button class="copy" type="button">Copy</button></div><p>Changes a function makes to a list affect the original list.</p><pre><code>def print_models(unprinted, printed):
    &quot;&quot;&quot;3d print a set of models.&quot;&quot;&quot;
    while unprinted:
        current_model = unprinted.pop()
        print(f&quot;Printing {current_model}&quot;)
        printed.append(current_model)

# Store some unprinted designs,
#   and print each of them.
unprinted = [&#x27;phone case&#x27;, &#x27;pendant&#x27;, &#x27;ring&#x27;]
printed = []
print_models(unprinted, printed)

print(f&quot;\nUnprinted: {unprinted}&quot;)
print(f&quot;Printed: {printed}&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Functions</p><h3>Preventing a function from modifying a list</h3></div><button class="copy" type="button">Copy</button></div><p>Passing a copy with [:] leaves the original list unchanged.</p><pre><code>def print_models(unprinted, printed):
    &quot;&quot;&quot;3d print a set of models.&quot;&quot;&quot;
    while unprinted:
        current_model = unprinted.pop()
        print(f&quot;Printing {current_model}&quot;)
        printed.append(current_model)

# Store some unprinted designs,
#   and print each of them.
original = [&#x27;phone case&#x27;, &#x27;pendant&#x27;, &#x27;ring&#x27;]
printed = []

print_models(original[:], printed)
print(f&quot;\nOriginal: {original}&quot;)
print(f&quot;Printed: {printed}&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Functions</p><h3>Collecting an arbitrary number of arguments</h3></div><button class="copy" type="button">Copy</button></div><p>*toppings collects all extra positional arguments into a tuple. It must come last.</p><pre><code>def make_pizza(size, *toppings):
    &quot;&quot;&quot;Make a pizza.&quot;&quot;&quot;
    print(f&quot;\nMaking a {size} pizza.&quot;)

    print(&quot;Toppings:&quot;)
    for topping in toppings:
        print(f&quot;- {topping}&quot;)

# Make three pizzas with different toppings.
make_pizza(&#x27;small&#x27;, &#x27;pepperoni&#x27;)
make_pizza(&#x27;large&#x27;, &#x27;bacon bits&#x27;, &#x27;pineapple&#x27;)
make_pizza(&#x27;medium&#x27;, &#x27;mushrooms&#x27;, &#x27;peppers&#x27;,
        &#x27;onions&#x27;, &#x27;extra cheese&#x27;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Functions</p><h3>Collecting an arbitrary number of keyword arguments</h3></div><button class="copy" type="button">Copy</button></div><p>**user_info collects extra keyword arguments into a dictionary.</p><pre><code>def build_profile(first, last, **user_info):
    &quot;&quot;&quot;Build a dictionary for a user.&quot;&quot;&quot;
    user_info[&#x27;first&#x27;] = first
    user_info[&#x27;last&#x27;] = last

    return user_info

# Create two users with different kinds
#   of information.
user_0 = build_profile(&#x27;albert&#x27;, &#x27;einstein&#x27;,
        location=&#x27;princeton&#x27;)

user_1 = build_profile(&#x27;marie&#x27;, &#x27;curie&#x27;,
        location=&#x27;paris&#x27;, field=&#x27;chemistry&#x27;)

print(user_0)
print(user_1)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Functions</p><h3>Storing a function in a module (pizza.py)</h3></div><button class="copy" type="button">Copy</button></div><pre><code>def make_pizza(size, *toppings):
    &quot;&quot;&quot;Make a pizza.&quot;&quot;&quot;
    print(f&quot;\nMaking a {size} pizza.&quot;)
    print(&quot;Toppings:&quot;)
    for topping in toppings:
        print(f&quot;- {topping}&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Functions</p><h3>Importing an entire module</h3></div><button class="copy" type="button">Copy</button></div><pre><code>import pizza

pizza.make_pizza(&#x27;medium&#x27;, &#x27;pepperoni&#x27;)
pizza.make_pizza(&#x27;small&#x27;, &#x27;bacon&#x27;, &#x27;pineapple&#x27;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Functions</p><h3>Importing a specific function</h3></div><button class="copy" type="button">Copy</button></div><pre><code>from pizza import make_pizza

make_pizza(&#x27;medium&#x27;, &#x27;pepperoni&#x27;)
make_pizza(&#x27;small&#x27;, &#x27;bacon&#x27;, &#x27;pineapple&#x27;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Functions</p><h3>Giving a module an alias</h3></div><button class="copy" type="button">Copy</button></div><pre><code>import pizza as p

p.make_pizza(&#x27;medium&#x27;, &#x27;pepperoni&#x27;)
p.make_pizza(&#x27;small&#x27;, &#x27;bacon&#x27;, &#x27;pineapple&#x27;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Functions</p><h3>Giving a function an alias</h3></div><button class="copy" type="button">Copy</button></div><pre><code>from pizza import make_pizza as mp

mp(&#x27;medium&#x27;, &#x27;pepperoni&#x27;)
mp(&#x27;small&#x27;, &#x27;bacon&#x27;, &#x27;pineapple&#x27;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Functions</p><h3>Importing all functions from a module</h3></div><button class="copy" type="button">Copy</button></div><p>Don&#x27;t do this, but recognize it. It can cause naming conflicts.</p><pre><code>from pizza import *

make_pizza(&#x27;medium&#x27;, &#x27;pepperoni&#x27;)
make_pizza(&#x27;small&#x27;, &#x27;bacon&#x27;, &#x27;pineapple&#x27;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Classes</p><h3>The Car class</h3></div><button class="copy" type="button">Copy</button></div><p>Variables on a class are attributes. Functions on a class are methods.</p><pre><code>class Car:
    &quot;&quot;&quot;A simple attempt to model a car.&quot;&quot;&quot;

    def __init__(self, make, model, year):
        &quot;&quot;&quot;Initialize car attributes.&quot;&quot;&quot;
        self.make = make
        self.model = model
        self.year = year

        # Fuel capacity and level in gallons.
        self.fuel_capacity = 15
        self.fuel_level = 0

    def fill_tank(self):
        &quot;&quot;&quot;Fill gas tank to capacity.&quot;&quot;&quot;
        self.fuel_level = self.fuel_capacity
        print(&quot;Fuel tank is full.&quot;)

    def drive(self):
        &quot;&quot;&quot;Simulate driving.&quot;&quot;&quot;
        print(&quot;The car is moving.&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Classes</p><h3>Creating an instance from a class</h3></div><button class="copy" type="button">Copy</button></div><pre><code>my_car = Car(&#x27;audi&#x27;, &#x27;a4&#x27;, 2021)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Classes</p><h3>Accessing attribute values</h3></div><button class="copy" type="button">Copy</button></div><pre><code>print(my_car.make)
print(my_car.model)
print(my_car.year)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Classes</p><h3>Calling methods</h3></div><button class="copy" type="button">Copy</button></div><pre><code>my_car.fill_tank()
my_car.drive()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Classes</p><h3>Creating multiple instances</h3></div><button class="copy" type="button">Copy</button></div><pre><code>my_car = Car(&#x27;audi&#x27;, &#x27;a4&#x27;, 2024)
my_old_car = Car(&#x27;subaru&#x27;, &#x27;outback&#x27;, 2018)
my_truck = Car(&#x27;toyota&#x27;, &#x27;tacoma&#x27;, 2020)
my_old_truck = Car(&#x27;ford&#x27;, &#x27;ranger&#x27;, 1999)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Classes</p><h3>Modifying an attribute directly</h3></div><button class="copy" type="button">Copy</button></div><pre><code>my_new_car = Car(&#x27;audi&#x27;, &#x27;a4&#x27;, 2024)
my_new_car.fuel_level = 5</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Classes</p><h3>Writing a method to update an attribute&#x27;s value</h3></div><button class="copy" type="button">Copy</button></div><pre><code>def update_fuel_level(self, new_level):
    &quot;&quot;&quot;Update the fuel level.&quot;&quot;&quot;
    if new_level &lt;= self.fuel_capacity:
        self.fuel_level = new_level
    else:
        print(&quot;The tank can&#x27;t hold that much!&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Classes</p><h3>Writing a method to increment an attribute&#x27;s value</h3></div><button class="copy" type="button">Copy</button></div><pre><code>def add_fuel(self, amount):
    &quot;&quot;&quot;Add fuel to the tank.&quot;&quot;&quot;
    if (self.fuel_level + amount
            &lt;= self.fuel_capacity):
        self.fuel_level += amount
        print(&quot;Added fuel.&quot;)
    else:
        print(&quot;The tank won&#x27;t hold that much.&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Classes</p><h3>The __init__() method for a child class</h3></div><button class="copy" type="button">Copy</button></div><p>Put the parent class in parentheses. super() runs the parent&#x27;s __init__().</p><pre><code>class ElectricCar(Car):
    &quot;&quot;&quot;A simple model of an electric car.&quot;&quot;&quot;

    def __init__(self, make, model, year):
        &quot;&quot;&quot;Initialize an electric car.&quot;&quot;&quot;
        super().__init__(make, model, year)

        # Attributes specific to electric cars.
        # Battery capacity in kWh.
        self.battery_size = 40

        # Charge level in %.
        self.charge_level = 0</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Classes</p><h3>Adding new methods to the child class</h3></div><button class="copy" type="button">Copy</button></div><pre><code>class ElectricCar(Car):
    --snip--

    def charge(self):
        &quot;&quot;&quot;Fully charge the vehicle.&quot;&quot;&quot;
        self.charge_level = 100
        print(&quot;The vehicle is fully charged.&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Classes</p><h3>Using child methods and parent methods</h3></div><button class="copy" type="button">Copy</button></div><p>The child class can use its own methods and everything from the parent.</p><pre><code>my_ecar = ElectricCar(&#x27;nissan&#x27;, &#x27;leaf&#x27;, 2024)

my_ecar.charge()
my_ecar.drive()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Classes</p><h3>Overriding parent methods</h3></div><button class="copy" type="button">Copy</button></div><pre><code>class ElectricCar(Car):
    --snip--

    def fill_tank(self):
        &quot;&quot;&quot;Display an error message.&quot;&quot;&quot;
        print(&quot;This car has no fuel tank!&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Classes</p><h3>A Battery class</h3></div><button class="copy" type="button">Copy</button></div><pre><code>class Battery:
    &quot;&quot;&quot;A battery for an electric car.&quot;&quot;&quot;

    def __init__(self, size=85):
        &quot;&quot;&quot;Initialize battery attributes.&quot;&quot;&quot;
        # Capacity in kWh, charge level in %.
        self.size = size
        self.charge_level = 0

    def get_range(self):
        &quot;&quot;&quot;Return the battery&#x27;s range.&quot;&quot;&quot;
        if self.size == 40:
            return 150
        elif self.size == 65:
            return 225</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Classes</p><h3>Using an instance as an attribute</h3></div><button class="copy" type="button">Copy</button></div><pre><code>class ElectricCar(Car):
    --snip--

    def __init__(self, make, model, year):
        &quot;&quot;&quot;Initialize an electric car.&quot;&quot;&quot;
        super().__init__(make, model, year)

        # Attribute specific to electric cars.
        self.battery = Battery()

    def charge(self):
        &quot;&quot;&quot;Fully charge the vehicle.&quot;&quot;&quot;
        self.battery.charge_level = 100
        print(&quot;The vehicle is fully charged.&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Classes</p><h3>Using the instance</h3></div><button class="copy" type="button">Copy</button></div><pre><code>my_ecar = ElectricCar(&#x27;nissan&#x27;, &#x27;leaf&#x27;, 2024)

my_ecar.charge()
print(my_ecar.battery.get_range())
my_ecar.drive()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Classes</p><h3>Storing classes in a file (car.py)</h3></div><button class="copy" type="button">Copy</button></div><pre><code>&quot;&quot;&quot;Represent gas and electric cars.&quot;&quot;&quot;

class Car:
    &quot;&quot;&quot;A simple attempt to model a car.&quot;&quot;&quot;
    --snip--

class Battery:
    &quot;&quot;&quot;A battery for an electric car.&quot;&quot;&quot;
    --snip--

class ElectricCar(Car):
    &quot;&quot;&quot;A simple model of an electric car.&quot;&quot;&quot;
    --snip--</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Classes</p><h3>Importing individual classes from a module</h3></div><button class="copy" type="button">Copy</button></div><pre><code>from car import Car, ElectricCar

my_beetle = Car(&#x27;volkswagen&#x27;, &#x27;beetle&#x27;, 2021)
my_beetle.fill_tank()
my_beetle.drive()

my_leaf = ElectricCar(&#x27;nissan&#x27;, &#x27;leaf&#x27;, 2024)
my_leaf.charge()
my_leaf.drive()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Classes</p><h3>Importing an entire module (classes)</h3></div><button class="copy" type="button">Copy</button></div><pre><code>import car

my_beetle = car.Car(
        &#x27;volkswagen&#x27;, &#x27;beetle&#x27;, 2021)
my_beetle.fill_tank()
my_beetle.drive()

my_leaf = car.ElectricCar(&#x27;nissan&#x27;, &#x27;leaf&#x27;,
        2024)
my_leaf.charge()
my_leaf.drive()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Classes</p><h3>Importing all classes from a module</h3></div><button class="copy" type="button">Copy</button></div><p>Don&#x27;t do this, but recognize it when you see it.</p><pre><code>from car import *

my_beetle = Car(&#x27;volkswagen&#x27;, &#x27;beetle&#x27;, 2021)
my_leaf = ElectricCar(&#x27;nissan&#x27;, &#x27;leaf&#x27;, 2024)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Classes</p><h3>Storing objects in a list: a fleet of rental cars</h3></div><button class="copy" type="button">Copy</button></div><pre><code>from car import Car, ElectricCar

# Make lists to hold a fleet of cars.
gas_fleet = []
electric_fleet = []

# Make 250 gas cars and 500 electric cars.
for _ in range(250):
    car = Car(&#x27;ford&#x27;, &#x27;escape&#x27;, 2024)
    gas_fleet.append(car)
for _ in range(500):
    ecar = ElectricCar(&#x27;nissan&#x27;, &#x27;leaf&#x27;, 2024)
    electric_fleet.append(ecar)

# Fill the gas cars, and charge electric cars.
for car in gas_fleet:
    car.fill_tank()
for ecar in electric_fleet:
    ecar.charge()

print(f&quot;Gas cars: {len(gas_fleet)}&quot;)
print(f&quot;Electric cars: {len(electric_fleet)}&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Classes</p><h3>Creating a dog class</h3></div><button class="copy" type="button">Copy</button></div><pre><code>class Dog:
    &quot;&quot;&quot;Represent a dog.&quot;&quot;&quot;

    def __init__(self, name):
        &quot;&quot;&quot;Initialize dog object.&quot;&quot;&quot;
        self.name = name

    def sit(self):
        &quot;&quot;&quot;Simulate sitting.&quot;&quot;&quot;
        print(f&quot;{self.name} is sitting.&quot;)

my_dog = Dog(&#x27;Peso&#x27;)

print(f&quot;{my_dog.name} is a great dog!&quot;)
my_dog.sit()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Classes</p><h3>Inheritance: a search dog</h3></div><button class="copy" type="button">Copy</button></div><pre><code>class SARDog(Dog):
    &quot;&quot;&quot;Represent a search dog.&quot;&quot;&quot;

    def __init__(self, name):
        &quot;&quot;&quot;Initialize the sardog.&quot;&quot;&quot;
        super().__init__(name)

    def search(self):
        &quot;&quot;&quot;Simulate searching.&quot;&quot;&quot;
        print(f&quot;{self.name} is searching.&quot;)

my_dog = SARDog(&#x27;Willie&#x27;)

print(f&quot;{my_dog.name} is a search dog.&quot;)
my_dog.sit()
my_dog.search()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Files and Exceptions</p><h3>Reading an entire file at once</h3></div><button class="copy" type="button">Copy</button></div><p>read_text() returns the whole file as one string.</p><pre><code>from pathlib import Path

path = Path(&#x27;siddhartha.txt&#x27;)
contents = path.read_text()

print(contents)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Files and Exceptions</p><h3>Working with a file&#x27;s lines</h3></div><button class="copy" type="button">Copy</button></div><pre><code>from pathlib import Path

path = Path(&#x27;siddhartha.txt&#x27;)
contents = path.read_text()

lines = contents.splitlines()

for line in lines:
    print(line)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Files and Exceptions</p><h3>Writing to a file</h3></div><button class="copy" type="button">Copy</button></div><p>This overwrites the file if it already exists.</p><pre><code>from pathlib import Path

path = Path(&quot;programming.txt&quot;)

msg = &quot;I love programming!&quot;
path.write_text(msg)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Files and Exceptions</p><h3>Writing multiple lines to a file</h3></div><button class="copy" type="button">Copy</button></div><pre><code>from pathlib import Path

path = Path(&quot;programming.txt&quot;)

msg = &quot;I love programming!&quot;
msg += &quot;\nI love making games.&quot;
path.write_text(msg)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Files and Exceptions</p><h3>Appending to a file</h3></div><button class="copy" type="button">Copy</button></div><p>To append, read the old contents first, add to them, and write everything back.</p><pre><code>from pathlib import Path

path = Path(&quot;programming.txt&quot;)
contents = path.read_text()

contents += &quot;\nI love programming!&quot;
contents += &quot;\nI love making games.&quot;
path.write_text(contents)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Files and Exceptions</p><h3>Relative path</h3></div><button class="copy" type="button">Copy</button></div><p>Relative to the .py file that&#x27;s running.</p><pre><code>path = Path(&quot;text_files/alice.txt&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Files and Exceptions</p><h3>Absolute path</h3></div><button class="copy" type="button">Copy</button></div><p>Starts at your system&#x27;s root folder. Use forward slashes even on Windows.</p><pre><code>path = Path(&quot;/Users/eric/text_files/alice.txt&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Files and Exceptions</p><h3>Get just the filename from a path</h3></div><button class="copy" type="button">Copy</button></div><pre><code>&gt;&gt;&gt; path = Path(&quot;text_files/alice.txt&quot;)
&gt;&gt;&gt; path.name
&#x27;alice.txt&#x27;</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Files and Exceptions</p><h3>Build a path</h3></div><button class="copy" type="button">Copy</button></div><pre><code>base_path = Path(&quot;/Users/eric/text_files&quot;)
file_path = base_path / &quot;alice.txt&quot;</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Files and Exceptions</p><h3>Check if a file exists</h3></div><button class="copy" type="button">Copy</button></div><pre><code>&gt;&gt;&gt; path = Path(&quot;text_files/alice.txt&quot;)
&gt;&gt;&gt; path.exists()
True</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Files and Exceptions</p><h3>Get the file type</h3></div><button class="copy" type="button">Copy</button></div><pre><code>&gt;&gt;&gt; path.suffix
&#x27;.txt&#x27;</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Files and Exceptions</p><h3>Handling the ZeroDivisionError exception</h3></div><button class="copy" type="button">Copy</button></div><p>Code that might fail goes in try. What to do on failure goes in except.</p><pre><code>try:
    print(5/0)
except ZeroDivisionError:
    print(&quot;You can&#x27;t divide by zero!&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Files and Exceptions</p><h3>Handling the FileNotFoundError exception</h3></div><button class="copy" type="button">Copy</button></div><pre><code>from pathlib import Path

path = Path(&quot;siddhartha.txt&quot;)
try:
    contents = path.read_text()
except FileNotFoundError:
    msg = f&quot;Can&#x27;t find file: {path.name}.&quot;
    print(msg)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Files and Exceptions</p><h3>Catching an exception (bad number input)</h3></div><button class="copy" type="button">Copy</button></div><p>The else block runs only if the try block succeeded.</p><pre><code>prompt = &quot;How many tickets do you need? &quot;
num_tickets = input(prompt)

try:
    num_tickets = int(num_tickets)
except ValueError:
    print(&quot;Please try again.&quot;)
else:
    print(&quot;Your tickets are printing.&quot;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Files and Exceptions</p><h3>Using an else block</h3></div><button class="copy" type="button">Copy</button></div><pre><code>print(&quot;Enter two numbers. I&#x27;ll divide them.&quot;)

x = input(&quot;First number: &quot;)
y = input(&quot;Second number: &quot;)

try:
    result = int(x) / int(y)
except ZeroDivisionError:
    print(&quot;You can&#x27;t divide by zero!&quot;)
else:
    print(result)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Files and Exceptions</p><h3>Preventing crashes caused by user input</h3></div><button class="copy" type="button">Copy</button></div><pre><code>&quot;&quot;&quot;A simple calculator for division only.&quot;&quot;&quot;

print(&quot;Enter two numbers. I&#x27;ll divide them.&quot;)
print(&quot;Enter &#x27;q&#x27; to quit.&quot;)

while True:
    x = input(&quot;\nFirst number: &quot;)
    if x == &#x27;q&#x27;:
        break

    y = input(&quot;Second number: &quot;)
    if y == &#x27;q&#x27;:
        break

    try:
        result = int(x) / int(y)
    except ZeroDivisionError:
        print(&quot;You can&#x27;t divide by zero!&quot;)
    else:
        print(result)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Files and Exceptions</p><h3>Failing silently with pass</h3></div><button class="copy" type="button">Copy</button></div><p>pass tells Python to do nothing and keep going.</p><pre><code>from pathlib import Path

f_names = [&#x27;alice.txt&#x27;, &#x27;siddhartha.txt&#x27;,
        &#x27;moby_dick.txt&#x27;, &#x27;little_women.txt&#x27;]

for f_name in f_names:
    # Report the length of each file found.
    path = Path(f_name)
    try:
        contents = path.read_text()
    except FileNotFoundError:
        pass
    else:
        lines = contents.splitlines()
        msg = f&quot;{f_name} has {len(lines)}&quot;
        msg += &quot; lines.&quot;
        print(msg)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Files and Exceptions</p><h3>Don&#x27;t use bare except blocks</h3></div><button class="copy" type="button">Copy</button></div><p>A bare except also catches Ctrl-C and system exits.</p><pre><code>try:
    # Do something
except:
    pass</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Files and Exceptions</p><h3>Use Exception instead</h3></div><button class="copy" type="button">Copy</button></div><pre><code>try:
    # Do something
except Exception:
    pass</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Files and Exceptions</p><h3>Printing the exception</h3></div><button class="copy" type="button">Copy</button></div><pre><code>try:
    # Do something
except Exception as e:
    print(e, type(e))</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Files and Exceptions</p><h3>Storing data with json.dumps()</h3></div><button class="copy" type="button">Copy</button></div><p>Saves a Python list or dictionary as text in a file.</p><pre><code>from pathlib import Path
import json

numbers = [2, 3, 5, 7, 11, 13]

path = Path(&quot;numbers.json&quot;)
contents = json.dumps(numbers)
path.write_text(contents)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Files and Exceptions</p><h3>Reading data with json.loads()</h3></div><button class="copy" type="button">Copy</button></div><pre><code>from pathlib import Path
import json

path = Path(&quot;numbers.json&quot;)
contents = path.read_text()
numbers = json.loads(contents)

print(numbers)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Files and Exceptions</p><h3>Making sure the stored data exists</h3></div><button class="copy" type="button">Copy</button></div><pre><code>from pathlib import Path
import json

path = Path(&quot;numbers.json&quot;)

try:
    contents = path.read_text()
except FileNotFoundError:
    msg = f&quot;Can&#x27;t find file: {path}&quot;
    print(msg)
else:
    numbers = json.loads(contents)
    print(numbers)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Testing Your Code</p><h3>Installing pytest with pip</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ python -m pip install --user pytest</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Testing Your Code</p><h3>A function to test (full_names.py)</h3></div><button class="copy" type="button">Copy</button></div><pre><code>def get_full_name(first, last):
    &quot;&quot;&quot;Return a full name.&quot;&quot;&quot;

    full_name = f&quot;{first} {last}&quot;
    return full_name.title()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Testing Your Code</p><h3>Using the function (names.py)</h3></div><button class="copy" type="button">Copy</button></div><pre><code>from full_names import get_full_name

janis = get_full_name(&#x27;janis&#x27;, &#x27;joplin&#x27;)
print(janis)

bob = get_full_name(&#x27;bob&#x27;, &#x27;dylan&#x27;)
print(bob)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Testing Your Code</p><h3>Building a test case with one unit test (test_full_names.py)</h3></div><button class="copy" type="button">Copy</button></div><p>pytest runs every function whose name starts with test_.</p><pre><code>from full_names import get_full_name

def test_first_last():
    &quot;&quot;&quot;Test names like Janis Joplin.&quot;&quot;&quot;
    full_name = get_full_name(&#x27;janis&#x27;,
            &#x27;joplin&#x27;)
    assert full_name == &#x27;Janis Joplin&#x27;</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Testing Your Code</p><h3>Running the test</h3></div><button class="copy" type="button">Copy</button></div><p>Each dot is one passing test.</p><pre><code>$ pytest
============= test session starts =============
platform darwin -- Python 3.11.0, pytest-7.1.2
rootdir: /.../testing_your_code
collected 1 item

test_full_names.py .                     [100%]
============== 1 passed in 0.01s ==============</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Testing Your Code</p><h3>Modifying the function in a way that breaks it</h3></div><button class="copy" type="button">Copy</button></div><p>A failing test shows that a change broke existing behavior.</p><pre><code>def get_full_name(first, middle, last):
    &quot;&quot;&quot;Return a full name.&quot;&quot;&quot;
    full_name = f&quot;{first} {middle} {last}&quot;
    return full_name.title()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Testing Your Code</p><h3>A failing test run</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ pytest
============= test session starts =============
test_full_names_failing.py F             [100%]

================== FAILURES ===================
_______________ test_first_last _______________
&gt;       full_name = get_full_name(&#x27;janis&#x27;,
                &#x27;joplin&#x27;)
E       TypeError: get_full_name() missing 1
        required positional argument: &#x27;last&#x27;

=========== short test summary info ===========
FAILED test_full_names.py::test_first_last...
============== 1 failed in 0.04s ==============</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Testing Your Code</p><h3>Using the function with middle names</h3></div><button class="copy" type="button">Copy</button></div><pre><code>from full_names import get_full_name

john = get_full_name(&#x27;john&#x27;, &#x27;lee&#x27;, &#x27;hooker&#x27;)
print(john)

david = get_full_name(&#x27;david&#x27;, &#x27;lee&#x27;, &#x27;roth&#x27;)
print(david)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Testing Your Code</p><h3>Fixing the code (make the middle name optional)</h3></div><button class="copy" type="button">Copy</button></div><p>Change the code until the test passes. Don&#x27;t rewrite the test to fit broken code.</p><pre><code>def get_full_name(first, last, middle=&#x27;&#x27;):
    &quot;&quot;&quot;Return a full name.&quot;&quot;&quot;

    if middle:
        full_name = f&quot;{first} {middle} {last}&quot;
    else:
        full_name = f&quot;{first} {last}&quot;

    return full_name.title()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Testing Your Code</p><h3>Running the test after the fix</h3></div><button class="copy" type="button">Copy</button></div><p>The original test passes again, so the old behavior still works.</p><pre><code>$ pytest
============= test session starts =============
test_full_names.py .                     [100%]
============== 1 passed in 0.01s ==============</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Testing Your Code</p><h3>Adding new tests</h3></div><button class="copy" type="button">Copy</button></div><pre><code>from full_names import get_full_name

def test_first_last():
    &quot;&quot;&quot;Test names like Janis Joplin.&quot;&quot;&quot;
    full_name = get_full_name(&#x27;janis&#x27;,
            &#x27;joplin&#x27;)
    assert full_name == &#x27;Janis Joplin&#x27;

def test_middle():
    &quot;&quot;&quot;Test names like David Lee Roth.&quot;&quot;&quot;
    full_name = get_full_name(&#x27;david&#x27;,
            &#x27;roth&#x27;, &#x27;lee&#x27;)
    assert full_name == &#x27;David Lee Roth&#x27;</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Testing Your Code</p><h3>Running the tests (two passing)</h3></div><button class="copy" type="button">Copy</button></div><p>Two dots mean two passing tests.</p><pre><code>$ pytest
============= test session starts =============
collected 2 items
test_full_names.py ..                    [100%]
============== 2 passed in 0.01s ==============</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Testing Your Code</p><h3>A variety of assert statements</h3></div><button class="copy" type="button">Copy</button></div><p>Check a==b or a!=b, whether x is True or False, and whether an item is in a list.</p><pre><code>assert a == b
assert a != b

assert x
assert not x

assert my_item in my_list
assert my_item not in my_list</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Testing Your Code</p><h3>Running tests from one file</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ pytest test_names_function.py</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Testing Your Code</p><h3>A class to test (account.py)</h3></div><button class="copy" type="button">Copy</button></div><pre><code>class Account():
    &quot;&quot;&quot;Manage a bank account.&quot;&quot;&quot;

    def __init__(self, balance=0):
        &quot;&quot;&quot;Set the initial balance.&quot;&quot;&quot;
        self.balance = balance

    def deposit(self, amount):
        &quot;&quot;&quot;Add to the balance.&quot;&quot;&quot;
        self.balance += amount

    def withdraw(self, amount):
        &quot;&quot;&quot;Subtract from the balance.&quot;&quot;&quot;
        self.balance -= amount</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Testing Your Code</p><h3>Building a test case for the class</h3></div><button class="copy" type="button">Copy</button></div><pre><code>from account import Account

def test_initial_balance():
    &quot;&quot;&quot;Default balance should be 0.&quot;&quot;&quot;
    account = Account()
    assert account.balance == 0

def test_deposit():
    &quot;&quot;&quot;Test a single deposit.&quot;&quot;&quot;
    account = Account()
    account.deposit(100)
    assert account.balance == 100</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Testing Your Code</p><h3>Using fixtures to support multiple tests</h3></div><button class="copy" type="button">Copy</button></div><p>A fixture builds one object that each test gets by naming it as a parameter.</p><pre><code>import pytest
from account import Account

@pytest.fixture
def account():
    account = Account()
    return account

def test_initial_balance(account):
    &quot;&quot;&quot;Default balance should be 0.&quot;&quot;&quot;
    assert account.balance == 0

def test_deposit(account):
    &quot;&quot;&quot;Test a single deposit.&quot;&quot;&quot;
    account.deposit(100)
    assert account.balance == 100

def test_withdrawal(account):
    &quot;&quot;&quot;Test a deposit followed by withdrawal.&quot;&quot;&quot;
    account.deposit(1_000)
    account.withdraw(100)
    assert account.balance == 900</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Testing Your Code</p><h3>Stop at the first failing test</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ pytest -x</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Testing Your Code</p><h3>Only run tests that failed during the last test run</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ pytest --last-failed</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Testing Your Code</p><h3>When is it okay to modify tests?</h3></div><button class="copy" type="button">Copy</button></div><p>That mostly happens early in a project, before anyone relies on your code.</p><pre><code># Usually a failing test means your new code broke something.
# Fix the code, not the test.
# Change a test only when the original requirements changed.</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>Installing Pygame with pip</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ python -m pip install --user pygame</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>An empty game window</h3></div><button class="copy" type="button">Copy</button></div><p>The whole game is a class. The while loop handles events and refreshes the screen 60 times per second.</p><pre><code>import sys
import pygame

class AlienInvasion:
    &quot;&quot;&quot;Overall class to manage the game.&quot;&quot;&quot;

    def __init__(self):
        pygame.init()
        self.clock = pygame.time.Clock()
        self.screen = pygame.display.set_mode(
                (1200, 800))
        pygame.display.set_caption(
                &quot;Alien Invasion&quot;)

    def run_game(self):
        while True:
            for event in pygame.event.get():
                if event.type == pygame.QUIT:
                    sys.exit()

            pygame.display.flip()
            self.clock.tick(60)

if __name__ == &#x27;__main__&#x27;:
    # Make a game instance, and run the game.
    ai = AlienInvasion()
    ai.run_game()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>Setting a custom window size</h3></div><button class="copy" type="button">Copy</button></div><pre><code>screen_dim = (1500, 1000)
self.screen = pygame.display.set_mode(
        screen_dim)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>Setting a custom background color</h3></div><button class="copy" type="button">Copy</button></div><p>Colors are (red, green, blue) tuples from 0 to 255. Fill before drawing anything else.</p><pre><code>def __init__(self):
    --snip--
    self.bg_color = (225, 225, 225)

def run_game(self):
    while True:
        for event in pygame.event.get():
            --snip--

        self.screen.fill(self.bg_color)
        pygame.display.flip()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>Getting the screen rect object</h3></div><button class="copy" type="button">Copy</button></div><pre><code>self.screen_rect = self.screen.get_rect()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>Finding the center of the screen</h3></div><button class="copy" type="button">Copy</button></div><pre><code>screen_center = self.screen_rect.center</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>Useful rect attributes</h3></div><button class="copy" type="button">Copy</button></div><pre><code># Individual x and y values:
screen_rect.left, screen_rect.right
screen_rect.top, screen_rect.bottom
screen_rect.centerx, screen_rect.centery
screen_rect.width, screen_rect.height

# Tuples
screen_rect.center
screen_rect.size</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>Creating a rect object</h3></div><button class="copy" type="button">Copy</button></div><p>Rect(x, y, width, height) takes the top-left corner and the size.</p><pre><code>bullet_rect = pygame.Rect(100, 100, 3, 15)
color = (100, 100, 100)

pygame.draw.rect(screen, color, bullet_rect)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>Loading an image</h3></div><button class="copy" type="button">Copy</button></div><pre><code>ship = pygame.image.load(&#x27;images/ship.bmp&#x27;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>Getting the rect object from an image</h3></div><button class="copy" type="button">Copy</button></div><pre><code>ship_rect = ship.get_rect()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>Positioning an image</h3></div><button class="copy" type="button">Copy</button></div><p>Match the ship&#x27;s bottom-center to the screen&#x27;s bottom-center.</p><pre><code>ship_rect.midbottom = screen_rect.midbottom</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>Drawing an image to the screen</h3></div><button class="copy" type="button">Copy</button></div><pre><code># Draw ship to screen.
screen.blit(ship, ship_rect)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>Transforming an image</h3></div><button class="copy" type="button">Copy</button></div><pre><code>rotated_image = pygame.transform.rotate(
        ship.image, 45)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>The blitme() method</h3></div><button class="copy" type="button">Copy</button></div><pre><code>def blitme(self):
    &quot;&quot;&quot;Draw ship at current location.&quot;&quot;&quot;
    self.screen.blit(self.image, self.rect)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>Responding to key presses</h3></div><button class="copy" type="button">Copy</button></div><pre><code>for event in pygame.event.get():
    if event.type == pygame.KEYDOWN:
        if event.key == pygame.K_RIGHT:
            ship_rect.x += 1
        elif event.key == pygame.K_LEFT:
            ship_rect.x -= 1
        elif event.key == pygame.K_SPACE:
            ship.fire_bullet()
        elif event.key == pygame.K_q:
            sys.exit()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>Responding to released keys</h3></div><button class="copy" type="button">Copy</button></div><pre><code>for event in pygame.event.get():
    if event.type == pygame.KEYUP:
        if event.key == pygame.K_RIGHT:
            ship.moving_right = False</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>Responding to the mouse button</h3></div><button class="copy" type="button">Copy</button></div><pre><code>for event in pygame.event.get():
    if event.type == pygame.MOUSEBUTTONDOWN:
        ship.fire_bullet()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>Finding the mouse position</h3></div><button class="copy" type="button">Copy</button></div><pre><code>mouse_pos = pygame.mouse.get_pos()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>Clicking a button</h3></div><button class="copy" type="button">Copy</button></div><pre><code>if button_rect.collidepoint(mouse_pos):
    start_game()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>Hiding the mouse</h3></div><button class="copy" type="button">Copy</button></div><pre><code>pygame.mouse.set_visible(False)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>Making and filling a group</h3></div><button class="copy" type="button">Copy</button></div><p>Anything you put in a group must inherit from Sprite.</p><pre><code>from pygame.sprite import Sprite, Group

class Bullet(Sprite):
    ...
    def draw_bullet(self):
        ...
    def update(self):
        ...

bullets = Group()

new_bullet = Bullet()
bullets.add(new_bullet)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>Looping through the items in a group</h3></div><button class="copy" type="button">Copy</button></div><pre><code>for bullet in bullets.sprites():
    bullet.draw_bullet()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>Calling update() on a group</h3></div><button class="copy" type="button">Copy</button></div><p>Calls update() on every member of the group.</p><pre><code>bullets.update()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>Removing an item from a group</h3></div><button class="copy" type="button">Copy</button></div><pre><code>bullets.remove(bullet)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>Collisions between a single object and a group</h3></div><button class="copy" type="button">Copy</button></div><pre><code>if pygame.sprite.spritecollideany(ship, aliens):
    ships_left -= 1</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>Collisions between two groups</h3></div><button class="copy" type="button">Copy</button></div><p>The two booleans say whether to delete the bullets and aliens that collided.</p><pre><code>collisions = pygame.sprite.groupcollide(
        bullets, aliens, True, True)

score += len(collisions) * alien_point_value</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Pygame</p><h3>Displaying a message</h3></div><button class="copy" type="button">Copy</button></div><pre><code>msg = &quot;Play again?&quot;
msg_color = (100, 100, 100)
bg_color = (230, 230, 230)

f = pygame.font.SysFont(None, 48)
msg_image = f.render(msg, True, msg_color,
        bg_color)
msg_image_rect = msg_image.get_rect()
msg_image_rect.center = screen_rect.center
screen.blit(msg_image, msg_image_rect)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Matplotlib</p><h3>Installing Matplotlib with pip</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ python -m pip install --user matplotlib</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Matplotlib</p><h3>Making a line graph</h3></div><button class="copy" type="button">Copy</button></div><p>fig is the whole figure. ax is one plot inside it.</p><pre><code>import matplotlib.pyplot as plt

x_values = [0, 1, 2, 3, 4, 5]
squares = [0, 1, 4, 9, 16, 25]

fig, ax = plt.subplots()
ax.plot(x_values, squares)

plt.show()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Matplotlib</p><h3>Making a scatter plot</h3></div><button class="copy" type="button">Copy</button></div><p>s=10 sets the size of each point.</p><pre><code>import matplotlib.pyplot as plt

x_values = list(range(1000))
squares = [x**2 for x in x_values]

fig, ax = plt.subplots()
ax.scatter(x_values, squares, s=10)
plt.show()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Matplotlib</p><h3>Using built-in styles</h3></div><button class="copy" type="button">Copy</button></div><p>Set the style before you create the figure.</p><pre><code>import matplotlib.pyplot as plt

x_values = list(range(1000))
squares = [x**2 for x in x_values]

plt.style.use(&#x27;seaborn-v0_8&#x27;)
fig, ax = plt.subplots()
ax.scatter(x_values, squares, s=10)

plt.show()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Matplotlib</p><h3>Seeing available styles</h3></div><button class="copy" type="button">Copy</button></div><pre><code>&gt;&gt;&gt; import matplotlib.pyplot as plt
&gt;&gt;&gt; plt.style.available
[&#x27;Solarize_Light2&#x27;, &#x27;_classic_test_patch&#x27;, ...</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Matplotlib</p><h3>Adding titles and labels, and scaling axes</h3></div><button class="copy" type="button">Copy</button></div><pre><code>import matplotlib.pyplot as plt

x_values = list(range(1000))
squares = [x**2 for x in x_values]

# Set overall style to use, and plot data.
plt.style.use(&#x27;seaborn-v0_8&#x27;)
fig, ax = plt.subplots()
ax.scatter(x_values, squares, s=10)

# Set chart title and label axes.
ax.set_title(&#x27;Square Numbers&#x27;, fontsize=24)
ax.set_xlabel(&#x27;Value&#x27;, fontsize=14)
ax.set_ylabel(&#x27;Square of Value&#x27;, fontsize=14)

# Set scale of axes, and size of tick labels.
ax.axis([0, 1100, 0, 1_100_000])
ax.tick_params(axis=&#x27;both&#x27;, labelsize=14)

plt.show()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Matplotlib</p><h3>Using a colormap</h3></div><button class="copy" type="button">Copy</button></div><p>A colormap shades each point based on its value.</p><pre><code>ax.scatter(x_values, squares, c=squares,
        cmap=plt.cm.Blues, s=10)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Matplotlib</p><h3>Emphasizing points</h3></div><button class="copy" type="button">Copy</button></div><pre><code>import matplotlib.pyplot as plt

x_values = list(range(1000))
squares = [x**2 for x in x_values]

fig, ax = plt.subplots()
ax.scatter(x_values, squares, c=squares,
        cmap=plt.cm.Blues, s=10)

ax.scatter(x_values[0], squares[0], c=&#x27;green&#x27;,
        s=100)
ax.scatter(x_values[-1], squares[-1], c=&#x27;red&#x27;,
        s=100)

ax.set_title(&#x27;Square Numbers&#x27;, fontsize=24)
--snip--</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Matplotlib</p><h3>Removing axes</h3></div><button class="copy" type="button">Copy</button></div><pre><code>ax.get_xaxis().set_visible(False)
ax.get_yaxis().set_visible(False)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Matplotlib</p><h3>Setting a custom figure size</h3></div><button class="copy" type="button">Copy</button></div><p>dpi is optional. Adjust figsize if you don&#x27;t know your screen&#x27;s resolution.</p><pre><code>fig, ax = plt.subplots(figsize=(10, 6),
        dpi=128)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Matplotlib</p><h3>Saving a plot</h3></div><button class="copy" type="button">Copy</button></div><p>Use this in place of plt.show(). bbox_inches trims extra whitespace.</p><pre><code>plt.savefig(&#x27;squares.png&#x27;, bbox_inches=&#x27;tight&#x27;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Matplotlib</p><h3>Plotting two sets of data</h3></div><button class="copy" type="button">Copy</button></div><pre><code>import matplotlib.pyplot as plt

x_values = list(range(11))
squares = [x**2 for x in x_values]
cubes = [x**3 for x in x_values]

plt.style.use(&#x27;seaborn-v0_8&#x27;)
fig, ax = plt.subplots()

ax.scatter(x_values, squares, c=&#x27;blue&#x27;, s=10)
ax.scatter(x_values, cubes, c=&#x27;red&#x27;, s=10)

plt.show()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Matplotlib</p><h3>Filling the space between data sets</h3></div><button class="copy" type="button">Copy</button></div><p>alpha controls how transparent the fill is.</p><pre><code>ax.fill_between(x_values, cubes, squares,
        facecolor=&#x27;blue&#x27;, alpha=0.25)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Matplotlib</p><h3>Generating the current date</h3></div><button class="copy" type="button">Copy</button></div><pre><code>from datetime import datetime as dt

today = dt.now()
date_string = today.strftime(&#x27;%m/%d/%Y&#x27;)
print(date_string)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Matplotlib</p><h3>Generating a specific date</h3></div><button class="copy" type="button">Copy</button></div><p>Order is year, month, day. Hour, minute, second are optional.</p><pre><code>from datetime import datetime as dt

new_years = dt(2023, 1, 1)
fall_equinox = dt(year=2023, month=9, day=22)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Matplotlib</p><h3>Datetime formatting codes</h3></div><button class="copy" type="button">Copy</button></div><pre><code>%A    Weekday name, such as Monday
%B    Month name, such as January
%m    Month, as a number (01 to 12)
%d    Day of the month, as a number (01 to 31)
%Y    Four-digit year, such as 2021
%y    Two-digit year, such as 21
%H    Hour, in 24-hour format (00 to 23)
%I    Hour, in 12-hour format (01 to 12)
%p    AM or PM
%M    Minutes (00 to 59)
%S    Seconds (00 to 61)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Matplotlib</p><h3>Converting a string to a datetime object</h3></div><button class="copy" type="button">Copy</button></div><pre><code>new_years = dt.strptime(&#x27;1/1/2023&#x27;, &#x27;%m/%d/%Y&#x27;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Matplotlib</p><h3>Converting a datetime object to a string</h3></div><button class="copy" type="button">Copy</button></div><pre><code>ny_string = new_years.strftime(&#x27;%B %d, %Y&#x27;)
print(ny_string)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Matplotlib</p><h3>Plotting high temperatures</h3></div><button class="copy" type="button">Copy</button></div><pre><code>from datetime import datetime as dt

import matplotlib.pyplot as plt
from matplotlib import dates as mdates

dates = [
    dt(2023, 6, 21), dt(2023, 6, 22),
    dt(2023, 6, 23), dt(2023, 6, 24),
    ]

highs = [56, 57, 57, 64]

plt.style.use(&#x27;seaborn-v0_8&#x27;)
fig, ax = plt.subplots()
ax.plot(dates, highs, c=&#x27;red&#x27;)

ax.set_title(&quot;Daily High Temps&quot;, fontsize=24)
ax.set_ylabel(&quot;Temp (F)&quot;, fontsize=16)
x_axis = ax.get_xaxis()
x_axis.set_major_formatter(
        mdates.DateFormatter(&#x27;%B %d %Y&#x27;)
        )
fig.autofmt_xdate()

plt.show()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Matplotlib</p><h3>Multiple plots: sharing an x-axis</h3></div><button class="copy" type="button">Copy</button></div><p>subplots(rows, columns) returns the figure and a list of axes.</p><pre><code>import matplotlib.pyplot as plt

x_values = list(range(11))
squares = [x**2 for x in x_values]
cubes = [x**3 for x in x_values]

fig, axs = plt.subplots(2, 1, sharex=True)

axs[0].scatter(x_values, squares)
axs[0].set_title(&#x27;Squares&#x27;)

axs[1].scatter(x_values, cubes, c=&#x27;red&#x27;)
axs[1].set_title(&#x27;Cubes&#x27;)

plt.show()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Matplotlib</p><h3>Multiple plots: sharing a y-axis</h3></div><button class="copy" type="button">Copy</button></div><pre><code>import matplotlib.pyplot as plt

x_values = list(range(11))
squares = [x**2 for x in x_values]
cubes = [x**3 for x in x_values]

plt.style.use(&#x27;seaborn-v0_8&#x27;)
fig, axs = plt.subplots(1, 2, sharey=True)

axs[0].scatter(x_values, squares)
axs[0].set_title(&#x27;Squares&#x27;)

axs[1].scatter(x_values, cubes, c=&#x27;red&#x27;)
axs[1].set_title(&#x27;Cubes&#x27;)

plt.show()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Plotly</p><h3>Installing Plotly with pip</h3></div><button class="copy" type="button">Copy</button></div><p>Plotly Express needs pandas.</p><pre><code>$ python -m pip install --user plotly
$ python -m pip install --user pandas</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Plotly</p><h3>Making a line graph</h3></div><button class="copy" type="button">Copy</button></div><p>fig.show() opens the plot in a new browser tab.</p><pre><code>import plotly.express as px

# Define the data.
x_values = list(range(11))
squares = [x**2 for x in x_values]

# Visualize the data.
fig = px.line(x=x_values, y=squares)
fig.show()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Plotly</p><h3>Making a scatter plot</h3></div><button class="copy" type="button">Copy</button></div><pre><code>fig = px.scatter(x=x_values, y=squares)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Plotly</p><h3>Making a bar graph</h3></div><button class="copy" type="button">Copy</button></div><pre><code>fig = px.bar(x=x_values, y=squares)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Plotly</p><h3>Adding a title and axis labels</h3></div><button class="copy" type="button">Copy</button></div><pre><code>import plotly.express as px

# Define the data.
x_values = list(range(11))
squares = [x**2 for x in x_values]

# Visualize the data.
title = &quot;Square Numbers&quot;
labels = {&#x27;x&#x27;: &#x27;Value&#x27;, &#x27;y&#x27;: &#x27;Square of Value&#x27;}

fig = px.scatter(x=x_values, y=squares,
        title=title, labels=labels)
fig.show()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Plotly</p><h3>More customizations in the plotting call</h3></div><button class="copy" type="button">Copy</button></div><pre><code>import plotly.express as px

x_values = list(range(11))
squares = [x**2 for x in x_values]

title = &quot;Square Numbers&quot;
labels = {&#x27;x&#x27;: &#x27;Value&#x27;, &#x27;y&#x27;: &#x27;Square of Value&#x27;}

fig = px.scatter(
    x=x_values,
    y=squares,
    title=title,
    labels=labels,
    size=squares,
    color=squares,
    opacity=0.5,
    width=1200,
    height=800,
)

fig.show()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Plotly</p><h3>Using update_layout()</h3></div><button class="copy" type="button">Copy</button></div><pre><code>import plotly.express as px

x_values = list(range(11))
squares = [x**2 for x in x_values]

title = &quot;Square Numbers&quot;
labels = {&#x27;x&#x27;: &#x27;Value&#x27;, &#x27;y&#x27;: &#x27;Square of Value&#x27;}

fig = px.scatter(
    x=x_values,
    y=squares,
    ...
)

fig.update_layout(
    title_font_size=30,
    xaxis_title_font_size=24,
    xaxis_dtick=1,
    xaxis_tickfont_size=16,
    yaxis_title_font_size=24,
    yaxis_tickfont_size=16,
)

fig.show()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Plotly</p><h3>Using a predefined theme</h3></div><button class="copy" type="button">Copy</button></div><pre><code>import plotly.express as px

# Define the data.
x_values = list(range(11))
squares = [x**2 for x in x_values]

# Visualize the data.
title = &quot;Square Numbers&quot;
labels = {&#x27;x&#x27;: &#x27;Value&#x27;, &#x27;y&#x27;: &#x27;Square of Value&#x27;}

fig = px.scatter(x=x_values, y=squares,
        title=title, labels=labels,
        template=&#x27;plotly_dark&#x27;)
fig.show()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Plotly</p><h3>Viewing all available themes</h3></div><button class="copy" type="button">Copy</button></div><pre><code>&gt;&gt;&gt; import plotly.io as pio
&gt;&gt;&gt; pio.templates
Templates configuration
-----------------------
    Default template: &#x27;plotly&#x27;
    Available templates:
        [&#x27;ggplot2&#x27;, &#x27;seaborn&#x27;,...,
         &#x27;ygridoff&#x27;, &#x27;gridon&#x27;, &#x27;none&#x27;]</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Plotly</p><h3>Adding traces to a Plotly Express plot</h3></div><button class="copy" type="button">Copy</button></div><p>A trace is one dataset on a chart.</p><pre><code>import plotly.express as px
import plotly.graph_objects as go

days = list(range(1, 10))
highs = [60, 63, 68, 70, 68, 70, 66, 62, 64]
lows = [51, 54, 53, 57, 54, 56, 52, 53, 49]

# Start by plotting low temperaturs.
fig = px.line(x=days, y=lows)

# Add a new trace for the high temperatures.
new_trace = go.Scatter(x=days, y=highs,
        mode=&#x27;lines&#x27;)
fig.add_trace(new_trace)

fig.show()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Plotly</p><h3>Adding subplots to a figure</h3></div><button class="copy" type="button">Copy</button></div><pre><code>from plotly.subplots import make_subplots
import plotly.graph_objects as go

x_values = list(range(11))
squares = [x**2 for x in x_values]
cubes = [x**3 for x in x_values]

# Make two subplots, sharing a y-axis.
fig = make_subplots(rows=1, cols=2,
        shared_yaxes=True)

# Start by plotting the square numbers.
squares_trace = go.Scatter(x=x_values,
        y=squares)
fig.add_trace(squares_trace, row=1, col=1)

# Add a new trace for the cubes.
cubes_trace = go.Scatter(x=x_values, y=cubes)
fig.add_trace(cubes_trace, row=1, col=2)

title = &quot;Squares and Cubes&quot;
fig.update_layout(title_text=title)

fig.show()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Plotly</p><h3>The scattergeo chart type</h3></div><button class="copy" type="button">Copy</button></div><p>Plots points by latitude and longitude on a map.</p><pre><code>import plotly.express as px

# Points in (lat, lon) format.
peak_coords = [
    (63.069, -151.0063),
    (60.5671, -140.4055),
    (46.8529, -121.7604),
]

# Make matching lists of lats, lons,
#   and labels.
lats = [pc[0] for pc in peak_coords]
lons = [pc[1] for pc in peak_coords]

peak_names = [
    &quot;Denali&quot;,
    &quot;Mt Logan&quot;,
    &quot;Mt Rainier&quot;
]
elevations = [20_000, 18_000, 14_000]

# Generate initial map.
title = &quot;Selected High Peaks&quot;
fig = px.scatter_geo(
    lat=lats,
    lon=lons,
    title=title,
    projection=&quot;natural earth&quot;,
    text=peak_names,
    size=elevations,
    scope=&quot;north america&quot;,
)

# Customize formatting options.
fig.update_layout(titlefont_size=24)
fig.update_traces(
    textposition=&quot;middle right&quot;,
    textfont_size=18,
)

fig.show()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Create a virtual environment</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ python -m venv ll_env</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Activate the environment (macOS and Linux)</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ source ll_env/bin/activate</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Activate the environment (Windows)</h3></div><button class="copy" type="button">Copy</button></div><pre><code>&gt; ll_env\Scripts\activate</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Install Django to the active environment</h3></div><button class="copy" type="button">Copy</button></div><pre><code>(ll_env)$ pip install Django</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Create a new project</h3></div><button class="copy" type="button">Copy</button></div><p>Include the dot at the end of the command.</p><pre><code>$ django-admin startproject ll_project .</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Create a database</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ python manage.py migrate</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>View the project</h3></div><button class="copy" type="button">Copy</button></div><p>Then open http://localhost:8000/ in your browser.</p><pre><code>$ python manage.py runserver</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Create a new app</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ python manage.py startapp learning_logs</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Defining a model</h3></div><button class="copy" type="button">Copy</button></div><p>Each model is a class. __str__() tells Django how to display one object.</p><pre><code>from django.db import models

class Topic(models.Model):
    &quot;&quot;&quot;A topic the user is learning about.&quot;&quot;&quot;

    text = models.CharField(max_length=200)
    date_added = models.DateTimeField(
            auto_now_add=True)

    def __str__(self):
        return self.text</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Activating a model</h3></div><button class="copy" type="button">Copy</button></div><p>Add your app to INSTALLED_APPS in settings.py.</p><pre><code>INSTALLED_APPS = [
    # My apps.
    &#x27;learning_logs&#x27;,

    # Default Django apps.
    &#x27;django.contrib.admin&#x27;,
]</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Migrating the database</h3></div><button class="copy" type="button">Copy</button></div><p>Run both commands every time you create or change a model.</p><pre><code>$ python manage.py makemigrations learning_logs
$ python manage.py migrate</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Creating a superuser</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ python manage.py createsuperuser</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Registering a model</h3></div><button class="copy" type="button">Copy</button></div><p>Then view the admin site at http://localhost:8000/admin/.</p><pre><code>from django.contrib import admin

from .models import Topic

admin.site.register(Topic)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Mapping a project&#x27;s URLs</h3></div><button class="copy" type="button">Copy</button></div><pre><code>from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path(&#x27;admin/&#x27;, admin.site.urls),
    path(&#x27;&#x27;, include(&#x27;learning_logs.urls&#x27;)),
]</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Mapping an app&#x27;s URLs</h3></div><button class="copy" type="button">Copy</button></div><pre><code>from django.urls import path

from . import views

app_name = &#x27;learning_logs&#x27;
urlpatterns = [
    # Home page.
    path(&#x27;&#x27;, views.index, name=&#x27;index&#x27;),
]</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Writing a simple view</h3></div><button class="copy" type="button">Copy</button></div><pre><code>from django.shortcuts import render

def index(request):
    &quot;&quot;&quot;The home page for Learning Log.&quot;&quot;&quot;
    return render(request,
            &#x27;learning_logs/index.html&#x27;)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Writing a simple template (index.html)</h3></div><button class="copy" type="button">Copy</button></div><p>Save it at learning_logs/templates/learning_logs/index.html.</p><pre><code>&lt;p&gt;Learning Log&lt;/p&gt;

&lt;p&gt;Learning Log helps you keep track of your
learning, for any topic you&#x27;re learning
about.&lt;/p&gt;</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>The parent template (base.html)</h3></div><button class="copy" type="button">Copy</button></div><pre><code>&lt;p&gt;
  &lt;a href=&quot;{% url &#x27;learning_logs:index&#x27; %}&quot;&gt;
    Learning Log
  &lt;/a&gt;
&lt;/p&gt;

{% block content %}{% endblock content %}</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>The child template</h3></div><button class="copy" type="button">Copy</button></div><pre><code>{% extends &#x27;learning_logs/base.html&#x27; %}

{% block content %}

  &lt;p&gt;
    Learning Log helps you keep track
    of your learning, for any topic you&#x27;re
    learning about.
  &lt;/p&gt;

{% endblock content %}</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Defining a model with a foreign key</h3></div><button class="copy" type="button">Copy</button></div><pre><code>class Entry(models.Model):
    &quot;&quot;&quot;Learning log entries for a topic.&quot;&quot;&quot;
    topic = models.ForeignKey(Topic,
            on_delete=models.CASCADE)
    text = models.TextField()
    date_added = models.DateTimeField(
            auto_now_add=True)

    def __str__(self):
        return f&quot;{self.text[:50]}...&quot;</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>URL parameters</h3></div><button class="copy" type="button">Copy</button></div><pre><code>urlpatterns = [
    --snip--
    # Detail page for a single topic.
    path(&#x27;topics/&lt;int:topic_id&gt;/&#x27;, views.topic,
            name=&#x27;topic&#x27;),
]</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Using data in a view</h3></div><button class="copy" type="button">Copy</button></div><pre><code>def topic(request, topic_id):
    &quot;&quot;&quot;Show a topic and all its entries.&quot;&quot;&quot;
    topic = Topic.objects.get(id=topic_id)
    entries = topic.entry_set.order_by(
            &#x27;-date_added&#x27;)
    context = {
        &#x27;topic&#x27;: topic,
        &#x27;entries&#x27;: entries,
    }
    return render(request,
            &#x27;learning_logs/topic.html&#x27;, context)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Using data in a template</h3></div><button class="copy" type="button">Copy</button></div><pre><code>{% extends &#x27;learning_logs/base.html&#x27; %}

{% block content %}

  &lt;p&gt;Topic: {{ topic }}&lt;/p&gt;

  &lt;p&gt;Entries:&lt;/p&gt;
  &lt;ul&gt;
  {% for entry in entries %}
    &lt;li&gt;
      &lt;p&gt;
        {{ entry.date_added|date:&#x27;M d, Y H:i&#x27; }}
      &lt;/p&gt;

      &lt;p&gt;
        {{ entry.text|linebreaks }}
      &lt;/p&gt;
    &lt;/li&gt;
  {% empty %}
    &lt;li&gt;There are no entries yet.&lt;/li&gt;
  {% endfor %}
  &lt;/ul&gt;

{% endblock content %}</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Start a shell session</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ python manage.py shell</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Access data from the project</h3></div><button class="copy" type="button">Copy</button></div><pre><code>&gt;&gt;&gt; from learning_logs.models import Topic
&gt;&gt;&gt; Topic.objects.all()
[&lt;Topic: Chess&gt;, &lt;Topic: Rock Climbing&gt;]
&gt;&gt;&gt; topic = Topic.objects.get(id=1)
&gt;&gt;&gt; topic.text
&#x27;Chess&#x27;
&gt;&gt;&gt; topic.entry_set.all()
&lt;QuerySet [&lt;Entry: In the opening phase...&gt;]&gt;</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Restarting the development server</h3></div><button class="copy" type="button">Copy</button></div><p>If a change doesn&#x27;t seem to have any effect, stop the server and run this again.</p><pre><code>$ python manage.py runserver</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Making an accounts app</h3></div><button class="copy" type="button">Copy</button></div><p>Then add &#x27;accounts&#x27; to INSTALLED_APPS in settings.py.</p><pre><code>$ python manage.py startapp accounts</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Including URLs for the accounts app</h3></div><button class="copy" type="button">Copy</button></div><pre><code>from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path(&#x27;admin/&#x27;, admin.site.urls),
    path(&#x27;accounts/&#x27;, include(&#x27;accounts.urls&#x27;)),
    path(&#x27;&#x27;, include(&#x27;learning_logs.urls&#x27;)),
]</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Defining the accounts URLs</h3></div><button class="copy" type="button">Copy</button></div><pre><code>from django.urls import path, include

from . import views

app_name = &#x27;accounts&#x27;
urlpatterns = [
    # Include default auth urls.
    path(&#x27;&#x27;, include(
            &#x27;django.contrib.auth.urls&#x27;)),

    # Registration page.
    path(&#x27;register/&#x27;, views.register,
            name=&#x27;register&#x27;),
]</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>The login template</h3></div><button class="copy" type="button">Copy</button></div><p>Save it as accounts/templates/registration/login.html. {% csrf_token %} helps prevent a common attack on forms.</p><pre><code>{% extends &quot;learning_logs/base.html&quot; %}

{% block content %}

  {% if form.errors %}
  &lt;p&gt;
    Your username and password didn&#x27;t match.
    Please try again.
  &lt;/p&gt;
  {% endif %}

  &lt;form action=&quot;{% url &#x27;accounts:login&#x27; %}&quot;
      method=&quot;post&quot;&gt;

    {% csrf_token %}
    {{ form.as_div }}
    &lt;button name=&quot;submit&quot;&gt;Log in&lt;/button&gt;

  &lt;/form&gt;

{% endblock content %}</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>The logout redirect setting in settings.py</h3></div><button class="copy" type="button">Copy</button></div><pre><code>LOGOUT_REDIRECT_URL = &#x27;learning_logs:index&#x27;</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Showing the current login status</h3></div><button class="copy" type="button">Copy</button></div><pre><code>&lt;p&gt;
  &lt;a href=&quot;{% url &#x27;learning_logs:index&#x27; %}&quot;&gt;
    Learning Log
  &lt;/a&gt;

  {% if user.is_authenticated %}
    Hello, {{ user.username }}.
    &lt;a href=&quot;{% url &#x27;accounts:logout&#x27; %}&quot;&gt;
      Log out
    &lt;/a&gt;
  {% else %}
    &lt;a href=&quot;{% url &#x27;accounts:register&#x27; %}&quot;&gt;
      Register
    &lt;/a&gt; -
    &lt;a href=&quot;{% url &#x27;accounts:login&#x27; %}&quot;&gt;
      Log in
    &lt;/a&gt;
  {% endif %}

&lt;/p&gt;

{% block content %}{% endblock content %}</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>The logout form</h3></div><button class="copy" type="button">Copy</button></div><pre><code>{% if user.is_authenticated %}
  &lt;form action=&quot;{% url &#x27;accounts:logout&#x27; %}&quot;
      method=&#x27;post&#x27;&gt;
    {% csrf_token %}
    &lt;button name=&#x27;submit&#x27;&gt;Log out&lt;/button&gt;

  &lt;/form&gt;
{% endif %}</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>The register view</h3></div><button class="copy" type="button">Copy</button></div><pre><code>from django.shortcuts import render, redirect
from django.contrib.auth import login
from django.contrib.auth.forms import \
        UserCreationForm

def register(request):
    &quot;&quot;&quot;Register a new user.&quot;&quot;&quot;

    if request.method != &#x27;POST&#x27;:
        # Display blank registration form.
        form = UserCreationForm()

    else:
        # Process completed form.
        form = UserCreationForm(
                data=request.POST)

        if form.is_valid():
            new_user = form.save()

            # Log in, redirect to home page.
            login(request, new_user)
            return redirect(
                    &#x27;learning_logs:index&#x27;)

    # Display a blank or invalid form.
    context = {&#x27;form&#x27;: form}

    return render(request,
        &#x27;registration/register.html&#x27;, context)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>The register template</h3></div><button class="copy" type="button">Copy</button></div><pre><code>{% extends &#x27;learning_logs/base.html&#x27; %}

{% block content %}

  &lt;form action=&quot;{% url &#x27;accounts:register&#x27; %}&quot;
      method=&quot;post&quot;&gt;

    {% csrf_token %}
    {{ form.as_div }}

    &lt;button name=&#x27;submit&#x27;&gt;Register&lt;/button&gt;

  &lt;/form&gt;

{% endblock content %}</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Making a topic belong to a user</h3></div><button class="copy" type="button">Copy</button></div><pre><code>from django.db import models
from django.contrib.auth.models import User

class Topic(models.Model):
    &quot;&quot;&quot;A topic the user is learning about.&quot;&quot;&quot;

    text = models.CharField(max_length=200)
    date_added = models.DateTimeField(
            auto_now_add=True)

    owner = models.ForeignKey(User,
            on_delete=models.CASCADE)

    def __str__(self):
        return self.text</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Querying data for the current user</h3></div><button class="copy" type="button">Copy</button></div><pre><code>topics = Topic.objects.filter(
        owner=request.user)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Restricting access to logged-in users</h3></div><button class="copy" type="button">Copy</button></div><pre><code>from django.contrib.auth.decorators import \
        login_required
--snip--

@login_required
def topic(request, topic_id):
    &quot;&quot;&quot;Show a topic and all its entries.&quot;&quot;&quot;</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Setting the redirect URL</h3></div><button class="copy" type="button">Copy</button></div><pre><code>LOGIN_URL = &#x27;accounts:login&#x27;</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Preventing inadvertent access</h3></div><button class="copy" type="button">Copy</button></div><pre><code>from django.http import Http404
--snip--

@login_required
def topic(request, topic_id):
    &quot;&quot;&quot;Show a topic and all its entries.&quot;&quot;&quot;
    topic = Topics.objects.get(id=topic_id)
    if topic.owner != request.user:
        raise Http404
    --snip--</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Creating a form with initial data</h3></div><button class="copy" type="button">Copy</button></div><pre><code>form = EntryForm(instance=entry)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Modifying data before saving</h3></div><button class="copy" type="button">Copy</button></div><p>commit=False lets you change the object before it&#x27;s written to the database.</p><pre><code>new_topic = form.save(commit=False)
new_topic.owner = request.user
new_topic.save()</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Django</p><h3>Deploying with Platform.sh and styling with Bootstrap</h3></div><button class="copy" type="button">Copy</button></div><p>Platform.sh has a free level for learning. You&#x27;ll need its command line tools and Git.</p><pre><code># Styling:    django-bootstrap5  -&gt;  django-bootstrap5.readthedocs.io/
# Deploying:  Platform.sh        -&gt;  platform.sh/marketplace/django</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Installing Git</h3></div><button class="copy" type="button">Copy</button></div><p>Check whether Git is already on your system. If not, get an installer at git-scm.com.</p><pre><code>$ git --version
git version 2.30.1 (Apple Git-130)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>See all global settings</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git config --list</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Set username</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git config --global user.name &quot;eric&quot;</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Set email</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git config --global user.email &quot;eric@example.com&quot;</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Set editor</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git config --global core.editor &quot;nano&quot;</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Ignore directories</h3></div><button class="copy" type="button">Copy</button></div><p>Put these in a file named .gitignore, with a leading dot and no extension.</p><pre><code>__pycache__/
my_venv/</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Ignore specific files</h3></div><button class="copy" type="button">Copy</button></div><pre><code>.DS_Store
secret_key.txt</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Ignore files with specific extensions</h3></div><button class="copy" type="button">Copy</button></div><pre><code>*.pyc</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Initialize a repository</h3></div><button class="copy" type="button">Copy</button></div><p>Don&#x27;t delete the hidden .git directory. It holds your history.</p><pre><code>$ git init
Initialized empty Git repository in my_project/.git/</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Check status</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git status
On branch main
No commits yet
Untracked files:
    .gitignore
    hello.py
    ...</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Add all files not in .gitignore</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git add .</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Add a single file</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git add hello.py</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Make a commit with a message</h3></div><button class="copy" type="button">Copy</button></div><p>-am commits all added files and records your message.</p><pre><code>$ git commit -am &quot;Started project, everything works.&quot;
2 files changed, 7 insertions(+)
create mode 100644 .gitignore
create mode 100644 hello.py</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Check log in default format</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git log
commit dc2ebd6... (HEAD -&gt; main)
Author: Eric Matthes &lt;eric@example.com&gt;
Date:   Feb 27 11:27:07 2023 -0900
    Greets user.
commit bf55851...
...</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Check log in simpler format</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git log --oneline
dc2ebd6 (HEAD -&gt; main) Greets uer.
bf55851 Started project, everything works.</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Visit a specific commit</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git checkout b9aedbb</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Return to most recent commit of main branch</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git checkout main</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Visit the previous commit</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git checkout HEAD^</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Visit an earlier commit</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git checkout HEAD^^^</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Visit the previous commit (HEAD~)</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git checkout HEAD~1</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Visit an earlier commit (HEAD~)</h3></div><button class="copy" type="button">Copy</button></div><p>HEAD is the most recent commit of the current branch.</p><pre><code>$ git checkout HEAD~3</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Make a new branch and switch to it</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git checkout -b new_branch_name
Switched to a new branch &#x27;new_branch_name&#x27;</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>See all branches</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git branch
main
* new_branch_name</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Switch to a different branch</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git checkout main
Switched to branch &#x27;main&#x27;</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Merge changes</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git merge new_branch_name
Updating b9aedbb..5e5130a
Fast-forward
 hello.py | 5 +++++
 1 file changed, 5 insertions(+)</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Delete a branch</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git branch -D new_branch_name
Deleted branch new_branch_name (was 5e5130a).</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Move last commit to new branch</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git branch new_branch_name
$ git reset --hard HEAD~1
$ git checkout new_branch_name</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Get rid of all uncommitted changes</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git checkout .</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Get rid of all changes since a specific commit</h3></div><button class="copy" type="button">Copy</button></div><p>Careful: this permanently discards your newer work.</p><pre><code>$ git reset --hard b9aedbb</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Create new branch starting at a previous commit</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git checkout -b branch_name b9aedbb</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Stash changes since last commit</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git stash
Saved working directory and index state
    WIP on main: f6f39a6...</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>See stashed changes</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git stash list
stash@{0}: WIP on main: f6f39a6...
stash@{1}: WIP on main: f6f39a6...
...</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Reapply changes from most recent stash</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git stash pop</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Reapply changes from a specific stash</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git stash pop --index 1</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Clear all stashed changes</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git stash clear</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>See all changes since last commit</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git diff</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>See changes in one file since last commit</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git diff hello.py</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>See changes since a specific commit</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git diff HEAD~2
$ git diff HEAD^^
$ git diff fab2cdd</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>See changes between two commits</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git diff fab2cdd 7c0a5d8</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>See changes in one file between two commits</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git diff fab2cdd 7c0a5d8 hello.py</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Clone an existing repository to your local system</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git clone https://github.com/ehmatthes/pcc_3e.git/
Cloning into &#x27;pcc_3e&#x27;...
...
Resolving deltas: 100% (1503/1503), done.</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Push a local project to a GitHub repository</h3></div><button class="copy" type="button">Copy</button></div><p>Make an empty repository on GitHub first.</p><pre><code>$ git remote add origin https://github.com/username/hello_repo.git
$ git push -u origin main
Enumerating objects: 10, done.
...
To https://github.com/username/hello_repo.git
 * [new branch]      main -&gt; main
Branch &#x27;main&#x27; set up to track remote branch &#x27;main&#x27; from &#x27;origin&#x27;.</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Push recent changes to your GitHub repository</h3></div><button class="copy" type="button">Copy</button></div><pre><code>$ git push origin branch_name</code></pre></article>
<article class="card"><div class="card-top"><div><p class="ref-group">Git</p><h3>Pull changes back into your local main branch</h3></div><button class="copy" type="button">Copy</button></div><p>Use this after merging a pull request on GitHub.</p><pre><code>$ git pull origin main</code></pre></article>
        </div>
      </details>
    </section>

    <section class="section" id="html">
      <div class="section-heading"><span class="badge">🧱</span><div><h2>HTML</h2></div></div>
      <p class="section-intro">HTML is the page's structure. Most tags have an opening tag and a closing tag. The closing tag has a slash.</p>
      <div class="cards">
        <article class="card"><div class="card-top"><h3>A tiny web page</h3><button class="copy" type="button">Copy</button></div><p>This is the basic shape of an HTML document.</p><pre><code>&lt;!doctype html&gt;
&lt;html lang="en"&gt;
  &lt;head&gt;&lt;title&gt;My Page&lt;/title&gt;&lt;/head&gt;
  &lt;body&gt;Hello!&lt;/body&gt;
&lt;/html&gt;</code></pre></article>
        <article class="card"><div class="card-top"><h3>Headings and paragraphs</h3><button class="copy" type="button">Copy</button></div><p>Use headings to name parts of a page and paragraphs for sentences.</p><pre><code>&lt;h1&gt;My Garden&lt;/h1&gt;
&lt;p&gt;I planted sunflowers.&lt;/p&gt;</code></pre></article>
        <article class="card"><div class="card-top"><h3>Make a link</h3><button class="copy" type="button">Copy</button></div><p><code>href</code> tells the link where to go. The words between the tags are clickable.</p><pre><code>&lt;a href="https://example.com"&gt;
  Visit this page
&lt;/a&gt;</code></pre></article>
        <article class="card"><div class="card-top"><h3>Add a picture</h3><button class="copy" type="button">Copy</button></div><p><code>src</code> is the picture file. <code>alt</code> describes it for people who cannot see it.</p><pre><code>&lt;img src="puppy.jpg"
     alt="A puppy playing"&gt;</code></pre></article>
        <article class="card"><div class="card-top"><h3>Make a list</h3><button class="copy" type="button">Copy</button></div><p><code>ul</code> makes a bullet list. Put each item inside an <code>li</code>.</p><pre><code>&lt;ul&gt;
  &lt;li&gt;Apples&lt;/li&gt;
  &lt;li&gt;Oranges&lt;/li&gt;
&lt;/ul&gt;</code></pre></article>
      </div>
<article class="card"><div class="card-top"><h3>Choose useful HTML elements</h3><button class="copy" type="button">Copy</button></div><p>Elements describe what their content means. This helps browsers, search tools, and assistive technology.</p><pre><code>&lt;header&gt;Top of the page&lt;/header&gt;
&lt;nav&gt;Page links&lt;/nav&gt;
&lt;main&gt;Main content&lt;/main&gt;
&lt;section&gt;A related part&lt;/section&gt;
&lt;footer&gt;Bottom of the page&lt;/footer&gt;</code></pre></article>
<article class="card"><div class="card-top"><h3>Add a button and a line break</h3><button class="copy" type="button">Copy</button></div><p>Buttons are for actions. Use a paragraph for a new paragraph; use &lt;br&gt; only for a line break inside text.</p><pre><code>&lt;button type=&quot;button&quot;&gt;Press me&lt;/button&gt;
&lt;p&gt;First line&lt;br&gt;Second line&lt;/p&gt;</code></pre></article>
<article class="card"><div class="card-top"><h3>Make an ordered list</h3><button class="copy" type="button">Copy</button></div><p>Use &lt;ol&gt; when the order matters, such as steps in a recipe.</p><pre><code>&lt;ol&gt;
  &lt;li&gt;Wash your hands&lt;/li&gt;
  &lt;li&gt;Mix the ingredients&lt;/li&gt;
  &lt;li&gt;Bake the muffins&lt;/li&gt;
&lt;/ol&gt;</code></pre></article>
<article class="card"><div class="card-top"><h3>Build a table for information</h3><button class="copy" type="button">Copy</button></div><p>Tables are for data arranged in rows and columns, not for page layout.</p><pre><code>&lt;table&gt;
  &lt;caption&gt;Team points&lt;/caption&gt;
  &lt;tr&gt;&lt;th scope=&quot;col&quot;&gt;Team&lt;/th&gt;&lt;th scope=&quot;col&quot;&gt;Points&lt;/th&gt;&lt;/tr&gt;
  &lt;tr&gt;&lt;td&gt;Owls&lt;/td&gt;&lt;td&gt;12&lt;/td&gt;&lt;/tr&gt;
&lt;/table&gt;</code></pre></article>
<article class="card"><div class="card-top"><h3>Create a simple form</h3><button class="copy" type="button">Copy</button></div><p>A label tells people what to enter. Matching for and id connect them.</p><pre><code>&lt;form&gt;
  &lt;label for=&quot;nickname&quot;&gt;Your nickname&lt;/label&gt;
  &lt;input id=&quot;nickname&quot; name=&quot;nickname&quot; type=&quot;text&quot;&gt;
  &lt;button type=&quot;submit&quot;&gt;Send&lt;/button&gt;
&lt;/form&gt;</code></pre></article>
<article class="card"><div class="card-top"><h3>Choose the right input</h3><button class="copy" type="button">Copy</button></div><p>Input types help a browser show the right keyboard and check the value.</p><pre><code>&lt;input type=&quot;email&quot; name=&quot;email&quot; required&gt;
&lt;input type=&quot;number&quot; name=&quot;age&quot; min=&quot;1&quot; max=&quot;120&quot;&gt;
&lt;input type=&quot;date&quot; name=&quot;birthday&quot;&gt;</code></pre></article>
<article class="card"><div class="card-top"><h3>Add a longer answer box</h3><button class="copy" type="button">Copy</button></div><p>Use textarea for a message that may take more than one line.</p><pre><code>&lt;label for=&quot;message&quot;&gt;Your message&lt;/label&gt;
&lt;textarea id=&quot;message&quot; name=&quot;message&quot; rows=&quot;4&quot;&gt;&lt;/textarea&gt;</code></pre></article>
<article class="card"><div class="card-top"><h3>Add sound or video</h3><button class="copy" type="button">Copy</button></div><p>Controls let visitors play, pause, or change the volume. Include fallback text.</p><pre><code>&lt;audio controls src=&quot;song.mp3&quot;&gt;Audio is not supported.&lt;/audio&gt;
&lt;video controls width=&quot;480&quot; src=&quot;movie.mp4&quot;&gt;Video is not supported.&lt;/video&gt;</code></pre></article>
<article class="card"><div class="card-top"><h3>Add a note for other coders</h3><button class="copy" type="button">Copy</button></div><p>Comments are visible in the source code, but do not appear on the page.</p><pre><code>&lt;!-- Remember to add a page title --&gt;
&lt;h1&gt;Science Fair&lt;/h1&gt;</code></pre></article>
<article class="card"><div class="card-top"><h3>Set page information</h3><button class="copy" type="button">Copy</button></div><p>The head holds page information. The viewport setting helps the page fit phone screens.</p><pre><code>&lt;head&gt;
  &lt;meta charset=&quot;utf-8&quot;&gt;
  &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width, initial-scale=1&quot;&gt;
  &lt;title&gt;My Website&lt;/title&gt;
&lt;/head&gt;</code></pre></article>
      <div class="tip"><strong>HTML reminder:</strong> Tags usually come in pairs, like <code>&lt;p&gt;</code> and <code>&lt;/p&gt;</code>. Put the page content inside <code>&lt;body&gt;</code>.</div>
    
      <details class="source-reference" open><summary>Full HTML reference: every entry from the supplied cheat sheet</summary>

      <div class="reference-topics" aria-label="Topics in the complete reference">
        <article class="reference-topic" id="html-topic-1"><h3>Document structure</h3><p>The document, head, body, and page title.</p></article>
        <article class="reference-topic" id="html-topic-2"><h3>Text and formatting</h3><p>Headings, paragraphs, line breaks, preformatted text, quotations, code, citations, emphasis, and older font tags.</p></article>
        <article class="reference-topic" id="html-topic-3"><h3>Links</h3><p>Website links, email links, and links to a place on the same page.</p></article>
        <article class="reference-topic" id="html-topic-4"><h3>Lists</h3><p>Bulleted lists, numbered lists, list items, and description lists.</p></article>
        <article class="reference-topic" id="html-topic-5"><h3>Images and page graphics</h3><p>Images, alternative text, horizontal rules, and older image sizing/alignment attributes.</p></article>
        <article class="reference-topic" id="html-topic-6"><h3>Forms</h3><p>Forms, dropdown menus, options, and text areas.</p></article>
        <article class="reference-topic" id="html-topic-7"><h3>Input types</h3><p>Text, email, URL, number, range, date/time, search, color, checkbox, radio, submit, image, and reset inputs.</p></article>
        <article class="reference-topic" id="html-topic-8"><h3>Tables</h3><p>Tables, rows, cells, header cells, row/column spans, and older table layout attributes.</p></article>
        <article class="reference-topic" id="html-topic-9"><h3>Older body styling attributes</h3><p>Legacy body color and link attributes; use CSS for modern pages.</p></article>
      </div>

<p class="section-intro">This preserves the complete original reference text. Some examples use older syntax; use the beginner examples above as the modern starting point.</p><pre class="source-text"><code>HTML Cheatsheet
Basic Tags Formatting
&lt;html&gt; &lt;/html&gt; &lt;p&gt; &lt;/p&gt;
Creates an HTML document Creates a new paragraph
&lt;head&gt; &lt;/head&gt; &lt;br&gt;
Sets off the title &amp; other info that isn&#x27;t displayed AInserts a line break (carriage return)
&lt;body&gt; &lt;/body&gt; &lt;blockquote&gt; &lt;/blockquote&gt;
Sets off the visible portion of the document Puts content in a quote - indents text from both sides
&lt;title&gt; &lt;/title&gt; &lt;div&gt; &lt;/div&gt;
Puts name of the document in the title bar; when Used to format block content with CSS
bookmarking pages, this is what is bookmarked &lt;span&gt; &lt;/span&gt;
Used to format inline content with CSS
Body attributes (only used in email newsletters)
&lt;body bgcolor=?&gt;
Sets background color, using name or hex value Lists
&lt;body text=?&gt; &lt;ul&gt; &lt;/ul&gt;
Sets text color, using name or hex value Creates an unordered list
&lt;body link=?&gt; &lt;ol start=?&gt; &lt;/ol&gt;
Sets color of links, using name or hex value Creates an ordered list (start=xx,
&lt;body vlink=?&gt; where xx is a counting number)
Sets color of visited links, using name or hex value &lt;li&gt; &lt;/li&gt;
&lt;body alink=?&gt; Encompasses each list item
Sets color of active links (while mouse-clicking) &lt;dl&gt; &lt;/dl&gt;
Creates a definition list
Text Tags &lt;dt&gt;
&lt;pre&gt; &lt;/pre&gt; Precedes each defintion term
Creates preformatted text &lt;dd&gt;
&lt;h1&gt; &lt;/h1&gt; --&gt; &lt;h6&gt; &lt;/h6&gt; Precedes each defintion
Creates headlines -- H1=largest, H6=smallest
&lt;b&gt; &lt;/b&gt; Graphical elements
Creates bold text (should use &lt;strong&gt; instead) &lt;hr&gt;
&lt;i&gt; &lt;/i&gt; Inserts a horizontal rule
Creates italicized text (should use &lt;em&gt; instead) &lt;hr size=?&gt;
&lt;tt&gt; &lt;/tt&gt; Sets size (height) of horizontal rule
Creates typewriter-style text &lt;hr width=?&gt;
&lt;code&gt; &lt;/code&gt; Sets width of rule (as a % or absolute pixel length)
Used to define source code, usually monospace &lt;hr noshade&gt;
&lt;cite&gt; &lt;/cite&gt; Creates a horizontal rule without a shadow
Creates a citation, usually processed in italics &lt;img src=&quot;URL&quot; /&gt;
&lt;address&gt; &lt;/address&gt; Adds image; it is a separate file located at the URL
Creates address section, usually processed in italics &lt;img src=&quot;URL&quot; align=?&gt;
&lt;em&gt; &lt;/em&gt; Aligns image left/right/center/bottom/top/middle (use CSS)
Emphasizes a word (usually processed in italics) &lt;img src=&quot;URL&quot; border=?&gt;
&lt;strong&gt; &lt;/strong&gt; Sets size of border surrounding image (use CSS)
Emphasizes a word (usually processed in bold) &lt;img src=&quot;URL&quot; height=?&gt;
&lt;font size=?&gt; &lt;/font&gt; Sets height of image, in pixels
Sets size of font - 1 to 7 (should use CSS instead) &lt;img src=&quot;URL&quot; width=?&gt;
&lt;font color=?&gt; &lt;/font&gt; Sets width of image, in pixels
Sets font color (should use CSS instead) &lt;img src=&quot;URL&quot; alt=?&gt;
&lt;font face=?&gt; &lt;/font&gt; Sets the alternate text for browsers that can&#x27;t
Defines the font used (should use CSS instead) process images (required by the ADA)
Links
&lt;a href=&quot;URL&quot;&gt;clickable text&lt;/a&gt;
Creates a hyperlink to a Uniform Resource Locator
&lt;a href=&quot;mailto:EMAIL_ADDRESS&quot;&gt;clickable text&lt;/a&gt;
Creates a hyperlink to an email address
&lt;a name=&quot;NAME&quot;&gt;
Creates a target location within a document
&lt;a href=&quot;#NAME&quot;&gt;clickable text&lt;/a&gt;
Creates a link to that target location
HTML Cheatsheet
Forms H TML5 input tag attributes
&lt;form&gt; &lt;/form&gt; (not all browsers support; visit http://caniuse.com
Defines a form for details)
&lt;select multiple name=? size=?&gt; &lt;/select&gt;
Creates a scrolling menu. Size sets the number of &lt;input type=&quot;email&quot; name=?&gt;
menu items visible before user needs to scroll. Sets a single-line textbox for email addresses
&lt;select name=?&gt; &lt;/select&gt; &lt;input type=&quot;url&quot; name=?&gt;
Creates a pulldown menu
Sets a single-line textbox for URLs
&lt;option&gt; &lt;input type=&quot;number&quot; name=?&gt;
Sets off each menu item
Sets a single-line textbox for a number
&lt;textarea name=? cols=&quot;x&quot; rows=&quot;y&quot;&gt;&lt;/textarea&gt;
&lt;input type=&quot;range&quot; name=?&gt;
Creates a text box area. Columns set the width;
Sets a single-line text box for a range of numbers
rows set the height.
&lt;input type=&quot;date/month/week/time&quot; name=?&gt;
&lt;input type=&quot;checkbox&quot; name=? value=?&gt;
Sets a single-line text box with a calendar
Creates a checkbox.
showing the date/month/week/time
&lt;input type=&quot;checkbox&quot; name=? value=? checked&gt;
&lt;input type=&quot;search&quot; name=?&gt;
Creates a checkbox which is pre-checked.
Sets a single-line text box for searching
&lt;input type=&quot;radio&quot; name=? value=?&gt;
&lt;input type=&quot;color&quot; name=?&gt;
Creates a radio button.
Sets a single-line text box for picking a color
&lt;input type=&quot;radio&quot; name=? value=? checked&gt;
Creates a radio button which is pre-checked.
&lt;input type=&quot;text&quot; name=? size=?&gt;
Creates a one-line text area. Size sets length, in
characters.
&lt;input type=&quot;submit&quot; value=?&gt;
Creates a submit button. Value sets the text in the
submit button.
&lt;input type=&quot;image&quot; name=? src=? border=? alt=?&gt;
Creates a submit button using an image.
&lt;input type=&quot;reset&quot;&gt;
Creates a reset button
Tables (use only for data layout - use CSS for page layout) Table attributes (only use for email newsletters)
&lt;table&gt; &lt;/table&gt; &lt;table border=?&gt;
Creates a table Sets the width of the border around table cells
&lt;tr&gt; &lt;/tr&gt; &lt;table cellspacing=?&gt;
Sets off each row in a table Sets amount of space between table cells
&lt;td&gt; &lt;/td&gt; &lt;table cellpadding=?&gt;
Sets off each cell in a row Sets amount of space between a cell&#x27;s border and
&lt;th&gt; &lt;/th&gt; its contents
Sets off the table header (a normal cell with bold, &lt;table width=?&gt;
centered text) Sets width of the table in pixels or as a percentage
&lt;tr align=?&gt;
Sets alignment for cells within the row
(left/center/right)
&lt;td align=?&gt;
Sets alignment for cells (left/center/right)
&lt;tr valign=?&gt;
Sets vertical alignment for cells within the row
(top/middle/bottom)
&lt;td valign=?&gt;
Sets vertical alignment for cell (top/middle/bottom)
&lt;td rowspan=?&gt;
Sets number of rows a cell should span (default=1)
&lt;td colspan=?&gt;
Sets number of columns a cell should span
&lt;td nowrap&gt;
Prevents lines within a cell from being broken to fit</code></pre></details>
</section>

    <section class="section" id="css">
      <div class="section-heading"><span class="badge">🎨</span><div><h2>CSS</h2></div></div>
      <p class="section-intro">CSS controls how a web page looks: colors, text, spacing, and where things sit.</p>
      <div class="cards">
        <article class="card"><div class="card-top"><h3>Pick a color and font</h3><button class="copy" type="button">Copy</button></div><p>A selector names what you want to style. This one styles every paragraph.</p><pre><code>p {
  color: navy;
  font-family: Arial, sans-serif;
}</code></pre></article>
        <article class="card"><div class="card-top"><h3>Style a heading</h3><button class="copy" type="button">Copy</button></div><p>Each style is a property followed by a value.</p><pre><code>h1 {
  color: purple;
  text-align: center;
}</code></pre></article>
        <article class="card"><div class="card-top"><h3>Use a class for one part</h3><button class="copy" type="button">Copy</button></div><p>A class lets you style selected elements. In CSS, its name starts with a dot.</p><pre><code>.important {
  background-color: #fff0b3;
  padding: 12px;
}</code></pre></article>
        <article class="card"><div class="card-top"><h3>Add a border and space</h3><button class="copy" type="button">Copy</button></div><p><code>padding</code> is space inside the border. <code>margin</code> is space outside it.</p><pre><code>.card {
  border: 2px solid steelblue;
  padding: 16px;
  margin: 12px;
}</code></pre></article>
        <article class="card"><div class="card-top"><h3>Line things up</h3><button class="copy" type="button">Copy</button></div><p>Flexbox makes it easier to place items next to each other.</p><pre><code>.row {
  display: flex;
  gap: 12px;
  align-items: center;
}</code></pre></article>
      </div>
<article class="card"><div class="card-top"><h3>Choose what to style</h3><button class="copy" type="button">Copy</button></div><p>A tag selector styles every matching tag. A class starts with a dot; an id starts with #.</p><pre><code>p { color: #253858; }
.note { background: lightyellow; }
#main-title { font-size: 2rem; }</code></pre></article>
<article class="card"><div class="card-top"><h3>Style links and hover</h3><button class="copy" type="button">Copy</button></div><p>A pseudo-class styles an element in a particular state, such as when a pointer is over it.</p><pre><code>a { color: #3157d5; }
a:hover { color: #19368e; }
button:focus-visible { outline: 3px solid orange; }</code></pre></article>
<article class="card"><div class="card-top"><h3>Understand the box model</h3><button class="copy" type="button">Copy</button></div><p>Every box has content, padding, border, and margin. This rule makes sizing easier to predict.</p><pre><code>* { box-sizing: border-box; }
.card {
  width: 240px;
  padding: 16px;
  border: 2px solid navy;
  margin: 12px;
}</code></pre></article>
<article class="card"><div class="card-top"><h3>Set a background</h3><button class="copy" type="button">Copy</button></div><p>Backgrounds can use colors or images. Keep text readable over them.</p><pre><code>body {
  background-color: #f4f7ff;
  background-image: linear-gradient(white, #eaf0ff);
}</code></pre></article>
<article class="card"><div class="card-top"><h3>Style text and spacing</h3><button class="copy" type="button">Copy</button></div><p>Line height and letter spacing can make text easier to read.</p><pre><code>p {
  font-size: 1rem;
  line-height: 1.6;
  letter-spacing: 0.02em;
  text-align: left;
}</code></pre></article>
<article class="card"><div class="card-top"><h3>Make a layout with grid</h3><button class="copy" type="button">Copy</button></div><p>Grid is useful for arranging items in rows and columns.</p><pre><code>.cards {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 16px;
}</code></pre></article>
<article class="card"><div class="card-top"><h3>Line items up with flexbox</h3><button class="copy" type="button">Copy</button></div><p>Flexbox arranges items in a row or column and can add space between them.</p><pre><code>.toolbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 12px;
}</code></pre></article>
<article class="card"><div class="card-top"><h3>Change layout for small screens</h3><button class="copy" type="button">Copy</button></div><p>A media query applies styles only when the screen is narrow.</p><pre><code>@media (max-width: 600px) {
  .cards { grid-template-columns: 1fr; }
  body { padding: 12px; }
}</code></pre></article>
<article class="card"><div class="card-top"><h3>Use a CSS variable</h3><button class="copy" type="button">Copy</button></div><p>Variables store reusable values. They start with two dashes and are read with var().</p><pre><code>:root { --favorite-color: #3157d5; }
button {
  color: white;
  background: var(--favorite-color);
}</code></pre></article>
<article class="card"><div class="card-top"><h3>Add a small animation</h3><button class="copy" type="button">Copy</button></div><p>Transitions make a style change feel smooth. Respect the reduced-motion setting.</p><pre><code>button { transition: transform 0.2s ease; }
button:hover { transform: scale(1.04); }
@media (prefers-reduced-motion: reduce) {
  button { transition: none; }
}</code></pre></article>
<article class="card"><div class="card-top"><h3>Control size and overflow</h3><button class="copy" type="button">Copy</button></div><p>max-width keeps an image from spilling out of its box.</p><pre><code>img {
  max-width: 100%;
  height: auto;
}
.long-list { overflow-x: auto; }</code></pre></article>
      <div class="tip"><strong>CSS reminder:</strong> The selector comes first. Put style rules inside <code>{ }</code> and end each rule with a semicolon.</div>
    
      <details class="source-reference" open><summary>Full CSS reference: every entry from the supplied cheat sheet</summary>

      <div class="reference-topics" aria-label="Topics in the complete reference">
        <article class="reference-topic" id="css-topic-1"><h3>Font properties</h3><p>Font family, style, variant, weight, size, and shorthand font rules.</p></article>
        <article class="reference-topic" id="css-topic-2"><h3>Text properties</h3><p>Word and letter spacing, decoration, vertical alignment, capitalization, alignment, indentation, and line height.</p></article>
        <article class="reference-topic" id="css-topic-3"><h3>Color and backgrounds</h3><p>Text color, background color, background images, repeat, attachment, and shorthand backgrounds.</p></article>
        <article class="reference-topic" id="css-topic-4"><h3>List styling</h3><p>List marker types, marker images, and marker placement.</p></article>
        <article class="reference-topic" id="css-topic-5"><h3>Margins</h3><p>All four margins and margin shorthand.</p></article>
        <article class="reference-topic" id="css-topic-6"><h3>Padding</h3><p>All four padding sides and padding shorthand.</p></article>
        <article class="reference-topic" id="css-topic-7"><h3>Borders</h3><p>Border sides, width, color, style, and shorthand.</p></article>
        <article class="reference-topic" id="css-topic-8"><h3>Sizing</h3><p>Width and height.</p></article>
        <article class="reference-topic" id="css-topic-9"><h3>Float and clear</h3><p>Older ways to wrap text around floated elements and move content below them.</p></article>
      </div>

<p class="section-intro">This preserves the complete original reference text. Some examples use older syntax; use the beginner examples above as the modern starting point.</p><pre class="source-text"><code>Cascading Style Sheets Cheat Sheet (CSS 1 and 2)
Font Properties Text Properties
Font-Family Word-Spacing
Changes the font family of certain words, sentences, Defines an additional amount of space between words.
paragraphs, etc. P EM { word-spacing: 0.4em; }
P { font-family: &quot;New Century Schoolbook&quot;, Times, serif; } P.note { word-spacing: -0.2em; }
Font-Style Letter-Spacing
Changes text: normal, oblique, and italics. Defines an additional amount of space between characters.
H1 { font-style: oblique; } H1 { letter-spacing: 0.1em; }
P { font-style: normal; } P.note { letter-spacing: -0.1em; }
Font-Variant Text-Decoration
Used to display font in normal or small-caps. Allows text to be decorated through one of five properties:
SPAN { font-variant: small-caps; } underline, overline, line-through, blink, none.
A:link, A:visited, A:active { text-decoration: none; }
Font-Weight
Used to specify the weight of the font. Vertical-Align
H1 { font-weight: 800; } or P { font-weight: normal; } Used to alter the vertical positioning of an inline element,
relative to its parent element or to the element&#x27;s line.
Font-Size IMG.middle { vertical-align: middle; }
Used to modify the size of the displayed font. IMG { vertical-align: 50%; }
H1 { font-size: large; } or P { font-size: 12pt; } .exponent { vertical-align: super; }
LI { font-size: 90%; }
STRONG { font-size: larger; } Text-Transform
Allows for capitalizing the first letter of each word (capitalize),
Font capitalizing all letters of a word (uppercase), using all small
Used to combine all properties of fonts. letters in each word(lowercase), and the inital value(none).
P { font: italic bold 12pt/14pt Times, serif; } H1 { text-transform: uppercase; }
H2 { text-transform: capitalize; }
Color and Background Properties Text-Align
Color Used to justify text left, center, right, and justify.
Changes the color of text. H1 { text-align: center; }
P.newspaper { text-align: justify; }
H1 { color: blue; } or H2 { color: #000080; }
Text-Indent
Background-Color
Used to specify the amount of indentation prior to the first line
Sets the background color of an element.
of text.
BODY { background-color: white; }
H1 { background-color: #000080; } P { text-indent: 5em; }
Background-Image Line-Height
Sets the background image of an element. Used to control the spacing between baselines of text.
BODY { background-image: url(/images/foo.gif); } P { line-height: 200%; }
P { background-image: url(http://www.htmlhelp.com/bg.png); }
Classification Properties
Background-Repeat
List-Style-Type
Determines how a specified background image is repeated.
Specifies the type of list-item marker, and is used if list-style-
The repeat-x value will repeat the image horizontally while the
image is none or if image loading is turned off.
repeat-y value will repeat the image vertically.
LI.square { list-style-type: square; }
BODY { background: white url(candybar.gif);
UL.plain { list-style-type: none; }
background-repeat: repeat-x; }
OL { list-style-type: upper-alpha; } /* A B C D E etc. */
OL OL { list-style-type: decimal; } /* 1 2 3 4 5 etc. */
Background-Attachment
OL OL OL { list-style-type: lower-roman; } /* i ii iii iv v etc. */
Determines if a specified background image will scroll with the
content or be fixed with regard to the canvas.
List-Style-Image
BODY { background: white url(candybar.gif);
Specifies the image that will be used as list-item marker when
background-attachment: fixed; }
image loading is turned on, replacing the marker specified in
the list-style-type property.
Background
UL.check { list-style-image: url(/LI-markers/checkmark.gif); }
Used to combine all properties of background.
UL LI.x { list-style-image: url(x.png); }
BODY { background: white url(http://www.htmlhelp.com/foo.gif); }
BLOCKQUOTE { background: #7fffd4; }
List-Style-Position
P { background: url(../backgrounds/pawn.png) #f0f8ff fixed; }
Determines where the marker is placed in regard to the list
TABLE { background: red url(leaves.jpg) no-repeat bottom right; }
item. If the value inside is used, the lines will wrap under the
marker instead of being indented. outside is default.
UL { list-style-position: inside; }
Cascading Style Sheets Cheatsheet (CSS 1&amp;2)
Box Properties
Margin-Top Border-Left-Width
Sets the top margin of an element by specifying a length or a Used to specify the width of an element&#x27;s left border.
percentage. P { border-left: 20%; }
BODY { margin-top: 5pt; }
Border-Width
Margin-Right Used to set the width of an element&#x27;s border (either all
Sets the right margin of an element by specifying a length or a borders, or specifying top border, right border, bottom border,
percentage. left border).
P.narrow { margin-right: 50%; } P { border-width: 20%; }
P { border-width: 10px 5px 10px 5px; }
Margin-Bottom
sets the bottom margin of an element by specifying a length or Border-Color
a percentage. Used to set the color of an element&#x27;s border.
DT { margin-bottom: 3em; } P { border-color: #00000; }
Margin-Left Border-Style
sets the left margin of an element by specifying a length or a Sets style of a border - none, dotted, dashed, solid, double.
percentage. P { border-style: dotted; }
ADDRESS { margin-left: 50%; }
Border-Top
Margin Sets the width, style, and color of an element&#x27;s top border.
Sets the margins of an element by specifying top, bottom, left P { border-top: 10px, red, double; }
and right margins -- all either specifying length or percentage.
Border-Right
BODY { margin: 5em; } /* all margins 5em */
P { margin: 2em 4em; } /* top &amp; bottom 2em, left &amp; right 4em */ Sets the width, style, and color of an element&#x27;s right border.
DIV { margin: 1em 2em 3em 4em; } P { border-right: 10px, red, double; }
/* top margin 1em, right 2em, bottom 3em, left 4em */
Border-Bottom
Padding-Top Sets the width, style, and color of an element&#x27;s bottom border.
Describes the amount of space between the top border and P { border-bottom: 10px, red, double; }
the content of the selector.
P { padding-top: 20%; } Border-Left
Sets the width, style, and color of an element&#x27;s left border.
Padding-Right P { border-left: 10px, red, double; }
Describes the amount of space between the right border and
the content of the selector. Border
P { padding-right: 20 px; } Sets the width, style, and color of an element&#x27;s border.
P { border: 10px, red, double; }
Padding-Bottom
Describes the amount of space between the bottom border Width
and the content of the selector. Each block-level or replaced element can be given a width,
P { padding-bottom: 5 em; } specified as a length, a percentage, or as auto.
P { width: 15px; }
Padding-Left H1 { width: 35%; }
Describes the amount of space between the left border and .foo { width: auto; }
the content of the selector.
Height
P { padding-left: 15 pt; }
Each block-level or replaced element can be given a height,
Padding specified as a length or as auto.
Shorthand for the padding-top, padding-right, padding-bottom, P { height: 15px; }
H1 { height: 35%; }
and padding-left properties.
.foo { height: auto; }
BLOCKQUOTE { padding: 2em 4em 5em 4em; }
Float
Border-Top-Width
Allows text to wrap around an element (left, right, none).
Used to specify the width of an element&#x27;s top border.
P { float: left; }
P { border-top: 20%; }
H1 { float: right; }
.foo { float: none; }
Border-Right-Width
Used to specify the width of an element&#x27;s right border.
Clear
P { border-right: 20%; }
Specifies whether an element allows floating elements to its
sides (left, right, none).
Border-Bottom-Width
P { clear: left; }
Used to specify the width of an element&#x27;s bottom border.
H1 { clear: right; }
P { border-bottom: 20%; }
.foo { clear: none; }</code></pre></details>
</section>

    <section class="section" id="javascript">
      <div class="section-heading"><span class="badge">⚡</span><div><h2>JavaScript</h2></div></div>
      <p class="section-intro">JavaScript makes a page interactive. It can remember information, make choices, and react to clicks.</p>
      <div class="cards">
        <article class="card"><div class="card-top"><h3>Remember a value</h3><button class="copy" type="button">Copy</button></div><p>Use <code>const</code> for a value you will not replace and <code>let</code> for one that can change.</p><pre><code>const player = "Ari";
let points = 0;
points = points + 1;</code></pre></article>
        <article class="card"><div class="card-top"><h3>Make a choice</h3><button class="copy" type="button">Copy</button></div><p>JavaScript runs one block when a test is true and another when it is false.</p><pre><code>if (points &gt; 0) {
  console.log("Nice job!");
} else {
  console.log("Start playing!");
}</code></pre></article>
        <article class="card"><div class="card-top"><h3>Repeat an action</h3><button class="copy" type="button">Copy</button></div><p>This loop counts from 1 up to 3. It stops before 4.</p><pre><code>for (let n = 1; n &lt;= 3; n++) {
  console.log(n);
}</code></pre></article>
        <article class="card"><div class="card-top"><h3>Write a function</h3><button class="copy" type="button">Copy</button></div><p>A function stores steps you can run again by calling its name.</p><pre><code>function sayHi(name) {
  return "Hi, " + name + "!";
}

console.log(sayHi("Lee"));</code></pre></article>
        <article class="card"><div class="card-top"><h3>React to a button click</h3><button class="copy" type="button">Copy</button></div><p>This finds a button on the page and listens for a click.</p><pre><code>const button = document.querySelector("button");
button.addEventListener("click", () =&gt; {
  alert("You clicked it!");
});</code></pre></article>
      </div>
<article class="card"><div class="card-top"><h3>Put JavaScript in a web page</h3><button class="copy" type="button">Copy</button></div><p>An external file is easier to organize. The defer option waits until the page is read.</p><pre><code>&lt;script src=&quot;app.js&quot; defer&gt;&lt;/script&gt;</code></pre></article>
<article class="card"><div class="card-top"><h3>Use comments and basic values</h3><button class="copy" type="button">Copy</button></div><p>Comments explain code to people. JavaScript has numbers, text, true/false values, and more.</p><pre><code>// Keep track of the game
const player = &quot;Nia&quot;;
let score = 0;
const isPlaying = true;</code></pre></article>
<article class="card"><div class="card-top"><h3>Work with arrays and objects</h3><button class="copy" type="button">Copy</button></div><p>An array is an ordered list. An object groups details under names.</p><pre><code>const colors = [&quot;red&quot;, &quot;blue&quot;, &quot;green&quot;];
colors.push(&quot;yellow&quot;);
console.log(colors[0]);

const pet = { name: &quot;Pip&quot;, kind: &quot;cat&quot; };
console.log(pet.name);</code></pre></article>
<article class="card"><div class="card-top"><h3>Use math and comparisons</h3><button class="copy" type="button">Copy</button></div><p>Math operators do arithmetic. === checks both value and type, so it is usually safer than ==.</p><pre><code>const total = 8 + 3 * 2;
const remainder = 10 % 3;
const isSame = (5 === 5);
const canPlay = (score &gt; 0 &amp;&amp; isPlaying);</code></pre></article>
<article class="card"><div class="card-top"><h3>Change or search text</h3><button class="copy" type="button">Copy</button></div><p>String methods can change letter case, split text, or find part of a word.</p><pre><code>const shout = &quot;hello&quot;.toUpperCase();
const words = &quot;red blue&quot;.split(&quot; &quot;);
const hasBlue = words.includes(&quot;blue&quot;);
const newName = &quot;Sam&quot;.replace(&quot;Sam&quot;, &quot;Sami&quot;);</code></pre></article>
<article class="card"><div class="card-top"><h3>Make a function that returns an answer</h3><button class="copy" type="button">Copy</button></div><p>Parameters are the inputs. return sends an answer back to the place that called the function.</p><pre><code>function add(a, b) {
  return a + b;
}
const answer = add(4, 6);</code></pre></article>
<article class="card"><div class="card-top"><h3>Repeat with while and break</h3><button class="copy" type="button">Copy</button></div><p>A while loop repeats while its test is true. Change something inside it so it can end.</p><pre><code>let count = 1;
while (count &lt;= 3) {
  console.log(count);
  count++;
}</code></pre></article>
<article class="card"><div class="card-top"><h3>Use Math and random numbers</h3><button class="copy" type="button">Copy</button></div><p>Math.random() gives a number from 0 up to (but not including) 1.</p><pre><code>const diceRoll = Math.floor(Math.random() * 6) + 1;
const bigger = Math.max(4, 9, 2);
const rounded = Math.round(3.6);</code></pre></article>
<article class="card"><div class="card-top"><h3>Work with dates</h3><button class="copy" type="button">Copy</button></div><p>Date can tell you the current time or the parts of a date. Months start at 0 when using getMonth().</p><pre><code>const now = new Date();
const year = now.getFullYear();
const month = now.getMonth() + 1;
const day = now.getDate();</code></pre></article>
<article class="card"><div class="card-top"><h3>Find and change a page element</h3><button class="copy" type="button">Copy</button></div><p>The DOM is the browser’s map of the page. querySelector finds the first matching element.</p><pre><code>const title = document.querySelector(&quot;h1&quot;);
title.textContent = &quot;Welcome!&quot;;
title.classList.add(&quot;highlight&quot;);</code></pre></article>
<article class="card"><div class="card-top"><h3>Listen for a click</h3><button class="copy" type="button">Copy</button></div><p>An event listener runs a function when an event happens.</p><pre><code>const button = document.querySelector(&quot;button&quot;);
button.addEventListener(&quot;click&quot;, () =&gt; {
  console.log(&quot;Clicked!&quot;);
});</code></pre></article>
<article class="card"><div class="card-top"><h3>Read a form safely</h3><button class="copy" type="button">Copy</button></div><p>The submit event happens when a form is sent. preventDefault stops the browser from reloading the page.</p><pre><code>const form = document.querySelector(&quot;form&quot;);
form.addEventListener(&quot;submit&quot;, event =&gt; {
  event.preventDefault();
  const answer = form.elements.nickname.value;
  console.log(answer);
});</code></pre></article>
<article class="card"><div class="card-top"><h3>Remember a small setting</h3><button class="copy" type="button">Copy</button></div><p>localStorage keeps simple text on this device between visits. Do not put passwords or secrets here.</p><pre><code>localStorage.setItem(&quot;theme&quot;, &quot;dark&quot;);
const theme = localStorage.getItem(&quot;theme&quot;);
localStorage.removeItem(&quot;theme&quot;);</code></pre></article>
<article class="card"><div class="card-top"><h3>Handle a problem</h3><button class="copy" type="button">Copy</button></div><p>try and catch let a program respond when something goes wrong.</p><pre><code>try {
  const data = JSON.parse(&quot;{bad json}&quot;);
} catch (error) {
  console.log(&quot;That data could not be read.&quot;);
}</code></pre></article>
<article class="card"><div class="card-top"><h3>Check text with a pattern</h3><button class="copy" type="button">Copy</button></div><p>A regular expression can check a simple pattern. This one checks for digits.</p><pre><code>const hasDigits = /\d+/.test(&quot;Room 12&quot;);
const cleaned = &quot;  hello  &quot;.trim();</code></pre></article>
<article class="card"><div class="card-top"><h3>Use a timer</h3><button class="copy" type="button">Copy</button></div><p>setTimeout runs a function once after a delay in milliseconds.</p><pre><code>setTimeout(() =&gt; {
  console.log(&quot;One second passed!&quot;);
}, 1000);</code></pre></article>
<article class="card"><div class="card-top"><h3>Understand the browser window</h3><button class="copy" type="button">Copy</button></div><p>The window is the browser tab. Use alerts sparingly; page content is usually friendlier.</p><pre><code>console.log(window.innerWidth);
console.log(window.location.href);
// Avoid putting private information in a URL.</code></pre></article>
<article class="card"><div class="card-top"><h3>Use keyboard and pointer events</h3><button class="copy" type="button">Copy</button></div><p>The same page can react to different kinds of user actions.</p><pre><code>document.addEventListener(&quot;keydown&quot;, event =&gt; {
  if (event.key === &quot;Escape&quot;) console.log(&quot;Escape pressed&quot;);
});

button.addEventListener(&quot;mouseover&quot;, () =&gt; {
  console.log(&quot;Pointer is over the button&quot;);
});</code></pre></article>
<article class="card"><div class="card-top"><h3>Avoid unsafe shortcuts</h3><button class="copy" type="button">Copy</button></div><p>Avoid eval(): it tries to run text as code and can create security problems.</p><pre><code>// Safer: parse JSON data as data
const settings = JSON.parse(&#x27;{&quot;sound&quot;: true}&#x27;);
// Do not use eval(userTypedText);</code></pre></article>
      <div class="tip"><strong>JavaScript reminder:</strong> Capital letters matter. <code>score</code> and <code>Score</code> are different names.</div>
    
      <details class="source-reference" open><summary>Full JavaScript reference, organized by topic</summary><p class="section-intro">Each topic opens separately. The original reference is preserved, including older methods and event names; see the note below about dated items.</p></details><details class="topic-detail" open><summary>Variables In JavaScript</summary><pre class="source-text"><code>var, const, let
var — The most common variable. Can be reassigned but only accessed
within a function. Variables defined with var move to the top when
code is executed.
const — Can not be reassigned and not accessible before they appear
within the code.
let — Similar to const, however, let variable can be reassigned but
not re-declared.
Data Types
Numbers — var age = 23
Variables — var x
Text (strings) — var a = &quot;init&quot;
Operations — var b = 1 + 2 + 3
3 of 24
True or fase statements — var c = true
Constant numbers — const PI = 3.14
Objects — var name = {firstName:&quot;John&quot;, lastName:”Doe&quot;}
Objects
var person = {
firstName:&quot;John&quot;,
lastName:&quot;Doe&quot;,
age:20,
nationality:&quot;German&quot;
};</code></pre></details><details class="topic-detail" open><summary>The Next Level: Arrays</summary><pre class="source-text"><code>var fruit = [&quot;Banana&quot;, &quot;Apple&quot;, &quot;Pear&quot;];
Array Methods
concat() — Join several arrays into one
indexOf() — Returns the primitive value of the specified object
join() — Combine elements of an array into a single string and return
the string
lastIndexOf() — Gives the last position at which a given element
appears in an array
pop() — Removes the last element of an array
push() — Add a new element at the end
reverse() — Sort elements in descending order
shift() — Remove the first element of an array
slice() — Pulls a copy of a portion of an array into a new array
4 of 24
sort() — Sorts elements alphabetically
splice() — Adds elements in a specified way and position
toString() — Converts elements to strings
unshift() — Adds a new element to the beginning
valueOf() — Returns the first position at which a given element
appears in an array</code></pre></details><details class="topic-detail" open><summary>Operators</summary><pre class="source-text"><code>Basic Operators
+ — Addition
- — Subtraction
* — Multiplication
/ — Division
(...) — Grouping operator, operations within brackets are executed
earlier than those outside
% — Modulus (remainder )
++ — Increment numbers
-- — Decrement numbers
Comparison Operators
== — Equal to
=== — Equal value and equal type
!= — Not equal
!== — Not equal value or not equal type
&gt; — Greater than
&lt; — Less than
&gt;= — Greater than or equal to
5 of 24
&lt;= — Less than or equal to
? — Ternary operator
Logical Operators
&amp;&amp; — Logical and
|| — Logical or
! — Logical not
Bitwise Operators
&amp; — AND statement
| — OR statement
~ — NOT
^ — XOR
&lt;&lt; — Left shift
&gt;&gt; — Right shift
&gt;&gt;&gt; — Zero fill right shift</code></pre></details><details class="topic-detail" open><summary>Functions</summary><pre class="source-text"><code>function name(parameter1, parameter2, parameter3) {
// what the function does
}
Outputting Data
alert() — Output data in an alert box in the browser window
confirm() — Opens up a yes/no dialog and returns true/false depending
on user click
console.log() — Writes information to the browser console, good for
debugging purposes
6 of 24
document.write() — Write directly to the HTML document
prompt() — Creates an dialogue for user input
Global Functions
decodeURI() — Decodes a Uniform Resource Identifier (URI) created
by encodeURI or similar
decodeURIComponent() — Decodes a URI component
encodeURI() — Encodes a URI into UTF-8
encodeURIComponent() — Same but for URI components
eval() — Evaluates JavaScript code represented as a string
isFinite() — Determines whether a passed value is a finite number
isNaN() — Determines whether a value is NaN or not
Number() — Returns a number converted from its argument
parseFloat() — Parses an argument and returns a floating point number
parseInt() — Parses its argument and returns an integer</code></pre></details><details class="topic-detail" open><summary>JavaScript Loops</summary><pre class="source-text"><code>for (before loop; condition for loop; execute after loop) {
// what to do during the loop
}
for — The most common way to create a loop in JavaScript
while — Sets up conditions under which aloop executes
do while — Similar to the while loop, however, it executes at least
once and performs a check at the end to see if the condition is met
to execute again
break — Used to stop and exit the cycle at certain conditions
continue — Skip parts of the cycle if certain conditions are met
7 of 24</code></pre></details><details class="topic-detail" open><summary>If and else choices</summary><pre class="source-text"><code>if (condition) {
// what to do if condition is met
} else {
// what to do if condition is not met
}</code></pre></details><details class="topic-detail" open><summary>Strings</summary><pre class="source-text"><code>var person = &quot;John Doe&quot;;
Escape Characters
\&#x27; — Single quote
\&quot; — Double quote
\\ — Backslash
\b — Backspace
\f — Form feed
\n — New line
\r — Carriage return
\t — Horizontal tabulator
\v — Vertical tabulator
String Methods
charAt() — Returns a character at a specified position inside a
string
charCodeAt() — Gives you the unicode of character at that position
concat() — Concatenates (joins) two or more strings into one
8 of 24
fromCharCode() — Returns a string created from the specified sequence
of UTF-16 code units
indexOf() — Provides the position of the first occurrence of a
specified text within a string
lastIndexOf() — Same as indexOf() but with the last occurrence,
searching backwards
match() — Retrieves the matches of a string against a search pattern
replace() — Find and replace specified text in a string
search() — Executes a search for a matching text and returns its
position
slice() — Extracts a section of a string and returns it as a new
string
split() — Splits a string object into an array of strings at a
specified position
substr() — Similar to slice() but extracts a substring depended on a
specified number of characters
substring() — Also similar to slice() but can’t accept negative
indices
toLowerCase() — Convert strings to lower case
toUpperCase() — Convert strings to upper case
valueOf() — Returns the primitive value (that has no properties or
methods) of a string object</code></pre></details><details class="topic-detail" open><summary>Regular Expression Syntax</summary><pre class="source-text"><code>Pattern Modifiers
e — Evaluate replacement
i — Perform case-insensitive matching
g — Perform global matching
m — Perform multiple line matching
s — Treat strings as single line
9 of 24
x — Allow comments and whitespace in pattern
U — Ungreedy pattern
Brackets
[abc] — Find any of the characters between the brackets
[^abc] — Find any character not in the brackets
[0-9] — Used to find any digit from 0 to 9
[A-z] — Find any character from uppercase A to lowercase z
(a|b|c) — Find any of the alternatives separated with |
Metacharacters
. — Find a single character, except newline or line terminator
\w — Word character
\W — Non-word character
\d — A digit
\D — A non-digit character
\s — Whitespace character
\S — Non-whitespace character
\b — Find a match at the beginning/end of a word
\B — A match not at the beginning/end of a word
\0 — NUL character
\n — A new line character
\f — Form feed character
\r — Carriage return character
\t — Tab character
\v — Vertical tab character
\xxx — The character specified by an octal number xxx
10 of 24
\xdd — Character specified by a hexadecimal number dd
\uxxxx — The Unicode character specified by a hexadecimal number xxxx
Quantifiers
n+ — Matches any string that contains at least one n
n* — Any string that contains zero or more occurrences of n
n? — A string that contains zero or one occurrences of n
n{X} — String that contains a sequence of X n’s
n{X,Y} — Strings that contains a sequence of X to Y n’s
n{X,} — Matches any string that contains a sequence of at least X n’s
n$ — Any string with n at the end of it
^n — String with n at the beginning of it
?=n — Any string that is followed by a specific string n
?!n — String that is not followed by a specific string n</code></pre></details><details class="topic-detail" open><summary>Numbers And Math</summary><pre class="source-text"><code>Number Properties
MAX_VALUE — The maximum numeric value representable in JavaScript
MIN_VALUE — Smallest positive numeric value representable in
JavaScript
NaN — The “Not-a-Number” value
NEGATIVE_INFINITY — The negative Infinity value
POSITIVE_INFINITY — Positive Infinity value
Number Methods
toExponential() — Returns a string with a rounded number written as
exponential notation
11 of 24
toFixed() — Returns the string of a number with a specified number of
decimals
toPrecision() — String of a number written with a specified length
toString() — Returns a number as a string
valueOf() — Returns a number as a number
Math Properties
E — Euler’s number
LN2 — The natural logarithm of 2
LN10 — Natural logarithm of 10
LOG2E — Base 2 logarithm of E
LOG10E — Base 10 logarithm of E
PI — The number PI
SQRT1_2 — Square root of 1/2
SQRT2 — The square root of 2
Math Methods
abs(x) — Returns the absolute (positive) value of x
acos(x) — The arccosine of x, in radians
asin(x) — Arcsine of x, in radians
atan(x) — The arctangent of x as a numeric value
atan2(y,x) — Arctangent of the quotient of its arguments
ceil(x) — Value of x rounded up to its nearest integer
cos(x) — The cosine of x (x is in radians)
exp(x) — Value of Ex
floor(x) — The value of x rounded down to its nearest integer
log(x) — The natural logarithm (base E) of x
12 of 24
max(x,y,z,...,n) — Returns the number with the highest value
min(x,y,z,...,n) — Same for the number with the lowest value
pow(x,y) — X to the power of y
random() — Returns a random number between 0 and 1
round(x) — The value of x rounded to its nearest integer
sin(x) — The sine of x (x is in radians)
sqrt(x) — Square root of x
tan(x) — The tangent of an angle</code></pre></details><details class="topic-detail" open><summary>Dealing With Dates In JavaScript</summary><pre class="source-text"><code>Setting Dates
Date() — Creates a new date object with the current date and time
Date(2017, 5, 21, 3, 23, 10, 0) — Create a custom date object. The
numbers represent year, month, day, hour, minutes, seconds,
milliseconds. You can omit anything you want except for year and
month.
Date(&quot;2017-06-23&quot;) — Date declaration as a string
Pulling Date and Time Values
getDate() — Get the day of the month as a number (1-31)
getDay() — The weekday as a number (0-6)
getFullYear() — Year as a four digit number (yyyy)
getHours() — Get the hour (0-23)
getMilliseconds() — The millisecond (0-999)
getMinutes() — Get the minute (0-59)
getMonth() — Month as a number (0-11)
getSeconds() — Get the second (0-59)
getTime() — Get the milliseconds since January 1, 1970
13 of 24
getUTCDate() — The day (date) of the month in the specified date
according to universal time (also available for day, month, fullyear,
hours, minutes etc.)
parse — Parses a string representation of a date, and returns the
number of milliseconds since January 1, 1970
Set Part of a Date
setDate() — Set the day as a number (1-31)
setFullYear() — Sets the year (optionally month and day)
setHours() — Set the hour (0-23)
setMilliseconds() — Set milliseconds (0-999)
setMinutes() — Sets the minutes (0-59)
setMonth() — Set the month (0-11)
setSeconds() — Sets the seconds (0-59)
setTime() — Set the time (milliseconds since January 1, 1970)
setUTCDate() — Sets the day of the month for a specified date
according to universal time (also available for day, month, fullyear,
hours, minutes etc.)</code></pre></details><details class="topic-detail" open><summary>DOM and the page</summary><pre class="source-text"><code>Node Properties
attributes — Returns a live collection of all attributes registered
to and element
baseURI — Provides the absolute base URL of an HTML element
childNodes — Gives a collection of an element’s child nodes
firstChild — Returns the first child node of an element
lastChild — The last child node of an element
nextSibling — Gives you the next node at the same node tree level
nodeName — Returns the name of a node
14 of 24
nodeType — Returns the type of a node
nodeValue — Sets or returns the value of a node
ownerDocument — The top-level document object for this node
parentNode — Returns the parent node of an element
previousSibling — Returns the node immediately preceding the current
one
textContent — Sets or returns the textual content of a node and its
descendants
Node Methods
appendChild() — Adds a new child node to an element as the last child
node
cloneNode() — Clones an HTML element
compareDocumentPosition() — Compares the document position of two
elements
getFeature() — Returns an object which implements the APIs of a
specified feature
hasAttributes() — Returns true if an element has any attributes,
otherwise false
hasChildNodes() — Returns true if an element has any child nodes,
otherwise false
insertBefore() — Inserts a new child node before a specified,
existing child node
isDefaultNamespace() — Returns true if a specified namespaceURI is
the default, otherwise false
isEqualNode() — Checks if two elements are equal
isSameNode() — Checks if two elements are the same node
isSupported() — Returns true if a specified feature is supported on
the element
lookupNamespaceURI() — Returns the namespaceURI associated with a
given node
15 of 24
lookupPrefix() — Returns a DOMString containing the prefix for a
given namespaceURI, if present
normalize() — Joins adjacent text nodes and removes empty text nodes
in an element
removeChild() — Removes a child node from an element
replaceChild() — Replaces a child node in an element
Element Methods
getAttribute() — Returns the specified attribute value of an element
node
getAttributeNS() — Returns string value of the attribute with the
specified namespace and name
getAttributeNode() — Gets the specified attribute node
getAttributeNodeNS() — Returns the attribute node for the attribute
with the given namespace and name
getElementsByTagName() — Provides a collection of all child elements
with the specified tag name
getElementsByTagNameNS() — Returns a live HTMLCollection of elements
with a certain tag name belonging to the given namespace
hasAttribute() — Returns true if an element has any attributes,
otherwise false
hasAttributeNS() — Provides a true/false value indicating whether the
current element in a given namespace has the specified attribute
removeAttribute() — Removes a specified attribute from an element
removeAttributeNS() — Removes the specified attribute from an element
within a certain namespace
removeAttributeNode() — Takes away a specified attribute node and
returns the removed node
setAttribute() — Sets or changes the specified attribute to a
specified value
setAttributeNS() — Adds a new attribute or changes the value of an
attribute with the given namespace and name
setAttributeNode() — Sets or changes the specified attribute node
16 of 24
setAttributeNodeNS() — Adds a new namespaced attribute node to an
element</code></pre></details><details class="topic-detail" open><summary>Browser window and screen</summary><pre class="source-text"><code>Window Properties
closed — Checks whether a window has been closed or not and returns
true or false
defaultStatus — Sets or returns the default text in the statusbar of
a window
document — Returns the document object for the window
frames — Returns all &lt;iframe&gt; elements in the current window
history — Provides the History object for the window
innerHeight — The inner height of a window’s content area
innerWidth — The inner width of the content area
length — Find out the number of &lt;iframe&gt; elements in the window
location — Returns the location object for the window
name — Sets or returns the name of a window
navigator — Returns the Navigator object for the window
opener — Returns a reference to the window that created the window
outerHeight — The outer height of a window, including toolbars/
scrollbars
outerWidth — The outer width of a window, including toolbars/
scrollbars
pageXOffset — Number of pixels the current document has been scrolled
horizontally
pageYOffset — Number of pixels the document has been scrolled
vertically
parent — The parent window of the current window
screen — Returns the Screen object for the window
17 of 24
screenLeft — The horizontal coordinate of the window (relative to
screen)
screenTop — The vertical coordinate of the window
screenX — Same as screenLeft but needed for some browsers
screenY — Same as screenTop but needed for some browsers
self — Returns the current window
status — Sets or returns the text in the statusbar of a window
top — Returns the topmost browser window
Window Methods
alert() — Displays an alert box with a message and an OK button
blur() — Removes focus from the current window
clearInterval() — Clears a timer set with setInterval()
clearTimeout() — Clears a timer set with setTimeout()
close() — Closes the current window
confirm() — Displays a dialogue box with a message and
an OK and Cancelbutton
focus() — Sets focus to the current window
moveBy() — Moves a window relative to its current position
moveTo() — Moves a window to a specified position
open() — Opens a new browser window
print() — Prints the content of the current window
prompt() — Displays a dialogue box that prompts the visitor for input
resizeBy() — Resizes the window by the specified number of pixels
resizeTo() — Resizes the window to a specified width and height
scrollBy() — Scrolls the document by a specified number of pixels
scrollTo() — Scrolls the document to specified coordinates
18 of 24
setInterval() — Calls a function or evaluates an expression at
specified intervals
setTimeout() — Calls a function or evaluates an expression after a
specified interval
stop() — Stops the window from loading
Screen Properties
availHeight — Returns the height of the screen (excluding the Windows
Taskbar)
availWidth — Returns the width of the screen (excluding the Windows
Taskbar)
colorDepth — Returns the bit depth of the color palette for
displaying images
height — The total height of the screen
pixelDepth — The color resolution of the screen in bits per pixel
width — The total width of the screen</code></pre></details><details class="topic-detail" open><summary>JavaScript Events</summary><pre class="source-text"><code>Mouse
onclick — The event occurs when the user clicks on an element
oncontextmenu — User right-clicks on an element to open a context
menu
ondblclick — The user double-clicks on an element
onmousedown — User presses a mouse button over an element
onmouseenter — The pointer moves onto an element
onmouseleave — Pointer moves out of an element
onmousemove — The pointer is moving while it is over an element
onmouseover — When the pointer is moved onto an element or one of its
children
19 of 24
onmouseout — User moves the mouse pointer out of an element or one of
its children
onmouseup — The user releases a mouse button while over an element
Keyboard
onkeydown — When the user is pressing a key down
onkeypress — The moment the user starts pressing a key
onkeyup — The user releases a key
Frame
onabort — The loading of a media is aborted
onbeforeunload — Event occurs before the document is about to be
unloaded
onerror — An error occurs while loading an external file
onhashchange — There have been changes to the anchor part of a URL
onload — When an object has loaded
onpagehide — The user navigates away from a webpage
onpageshow — When the user navigates to a webpage
onresize — The document view is resized
onscroll — An element’s scrollbar is being scrolled
onunload — Event occurs when a page has unloaded
Form
onblur — When an element loses focus
onchange — The content of a form element changes
(for &lt;input&gt;, &lt;select&gt;and &lt;textarea&gt;)
onfocus — An element gets focus
onfocusin — When an element is about to get focus
onfocusout — The element is about to lose focus
20 of 24
oninput — User input on an element
oninvalid — An element is invalid
onreset — A form is reset
onsearch — The user writes something in a search field
(for &lt;input=&quot;search&quot;&gt;)
onselect — The user selects some text (for &lt;input&gt; and &lt;textarea&gt;)
onsubmit — A form is submitted
Drag
ondrag — An element is dragged
ondragend — The user has finished dragging the element
ondragenter — The dragged element enters a drop target
ondragleave — A dragged element leaves the drop target
ondragover — The dragged element is on top of the drop target
ondragstart — User starts to drag an element
ondrop — Dragged element is dropped on the drop target
Clipboard
oncopy — User copies the content of an element
oncut — The user cuts an element’s content
onpaste — A user pastes content in an element
Media
onabort — Media loading is aborted
oncanplay — The browser can start playing media (e.g. a file has
buffered enough)
oncanplaythrough — When browser can play through media without
stopping
ondurationchange — The duration of the media changes
21 of 24
onended — The media has reach its end
onerror — Happens when an error occurs while loading an external file
onloadeddata — Media data is loaded
onloadedmetadata — Meta data (like dimensions and duration) are
loaded
onloadstart — Browser starts looking for specified media
onpause — Media is paused either by the user or automatically
onplay — The media has been started or is no longer paused
onplaying — Media is playing after having been paused or stopped for
buffering
onprogress — Browser is in the process of downloading the media
onratechange — The playing speed of the media changes
onseeked — User is finished moving/skipping to a new position in the
media
onseeking — The user starts moving/skipping
onstalled — The browser is trying to load the media but it is not
available
onsuspend — Browser is intentionally not loading media
ontimeupdate — The playing position has changed (e.g. because of fast
forward)
onvolumechange — Media volume has changed (including mute)
onwaiting — Media paused but expected to resume (for example,
buffering)
Animation
animationend — A CSS animation is complete
animationiteration — CSS animation is repeated
animationstart — CSS animation has started
Other
22 of 24
transitionend — Fired when a CSS transition has completed
onmessage — A message is received through the event source
onoffline — Browser starts to work offline
ononline — The browser starts to work online
onpopstate — When the window’s history changes
onshow — A &lt;menu&gt; element is shown as a context menu
onstorage — A Web Storage area is updated
ontoggle — The user opens or closes the &lt;details&gt; element
onwheel — Mouse wheel rolls up or down over an element
ontouchcancel — Screen touch is interrupted
ontouchend — User finger is removed from a touch screen
ontouchmove — A finger is dragged across the screen
ontouchstart — Finger is placed on touch screen</code></pre></details><details class="topic-detail" open><summary>Errors and exceptions</summary><pre class="source-text"><code>Errors
try — Lets you define a block of code to test for errors
catch — Set up a block of code to execute in case of an error
throw — Create custom error messages instead of the standard
JavaScript errors
finally — Lets you execute code, after try and catch, regardless of
the result
Error Name Values
name — Sets or returns the error name
message — Sets or returns an error message in string from
EvalError — An error has occurred in the eval() function
RangeError — A number is “out of range”
ReferenceError — An illegal reference has occurred
23 of 24
SyntaxError — A syntax error has occurred
TypeError — A type error has occurred
URIError — An encodeURI() error has occurred
24 of 24</code></pre></details></details>
</section>
    <p class="empty" id="empty">No examples match that search. Try a different word.</p>
  </main>
  </div>

    <section class="planner-section app-view" id="nikhil-planner" hidden>
    <h2>Nikhil’s Python notebook</h2>
    <iframe class="docs-workspace-frame" data-owner="nikhil" title="Nikhil’s Python notes workspace"></iframe>
    <p class="course-planner-intro">Course schedule and progress tracker</p>
    <iframe class="planner-frame" title="Nikhil’s Python course planner" loading="lazy" srcdoc="&lt;!doctype html&gt;&lt;html lang=&quot;en&quot;&gt;&lt;head&gt;&lt;meta charset=&quot;utf-8&quot;&gt;&lt;meta name=&quot;viewport&quot; content=&quot;width=device-width,initial-scale=1&quot;&gt;&lt;title&gt;Nikhil’s Python Course — Daily To‑Do&lt;/title&gt;&lt;style&gt;
:root{--ink:#20213a;--muted:#77798d;--purple:#7044df;--lav:#f1edff;--line:#e8e7ef;--bg:#f6f6fa;--green:#16835d;--amber:#b87516}*{box-sizing:border-box}body{margin:0;background:var(--bg);color:var(--ink);font:15px/1.5 system-ui,-apple-system,Segoe UI,sans-serif}.wrap{max-width:1100px;margin:auto;padding:30px 20px 60px}.top{display:flex;justify-content:space-between;align-items:center;gap:15px}.eyebrow{font-size:12px;text-transform:uppercase;letter-spacing:.1em;color:var(--purple);font-weight:750}h1{font-size:clamp(28px,4vw,42px);line-height:1.12;margin:5px 0}p{margin:6px 0;color:var(--muted)}.today{background:#fff;border:1px solid var(--line);border-radius:13px;padding:10px 14px;color:var(--muted)}.today b{display:block;color:var(--ink)}.stats{display:grid;grid-template-columns:repeat(4,1fr);gap:12px;margin:22px 0}.stat,.panel{background:#fff;border:1px solid var(--line);border-radius:15px}.stat{padding:13px 17px}.stat b{font-size:25px;display:block}.stat span{font-size:12px;color:var(--muted)}.layout{display:grid;grid-template-columns:minmax(0,1fr) 285px;gap:16px}.panel{padding:18px}.panel h2{font-size:19px;margin:0}.head{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-bottom:14px}.tools{display:flex;gap:8px;flex-wrap:wrap}.btn,select,input{font:inherit}.btn{border:1px solid var(--line);background:#fff;border-radius:9px;padding:8px 11px;color:var(--ink);cursor:pointer}.btn.primary{background:var(--purple);border-color:var(--purple);color:white;font-weight:650}.filters{display:flex;gap:7px;margin-bottom:12px;flex-wrap:wrap}.filter{border:1px solid var(--line);background:white;border-radius:99px;padding:6px 10px;color:var(--muted);cursor:pointer;font-size:12px}.filter.active{background:var(--lav);border-color:#d8ccff;color:var(--purple);font-weight:700}.list{display:grid;gap:8px}.task{display:grid;grid-template-columns:32px 1fr auto;gap:10px;align-items:start;border:1px solid var(--line);border-radius:11px;padding:11px}.task.done{background:#fbfffd}.check{width:26px;height:26px;border:1.5px solid #c9c8d5;border-radius:8px;background:white;color:white;cursor:pointer;font-size:16px;line-height:20px}.task.done .check{background:var(--green);border-color:var(--green)}.title{font-weight:650;line-height:1.35}.task.done .title{text-decoration:line-through;color:var(--muted)}.meta{font-size:11px;color:var(--muted);margin-top:4px}.meter{white-space:nowrap;display:flex;align-items:center;gap:6px}.meter button{width:25px;height:25px;border-radius:7px;border:1px solid var(--line);background:white;cursor:pointer}.count{font-size:12px;font-weight:700;min-width:32px;text-align:center}.bar{height:4px;width:65px;border-radius:4px;background:#eeeaf5;margin-top:5px}.bar i{display:block;height:100%;background:var(--purple);border-radius:4px}.sidebar{display:grid;gap:15px;align-content:start}.weeknav{display:flex;justify-content:space-between;align-items:center;margin:12px 0}.weeknav button{border:1px solid var(--line);background:white;border-radius:8px;padding:6px 10px;cursor:pointer}.days{display:grid;gap:6px}.day{display:flex;justify-content:space-between;padding:9px;border:1px solid transparent;border-radius:9px;background:#faf9fd;cursor:pointer;font-size:13px}.day.selected{background:var(--lav);border-color:#d8ccff}.day small{color:var(--muted)}.progress{height:7px;border-radius:9px;background:#eeeaf5;margin:12px 0 5px;overflow:hidden}.progress i{display:block;height:100%;background:var(--purple)}.addform{display:grid;gap:8px;margin-top:12px}.addform input,.addform select{width:100%;border:1px solid var(--line);border-radius:8px;padding:9px;background:#fff}.notice{font-size:11px;color:var(--muted);margin-top:13px}.empty{text-align:center;padding:28px;color:var(--muted);border:1px dashed var(--line);border-radius:10px}.foot{font-size:11px;color:var(--muted);margin-top:15px}@media(max-width:760px){.layout{grid-template-columns:1fr}.stats{grid-template-columns:repeat(2,1fr)}.top{align-items:flex-start;flex-direction:column}.today{width:100%}.task{grid-template-columns:30px 1fr}.meter{grid-column:2}}
&lt;/style&gt;&lt;/head&gt;&lt;body&gt;&lt;main class=&quot;wrap&quot;&gt;&lt;header class=&quot;top&quot;&gt;&lt;div&gt;&lt;div class=&quot;eyebrow&quot;&gt;102 course sections · day-by-day plan&lt;/div&gt;&lt;h1&gt;Nikhil’s Python Course To‑Do&lt;/h1&gt;&lt;p&gt;Check off a section or adjust the lesson count as you go. Your progress saves in this browser.&lt;/p&gt;&lt;/div&gt;&lt;div class=&quot;today&quot;&gt;Today&lt;b id=&quot;today&quot;&gt;&lt;/b&gt;&lt;/div&gt;&lt;/header&gt;&lt;section class=&quot;stats&quot;&gt;&lt;div class=&quot;stat&quot;&gt;&lt;b id=&quot;finished&quot;&gt;0&lt;/b&gt;&lt;span&gt;Sections finished&lt;/span&gt;&lt;/div&gt;&lt;div class=&quot;stat&quot;&gt;&lt;b id=&quot;remaining&quot;&gt;0&lt;/b&gt;&lt;span&gt;Sections to do&lt;/span&gt;&lt;/div&gt;&lt;div class=&quot;stat&quot;&gt;&lt;b id=&quot;lessons&quot;&gt;&lt;/b&gt;&lt;span&gt;Lessons completed&lt;/span&gt;&lt;/div&gt;&lt;div class=&quot;stat&quot;&gt;&lt;b id=&quot;percent&quot;&gt;0%&lt;/b&gt;&lt;span&gt;Course progress&lt;/span&gt;&lt;/div&gt;&lt;/section&gt;&lt;div class=&quot;layout&quot;&gt;&lt;section class=&quot;panel&quot;&gt;&lt;div class=&quot;head&quot;&gt;&lt;div&gt;&lt;h2 id=&quot;listTitle&quot;&gt;Your day-by-day list&lt;/h2&gt;&lt;p id=&quot;listSub&quot;&gt;Sections are scheduled one per day, starting today.&lt;/p&gt;&lt;/div&gt;&lt;div class=&quot;tools&quot;&gt;&lt;button class=&quot;btn&quot; id=&quot;viewBtn&quot;&gt;View: All&lt;/button&gt;&lt;button class=&quot;btn&quot; id=&quot;resetBtn&quot;&gt;Reset progress&lt;/button&gt;&lt;/div&gt;&lt;/div&gt;&lt;div class=&quot;filters&quot;&gt;&lt;button class=&quot;filter active&quot; data-filter=&quot;all&quot;&gt;All sections&lt;/button&gt;&lt;button class=&quot;filter&quot; data-filter=&quot;todo&quot;&gt;To do&lt;/button&gt;&lt;button class=&quot;filter&quot; data-filter=&quot;progress&quot;&gt;In progress&lt;/button&gt;&lt;button class=&quot;filter&quot; data-filter=&quot;done&quot;&gt;Completed&lt;/button&gt;&lt;/div&gt;&lt;div class=&quot;list&quot; id=&quot;list&quot;&gt;&lt;/div&gt;&lt;div class=&quot;foot&quot;&gt;Lesson totals and completed counts are copied from the progress shown in your screenshots. Titles ending in … were cut off in the images.&lt;/div&gt;&lt;/section&gt;&lt;aside class=&quot;sidebar&quot;&gt;&lt;section class=&quot;panel&quot;&gt;&lt;h2&gt;Calendar&lt;/h2&gt;&lt;div class=&quot;weeknav&quot;&gt;&lt;button id=&quot;prev&quot;&gt;←&lt;/button&gt;&lt;b id=&quot;weekLabel&quot;&gt;&lt;/b&gt;&lt;button id=&quot;next&quot;&gt;→&lt;/button&gt;&lt;/div&gt;&lt;div id=&quot;days&quot; class=&quot;days&quot;&gt;&lt;/div&gt;&lt;/section&gt;&lt;section class=&quot;panel&quot;&gt;&lt;h2&gt;Add a personal task&lt;/h2&gt;&lt;p&gt;Add reminders alongside the course.&lt;/p&gt;&lt;form id=&quot;form&quot; class=&quot;addform&quot;&gt;&lt;input id=&quot;name&quot; placeholder=&quot;What do you need to do?&quot; required&gt;&lt;input id=&quot;date&quot; type=&quot;date&quot; required&gt;&lt;button class=&quot;btn primary&quot;&gt;Add task&lt;/button&gt;&lt;/form&gt;&lt;div id=&quot;customList&quot; class=&quot;notice&quot;&gt;&lt;/div&gt;&lt;/section&gt;&lt;section class=&quot;panel&quot;&gt;&lt;h2&gt;Overall progress&lt;/h2&gt;&lt;div class=&quot;progress&quot;&gt;&lt;i id=&quot;overallBar&quot;&gt;&lt;/i&gt;&lt;/div&gt;&lt;div class=&quot;notice&quot; id=&quot;overallText&quot;&gt;&lt;/div&gt;&lt;/section&gt;&lt;/aside&gt;&lt;/div&gt;&lt;/main&gt;&lt;script&gt;
const original=[{&quot;day&quot;: 1, &quot;title&quot;: &quot;Day 1 - Beginner - Working with Variables in Python to Manage…&quot;, &quot;done&quot;: 15, &quot;total&quot;: 16, &quot;duration&quot;: &quot;1hr 12min&quot;}, {&quot;day&quot;: 2, &quot;title&quot;: &quot;Day 2 - Beginner - Understanding Data Types and How t…&quot;, &quot;done&quot;: 1, &quot;total&quot;: 10, &quot;duration&quot;: &quot;58min&quot;}, {&quot;day&quot;: 3, &quot;title&quot;: &quot;Day 3 - Beginner - Control Flow and Logical Operators&quot;, &quot;done&quot;: 8, &quot;total&quot;: 12, &quot;duration&quot;: &quot;1hr 15min&quot;}, {&quot;day&quot;: 4, &quot;title&quot;: &quot;Day 4 - Beginner - Randomisation and Python Lists&quot;, &quot;done&quot;: 0, &quot;total&quot;: 8, &quot;duration&quot;: &quot;1hr 4min&quot;}, {&quot;day&quot;: 5, &quot;title&quot;: &quot;Day 5 - Beginner - Python Loops&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;41min&quot;}, {&quot;day&quot;: 6, &quot;title&quot;: &quot;Day 6 - Beginner - Python Functions &amp; Karel&quot;, &quot;done&quot;: 0, &quot;total&quot;: 10, &quot;duration&quot;: &quot;1hr 23min&quot;}, {&quot;day&quot;: 7, &quot;title&quot;: &quot;Day 7 - Beginner - Hangman&quot;, &quot;done&quot;: 0, &quot;total&quot;: 8, &quot;duration&quot;: &quot;58min&quot;}, {&quot;day&quot;: 8, &quot;title&quot;: &quot;Day 8 - Beginner - Function Parameters &amp; Caesar Cipher&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;1hr 5min&quot;}, {&quot;day&quot;: 9, &quot;title&quot;: &quot;Day 9 - Beginner - Dictionaries, Nesting and the Secret…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;50min&quot;}, {&quot;day&quot;: 10, &quot;title&quot;: &quot;Day 10 - Beginner - Functions with Outputs&quot;, &quot;done&quot;: 0, &quot;total&quot;: 8, &quot;duration&quot;: &quot;55min&quot;}, {&quot;day&quot;: 11, &quot;title&quot;: &quot;Day 11 - Beginner - The Blackjack Capstone Project&quot;, &quot;done&quot;: 0, &quot;total&quot;: 6, &quot;duration&quot;: &quot;43min&quot;}, {&quot;day&quot;: 12, &quot;title&quot;: &quot;Day 12 - Beginner - Scope &amp; Number Guessing Game&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;49min&quot;}, {&quot;day&quot;: 13, &quot;title&quot;: &quot;Day 13 - Beginner - Debugging: How to Find and Fix Errors…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 11, &quot;duration&quot;: &quot;43min&quot;}, {&quot;day&quot;: 14, &quot;title&quot;: &quot;Day 14 - Beginner - Higher Lower Game Project&quot;, &quot;done&quot;: 0, &quot;total&quot;: 3, &quot;duration&quot;: &quot;37min&quot;}, {&quot;day&quot;: 15, &quot;title&quot;: &quot;Day 15 - Intermediate - Local Development Environment Setu…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 3, &quot;duration&quot;: &quot;39min&quot;}, {&quot;day&quot;: 16, &quot;title&quot;: &quot;Day 16 - Intermediate - Object Oriented Programming (OOP)&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;1hr 5min&quot;}, {&quot;day&quot;: 17, &quot;title&quot;: &quot;Day 17 - Intermediate - The Quiz Project &amp; The Benefits of OOP&quot;, &quot;done&quot;: 0, &quot;total&quot;: 11, &quot;duration&quot;: &quot;1hr 3min&quot;}, {&quot;day&quot;: 18, &quot;title&quot;: &quot;Day 18 - Intermediate - Turtle &amp; the Graphical User Interface…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 12, &quot;duration&quot;: &quot;1hr 28min&quot;}, {&quot;day&quot;: 19, &quot;title&quot;: &quot;Day 19 - Intermediate - Instances, State and Higher Order…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 8, &quot;duration&quot;: &quot;54min&quot;}, {&quot;day&quot;: 20, &quot;title&quot;: &quot;Day 20 - Intermediate - Build the Snake Game Part 1: Animati…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 6, &quot;duration&quot;: &quot;51min&quot;}, {&quot;day&quot;: 21, &quot;title&quot;: &quot;Day 21 - Intermediate - Build the Snake Game Part 2: …&quot;, &quot;done&quot;: 0, &quot;total&quot;: 8, &quot;duration&quot;: &quot;51min&quot;}, {&quot;day&quot;: 22, &quot;title&quot;: &quot;Day 22 - Intermediate - Build Pong: The Famous Arcade Game&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;53min&quot;}, {&quot;day&quot;: 23, &quot;title&quot;: &quot;Day 23 - Intermediate - The Turtle Crossing Capstone Project&quot;, &quot;done&quot;: 0, &quot;total&quot;: 11, &quot;duration&quot;: &quot;38min&quot;}, {&quot;day&quot;: 24, &quot;title&quot;: &quot;Day 24 - Intermediate - Files, Directories and Paths&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;1hr 3min&quot;}, {&quot;day&quot;: 25, &quot;title&quot;: &quot;Day 25 - Intermediate - Working with CSV Data and the Panda…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;1hr 15min&quot;}, {&quot;day&quot;: 26, &quot;title&quot;: &quot;Day 26 - Intermediate - List Comprehension and the NATO Alphabet&quot;, &quot;done&quot;: 0, &quot;total&quot;: 12, &quot;duration&quot;: &quot;45min&quot;}, {&quot;day&quot;: 27, &quot;title&quot;: &quot;Day 27 - Intermediate - Tkinter, *args, **kwargs and Creating…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 12, &quot;duration&quot;: &quot;1hr 18min&quot;}, {&quot;day&quot;: 28, &quot;title&quot;: &quot;Day 28 - Intermediate - Internet, DNS, Domain Typing and the…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;39min&quot;}, {&quot;day&quot;: 29, &quot;title&quot;: &quot;Day 29 - Intermediate - Building a Password Manager GUI App…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;55min&quot;}, {&quot;day&quot;: 30, &quot;title&quot;: &quot;Day 30 - Intermediate - Errors, Exceptions and JSON Data…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;1hr 5min&quot;}, {&quot;day&quot;: 31, &quot;title&quot;: &quot;Day 31 - Intermediate - Flash Card App Capstone Project&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;51min&quot;}, {&quot;day&quot;: 32, &quot;title&quot;: &quot;Day 32 - Intermediate - Send Email (Smtplib) &amp; Manage Dates…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;1hr 6min&quot;}, {&quot;day&quot;: 33, &quot;title&quot;: &quot;Day 33 - Intermediate - API Endpoints &amp; API Parameters - ISS…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;52min&quot;}, {&quot;day&quot;: 34, &quot;title&quot;: &quot;Day 34 - Intermediate - API Practice - Creating a GUI Quiz App&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;55min&quot;}, {&quot;day&quot;: 35, &quot;title&quot;: &quot;Day 35 - Intermediate - Keys, Authentication &amp; Environment…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;1hr 11min&quot;}, {&quot;day&quot;: 36, &quot;title&quot;: &quot;Day 36 - Intermediate - Stock Trading News Alert Project&quot;, &quot;done&quot;: 0, &quot;total&quot;: 5, &quot;duration&quot;: &quot;40min&quot;}, {&quot;day&quot;: 37, &quot;title&quot;: &quot;Day 37 - Intermediate - Habit Tracking Project: API Post…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 6, &quot;duration&quot;: &quot;39min&quot;}, {&quot;day&quot;: 38, &quot;title&quot;: &quot;Day 38 - Intermediate - Workout Tracking Using Google Sheets&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;1hr 8min&quot;}, {&quot;day&quot;: 39, &quot;title&quot;: &quot;Day 39 - Intermediate - Capstone Part 1: Flight Deal Finder&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;16min&quot;}, {&quot;day&quot;: 40, &quot;title&quot;: &quot;Day 40 - Intermediate - Capstone Part 2: Flight Club&quot;, &quot;done&quot;: 0, &quot;total&quot;: 6, &quot;duration&quot;: &quot;8min&quot;}, {&quot;day&quot;: 41, &quot;title&quot;: &quot;Day 41 - Web Foundation - Introduction to HTML&quot;, &quot;done&quot;: 0, &quot;total&quot;: 8, &quot;duration&quot;: &quot;58min&quot;}, {&quot;day&quot;: 42, &quot;title&quot;: &quot;Day 42 - Web Foundation - Intermediate HTML&quot;, &quot;done&quot;: 0, &quot;total&quot;: 6, &quot;duration&quot;: &quot;1hr 1min&quot;}, {&quot;day&quot;: 43, &quot;title&quot;: &quot;Day 43 - Web Foundation - Introduction to CSS&quot;, &quot;done&quot;: 0, &quot;total&quot;: 5, &quot;duration&quot;: &quot;56min&quot;}, {&quot;day&quot;: 44, &quot;title&quot;: &quot;Day 44 - Web Foundation - Intermediate CSS&quot;, &quot;done&quot;: 0, &quot;total&quot;: 5, &quot;duration&quot;: &quot;1hr 39min&quot;}, {&quot;day&quot;: 45, &quot;title&quot;: &quot;Day 45 - Advanced+ Web Scraping with Beautiful Soup&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;1hr 4min&quot;}, {&quot;day&quot;: 46, &quot;title&quot;: &quot;Day 46 - Intermediate+ Create a Spotify Playlist using the…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 8, &quot;duration&quot;: &quot;1hr 1min&quot;}, {&quot;day&quot;: 47, &quot;title&quot;: &quot;Day 47 - Intermediate+ Create an Automated Amazon Price…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 5, &quot;duration&quot;: &quot;50min&quot;}, {&quot;day&quot;: 48, &quot;title&quot;: &quot;Day 48 - Intermediate+ Selenium Webdriver Browser and Gam…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 8, &quot;duration&quot;: &quot;54min&quot;}, {&quot;day&quot;: 49, &quot;title&quot;: &quot;Day 49 - Intermediate+ Automating your Exercise Routine at…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;1hr 13min&quot;}, {&quot;day&quot;: 50, &quot;title&quot;: &quot;Day 50 - Intermediate+ Auto Tinder Swiping Bot&quot;, &quot;done&quot;: 0, &quot;total&quot;: 6, &quot;duration&quot;: &quot;11min&quot;}, {&quot;day&quot;: 51, &quot;title&quot;: &quot;Day 51 - Intermediate+ Internet Speed X Complaint Bot&quot;, &quot;done&quot;: 0, &quot;total&quot;: 8, &quot;duration&quot;: &quot;51min&quot;}, {&quot;day&quot;: 52, &quot;title&quot;: &quot;Day 52 - Intermediate+ Instagram Follower Bot&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;1hr 6min&quot;}, {&quot;day&quot;: 53, &quot;title&quot;: &quot;Day 53 - Intermediate+ Web Scraping Capstone - Data Entry Job…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 3, &quot;duration&quot;: &quot;10min&quot;}, {&quot;day&quot;: 54, &quot;title&quot;: &quot;Day 54 - Intermediate+ Introduction to Web Development wit…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;53min&quot;}, {&quot;day&quot;: 55, &quot;title&quot;: &quot;Day 55 - Advanced+ HTML &amp; URL Parsing in Flask and the…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;33min&quot;}, {&quot;day&quot;: 56, &quot;title&quot;: &quot;Day 56 - Intermediate+ Rendering HTML/Static files and Using…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 6, &quot;duration&quot;: &quot;49min&quot;}, {&quot;day&quot;: 57, &quot;title&quot;: &quot;Day 57 - Intermediate+ Templating with Jinja in Flask…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;38min&quot;}, {&quot;day&quot;: 58, &quot;title&quot;: &quot;Day 58 - Web Foundation Bootstrap&quot;, &quot;done&quot;: 0, &quot;total&quot;: 5, &quot;duration&quot;: &quot;1hr 40min&quot;}, {&quot;day&quot;: 59, &quot;title&quot;: &quot;Day 59 - Advanced - Blog Capstone Project Part 2 - Adding…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 8, &quot;duration&quot;: &quot;4min&quot;}, {&quot;day&quot;: 60, &quot;title&quot;: &quot;Day 60 - Advanced - Make POST Requests with Flask and HTML…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 6, &quot;duration&quot;: &quot;4min&quot;}, {&quot;day&quot;: 61, &quot;title&quot;: &quot;Day 61 - Advanced - Building Advanced Forms with Flask-…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;11min&quot;}, {&quot;day&quot;: 62, &quot;title&quot;: &quot;Day 62 - Advanced - Flask, WTForms, Bootstrap and CSV - Coffee…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 3, &quot;duration&quot;: &quot;3min&quot;}, {&quot;day&quot;: 63, &quot;title&quot;: &quot;Day 63 - Advanced - Databases with SQLite and…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 8, &quot;duration&quot;: &quot;12min&quot;}, {&quot;day&quot;: 64, &quot;title&quot;: &quot;Day 64 - Advanced - Top 10 Movies Website&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;7min&quot;}, {&quot;day&quot;: 65, &quot;title&quot;: &quot;Day 65 - Web Design School - How to Create a Website that Peopl…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 6, &quot;duration&quot;: &quot;1hr 6min&quot;}, {&quot;day&quot;: 66, &quot;title&quot;: &quot;Day 66 - Advanced - Building Your Own API with RESTful…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 12, &quot;duration&quot;: &quot;23min&quot;}, {&quot;day&quot;: 67, &quot;title&quot;: &quot;Day 67 - Advanced - Blog Capstone Project Part 3 - RESTful…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 6, &quot;duration&quot;: &quot;6min&quot;}, {&quot;day&quot;: 68, &quot;title&quot;: &quot;Day 68 - Advanced - Authentication with Flask&quot;, &quot;done&quot;: 0, &quot;total&quot;: 12, &quot;duration&quot;: &quot;45min&quot;}, {&quot;day&quot;: 69, &quot;title&quot;: &quot;Day 69 - Advanced - Blog Capstone Project Part 4 - Adding Users&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;10min&quot;}, {&quot;day&quot;: 70, &quot;title&quot;: &quot;Day 70 - Advanced - Git, Github and Version Control&quot;, &quot;done&quot;: 0, &quot;total&quot;: 10, &quot;duration&quot;: &quot;1hr 16min&quot;}, {&quot;day&quot;: 71, &quot;title&quot;: &quot;Day 71 - Advanced - Deploying Your Web Application&quot;, &quot;done&quot;: 0, &quot;total&quot;: 8, &quot;duration&quot;: &quot;10min&quot;}, {&quot;day&quot;: 72, &quot;title&quot;: &quot;Day 72 - Advanced - Data Exploration with Pandas: College Maj…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 10, &quot;duration&quot;: &quot;8min&quot;}, {&quot;day&quot;: 73, &quot;title&quot;: &quot;Day 73 - Advanced - Data Visualisation with Matplotlib…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 11, &quot;duration&quot;: &quot;9min&quot;}, {&quot;day&quot;: 74, &quot;title&quot;: &quot;Day 74 - Advanced - Aggregate &amp; Merge Data with Pandas…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;14min&quot;}, {&quot;day&quot;: 75, &quot;title&quot;: &quot;Day 75 - Advanced - Google Trends Data: Resampling and Visualisi…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;15min&quot;}, {&quot;day&quot;: 76, &quot;title&quot;: &quot;Day 76 - Advanced - Beautiful Plotly Charts &amp; Analysing th…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;16min&quot;}, {&quot;day&quot;: 77, &quot;title&quot;: &quot;Day 77 - Advanced - Computation with NumPy and N-…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 6, &quot;duration&quot;: &quot;12min&quot;}, {&quot;day&quot;: 78, &quot;title&quot;: &quot;Day 78 - Advanced - Linear Regression and Data Visualisation wit…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;17min&quot;}, {&quot;day&quot;: 79, &quot;title&quot;: &quot;Day 79 - Advanced - Analysing the Nobel Prize with Plotly…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 8, &quot;duration&quot;: &quot;22min&quot;}, {&quot;day&quot;: 80, &quot;title&quot;: &quot;Day 80 - Advanced - The Tragic Discovery of Hacking: t…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 6, &quot;duration&quot;: &quot;16min&quot;}, {&quot;day&quot;: 81, &quot;title&quot;: &quot;Day 81 - Advanced - Capstone Project - Predict House Prices&quot;, &quot;done&quot;: 0, &quot;total&quot;: 2, &quot;duration&quot;: &quot;1min&quot;}, {&quot;day&quot;: 82, &quot;title&quot;: &quot;Day 82 - Professional Portfolio Project - [Python Scripting]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 2, &quot;duration&quot;: &quot;1min&quot;}, {&quot;day&quot;: 83, &quot;title&quot;: &quot;Day 83 - Professional Portfolio Project - [Python Web…]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 2, &quot;duration&quot;: &quot;3min&quot;}, {&quot;day&quot;: 84, &quot;title&quot;: &quot;Day 84 - Professional Portfolio Project - [Python Scripting]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 85, &quot;title&quot;: &quot;Day 85 - Professional Portfolio Project - [GUI]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 86, &quot;title&quot;: &quot;Day 86 - Professional Portfolio Project - [GUI]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 87, &quot;title&quot;: &quot;Day 87 - Professional Portfolio Project - [Game]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 88, &quot;title&quot;: &quot;Day 88 - Professional Portfolio Project - [Web Development]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 89, &quot;title&quot;: &quot;Day 89 - Professional Portfolio Project - [Web Development]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 90, &quot;title&quot;: &quot;Day 90 - Professional Portfolio Project - [GUI Desktop App]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 91, &quot;title&quot;: &quot;Day 91 - Professional Portfolio Project - [HTTP Requests &amp;…]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 92, &quot;title&quot;: &quot;Day 92 - Professional Portfolio Project - [Image Processing …]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 93, &quot;title&quot;: &quot;Day 93 - Professional Portfolio Project - [Web Scraping]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 94, &quot;title&quot;: &quot;Day 94 - Professional Portfolio Project - [GUI Automation]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 95, &quot;title&quot;: &quot;Day 95 - Professional Portfolio Project - [Game]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 96, &quot;title&quot;: &quot;Day 96 - Professional Portfolio Project - [HTTP Requests &amp;…]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 97, &quot;title&quot;: &quot;Day 97 - Professional Portfolio Project - [Web Development]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 98, &quot;title&quot;: &quot;Day 98 - Professional Portfolio Project - [Python Automation]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 99, &quot;title&quot;: &quot;Day 99 - Professional Portfolio Project - [Data Science]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 100, &quot;title&quot;: &quot;Day 100 - Professional Portfolio Project - [Data Science]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 101, &quot;title&quot;: &quot;Final Stretch&quot;, &quot;done&quot;: 3, &quot;total&quot;: 3, &quot;duration&quot;: &quot;2hr 41min&quot;}, {&quot;day&quot;: 102, &quot;title&quot;: &quot;Bonus Lecture: Succeeding in the Age of AI&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;2min&quot;}];const KEY=&quot;course-todo-102-v1-nikhil&quot;,CUSTOM=&quot;course-custom-tasks-v1-nikhil&quot;;let saved=JSON.parse(localStorage.getItem(KEY)||&quot;null&quot;);let sections=saved||original.map(x=&gt;({...x}));let custom=JSON.parse(localStorage.getItem(CUSTOM)||&quot;[]&quot;);let selected=new Date();selected.setHours(0,0,0,0);let weekShift=0,filter=&quot;all&quot;,showAll=true;const z=n=&gt;String(n).padStart(2,&quot;0&quot;),iso=d=&gt;`${d.getFullYear()}-${z(d.getMonth()+1)}-${z(d.getDate())}`,today=new Date();today.setHours(0,0,0,0);const dueDate=day=&gt;{let d=new Date(today);d.setDate(d.getDate()+day-1);return d},esc=s=&gt;String(s).replace(/[&amp;&lt;&gt;&quot;&#x27;]/g,c=&gt;({&quot;&amp;&quot;:&quot;&amp;amp;&quot;,&quot;&lt;&quot;:&quot;&amp;lt;&quot;,&quot;&gt;&quot;:&quot;&amp;gt;&quot;,&#x27;&quot;&#x27;:&quot;&amp;quot;&quot;,&quot;&#x27;&quot;:&quot;&amp;#39;&quot;}[c]));function persist(){localStorage.setItem(KEY,JSON.stringify(sections));draw()}function isDone(s){return s.done&gt;=s.total}function dayStart(d){let x=new Date(d);x.setDate(x.getDate()-((x.getDay()+6)%7));x.setHours(0,0,0,0);return x}function draw(){document.querySelector(&quot;#today&quot;).textContent=today.toLocaleDateString(undefined,{weekday:&quot;long&quot;,month:&quot;long&quot;,day:&quot;numeric&quot;});let finished=sections.filter(isDone).length,doneLessons=sections.reduce((a,s)=&gt;a+s.done,0),totalLessons=sections.reduce((a,s)=&gt;a+s.total,0);document.querySelector(&quot;#finished&quot;).textContent=finished;document.querySelector(&quot;#remaining&quot;).textContent=sections.length-finished;document.querySelector(&quot;#lessons&quot;).textContent=`${doneLessons} / ${totalLessons}`;let pct=Math.round(100*doneLessons/totalLessons);document.querySelector(&quot;#percent&quot;).textContent=pct+&quot;%&quot;;document.querySelector(&quot;#overallBar&quot;).style.width=pct+&quot;%&quot;;document.querySelector(&quot;#overallText&quot;).textContent=`${doneLessons} of ${totalLessons} lessons complete across ${sections.length} sections.`;let week=dayStart(selected);week.setDate(week.getDate()+7*weekShift);document.querySelector(&quot;#weekLabel&quot;).textContent=week.toLocaleDateString(undefined,{month:&quot;short&quot;,day:&quot;numeric&quot;})+&quot; – &quot;+new Date(week.getTime()+6*86400000).toLocaleDateString(undefined,{month:&quot;short&quot;,day:&quot;numeric&quot;});let days=document.querySelector(&quot;#days&quot;);days.innerHTML=&quot;&quot;;for(let i=0;i&lt;7;i++){let d=new Date(week);d.setDate(d.getDate()+i);let date=iso(d),due=sections.filter(s=&gt;iso(dueDate(s.day))===date),nDone=due.filter(isDone).length;let el=document.createElement(&quot;div&quot;);el.className=&quot;day&quot;+(iso(selected)===date?&quot; selected&quot;:&quot;&quot;);el.innerHTML=`&lt;span&gt;${d.toLocaleDateString(undefined,{weekday:&quot;short&quot;,month:&quot;short&quot;,day:&quot;numeric&quot;})}&lt;/span&gt;&lt;small&gt;${due.length?`${nDone}/${due.length} done`:&quot;—&quot;}&lt;/small&gt;`;el.onclick=()=&gt;{selected=d;showAll=false;draw()};days.appendChild(el)}let items=sections.filter(s=&gt;{let done=isDone(s),partial=s.done&gt;0&amp;&amp;!done,match=filter===&quot;all&quot;||filter===&quot;done&quot;&amp;&amp;done||filter===&quot;todo&quot;&amp;&amp;!done||filter===&quot;progress&quot;&amp;&amp;partial;return match&amp;&amp;(showAll||iso(dueDate(s.day))===iso(selected))});document.querySelector(&quot;#listTitle&quot;).textContent=showAll?&quot;Your day-by-day list&quot;:selected.toLocaleDateString(undefined,{weekday:&quot;long&quot;,month:&quot;long&quot;,day:&quot;numeric&quot;});document.querySelector(&quot;#listSub&quot;).textContent=showAll?`${items.length} sections shown · ${sections.length} total`: `${items.length} course section(s) planned for this date`;let list=document.querySelector(&quot;#list&quot;);list.innerHTML=&quot;&quot;;if(!items.length)list.innerHTML=&#x27;&lt;div class=&quot;empty&quot;&gt;Nothing here for this view. Try another filter or calendar day.&lt;/div&gt;&#x27;;for(const s of items){let d=dueDate(s.day),complete=isDone(s),el=document.createElement(&quot;article&quot;);el.className=&quot;task&quot;+(complete?&quot; done&quot;:&quot;&quot;);el.innerHTML=`&lt;button class=&quot;check&quot; title=&quot;${complete?&quot;Mark section to do&quot;:&quot;Mark section complete&quot;}&quot; aria-label=&quot;Toggle completion&quot;&gt;${complete?&quot;✓&quot;:&quot;&quot;}&lt;/button&gt;&lt;div&gt;&lt;div class=&quot;title&quot;&gt;Section ${s.day}: ${esc(s.title)}&lt;/div&gt;&lt;div class=&quot;meta&quot;&gt;Day ${s.day} · ${d.toLocaleDateString(undefined,{weekday:&quot;short&quot;,month:&quot;short&quot;,day:&quot;numeric&quot;})} · ${esc(s.duration)}&lt;/div&gt;&lt;div class=&quot;bar&quot;&gt;&lt;i style=&quot;width:${Math.round(100*s.done/s.total)}%&quot;&gt;&lt;/i&gt;&lt;/div&gt;&lt;/div&gt;&lt;div class=&quot;meter&quot;&gt;&lt;button class=&quot;minus&quot; aria-label=&quot;One fewer lesson complete&quot;&gt;−&lt;/button&gt;&lt;span class=&quot;count&quot;&gt;${s.done}/${s.total}&lt;/span&gt;&lt;button class=&quot;plus&quot; aria-label=&quot;One more lesson complete&quot;&gt;+&lt;/button&gt;&lt;/div&gt;`;el.querySelector(&quot;.check&quot;).onclick=()=&gt;{s.done=complete?Math.max(0,s.total-1):s.total;persist()};el.querySelector(&quot;.minus&quot;).onclick=()=&gt;{s.done=Math.max(0,s.done-1);persist()};el.querySelector(&quot;.plus&quot;).onclick=()=&gt;{s.done=Math.min(s.total,s.done+1);persist()};list.appendChild(el)}let ct=custom.filter(t=&gt;t.date===iso(selected));document.querySelector(&quot;#customList&quot;).innerHTML=ct.length?ct.map((t,i)=&gt;`&lt;label style=&quot;display:flex;gap:7px;margin-top:7px&quot;&gt;&lt;input type=&quot;checkbox&quot; data-custom=&quot;${i}&quot; ${t.done?&quot;checked&quot;:&quot;&quot;}&gt; &lt;span style=&quot;${t.done?&quot;text-decoration:line-through&quot;:&quot;&quot;}&quot;&gt;${esc(t.name)}&lt;/span&gt;&lt;/label&gt;`).join(&quot;&quot;):&quot;Personal reminders for the selected calendar date appear here.&quot;;document.querySelectorAll(&quot;[data-custom]&quot;).forEach(cb=&gt;cb.onchange=()=&gt;{let idx=ct[+cb.dataset.custom],real=custom.indexOf(idx);custom[real].done=cb.checked;localStorage.setItem(CUSTOM,JSON.stringify(custom));draw()})}document.querySelectorAll(&quot;.filter&quot;).forEach(b=&gt;b.onclick=()=&gt;{filter=b.dataset.filter;document.querySelectorAll(&quot;.filter&quot;).forEach(x=&gt;x.classList.toggle(&quot;active&quot;,x===b));draw()});document.querySelector(&quot;#viewBtn&quot;).onclick=()=&gt;{showAll=!showAll;document.querySelector(&quot;#viewBtn&quot;).textContent=showAll?&quot;View: All&quot;:&quot;View: Selected day&quot;;draw()};document.querySelector(&quot;#prev&quot;).onclick=()=&gt;{weekShift--;draw()};document.querySelector(&quot;#next&quot;).onclick=()=&gt;{weekShift++;draw()};document.querySelector(&quot;#resetBtn&quot;).onclick=()=&gt;{if(confirm(&quot;Reset all course lesson counts to the progress shown in the screenshots?&quot;)){sections=original.map(x=&gt;({...x}));persist()}};document.querySelector(&quot;#date&quot;).value=iso(selected);document.querySelector(&quot;#form&quot;).onsubmit=e=&gt;{e.preventDefault();custom.push({name:document.querySelector(&quot;#name&quot;).value.trim(),date:document.querySelector(&quot;#date&quot;).value,done:false});localStorage.setItem(CUSTOM,JSON.stringify(custom));document.querySelector(&quot;#name&quot;).value=&quot;&quot;;selected=new Date(document.querySelector(&quot;#date&quot;).value+&quot;T12:00:00&quot;);showAll=false;draw()};draw();
&lt;/script&gt;&lt;/body&gt;&lt;/html&gt;"></iframe>
  </section>
  <section class="planner-section app-view" id="akshat-planner" hidden>
    <h2>Akshat’s Python notebook</h2>
    <iframe class="docs-workspace-frame" data-owner="akshat" title="Akshat’s Python notes workspace"></iframe>
    <p class="course-planner-intro">Course schedule and progress tracker</p>
    <iframe class="planner-frame" title="Akshat’s Python course planner" loading="lazy" srcdoc="&lt;!doctype html&gt;&lt;html lang=&quot;en&quot;&gt;&lt;head&gt;&lt;meta charset=&quot;utf-8&quot;&gt;&lt;meta name=&quot;viewport&quot; content=&quot;width=device-width,initial-scale=1&quot;&gt;&lt;title&gt;Akshat’s Python Course — Daily To‑Do&lt;/title&gt;&lt;style&gt;
:root{--ink:#20213a;--muted:#77798d;--purple:#7044df;--lav:#f1edff;--line:#e8e7ef;--bg:#f6f6fa;--green:#16835d;--amber:#b87516}*{box-sizing:border-box}body{margin:0;background:var(--bg);color:var(--ink);font:15px/1.5 system-ui,-apple-system,Segoe UI,sans-serif}.wrap{max-width:1100px;margin:auto;padding:30px 20px 60px}.top{display:flex;justify-content:space-between;align-items:center;gap:15px}.eyebrow{font-size:12px;text-transform:uppercase;letter-spacing:.1em;color:var(--purple);font-weight:750}h1{font-size:clamp(28px,4vw,42px);line-height:1.12;margin:5px 0}p{margin:6px 0;color:var(--muted)}.today{background:#fff;border:1px solid var(--line);border-radius:13px;padding:10px 14px;color:var(--muted)}.today b{display:block;color:var(--ink)}.stats{display:grid;grid-template-columns:repeat(4,1fr);gap:12px;margin:22px 0}.stat,.panel{background:#fff;border:1px solid var(--line);border-radius:15px}.stat{padding:13px 17px}.stat b{font-size:25px;display:block}.stat span{font-size:12px;color:var(--muted)}.layout{display:grid;grid-template-columns:minmax(0,1fr) 285px;gap:16px}.panel{padding:18px}.panel h2{font-size:19px;margin:0}.head{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-bottom:14px}.tools{display:flex;gap:8px;flex-wrap:wrap}.btn,select,input{font:inherit}.btn{border:1px solid var(--line);background:#fff;border-radius:9px;padding:8px 11px;color:var(--ink);cursor:pointer}.btn.primary{background:var(--purple);border-color:var(--purple);color:white;font-weight:650}.filters{display:flex;gap:7px;margin-bottom:12px;flex-wrap:wrap}.filter{border:1px solid var(--line);background:white;border-radius:99px;padding:6px 10px;color:var(--muted);cursor:pointer;font-size:12px}.filter.active{background:var(--lav);border-color:#d8ccff;color:var(--purple);font-weight:700}.list{display:grid;gap:8px}.task{display:grid;grid-template-columns:32px 1fr auto;gap:10px;align-items:start;border:1px solid var(--line);border-radius:11px;padding:11px}.task.done{background:#fbfffd}.check{width:26px;height:26px;border:1.5px solid #c9c8d5;border-radius:8px;background:white;color:white;cursor:pointer;font-size:16px;line-height:20px}.task.done .check{background:var(--green);border-color:var(--green)}.title{font-weight:650;line-height:1.35}.task.done .title{text-decoration:line-through;color:var(--muted)}.meta{font-size:11px;color:var(--muted);margin-top:4px}.meter{white-space:nowrap;display:flex;align-items:center;gap:6px}.meter button{width:25px;height:25px;border-radius:7px;border:1px solid var(--line);background:white;cursor:pointer}.count{font-size:12px;font-weight:700;min-width:32px;text-align:center}.bar{height:4px;width:65px;border-radius:4px;background:#eeeaf5;margin-top:5px}.bar i{display:block;height:100%;background:var(--purple);border-radius:4px}.sidebar{display:grid;gap:15px;align-content:start}.weeknav{display:flex;justify-content:space-between;align-items:center;margin:12px 0}.weeknav button{border:1px solid var(--line);background:white;border-radius:8px;padding:6px 10px;cursor:pointer}.days{display:grid;gap:6px}.day{display:flex;justify-content:space-between;padding:9px;border:1px solid transparent;border-radius:9px;background:#faf9fd;cursor:pointer;font-size:13px}.day.selected{background:var(--lav);border-color:#d8ccff}.day small{color:var(--muted)}.progress{height:7px;border-radius:9px;background:#eeeaf5;margin:12px 0 5px;overflow:hidden}.progress i{display:block;height:100%;background:var(--purple)}.addform{display:grid;gap:8px;margin-top:12px}.addform input,.addform select{width:100%;border:1px solid var(--line);border-radius:8px;padding:9px;background:#fff}.notice{font-size:11px;color:var(--muted);margin-top:13px}.empty{text-align:center;padding:28px;color:var(--muted);border:1px dashed var(--line);border-radius:10px}.foot{font-size:11px;color:var(--muted);margin-top:15px}@media(max-width:760px){.layout{grid-template-columns:1fr}.stats{grid-template-columns:repeat(2,1fr)}.top{align-items:flex-start;flex-direction:column}.today{width:100%}.task{grid-template-columns:30px 1fr}.meter{grid-column:2}}
&lt;/style&gt;&lt;/head&gt;&lt;body&gt;&lt;main class=&quot;wrap&quot;&gt;&lt;header class=&quot;top&quot;&gt;&lt;div&gt;&lt;div class=&quot;eyebrow&quot;&gt;102 course sections · day-by-day plan&lt;/div&gt;&lt;h1&gt;Akshat’s Python Course To‑Do&lt;/h1&gt;&lt;p&gt;Check off a section or adjust the lesson count as you go. Your progress saves in this browser.&lt;/p&gt;&lt;/div&gt;&lt;div class=&quot;today&quot;&gt;Today&lt;b id=&quot;today&quot;&gt;&lt;/b&gt;&lt;/div&gt;&lt;/header&gt;&lt;section class=&quot;stats&quot;&gt;&lt;div class=&quot;stat&quot;&gt;&lt;b id=&quot;finished&quot;&gt;0&lt;/b&gt;&lt;span&gt;Sections finished&lt;/span&gt;&lt;/div&gt;&lt;div class=&quot;stat&quot;&gt;&lt;b id=&quot;remaining&quot;&gt;0&lt;/b&gt;&lt;span&gt;Sections to do&lt;/span&gt;&lt;/div&gt;&lt;div class=&quot;stat&quot;&gt;&lt;b id=&quot;lessons&quot;&gt;&lt;/b&gt;&lt;span&gt;Lessons completed&lt;/span&gt;&lt;/div&gt;&lt;div class=&quot;stat&quot;&gt;&lt;b id=&quot;percent&quot;&gt;0%&lt;/b&gt;&lt;span&gt;Course progress&lt;/span&gt;&lt;/div&gt;&lt;/section&gt;&lt;div class=&quot;layout&quot;&gt;&lt;section class=&quot;panel&quot;&gt;&lt;div class=&quot;head&quot;&gt;&lt;div&gt;&lt;h2 id=&quot;listTitle&quot;&gt;Your day-by-day list&lt;/h2&gt;&lt;p id=&quot;listSub&quot;&gt;Sections are scheduled one per day, starting today.&lt;/p&gt;&lt;/div&gt;&lt;div class=&quot;tools&quot;&gt;&lt;button class=&quot;btn&quot; id=&quot;viewBtn&quot;&gt;View: All&lt;/button&gt;&lt;button class=&quot;btn&quot; id=&quot;resetBtn&quot;&gt;Reset progress&lt;/button&gt;&lt;/div&gt;&lt;/div&gt;&lt;div class=&quot;filters&quot;&gt;&lt;button class=&quot;filter active&quot; data-filter=&quot;all&quot;&gt;All sections&lt;/button&gt;&lt;button class=&quot;filter&quot; data-filter=&quot;todo&quot;&gt;To do&lt;/button&gt;&lt;button class=&quot;filter&quot; data-filter=&quot;progress&quot;&gt;In progress&lt;/button&gt;&lt;button class=&quot;filter&quot; data-filter=&quot;done&quot;&gt;Completed&lt;/button&gt;&lt;/div&gt;&lt;div class=&quot;list&quot; id=&quot;list&quot;&gt;&lt;/div&gt;&lt;div class=&quot;foot&quot;&gt;Lesson totals and completed counts are copied from the progress shown in your screenshots. Titles ending in … were cut off in the images.&lt;/div&gt;&lt;/section&gt;&lt;aside class=&quot;sidebar&quot;&gt;&lt;section class=&quot;panel&quot;&gt;&lt;h2&gt;Calendar&lt;/h2&gt;&lt;div class=&quot;weeknav&quot;&gt;&lt;button id=&quot;prev&quot;&gt;←&lt;/button&gt;&lt;b id=&quot;weekLabel&quot;&gt;&lt;/b&gt;&lt;button id=&quot;next&quot;&gt;→&lt;/button&gt;&lt;/div&gt;&lt;div id=&quot;days&quot; class=&quot;days&quot;&gt;&lt;/div&gt;&lt;/section&gt;&lt;section class=&quot;panel&quot;&gt;&lt;h2&gt;Add a personal task&lt;/h2&gt;&lt;p&gt;Add reminders alongside the course.&lt;/p&gt;&lt;form id=&quot;form&quot; class=&quot;addform&quot;&gt;&lt;input id=&quot;name&quot; placeholder=&quot;What do you need to do?&quot; required&gt;&lt;input id=&quot;date&quot; type=&quot;date&quot; required&gt;&lt;button class=&quot;btn primary&quot;&gt;Add task&lt;/button&gt;&lt;/form&gt;&lt;div id=&quot;customList&quot; class=&quot;notice&quot;&gt;&lt;/div&gt;&lt;/section&gt;&lt;section class=&quot;panel&quot;&gt;&lt;h2&gt;Overall progress&lt;/h2&gt;&lt;div class=&quot;progress&quot;&gt;&lt;i id=&quot;overallBar&quot;&gt;&lt;/i&gt;&lt;/div&gt;&lt;div class=&quot;notice&quot; id=&quot;overallText&quot;&gt;&lt;/div&gt;&lt;/section&gt;&lt;/aside&gt;&lt;/div&gt;&lt;/main&gt;&lt;script&gt;
const original=[{&quot;day&quot;: 1, &quot;title&quot;: &quot;Day 1 - Beginner - Working with Variables in Python to Manage…&quot;, &quot;done&quot;: 15, &quot;total&quot;: 16, &quot;duration&quot;: &quot;1hr 12min&quot;}, {&quot;day&quot;: 2, &quot;title&quot;: &quot;Day 2 - Beginner - Understanding Data Types and How t…&quot;, &quot;done&quot;: 1, &quot;total&quot;: 10, &quot;duration&quot;: &quot;58min&quot;}, {&quot;day&quot;: 3, &quot;title&quot;: &quot;Day 3 - Beginner - Control Flow and Logical Operators&quot;, &quot;done&quot;: 8, &quot;total&quot;: 12, &quot;duration&quot;: &quot;1hr 15min&quot;}, {&quot;day&quot;: 4, &quot;title&quot;: &quot;Day 4 - Beginner - Randomisation and Python Lists&quot;, &quot;done&quot;: 0, &quot;total&quot;: 8, &quot;duration&quot;: &quot;1hr 4min&quot;}, {&quot;day&quot;: 5, &quot;title&quot;: &quot;Day 5 - Beginner - Python Loops&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;41min&quot;}, {&quot;day&quot;: 6, &quot;title&quot;: &quot;Day 6 - Beginner - Python Functions &amp; Karel&quot;, &quot;done&quot;: 0, &quot;total&quot;: 10, &quot;duration&quot;: &quot;1hr 23min&quot;}, {&quot;day&quot;: 7, &quot;title&quot;: &quot;Day 7 - Beginner - Hangman&quot;, &quot;done&quot;: 0, &quot;total&quot;: 8, &quot;duration&quot;: &quot;58min&quot;}, {&quot;day&quot;: 8, &quot;title&quot;: &quot;Day 8 - Beginner - Function Parameters &amp; Caesar Cipher&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;1hr 5min&quot;}, {&quot;day&quot;: 9, &quot;title&quot;: &quot;Day 9 - Beginner - Dictionaries, Nesting and the Secret…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;50min&quot;}, {&quot;day&quot;: 10, &quot;title&quot;: &quot;Day 10 - Beginner - Functions with Outputs&quot;, &quot;done&quot;: 0, &quot;total&quot;: 8, &quot;duration&quot;: &quot;55min&quot;}, {&quot;day&quot;: 11, &quot;title&quot;: &quot;Day 11 - Beginner - The Blackjack Capstone Project&quot;, &quot;done&quot;: 0, &quot;total&quot;: 6, &quot;duration&quot;: &quot;43min&quot;}, {&quot;day&quot;: 12, &quot;title&quot;: &quot;Day 12 - Beginner - Scope &amp; Number Guessing Game&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;49min&quot;}, {&quot;day&quot;: 13, &quot;title&quot;: &quot;Day 13 - Beginner - Debugging: How to Find and Fix Errors…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 11, &quot;duration&quot;: &quot;43min&quot;}, {&quot;day&quot;: 14, &quot;title&quot;: &quot;Day 14 - Beginner - Higher Lower Game Project&quot;, &quot;done&quot;: 0, &quot;total&quot;: 3, &quot;duration&quot;: &quot;37min&quot;}, {&quot;day&quot;: 15, &quot;title&quot;: &quot;Day 15 - Intermediate - Local Development Environment Setu…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 3, &quot;duration&quot;: &quot;39min&quot;}, {&quot;day&quot;: 16, &quot;title&quot;: &quot;Day 16 - Intermediate - Object Oriented Programming (OOP)&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;1hr 5min&quot;}, {&quot;day&quot;: 17, &quot;title&quot;: &quot;Day 17 - Intermediate - The Quiz Project &amp; The Benefits of OOP&quot;, &quot;done&quot;: 0, &quot;total&quot;: 11, &quot;duration&quot;: &quot;1hr 3min&quot;}, {&quot;day&quot;: 18, &quot;title&quot;: &quot;Day 18 - Intermediate - Turtle &amp; the Graphical User Interface…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 12, &quot;duration&quot;: &quot;1hr 28min&quot;}, {&quot;day&quot;: 19, &quot;title&quot;: &quot;Day 19 - Intermediate - Instances, State and Higher Order…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 8, &quot;duration&quot;: &quot;54min&quot;}, {&quot;day&quot;: 20, &quot;title&quot;: &quot;Day 20 - Intermediate - Build the Snake Game Part 1: Animati…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 6, &quot;duration&quot;: &quot;51min&quot;}, {&quot;day&quot;: 21, &quot;title&quot;: &quot;Day 21 - Intermediate - Build the Snake Game Part 2: …&quot;, &quot;done&quot;: 0, &quot;total&quot;: 8, &quot;duration&quot;: &quot;51min&quot;}, {&quot;day&quot;: 22, &quot;title&quot;: &quot;Day 22 - Intermediate - Build Pong: The Famous Arcade Game&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;53min&quot;}, {&quot;day&quot;: 23, &quot;title&quot;: &quot;Day 23 - Intermediate - The Turtle Crossing Capstone Project&quot;, &quot;done&quot;: 0, &quot;total&quot;: 11, &quot;duration&quot;: &quot;38min&quot;}, {&quot;day&quot;: 24, &quot;title&quot;: &quot;Day 24 - Intermediate - Files, Directories and Paths&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;1hr 3min&quot;}, {&quot;day&quot;: 25, &quot;title&quot;: &quot;Day 25 - Intermediate - Working with CSV Data and the Panda…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;1hr 15min&quot;}, {&quot;day&quot;: 26, &quot;title&quot;: &quot;Day 26 - Intermediate - List Comprehension and the NATO Alphabet&quot;, &quot;done&quot;: 0, &quot;total&quot;: 12, &quot;duration&quot;: &quot;45min&quot;}, {&quot;day&quot;: 27, &quot;title&quot;: &quot;Day 27 - Intermediate - Tkinter, *args, **kwargs and Creating…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 12, &quot;duration&quot;: &quot;1hr 18min&quot;}, {&quot;day&quot;: 28, &quot;title&quot;: &quot;Day 28 - Intermediate - Internet, DNS, Domain Typing and the…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;39min&quot;}, {&quot;day&quot;: 29, &quot;title&quot;: &quot;Day 29 - Intermediate - Building a Password Manager GUI App…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;55min&quot;}, {&quot;day&quot;: 30, &quot;title&quot;: &quot;Day 30 - Intermediate - Errors, Exceptions and JSON Data…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;1hr 5min&quot;}, {&quot;day&quot;: 31, &quot;title&quot;: &quot;Day 31 - Intermediate - Flash Card App Capstone Project&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;51min&quot;}, {&quot;day&quot;: 32, &quot;title&quot;: &quot;Day 32 - Intermediate - Send Email (Smtplib) &amp; Manage Dates…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;1hr 6min&quot;}, {&quot;day&quot;: 33, &quot;title&quot;: &quot;Day 33 - Intermediate - API Endpoints &amp; API Parameters - ISS…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;52min&quot;}, {&quot;day&quot;: 34, &quot;title&quot;: &quot;Day 34 - Intermediate - API Practice - Creating a GUI Quiz App&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;55min&quot;}, {&quot;day&quot;: 35, &quot;title&quot;: &quot;Day 35 - Intermediate - Keys, Authentication &amp; Environment…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;1hr 11min&quot;}, {&quot;day&quot;: 36, &quot;title&quot;: &quot;Day 36 - Intermediate - Stock Trading News Alert Project&quot;, &quot;done&quot;: 0, &quot;total&quot;: 5, &quot;duration&quot;: &quot;40min&quot;}, {&quot;day&quot;: 37, &quot;title&quot;: &quot;Day 37 - Intermediate - Habit Tracking Project: API Post…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 6, &quot;duration&quot;: &quot;39min&quot;}, {&quot;day&quot;: 38, &quot;title&quot;: &quot;Day 38 - Intermediate - Workout Tracking Using Google Sheets&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;1hr 8min&quot;}, {&quot;day&quot;: 39, &quot;title&quot;: &quot;Day 39 - Intermediate - Capstone Part 1: Flight Deal Finder&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;16min&quot;}, {&quot;day&quot;: 40, &quot;title&quot;: &quot;Day 40 - Intermediate - Capstone Part 2: Flight Club&quot;, &quot;done&quot;: 0, &quot;total&quot;: 6, &quot;duration&quot;: &quot;8min&quot;}, {&quot;day&quot;: 41, &quot;title&quot;: &quot;Day 41 - Web Foundation - Introduction to HTML&quot;, &quot;done&quot;: 0, &quot;total&quot;: 8, &quot;duration&quot;: &quot;58min&quot;}, {&quot;day&quot;: 42, &quot;title&quot;: &quot;Day 42 - Web Foundation - Intermediate HTML&quot;, &quot;done&quot;: 0, &quot;total&quot;: 6, &quot;duration&quot;: &quot;1hr 1min&quot;}, {&quot;day&quot;: 43, &quot;title&quot;: &quot;Day 43 - Web Foundation - Introduction to CSS&quot;, &quot;done&quot;: 0, &quot;total&quot;: 5, &quot;duration&quot;: &quot;56min&quot;}, {&quot;day&quot;: 44, &quot;title&quot;: &quot;Day 44 - Web Foundation - Intermediate CSS&quot;, &quot;done&quot;: 0, &quot;total&quot;: 5, &quot;duration&quot;: &quot;1hr 39min&quot;}, {&quot;day&quot;: 45, &quot;title&quot;: &quot;Day 45 - Advanced+ Web Scraping with Beautiful Soup&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;1hr 4min&quot;}, {&quot;day&quot;: 46, &quot;title&quot;: &quot;Day 46 - Intermediate+ Create a Spotify Playlist using the…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 8, &quot;duration&quot;: &quot;1hr 1min&quot;}, {&quot;day&quot;: 47, &quot;title&quot;: &quot;Day 47 - Intermediate+ Create an Automated Amazon Price…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 5, &quot;duration&quot;: &quot;50min&quot;}, {&quot;day&quot;: 48, &quot;title&quot;: &quot;Day 48 - Intermediate+ Selenium Webdriver Browser and Gam…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 8, &quot;duration&quot;: &quot;54min&quot;}, {&quot;day&quot;: 49, &quot;title&quot;: &quot;Day 49 - Intermediate+ Automating your Exercise Routine at…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;1hr 13min&quot;}, {&quot;day&quot;: 50, &quot;title&quot;: &quot;Day 50 - Intermediate+ Auto Tinder Swiping Bot&quot;, &quot;done&quot;: 0, &quot;total&quot;: 6, &quot;duration&quot;: &quot;11min&quot;}, {&quot;day&quot;: 51, &quot;title&quot;: &quot;Day 51 - Intermediate+ Internet Speed X Complaint Bot&quot;, &quot;done&quot;: 0, &quot;total&quot;: 8, &quot;duration&quot;: &quot;51min&quot;}, {&quot;day&quot;: 52, &quot;title&quot;: &quot;Day 52 - Intermediate+ Instagram Follower Bot&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;1hr 6min&quot;}, {&quot;day&quot;: 53, &quot;title&quot;: &quot;Day 53 - Intermediate+ Web Scraping Capstone - Data Entry Job…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 3, &quot;duration&quot;: &quot;10min&quot;}, {&quot;day&quot;: 54, &quot;title&quot;: &quot;Day 54 - Intermediate+ Introduction to Web Development wit…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;53min&quot;}, {&quot;day&quot;: 55, &quot;title&quot;: &quot;Day 55 - Advanced+ HTML &amp; URL Parsing in Flask and the…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;33min&quot;}, {&quot;day&quot;: 56, &quot;title&quot;: &quot;Day 56 - Intermediate+ Rendering HTML/Static files and Using…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 6, &quot;duration&quot;: &quot;49min&quot;}, {&quot;day&quot;: 57, &quot;title&quot;: &quot;Day 57 - Intermediate+ Templating with Jinja in Flask…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;38min&quot;}, {&quot;day&quot;: 58, &quot;title&quot;: &quot;Day 58 - Web Foundation Bootstrap&quot;, &quot;done&quot;: 0, &quot;total&quot;: 5, &quot;duration&quot;: &quot;1hr 40min&quot;}, {&quot;day&quot;: 59, &quot;title&quot;: &quot;Day 59 - Advanced - Blog Capstone Project Part 2 - Adding…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 8, &quot;duration&quot;: &quot;4min&quot;}, {&quot;day&quot;: 60, &quot;title&quot;: &quot;Day 60 - Advanced - Make POST Requests with Flask and HTML…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 6, &quot;duration&quot;: &quot;4min&quot;}, {&quot;day&quot;: 61, &quot;title&quot;: &quot;Day 61 - Advanced - Building Advanced Forms with Flask-…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;11min&quot;}, {&quot;day&quot;: 62, &quot;title&quot;: &quot;Day 62 - Advanced - Flask, WTForms, Bootstrap and CSV - Coffee…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 3, &quot;duration&quot;: &quot;3min&quot;}, {&quot;day&quot;: 63, &quot;title&quot;: &quot;Day 63 - Advanced - Databases with SQLite and…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 8, &quot;duration&quot;: &quot;12min&quot;}, {&quot;day&quot;: 64, &quot;title&quot;: &quot;Day 64 - Advanced - Top 10 Movies Website&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;7min&quot;}, {&quot;day&quot;: 65, &quot;title&quot;: &quot;Day 65 - Web Design School - How to Create a Website that Peopl…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 6, &quot;duration&quot;: &quot;1hr 6min&quot;}, {&quot;day&quot;: 66, &quot;title&quot;: &quot;Day 66 - Advanced - Building Your Own API with RESTful…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 12, &quot;duration&quot;: &quot;23min&quot;}, {&quot;day&quot;: 67, &quot;title&quot;: &quot;Day 67 - Advanced - Blog Capstone Project Part 3 - RESTful…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 6, &quot;duration&quot;: &quot;6min&quot;}, {&quot;day&quot;: 68, &quot;title&quot;: &quot;Day 68 - Advanced - Authentication with Flask&quot;, &quot;done&quot;: 0, &quot;total&quot;: 12, &quot;duration&quot;: &quot;45min&quot;}, {&quot;day&quot;: 69, &quot;title&quot;: &quot;Day 69 - Advanced - Blog Capstone Project Part 4 - Adding Users&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;10min&quot;}, {&quot;day&quot;: 70, &quot;title&quot;: &quot;Day 70 - Advanced - Git, Github and Version Control&quot;, &quot;done&quot;: 0, &quot;total&quot;: 10, &quot;duration&quot;: &quot;1hr 16min&quot;}, {&quot;day&quot;: 71, &quot;title&quot;: &quot;Day 71 - Advanced - Deploying Your Web Application&quot;, &quot;done&quot;: 0, &quot;total&quot;: 8, &quot;duration&quot;: &quot;10min&quot;}, {&quot;day&quot;: 72, &quot;title&quot;: &quot;Day 72 - Advanced - Data Exploration with Pandas: College Maj…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 10, &quot;duration&quot;: &quot;8min&quot;}, {&quot;day&quot;: 73, &quot;title&quot;: &quot;Day 73 - Advanced - Data Visualisation with Matplotlib…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 11, &quot;duration&quot;: &quot;9min&quot;}, {&quot;day&quot;: 74, &quot;title&quot;: &quot;Day 74 - Advanced - Aggregate &amp; Merge Data with Pandas…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 7, &quot;duration&quot;: &quot;14min&quot;}, {&quot;day&quot;: 75, &quot;title&quot;: &quot;Day 75 - Advanced - Google Trends Data: Resampling and Visualisi…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;15min&quot;}, {&quot;day&quot;: 76, &quot;title&quot;: &quot;Day 76 - Advanced - Beautiful Plotly Charts &amp; Analysing th…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;16min&quot;}, {&quot;day&quot;: 77, &quot;title&quot;: &quot;Day 77 - Advanced - Computation with NumPy and N-…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 6, &quot;duration&quot;: &quot;12min&quot;}, {&quot;day&quot;: 78, &quot;title&quot;: &quot;Day 78 - Advanced - Linear Regression and Data Visualisation wit…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 9, &quot;duration&quot;: &quot;17min&quot;}, {&quot;day&quot;: 79, &quot;title&quot;: &quot;Day 79 - Advanced - Analysing the Nobel Prize with Plotly…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 8, &quot;duration&quot;: &quot;22min&quot;}, {&quot;day&quot;: 80, &quot;title&quot;: &quot;Day 80 - Advanced - The Tragic Discovery of Hacking: t…&quot;, &quot;done&quot;: 0, &quot;total&quot;: 6, &quot;duration&quot;: &quot;16min&quot;}, {&quot;day&quot;: 81, &quot;title&quot;: &quot;Day 81 - Advanced - Capstone Project - Predict House Prices&quot;, &quot;done&quot;: 0, &quot;total&quot;: 2, &quot;duration&quot;: &quot;1min&quot;}, {&quot;day&quot;: 82, &quot;title&quot;: &quot;Day 82 - Professional Portfolio Project - [Python Scripting]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 2, &quot;duration&quot;: &quot;1min&quot;}, {&quot;day&quot;: 83, &quot;title&quot;: &quot;Day 83 - Professional Portfolio Project - [Python Web…]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 2, &quot;duration&quot;: &quot;3min&quot;}, {&quot;day&quot;: 84, &quot;title&quot;: &quot;Day 84 - Professional Portfolio Project - [Python Scripting]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 85, &quot;title&quot;: &quot;Day 85 - Professional Portfolio Project - [GUI]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 86, &quot;title&quot;: &quot;Day 86 - Professional Portfolio Project - [GUI]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 87, &quot;title&quot;: &quot;Day 87 - Professional Portfolio Project - [Game]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 88, &quot;title&quot;: &quot;Day 88 - Professional Portfolio Project - [Web Development]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 89, &quot;title&quot;: &quot;Day 89 - Professional Portfolio Project - [Web Development]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 90, &quot;title&quot;: &quot;Day 90 - Professional Portfolio Project - [GUI Desktop App]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 91, &quot;title&quot;: &quot;Day 91 - Professional Portfolio Project - [HTTP Requests &amp;…]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 92, &quot;title&quot;: &quot;Day 92 - Professional Portfolio Project - [Image Processing …]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 93, &quot;title&quot;: &quot;Day 93 - Professional Portfolio Project - [Web Scraping]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 94, &quot;title&quot;: &quot;Day 94 - Professional Portfolio Project - [GUI Automation]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 95, &quot;title&quot;: &quot;Day 95 - Professional Portfolio Project - [Game]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 96, &quot;title&quot;: &quot;Day 96 - Professional Portfolio Project - [HTTP Requests &amp;…]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 97, &quot;title&quot;: &quot;Day 97 - Professional Portfolio Project - [Web Development]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 98, &quot;title&quot;: &quot;Day 98 - Professional Portfolio Project - [Python Automation]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 99, &quot;title&quot;: &quot;Day 99 - Professional Portfolio Project - [Data Science]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 100, &quot;title&quot;: &quot;Day 100 - Professional Portfolio Project - [Data Science]&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;0min&quot;}, {&quot;day&quot;: 101, &quot;title&quot;: &quot;Final Stretch&quot;, &quot;done&quot;: 3, &quot;total&quot;: 3, &quot;duration&quot;: &quot;2hr 41min&quot;}, {&quot;day&quot;: 102, &quot;title&quot;: &quot;Bonus Lecture: Succeeding in the Age of AI&quot;, &quot;done&quot;: 0, &quot;total&quot;: 1, &quot;duration&quot;: &quot;2min&quot;}];const KEY=&quot;course-todo-102-v1-akshat&quot;,CUSTOM=&quot;course-custom-tasks-v1-akshat&quot;;let saved=JSON.parse(localStorage.getItem(KEY)||&quot;null&quot;);let sections=saved||original.map(x=&gt;({...x}));let custom=JSON.parse(localStorage.getItem(CUSTOM)||&quot;[]&quot;);let selected=new Date();selected.setHours(0,0,0,0);let weekShift=0,filter=&quot;all&quot;,showAll=true;const z=n=&gt;String(n).padStart(2,&quot;0&quot;),iso=d=&gt;`${d.getFullYear()}-${z(d.getMonth()+1)}-${z(d.getDate())}`,today=new Date();today.setHours(0,0,0,0);const dueDate=day=&gt;{let d=new Date(today);d.setDate(d.getDate()+day-1);return d},esc=s=&gt;String(s).replace(/[&amp;&lt;&gt;&quot;&#x27;]/g,c=&gt;({&quot;&amp;&quot;:&quot;&amp;amp;&quot;,&quot;&lt;&quot;:&quot;&amp;lt;&quot;,&quot;&gt;&quot;:&quot;&amp;gt;&quot;,&#x27;&quot;&#x27;:&quot;&amp;quot;&quot;,&quot;&#x27;&quot;:&quot;&amp;#39;&quot;}[c]));function persist(){localStorage.setItem(KEY,JSON.stringify(sections));draw()}function isDone(s){return s.done&gt;=s.total}function dayStart(d){let x=new Date(d);x.setDate(x.getDate()-((x.getDay()+6)%7));x.setHours(0,0,0,0);return x}function draw(){document.querySelector(&quot;#today&quot;).textContent=today.toLocaleDateString(undefined,{weekday:&quot;long&quot;,month:&quot;long&quot;,day:&quot;numeric&quot;});let finished=sections.filter(isDone).length,doneLessons=sections.reduce((a,s)=&gt;a+s.done,0),totalLessons=sections.reduce((a,s)=&gt;a+s.total,0);document.querySelector(&quot;#finished&quot;).textContent=finished;document.querySelector(&quot;#remaining&quot;).textContent=sections.length-finished;document.querySelector(&quot;#lessons&quot;).textContent=`${doneLessons} / ${totalLessons}`;let pct=Math.round(100*doneLessons/totalLessons);document.querySelector(&quot;#percent&quot;).textContent=pct+&quot;%&quot;;document.querySelector(&quot;#overallBar&quot;).style.width=pct+&quot;%&quot;;document.querySelector(&quot;#overallText&quot;).textContent=`${doneLessons} of ${totalLessons} lessons complete across ${sections.length} sections.`;let week=dayStart(selected);week.setDate(week.getDate()+7*weekShift);document.querySelector(&quot;#weekLabel&quot;).textContent=week.toLocaleDateString(undefined,{month:&quot;short&quot;,day:&quot;numeric&quot;})+&quot; – &quot;+new Date(week.getTime()+6*86400000).toLocaleDateString(undefined,{month:&quot;short&quot;,day:&quot;numeric&quot;});let days=document.querySelector(&quot;#days&quot;);days.innerHTML=&quot;&quot;;for(let i=0;i&lt;7;i++){let d=new Date(week);d.setDate(d.getDate()+i);let date=iso(d),due=sections.filter(s=&gt;iso(dueDate(s.day))===date),nDone=due.filter(isDone).length;let el=document.createElement(&quot;div&quot;);el.className=&quot;day&quot;+(iso(selected)===date?&quot; selected&quot;:&quot;&quot;);el.innerHTML=`&lt;span&gt;${d.toLocaleDateString(undefined,{weekday:&quot;short&quot;,month:&quot;short&quot;,day:&quot;numeric&quot;})}&lt;/span&gt;&lt;small&gt;${due.length?`${nDone}/${due.length} done`:&quot;—&quot;}&lt;/small&gt;`;el.onclick=()=&gt;{selected=d;showAll=false;draw()};days.appendChild(el)}let items=sections.filter(s=&gt;{let done=isDone(s),partial=s.done&gt;0&amp;&amp;!done,match=filter===&quot;all&quot;||filter===&quot;done&quot;&amp;&amp;done||filter===&quot;todo&quot;&amp;&amp;!done||filter===&quot;progress&quot;&amp;&amp;partial;return match&amp;&amp;(showAll||iso(dueDate(s.day))===iso(selected))});document.querySelector(&quot;#listTitle&quot;).textContent=showAll?&quot;Your day-by-day list&quot;:selected.toLocaleDateString(undefined,{weekday:&quot;long&quot;,month:&quot;long&quot;,day:&quot;numeric&quot;});document.querySelector(&quot;#listSub&quot;).textContent=showAll?`${items.length} sections shown · ${sections.length} total`: `${items.length} course section(s) planned for this date`;let list=document.querySelector(&quot;#list&quot;);list.innerHTML=&quot;&quot;;if(!items.length)list.innerHTML=&#x27;&lt;div class=&quot;empty&quot;&gt;Nothing here for this view. Try another filter or calendar day.&lt;/div&gt;&#x27;;for(const s of items){let d=dueDate(s.day),complete=isDone(s),el=document.createElement(&quot;article&quot;);el.className=&quot;task&quot;+(complete?&quot; done&quot;:&quot;&quot;);el.innerHTML=`&lt;button class=&quot;check&quot; title=&quot;${complete?&quot;Mark section to do&quot;:&quot;Mark section complete&quot;}&quot; aria-label=&quot;Toggle completion&quot;&gt;${complete?&quot;✓&quot;:&quot;&quot;}&lt;/button&gt;&lt;div&gt;&lt;div class=&quot;title&quot;&gt;Section ${s.day}: ${esc(s.title)}&lt;/div&gt;&lt;div class=&quot;meta&quot;&gt;Day ${s.day} · ${d.toLocaleDateString(undefined,{weekday:&quot;short&quot;,month:&quot;short&quot;,day:&quot;numeric&quot;})} · ${esc(s.duration)}&lt;/div&gt;&lt;div class=&quot;bar&quot;&gt;&lt;i style=&quot;width:${Math.round(100*s.done/s.total)}%&quot;&gt;&lt;/i&gt;&lt;/div&gt;&lt;/div&gt;&lt;div class=&quot;meter&quot;&gt;&lt;button class=&quot;minus&quot; aria-label=&quot;One fewer lesson complete&quot;&gt;−&lt;/button&gt;&lt;span class=&quot;count&quot;&gt;${s.done}/${s.total}&lt;/span&gt;&lt;button class=&quot;plus&quot; aria-label=&quot;One more lesson complete&quot;&gt;+&lt;/button&gt;&lt;/div&gt;`;el.querySelector(&quot;.check&quot;).onclick=()=&gt;{s.done=complete?Math.max(0,s.total-1):s.total;persist()};el.querySelector(&quot;.minus&quot;).onclick=()=&gt;{s.done=Math.max(0,s.done-1);persist()};el.querySelector(&quot;.plus&quot;).onclick=()=&gt;{s.done=Math.min(s.total,s.done+1);persist()};list.appendChild(el)}let ct=custom.filter(t=&gt;t.date===iso(selected));document.querySelector(&quot;#customList&quot;).innerHTML=ct.length?ct.map((t,i)=&gt;`&lt;label style=&quot;display:flex;gap:7px;margin-top:7px&quot;&gt;&lt;input type=&quot;checkbox&quot; data-custom=&quot;${i}&quot; ${t.done?&quot;checked&quot;:&quot;&quot;}&gt; &lt;span style=&quot;${t.done?&quot;text-decoration:line-through&quot;:&quot;&quot;}&quot;&gt;${esc(t.name)}&lt;/span&gt;&lt;/label&gt;`).join(&quot;&quot;):&quot;Personal reminders for the selected calendar date appear here.&quot;;document.querySelectorAll(&quot;[data-custom]&quot;).forEach(cb=&gt;cb.onchange=()=&gt;{let idx=ct[+cb.dataset.custom],real=custom.indexOf(idx);custom[real].done=cb.checked;localStorage.setItem(CUSTOM,JSON.stringify(custom));draw()})}document.querySelectorAll(&quot;.filter&quot;).forEach(b=&gt;b.onclick=()=&gt;{filter=b.dataset.filter;document.querySelectorAll(&quot;.filter&quot;).forEach(x=&gt;x.classList.toggle(&quot;active&quot;,x===b));draw()});document.querySelector(&quot;#viewBtn&quot;).onclick=()=&gt;{showAll=!showAll;document.querySelector(&quot;#viewBtn&quot;).textContent=showAll?&quot;View: All&quot;:&quot;View: Selected day&quot;;draw()};document.querySelector(&quot;#prev&quot;).onclick=()=&gt;{weekShift--;draw()};document.querySelector(&quot;#next&quot;).onclick=()=&gt;{weekShift++;draw()};document.querySelector(&quot;#resetBtn&quot;).onclick=()=&gt;{if(confirm(&quot;Reset all course lesson counts to the progress shown in the screenshots?&quot;)){sections=original.map(x=&gt;({...x}));persist()}};document.querySelector(&quot;#date&quot;).value=iso(selected);document.querySelector(&quot;#form&quot;).onsubmit=e=&gt;{e.preventDefault();custom.push({name:document.querySelector(&quot;#name&quot;).value.trim(),date:document.querySelector(&quot;#date&quot;).value,done:false});localStorage.setItem(CUSTOM,JSON.stringify(custom));document.querySelector(&quot;#name&quot;).value=&quot;&quot;;selected=new Date(document.querySelector(&quot;#date&quot;).value+&quot;T12:00:00&quot;);showAll=false;draw()};draw();
&lt;/script&gt;&lt;/body&gt;&lt;/html&gt;"></iframe>
  </section>
  <footer>Keep experimenting: change a value, save, and see what happens.</footer>
  <script>

    const languageLinks = [...document.querySelectorAll('.nav-inner nav a[href^="#"]')];
    const languageSections = languageLinks.map(link => document.querySelector(link.getAttribute("href"))).filter(Boolean);
    if ("IntersectionObserver" in window) {
      const languageObserver = new IntersectionObserver(entries => {
        const visible = entries.filter(entry => entry.isIntersecting).sort((a, b) => b.intersectionRatio - a.intersectionRatio)[0];
        if (!visible) return;
        languageLinks.forEach(link => {
          if (link.getAttribute("href") === "#" + visible.target.id) link.setAttribute("aria-current", "location");
          else link.removeAttribute("aria-current");
        });
      }, { rootMargin: "-22% 0px -62% 0px", threshold: [0, .1, .3, .6] });
      languageSections.forEach(section => languageObserver.observe(section));
    }
    const search = document.querySelector("#search");
    const cards = [...document.querySelectorAll(".card")];
    const empty = document.querySelector("#empty");
    search.addEventListener("input", () => {
      const term = search.value.trim().toLowerCase();
      let shown = 0;
      cards.forEach(card => {
        const match = card.textContent.toLowerCase().includes(term);
        card.hidden = !match;
        if (match) shown++;
      });
      document.querySelectorAll(".section").forEach(section => {
        const cardMatch = section.querySelector(".card:not([hidden])");
        const fullReference = section.querySelector(".full-reference");
        if (fullReference && term) fullReference.open = !!fullReference.querySelector(".card:not([hidden])");
        const sourceReference = section.querySelector(".source-reference");
        const sourceMatch = !!(term && sourceReference && sourceReference.textContent.toLowerCase().includes(term));
        if (sourceMatch) {
          sourceReference.open = true;
          sourceReference.querySelectorAll(".topic-detail").forEach(topic => {
            topic.open = topic.textContent.toLowerCase().includes(term);
          });
          shown++;
        }
        section.hidden = !cardMatch && !sourceMatch;
      });
      empty.style.display = shown ? "none" : "block";
    });
    document.addEventListener("click", async event => {
      const button = event.target.closest(".copy");
      if (!button) return;
      const code = button.closest(".card").querySelector("pre code").innerText;
      try {
        await navigator.clipboard.writeText(code);
        button.textContent = "Copied!";
      } catch {
        button.textContent = "Select code to copy";
      }
      window.setTimeout(() => { button.textContent = "Copy"; }, 1600);
    });
  </script>

  <script>
    // Embed the workspace so the cheat sheet still works when it is moved by itself.
    const PYTHON_NOTES_WORKSPACE_HTML = "<!DOCTYPE html>\n<html lang=\"en\">\n<head>\n  <meta charset=\"UTF-8\" />\n  <meta name=\"viewport\" content=\"width=device-width, initial-scale=1.0\" />\n  <title>Python Notes Workspace<\/title>\n  <script src=\"https://cdn.tailwindcss.com\"><\/script>\n  <link rel=\"preconnect\" href=\"https://fonts.googleapis.com\" />\n  <link rel=\"preconnect\" href=\"https://fonts.gstatic.com\" crossorigin />\n  <link href=\"https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=JetBrains+Mono:ital,wght@0,400;0,500;0,600;1,400&family=Lora:ital,wght@0,400;0,600;1,400&family=Merriweather:ital,wght@0,400;0,700;1,400&family=Roboto:ital,wght@0,300;0,400;0,500;0,700;1,400&display=swap\" rel=\"stylesheet\" />\n  <link rel=\"stylesheet\" href=\"https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200\" />\n\n  <style>\n    :root {\n      --workspace-bg: #f9fbfd;\n      --toolbar-bg: #edf2fa;\n      --toolbar-hover: #dfe5ef;\n      --toolbar-active: #d3e3fd;\n      --toolbar-active-text: #041e49;\n      --border-subtle: #e0e3e7;\n      --text-primary: #1f1f1f;\n      --text-secondary: #444746;\n      --docs-blue: #0b57d0;\n      --docs-blue-light: #c2e7ff;\n      --docs-blue-hover: #b3d7ef;\n    }\n\n    * {\n      box-sizing: border-box;\n    }\n\n    body {\n      font-family: 'Roboto', 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;\n      background-color: var(--workspace-bg);\n      color: var(--text-primary);\n      margin: 0;\n      padding: 0;\n      overflow: hidden;\n      height: 100vh;\n      display: flex;\n      flex-direction: column;\n      user-select: none;\n    }\n\n    .material-symbols-outlined {\n      font-variation-settings: 'FILL' 0, 'wght' 400, 'GRAD' 0, 'opsz' 20;\n      font-size: 19px;\n      line-height: 1;\n      vertical-align: middle;\n    }\n    .material-symbols-outlined.filled {\n      font-variation-settings: 'FILL' 1, 'wght' 400, 'GRAD' 0, 'opsz' 20;\n    }\n\n    ::-webkit-scrollbar {\n      width: 10px;\n      height: 10px;\n    }\n    ::-webkit-scrollbar-track {\n      background: transparent;\n    }\n    ::-webkit-scrollbar-thumb {\n      background: #dadce0;\n      border-radius: 5px;\n      border: 2px solid transparent;\n      background-clip: content-box;\n    }\n    ::-webkit-scrollbar-thumb:hover {\n      background: #bdc1c6;\n      border: 2px solid transparent;\n      background-clip: content-box;\n    }\n\n    /* Top Menu Bar */\n    .menu-btn {\n      padding: 2px 7px;\n      font-size: 14px;\n      color: var(--text-primary);\n      border-radius: 4px;\n      cursor: pointer;\n      transition: background-color 0.12s ease;\n    }\n    .menu-btn:hover,\n    .menu-btn.active {\n      background-color: #e8eaed;\n    }\n\n    .dropdown-panel {\n      position: absolute;\n      top: 100%;\n      left: 0;\n      min-width: 245px;\n      background: #ffffff;\n      border-radius: 8px;\n      box-shadow: 0 2px 6px 2px rgba(60, 64, 67, 0.15), 0 1px 2px 0 rgba(60, 64, 67, 0.3);\n      padding: 6px 0;\n      z-index: 1000;\n      display: none;\n      animation: fadeInScale 0.1s ease-out;\n    }\n    .dropdown-panel.open {\n      display: block;\n    }\n    @keyframes fadeInScale {\n      from { opacity: 0; transform: translateY(-4px) scale(0.98); }\n      to { opacity: 1; transform: translateY(0) scale(1); }\n    }\n\n    .dropdown-item {\n      display: flex;\n      align-items: center;\n      justify-content: space-between;\n      padding: 6px 16px;\n      font-size: 13.5px;\n      color: #1f1f1f;\n      cursor: pointer;\n      gap: 16px;\n    }\n    .dropdown-item:hover {\n      background-color: #f1f3f4;\n    }\n    .dropdown-item .shortcut {\n      font-size: 11.5px;\n      color: #5f6368;\n      font-weight: 500;\n    }\n    .dropdown-divider {\n      height: 1px;\n      background-color: #e0e3e7;\n      margin: 5px 0;\n    }\n\n    /* Toolbar Pill */\n    .toolbar-pill {\n      background-color: var(--toolbar-bg);\n      border-radius: 24px;\n      min-height: 40px;\n      padding: 3px 10px;\n      display: flex;\n      align-items: center;\n      flex-wrap: nowrap;\n      gap: 2px;\n      overflow-x: auto;\n      overflow-y: hidden;\n    }\n    .toolbar-pill::-webkit-scrollbar {\n      height: 0px;\n    }\n\n    .tool-btn {\n      display: inline-flex;\n      align-items: center;\n      justify-content: center;\n      height: 28px;\n      min-width: 28px;\n      padding: 0 6px;\n      border-radius: 4px;\n      color: #444746;\n      cursor: pointer;\n      transition: background-color 0.1s ease, color 0.1s ease;\n      position: relative;\n      flex-shrink: 0;\n      font-size: 12.5px;\n    }\n    .tool-btn:hover {\n      background-color: var(--toolbar-hover);\n      color: #1f1f1f;\n    }\n    .tool-btn.active {\n      background-color: var(--toolbar-active);\n      color: var(--toolbar-active-text);\n    }\n\n    .tool-sep {\n      width: 1px;\n      height: 18px;\n      background-color: #c7c7c7;\n      margin: 0 4px;\n      flex-shrink: 0;\n    }\n\n    /* Horizontal Ruler */\n    #ruler-container {\n      height: 24px;\n      background-color: #f9fbfd;\n      border-bottom: 1px solid #e0e3e7;\n      display: flex;\n      justify-content: center;\n      position: relative;\n      z-index: 20;\n      flex-shrink: 0;\n    }\n    #ruler-track {\n      width: 816px;\n      height: 100%;\n      background: #ffffff;\n      position: relative;\n      border-left: 1px solid #dadce0;\n      border-right: 1px solid #dadce0;\n      transform-origin: top center;\n    }\n    .ruler-margin-shade {\n      position: absolute;\n      top: 0;\n      bottom: 0;\n      background-color: #e8eaed;\n      pointer-events: none;\n    }\n    .margin-handle {\n      position: absolute;\n      top: 2px;\n      width: 12px;\n      height: 20px;\n      cursor: ew-resize;\n      z-index: 15;\n      display: flex;\n      flex-direction: column;\n      align-items: center;\n      transform: translateX(-50%);\n    }\n    .margin-handle .bar {\n      width: 10px;\n      height: 3px;\n      background: #1a73e8;\n      border-radius: 1px;\n      margin-bottom: 2px;\n    }\n    .margin-handle .triangle {\n      width: 0;\n      height: 0;\n      border-left: 5px solid transparent;\n      border-right: 5px solid transparent;\n      border-top: 6px solid #1a73e8;\n    }\n\n    /* Workspace & Multi-page US Letter Canvas */\n    #workspace-scroll {\n      flex: 1;\n      overflow-y: auto;\n      overflow-x: auto;\n      display: flex;\n      flex-direction: column;\n      align-items: center;\n      padding: 20px 24px 90px 24px;\n      position: relative;\n      scroll-behavior: smooth;\n    }\n\n    #paper-wrapper {\n      transform-origin: top center;\n      transition: transform 0.15s ease;\n      display: flex;\n      flex-direction: column;\n      gap: 20px;\n    }\n\n    .doc-sheet {\n      width: 816px;\n      min-height: 1056px;\n      background-color: #ffffff;\n      box-shadow: 0 1px 3px 1px rgba(60, 64, 67, 0.15);\n      display: flex;\n      flex-direction: column;\n      position: relative;\n    }\n\n    .doc-header-zone,\n    .doc-footer-zone {\n      min-height: 48px;\n      padding: 16px 96px 8px 96px;\n      font-size: 9.5pt;\n      color: #5f6368;\n      outline: none;\n      user-select: text;\n      border-bottom: 1px dashed transparent;\n      transition: border-color 0.15s ease;\n    }\n    .doc-footer-zone {\n      padding: 8px 96px 16px 96px;\n      border-bottom: none;\n      border-top: 1px dashed transparent;\n      margin-top: auto;\n      display: flex;\n      justify-content: space-between;\n      align-items: center;\n    }\n    .doc-header-zone:focus,\n    .doc-header-zone:hover {\n      border-bottom-color: #dadce0;\n    }\n    .doc-footer-zone:focus,\n    .doc-footer-zone:hover {\n      border-top-color: #dadce0;\n    }\n\n    .doc-body {\n      flex: 1;\n      padding: 24px 96px 48px 96px;\n      outline: none;\n      user-select: text;\n      font-family: 'Arial', 'Roboto', sans-serif;\n      font-size: 11pt;\n      line-height: 1.35;\n      color: #1f1f1f;\n      word-wrap: break-word;\n    }\n\n    /* Document Rich Text Elements */\n    .doc-body h1 {\n      font-size: 20pt;\n      font-weight: 500;\n      margin: 14pt 0 6pt 0;\n      line-height: 1.25;\n    }\n    .doc-body h2 {\n      font-size: 15.5pt;\n      font-weight: 500;\n      margin: 12pt 0 4pt 0;\n      line-height: 1.25;\n    }\n    .doc-body h3 {\n      font-size: 13pt;\n      font-weight: 500;\n      color: #434343;\n      margin: 10pt 0 4pt 0;\n      line-height: 1.25;\n    }\n    .doc-body .doc-title-style {\n      font-size: 25pt;\n      font-weight: 400;\n      margin: 0 0 6pt 0;\n      line-height: 1.15;\n    }\n    .doc-body .doc-subtitle-style {\n      font-size: 14pt;\n      font-weight: 400;\n      color: #5f6368;\n      margin: 0 0 14pt 0;\n      line-height: 1.25;\n    }\n    .doc-body p {\n      margin: 0 0 8pt 0;\n    }\n    .doc-body a {\n      color: #1155cc;\n      text-decoration: underline;\n      cursor: pointer;\n    }\n    .doc-body ul {\n      list-style-type: disc;\n      padding-left: 26px;\n      margin: 4pt 0 8pt 0;\n    }\n    .doc-body ol {\n      list-style-type: decimal;\n      padding-left: 26px;\n      margin: 4pt 0 8pt 0;\n    }\n    .doc-body table {\n      border-collapse: collapse;\n      width: 100%;\n      margin: 10pt 0;\n    }\n    .doc-body td,\n    .doc-body th {\n      border: 1px solid #80868b;\n      padding: 6px 8px;\n      min-width: 40px;\n      vertical-align: top;\n    }\n    .doc-body img {\n      max-width: 100%;\n      height: auto;\n      border-radius: 4px;\n    }\n\n    /* Inline Code Chip */\n    .doc-inline-code {\n      font-family: 'JetBrains Mono', monospace;\n      font-size: 9.5pt;\n      background-color: #f1f3f4;\n      color: #c5221f;\n      border: 1px solid #e0e3e7;\n      border-radius: 4px;\n      padding: 1px 5px;\n    }\n\n    /* Checklist Styling */\n    .docs-checklist {\n      list-style: none !important;\n      padding-left: 4px !important;\n    }\n    .docs-checklist li {\n      display: flex;\n      align-items: flex-start;\n      gap: 8px;\n      margin-bottom: 4px;\n    }\n    .docs-checklist input[type=\"checkbox\"] {\n      margin-top: 3px;\n      accent-color: #0b57d0;\n      cursor: pointer;\n      width: 15px;\n      height: 15px;\n    }\n    .docs-checklist li.checked span {\n      text-decoration: line-through;\n      color: #5f6368;\n    }\n\n    /* Comment Highlight */\n    .doc-comment-highlight {\n      background-color: #fef7e0;\n      border-bottom: 2px solid #f9ab00;\n      cursor: pointer;\n    }\n\n    /* =========================================================================\n       EMBEDDED IDE CODE BLOCK & LIVE SYNTAX HIGHLIGHTING (LIGHT & DARK THEMES)\n       ========================================================================= */\n    .code-card {\n      margin: 12pt 0;\n      border-radius: 10px;\n      overflow: hidden;\n      border: 1px solid #d0d7de;\n      background: #f6f8fa;\n      font-family: 'JetBrains Mono', monospace;\n      user-select: none;\n      box-shadow: 0 1px 2px rgba(0, 0, 0, 0.04);\n    }\n    .code-card-header {\n      display: flex;\n      align-items: center;\n      justify-content: space-between;\n      padding: 6px 12px;\n      background: #eaeef2;\n      border-bottom: 1px solid #d0d7de;\n      font-family: 'Inter', sans-serif;\n      font-size: 12px;\n      color: #24292f;\n      gap: 8px;\n    }\n    .code-card-body {\n      display: flex;\n      position: relative;\n      overflow-x: auto;\n    }\n    .code-gutter {\n      padding: 12px 10px;\n      text-align: right;\n      background: #eef1f5;\n      color: #6e7781;\n      border-right: 1px solid #d8dee4;\n      font-size: 12.5px;\n      line-height: 1.55;\n      user-select: none;\n      min-width: 40px;\n      flex-shrink: 0;\n    }\n    .code-editor-stack {\n      position: relative;\n      flex: 1;\n      min-width: 0;\n    }\n    .code-highlight-layer,\n    .code-textarea-layer {\n      margin: 0;\n      padding: 12px 14px;\n      font-family: 'JetBrains Mono', monospace;\n      font-size: 12.5px;\n      line-height: 1.55;\n      tab-size: 2;\n      white-space: pre;\n      overflow-wrap: normal;\n      word-break: normal;\n      width: 100%;\n      min-height: 64px;\n    }\n    .code-highlight-layer {\n      pointer-events: none;\n      color: #24292f;\n    }\n    .code-textarea-layer {\n      position: absolute;\n      inset: 0;\n      background: transparent;\n      color: transparent;\n      caret-color: #0b57d0;\n      border: none;\n      outline: none;\n      resize: none;\n      overflow: hidden;\n      user-select: text;\n    }\n    .code-textarea-layer::selection {\n      background: rgba(11, 87, 208, 0.22);\n    }\n\n    /* Light Theme Tokens (GitHub Light) */\n    .tok-kw { color: #cf222e; font-weight: 500; }\n    .tok-str { color: #0a3069; }\n    .tok-num { color: #0550ae; }\n    .tok-com { color: #6e7781; font-style: italic; }\n    .tok-fn { color: #8250df; }\n    .tok-tag { color: #116329; }\n    .tok-attr { color: #0550ae; }\n    .tok-op { color: #24292f; }\n\n    /* Dark Theme Overrides (One Dark Pro) */\n    body.ide-dark .code-card {\n      border-color: #30363d;\n      background: #1e1e2e;\n    }\n    body.ide-dark .code-card-header {\n      background: #181825;\n      border-bottom-color: #30363d;\n      color: #cdd6f4;\n    }\n    body.ide-dark .code-gutter {\n      background: #181825;\n      color: #6c7086;\n      border-right-color: #30363d;\n    }\n    body.ide-dark .code-highlight-layer {\n      color: #cdd6f4;\n    }\n    body.ide-dark .code-textarea-layer {\n      caret-color: #89b4fa;\n    }\n    body.ide-dark .code-textarea-layer::selection {\n      background: rgba(137, 180, 250, 0.25);\n    }\n    body.ide-dark .tok-kw { color: #cba6f7; font-weight: 500; }\n    body.ide-dark .tok-str { color: #a6e3a1; }\n    body.ide-dark .tok-num { color: #fab387; }\n    body.ide-dark .tok-com { color: #6c7086; font-style: italic; }\n    body.ide-dark .tok-fn { color: #89b4fa; }\n    body.ide-dark .tok-tag { color: #f38ba8; }\n    body.ide-dark .tok-attr { color: #f9e2af; }\n    body.ide-dark .tok-op { color: #94e2d5; }\n\n    @media print {\n      body { background: #fff !important; overflow: visible !important; height: auto !important; }\n      #app-header, #formatting-bar-wrapper, #ruler-container, #left-outline-sidebar, #right-comments-sidebar, #status-pill, #toast-notification, .code-card-actions, #add-page-bar {\n        display: none !important;\n      }\n      #workspace-scroll { padding: 0 !important; overflow: visible !important; }\n      #paper-wrapper { transform: none !important; gap: 0 !important; }\n      .doc-sheet { box-shadow: none !important; width: 100% !important; min-height: auto !important; page-break-after: always; }\n    }\n  <\/style>\n<\/head>\n<body>\n\n  <!-- ================= TOP HEADER ================= -->\n  <header id=\"app-header\" class=\"bg-[#f9fbfd] px-3 pt-2 pb-1 flex items-center justify-between gap-2 flex-shrink-0 z-30\">\n    <div class=\"flex items-center gap-1.5 min-w-0\">\n      <!-- Docs + Code SVG Icon -->\n      <a href=\"#\" onclick=\"event.preventDefault(); showToast('Google Docs + Code Workspace');\" class=\"p-1.5 rounded-lg hover:bg-gray-200/70 transition flex-shrink-0 relative\" title=\"Docs + Code Home\">\n        <svg width=\"36\" height=\"36\" viewBox=\"0 0 48 48\" fill=\"none\" xmlns=\"http://www.w3.org/2000/svg\">\n          <path d=\"M29.5 4H11C9.34315 4 8 5.34315 8 7V41C8 42.6569 9.34315 44 11 44H37C38.6569 44 40 42.6569 40 41V14.5L29.5 4Z\" fill=\"#2684FC\"/>\n          <path d=\"M29.5 4V14.5H40L29.5 4Z\" fill=\"#0066DA\"/>\n          <rect x=\"14\" y=\"21\" width=\"20\" height=\"2.4\" rx=\"1\" fill=\"white\"/>\n          <rect x=\"14\" y=\"26.5\" width=\"20\" height=\"2.4\" rx=\"1\" fill=\"white\"/>\n          <rect x=\"14\" y=\"32\" width=\"13\" height=\"2.4\" rx=\"1\" fill=\"white\"/>\n        <\/svg>\n        <span class=\"absolute bottom-1 right-0.5 bg-[#0b57d0] text-white text-[9px] font-mono font-bold px-1 rounded shadow-xs\">&lt;/&gt;<\/span>\n      <\/a>\n\n      <div class=\"flex flex-col min-w-0\">\n        <!-- Title Row -->\n        <div class=\"flex items-center gap-1 flex-wrap\">\n          <input id=\"doc-title-input\" type=\"text\" value=\"Untitled document\" aria-label=\"Document title\"\n            class=\"text-[18px] font-normal text-[#1f1f1f] bg-transparent border border-transparent hover:border-[#747775] focus:border-[#0b57d0] focus:border-2 focus:bg-white rounded px-1.5 py-0.5 outline-none transition max-w-[240px] sm:max-w-[340px] truncate\" />\n\n          <button id=\"btn-star\" onclick=\"toggleStar()\" class=\"w-7 h-7 rounded-full hover:bg-gray-200/80 flex items-center justify-center text-[#444746] transition\" title=\"Star\">\n            <span id=\"star-icon\" class=\"material-symbols-outlined\">star<\/span>\n          <\/button>\n\n          <button id=\"btn-cloud-status\" onclick=\"triggerManualSave()\" class=\"h-7 px-2 rounded-full hover:bg-gray-200/80 flex items-center gap-1.5 text-[#444746] text-xs transition\" title=\"Document status\">\n            <span id=\"cloud-icon\" class=\"material-symbols-outlined\">cloud_done<\/span>\n            <span id=\"cloud-text\" class=\"hidden md:inline text-[12px] text-[#444746]\">Saved on this device<\/span>\n          <\/button>\n        <\/div>\n\n        <!-- Menu Bar Row -->\n        <nav id=\"top-menubar\" class=\"flex items-center gap-0.5 text-[14px] relative select-none\">\n          <!-- FILE -->\n          <div class=\"relative menu-container\">\n            <button class=\"menu-btn\" data-menu=\"menu-file\">File<\/button>\n            <div id=\"menu-file\" class=\"dropdown-panel\">\n              <div class=\"dropdown-item\" onclick=\"newDocument()\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">description<\/span>New blank doc<\/span><\/div>\n              <div class=\"dropdown-item\" onclick=\"openModal('templates-modal')\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">dashboard_customize<\/span>From template...<\/span><\/div>\n              <div class=\"dropdown-item\" onclick=\"document.getElementById('import-file-input').click()\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">folder_open<\/span>Open file...<\/span><span class=\"shortcut\">Ctrl+O<\/span><\/div>\n              <div class=\"dropdown-item\" onclick=\"makeCopy()\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">file_copy<\/span>Make a copy<\/span><\/div>\n              <div class=\"dropdown-divider\"><\/div>\n              <div class=\"dropdown-item\" onclick=\"downloadDoc('html')\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">download<\/span>Export a copy<\/span><\/div>\n              <div class=\"dropdown-item\" onclick=\"downloadDoc('html')\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">download<\/span>Download as HTML (.html)<\/span><\/div>\n              <div class=\"dropdown-item\" onclick=\"downloadDoc('md')\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">markdown<\/span>Download as Markdown (.md)<\/span><\/div>\n              <div class=\"dropdown-item\" onclick=\"downloadDoc('txt')\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">text_snippet<\/span>Download as Plain Text (.txt)<\/span><\/div>\n              <div class=\"dropdown-divider\"><\/div>\n              <div class=\"dropdown-item\" onclick=\"openModal('page-setup-modal')\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">settings_overscan<\/span>Page setup<\/span><\/div>\n              <div class=\"dropdown-item\" onclick=\"window.print()\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">print<\/span>Print<\/span><span class=\"shortcut\">Ctrl+P<\/span><\/div>\n            <\/div>\n          <\/div>\n\n          <!-- EDIT -->\n          <div class=\"relative menu-container\">\n            <button class=\"menu-btn\" data-menu=\"menu-edit\">Edit<\/button>\n            <div id=\"menu-edit\" class=\"dropdown-panel\">\n              <div class=\"dropdown-item\" onclick=\"execCmd('undo')\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">undo<\/span>Undo<\/span><span class=\"shortcut\">Ctrl+Z<\/span><\/div>\n              <div class=\"dropdown-item\" onclick=\"execCmd('redo')\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">redo<\/span>Redo<\/span><span class=\"shortcut\">Ctrl+Y<\/span><\/div>\n              <div class=\"dropdown-divider\"><\/div>\n              <div class=\"dropdown-item\" onclick=\"selectAllDoc()\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">select_all<\/span>Select all<\/span><span class=\"shortcut\">Ctrl+A<\/span><\/div>\n              <div class=\"dropdown-item\" onclick=\"openModal('find-replace-modal')\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">find_replace<\/span>Find and replace<\/span><span class=\"shortcut\">Ctrl+H<\/span><\/div>\n            <\/div>\n          <\/div>\n\n          <!-- VIEW -->\n          <div class=\"relative menu-container\">\n            <button class=\"menu-btn\" data-menu=\"menu-view\">View<\/button>\n            <div id=\"menu-view\" class=\"dropdown-panel\">\n              <div class=\"dropdown-item\" onclick=\"toggleOutlineSidebar()\"><span class=\"flex items-center gap-2.5\"><span id=\"check-outline\" class=\"material-symbols-outlined\">check<\/span>Show outline<\/span><\/div>\n              <div class=\"dropdown-item\" onclick=\"toggleRuler()\"><span class=\"flex items-center gap-2.5\"><span id=\"check-ruler\" class=\"material-symbols-outlined\">check<\/span>Show ruler<\/span><\/div>\n              <div class=\"dropdown-item\" onclick=\"toggleCommentsSidebar()\"><span class=\"flex items-center gap-2.5\"><span id=\"check-comments\" class=\"material-symbols-outlined opacity-0\">check<\/span>Show comments sidebar<\/span><\/div>\n              <div class=\"dropdown-divider\"><\/div>\n              <div class=\"dropdown-item\" onclick=\"toggleIdeTheme()\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">contrast<\/span>Toggle Dark/Light IDE theme<\/span><\/div>\n              <div class=\"dropdown-item\" onclick=\"toggleFullScreen()\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">fullscreen<\/span>Full screen<\/span><\/div>\n            <\/div>\n          <\/div>\n\n          <!-- INSERT -->\n          <div class=\"relative menu-container\">\n            <button class=\"menu-btn\" data-menu=\"menu-insert\">Insert<\/button>\n            <div id=\"menu-insert\" class=\"dropdown-panel\">\n              <div class=\"dropdown-item\" onclick=\"insertCodeBlock()\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined text-[#0b57d0]\">code_blocks<\/span>Code block<\/span><span class=\"shortcut\">Ctrl+Alt+C<\/span><\/div>\n              <div class=\"dropdown-item\" onclick=\"toggleInlineCode()\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">code<\/span>Inline code<\/span><span class=\"shortcut\">Ctrl+E<\/span><\/div>\n              <div class=\"dropdown-divider\"><\/div>\n              <div class=\"dropdown-item\" onclick=\"openModal('image-modal')\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">image<\/span>Image<\/span><\/div>\n              <div class=\"dropdown-item\" onclick=\"openModal('table-modal')\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">table_chart<\/span>Table<\/span><\/div>\n              <div class=\"dropdown-item\" onclick=\"openModal('link-modal')\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">link<\/span>Link<\/span><span class=\"shortcut\">Ctrl+K<\/span><\/div>\n              <div class=\"dropdown-item\" onclick=\"openCommentComposer()\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">add_comment<\/span>Comment<\/span><span class=\"shortcut\">Ctrl+Alt+M<\/span><\/div>\n              <div class=\"dropdown-divider\"><\/div>\n              <div class=\"dropdown-item\" onclick=\"insertHorizontalLine()\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">horizontal_rule<\/span>Horizontal line<\/span><\/div>\n              <div class=\"dropdown-item\" onclick=\"addNewPage()\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">insert_page_break<\/span>New page<\/span><span class=\"shortcut\">Ctrl+Enter<\/span><\/div>\n              <div class=\"dropdown-item\" onclick=\"insertCurrentDate()\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">calendar_today<\/span>Date chip<\/span><\/div>\n            <\/div>\n          <\/div>\n\n          <!-- FORMAT -->\n          <div class=\"relative menu-container\">\n            <button class=\"menu-btn\" data-menu=\"menu-format\">Format<\/button>\n            <div id=\"menu-format\" class=\"dropdown-panel\">\n              <div class=\"dropdown-item\" onclick=\"execCmd('bold')\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">format_bold<\/span>Bold<\/span><span class=\"shortcut\">Ctrl+B<\/span><\/div>\n              <div class=\"dropdown-item\" onclick=\"execCmd('italic')\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">format_italic<\/span>Italic<\/span><span class=\"shortcut\">Ctrl+I<\/span><\/div>\n              <div class=\"dropdown-item\" onclick=\"execCmd('underline')\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">format_underlined<\/span>Underline<\/span><span class=\"shortcut\">Ctrl+U<\/span><\/div>\n              <div class=\"dropdown-item\" onclick=\"execCmd('strikeThrough')\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">strikethrough_s<\/span>Strikethrough<\/span><\/div>\n              <div class=\"dropdown-divider\"><\/div>\n              <div class=\"dropdown-item\" onclick=\"clearFormatting()\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">format_clear<\/span>Clear formatting<\/span><span class=\"shortcut\">Ctrl+\\<\/span><\/div>\n            <\/div>\n          <\/div>\n\n          <!-- CODE MENU -->\n          <div class=\"relative menu-container\">\n            <button class=\"menu-btn font-medium text-[#0b57d0]\" data-menu=\"menu-code\">Code<\/button>\n            <div id=\"menu-code\" class=\"dropdown-panel\">\n              <div class=\"dropdown-item\" onclick=\"insertCodeBlock()\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">code_blocks<\/span>Insert syntax-colored block<\/span><span class=\"shortcut\">Ctrl+Alt+C<\/span><\/div>\n              <div class=\"dropdown-item\" onclick=\"toggleInlineCode()\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">code<\/span>Format selection as inline code<\/span><span class=\"shortcut\">Ctrl+E<\/span><\/div>\n              <div class=\"dropdown-item\" onclick=\"convertSelectionToCodeBlock()\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">auto_fix_high<\/span>Convert selected text to code block<\/span><\/div>\n              <div class=\"dropdown-divider\"><\/div>\n              <div class=\"dropdown-item\" onclick=\"toggleAutoColor()\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">palette<\/span>Toggle live auto-coloring<\/span><\/div>\n              <div class=\"dropdown-item\" onclick=\"toggleIdeTheme()\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">dark_mode<\/span>Switch IDE Light / Dark theme<\/span><\/div>\n            <\/div>\n          <\/div>\n\n          <!-- TOOLS -->\n          <div class=\"relative menu-container hidden sm:block\">\n            <button class=\"menu-btn\" data-menu=\"menu-tools\">Tools<\/button>\n            <div id=\"menu-tools\" class=\"dropdown-panel\">\n              <div class=\"dropdown-item\" onclick=\"openModal('word-count-modal')\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">123<\/span>Word &amp; code line count<\/span><span class=\"shortcut\">Ctrl+Shift+C<\/span><\/div>\n              <div class=\"dropdown-item\" onclick=\"toggleVoiceTyping()\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">mic<\/span>Voice typing<\/span><\/div>\n            <\/div>\n          <\/div>\n\n          <!-- HELP -->\n          <div class=\"relative menu-container hidden sm:block\">\n            <button class=\"menu-btn\" data-menu=\"menu-help\">Help<\/button>\n            <div id=\"menu-help\" class=\"dropdown-panel\">\n              <div class=\"dropdown-item\" onclick=\"openModal('shortcuts-modal')\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">keyboard<\/span>Keyboard &amp; Markdown shortcuts<\/span><span class=\"shortcut\">Ctrl+/<\/span><\/div>\n              <div class=\"dropdown-item\" onclick=\"applyTemplate('coding')\"><span class=\"flex items-center gap-2.5\"><span class=\"material-symbols-outlined\">auto_awesome<\/span>Load sample Python &amp; JS notes<\/span><\/div>\n            <\/div>\n          <\/div>\n        <\/nav>\n      <\/div>\n    <\/div>\n\n    <!-- Right Header Controls -->\n    <div class=\"flex items-center gap-1.5 sm:gap-2 flex-shrink-0\">\n      <button onclick=\"openModal('history-modal')\" class=\"w-9 h-9 rounded-full hover:bg-gray-200/80 hidden md:flex items-center justify-center text-[#444746] transition\" title=\"Version history\">\n        <span class=\"material-symbols-outlined text-[22px]\">history<\/span>\n      <\/button>\n\n      <button onclick=\"toggleCommentsSidebar()\" class=\"w-9 h-9 rounded-full hover:bg-gray-200/80 flex items-center justify-center text-[#444746] transition relative\" title=\"Comments\">\n        <span class=\"material-symbols-outlined text-[22px]\">comment<\/span>\n        <span id=\"comment-badge\" class=\"hidden absolute top-1.5 right-1.5 w-2 h-2 bg-[#0b57d0] rounded-full\"><\/span>\n      <\/button>\n\n      <button onclick=\"downloadDoc('html')\" class=\"h-10 px-4 sm:px-5 rounded-full bg-[#c2e7ff] hover:bg-[#b3d7ef] hover:shadow-sm text-[#001d35] font-medium text-[14px] flex items-center gap-2 transition cursor-pointer\" title=\"Download an HTML copy\">\n        <span class=\"material-symbols-outlined text-[18px]\">download<\/span>\n        <span>Export<\/span>\n      <\/button>\n\n      <div id=\"owner-avatar\" class=\"w-8 h-8 rounded-full bg-[#0b57d0] text-white font-medium text-sm flex items-center justify-center ml-0.5\" title=\"Personal notebook\"><\/div>\n    <\/div>\n  <\/header>\n\n  <!-- ================= FORMATTING + CODE TOOLBAR PILL ================= -->\n  <div id=\"formatting-bar-wrapper\" class=\"px-3 pb-1.5 bg-[#f9fbfd] flex-shrink-0 z-20\">\n    <div class=\"toolbar-pill\">\n      <button class=\"tool-btn\" onclick=\"execCmd('undo')\" title=\"Undo (Ctrl+Z)\">\n        <span class=\"material-symbols-outlined\">undo<\/span>\n      <\/button>\n      <button class=\"tool-btn\" onclick=\"execCmd('redo')\" title=\"Redo (Ctrl+Y)\">\n        <span class=\"material-symbols-outlined\">redo<\/span>\n      <\/button>\n      <button class=\"tool-btn\" onclick=\"window.print()\" title=\"Print (Ctrl+P)\">\n        <span class=\"material-symbols-outlined\">print<\/span>\n      <\/button>\n\n      <div class=\"tool-sep\"><\/div>\n\n      <!-- Zoom -->\n      <select id=\"zoom-select\" onchange=\"setZoom(this.value)\" class=\"h-7 bg-transparent hover:bg-[#dfe5ef] text-[#444746] text-[13px] font-medium rounded px-1.5 outline-none cursor-pointer\" title=\"Zoom\">\n        <option value=\"0.75\">75%<\/option>\n        <option value=\"0.9\">90%<\/option>\n        <option value=\"1\" selected>100%<\/option>\n        <option value=\"1.15\">115%<\/option>\n        <option value=\"1.25\">125%<\/option>\n      <\/select>\n\n      <div class=\"tool-sep\"><\/div>\n\n      <!-- Paragraph Styles -->\n      <select id=\"style-select\" onchange=\"applyHeadingStyle(this.value)\" class=\"h-7 bg-transparent hover:bg-[#dfe5ef] text-[#444746] text-[13px] font-medium rounded px-2 outline-none cursor-pointer w-[112px]\" title=\"Styles\">\n        <option value=\"P\">Normal text<\/option>\n        <option value=\"TITLE\">Title<\/option>\n        <option value=\"SUBTITLE\">Subtitle<\/option>\n        <option value=\"H1\">Heading 1<\/option>\n        <option value=\"H2\">Heading 2<\/option>\n        <option value=\"H3\">Heading 3<\/option>\n      <\/select>\n\n      <div class=\"tool-sep\"><\/div>\n\n      <!-- Font Family -->\n      <select id=\"font-family-select\" onchange=\"applyFontFamily(this.value)\" class=\"h-7 bg-transparent hover:bg-[#dfe5ef] text-[#444746] text-[13px] font-medium rounded px-2 outline-none cursor-pointer w-[105px]\" title=\"Font\">\n        <option value=\"Arial, sans-serif\">Arial<\/option>\n        <option value=\"'Roboto', sans-serif\">Roboto<\/option>\n        <option value=\"'Inter', sans-serif\">Inter<\/option>\n        <option value=\"'Lora', serif\">Lora<\/option>\n        <option value=\"'Merriweather', serif\">Merriweather<\/option>\n        <option value=\"'JetBrains Mono', monospace\">JetBrains Mono<\/option>\n      <\/select>\n\n      <div class=\"tool-sep\"><\/div>\n\n      <!-- Font Size -->\n      <div class=\"flex items-center gap-0.5\">\n        <button class=\"tool-btn !min-w-[22px] !px-0\" onclick=\"stepFontSize(-1)\" title=\"Decrease font size\">\n          <span class=\"material-symbols-outlined text-[16px]\">remove<\/span>\n        <\/button>\n        <input id=\"font-size-input\" type=\"number\" min=\"6\" max=\"96\" value=\"11\" onchange=\"applyFontSizePt(this.value)\"\n          class=\"w-8 h-6 text-center text-[13px] text-[#1f1f1f] bg-transparent border border-[#747775]/50 hover:bg-white focus:bg-white focus:border-[#0b57d0] rounded outline-none\" title=\"Font size\" />\n        <button class=\"tool-btn !min-w-[22px] !px-0\" onclick=\"stepFontSize(1)\" title=\"Increase font size\">\n          <span class=\"material-symbols-outlined text-[16px]\">add<\/span>\n        <\/button>\n      <\/div>\n\n      <div class=\"tool-sep\"><\/div>\n\n      <!-- Text Formatting -->\n      <button id=\"btn-bold\" class=\"tool-btn\" onclick=\"execCmd('bold')\" title=\"Bold (Ctrl+B)\">\n        <span class=\"material-symbols-outlined\">format_bold<\/span>\n      <\/button>\n      <button id=\"btn-italic\" class=\"tool-btn\" onclick=\"execCmd('italic')\" title=\"Italic (Ctrl+I)\">\n        <span class=\"material-symbols-outlined\">format_italic<\/span>\n      <\/button>\n      <button id=\"btn-underline\" class=\"tool-btn\" onclick=\"execCmd('underline')\" title=\"Underline (Ctrl+U)\">\n        <span class=\"material-symbols-outlined\">format_underlined<\/span>\n      <\/button>\n\n      <!-- Text & Highlight Color -->\n      <label class=\"tool-btn cursor-pointer flex-col !py-0.5\" title=\"Text color\">\n        <span class=\"material-symbols-outlined text-[18px] leading-none\">format_color_text<\/span>\n        <span id=\"text-color-bar\" class=\"w-4 h-[3px] bg-black rounded-xs mt-[1px]\"><\/span>\n        <input type=\"color\" id=\"text-color-picker\" value=\"#000000\" onchange=\"applyTextColor(this.value)\" class=\"sr-only\" />\n      <\/label>\n\n      <label class=\"tool-btn cursor-pointer flex-col !py-0.5\" title=\"Highlight color\">\n        <span class=\"material-symbols-outlined text-[18px] leading-none\">ink_highlighter<\/span>\n        <span id=\"highlight-color-bar\" class=\"w-4 h-[3px] bg-yellow-300 rounded-xs mt-[1px]\"><\/span>\n        <input type=\"color\" id=\"highlight-color-picker\" value=\"#ffff00\" onchange=\"applyHighlightColor(this.value)\" class=\"sr-only\" />\n      <\/label>\n\n      <div class=\"tool-sep\"><\/div>\n\n      <!-- DEDICATED CODE CONTROLS -->\n      <div class=\"flex items-center bg-[#d3e3fd]/80 rounded-full px-1.5 py-0.5 gap-1 flex-shrink-0\">\n        <button onclick=\"insertCodeBlock()\" class=\"h-6 px-2.5 rounded-full bg-[#0b57d0] hover:bg-[#0842a0] text-white text-xs font-medium flex items-center gap-1 transition\" title=\"Insert Syntax-Colored Code Block (Ctrl+Alt+C)\">\n          <span class=\"material-symbols-outlined text-[15px]\">code_blocks<\/span>\n          <span>Code Block<\/span>\n        <\/button>\n\n        <select id=\"default-code-lang\" class=\"h-6 bg-transparent hover:bg-white/60 text-[#041e49] text-xs font-medium rounded-full px-1.5 outline-none cursor-pointer\" title=\"Default code language\">\n          <option value=\"auto\">Auto-Detect<\/option>\n          <option value=\"python\">Python<\/option>\n          <option value=\"javascript\">JavaScript<\/option>\n          <option value=\"html\">HTML<\/option>\n          <option value=\"css\">CSS<\/option>\n          <option value=\"sql\">SQL<\/option>\n          <option value=\"json\">JSON<\/option>\n          <option value=\"cpp\">C++<\/option>\n          <option value=\"bash\">Bash<\/option>\n        <\/select>\n\n        <button onclick=\"toggleInlineCode()\" class=\"tool-btn !h-6 !min-w-[26px] !px-1 text-[#041e49]\" title=\"Inline Code (Ctrl+E)\">\n          <span class=\"material-symbols-outlined text-[16px]\">code<\/span>\n        <\/button>\n\n        <button id=\"btn-auto-color\" onclick=\"toggleAutoColor()\" class=\"h-6 px-2 rounded-full bg-white text-[#0b57d0] text-[11px] font-medium flex items-center gap-1 shadow-2xs transition\" title=\"Toggle live syntax color coding\">\n          <span class=\"w-1.5 h-1.5 rounded-full bg-emerald-500\"><\/span>\n          <span id=\"auto-color-label\">Auto-Color: ON<\/span>\n        <\/button>\n\n        <button id=\"btn-ide-theme\" onclick=\"toggleIdeTheme()\" class=\"tool-btn !h-6 !min-w-[26px] !px-1 text-[#041e49]\" title=\"Switch IDE Light / Dark Theme\">\n          <span id=\"ide-theme-icon\" class=\"material-symbols-outlined text-[16px]\">dark_mode<\/span>\n        <\/button>\n      <\/div>\n\n      <div class=\"tool-sep\"><\/div>\n\n      <!-- Link, Comment, Image -->\n      <button class=\"tool-btn\" onclick=\"openModal('link-modal')\" title=\"Insert link (Ctrl+K)\">\n        <span class=\"material-symbols-outlined\">link<\/span>\n      <\/button>\n      <button class=\"tool-btn\" onclick=\"openCommentComposer()\" title=\"Add comment (Ctrl+Alt+M)\">\n        <span class=\"material-symbols-outlined\">add_comment<\/span>\n      <\/button>\n      <button class=\"tool-btn\" onclick=\"openModal('image-modal')\" title=\"Insert image\">\n        <span class=\"material-symbols-outlined\">image<\/span>\n      <\/button>\n\n      <div class=\"tool-sep\"><\/div>\n\n      <!-- Alignment & Lists -->\n      <button id=\"btn-align-left\" class=\"tool-btn active\" onclick=\"execCmd('justifyLeft')\" title=\"Left align\">\n        <span class=\"material-symbols-outlined\">format_align_left<\/span>\n      <\/button>\n      <button id=\"btn-align-center\" class=\"tool-btn\" onclick=\"execCmd('justifyCenter')\" title=\"Center align\">\n        <span class=\"material-symbols-outlined\">format_align_center<\/span>\n      <\/button>\n      <button id=\"btn-align-right\" class=\"tool-btn\" onclick=\"execCmd('justifyRight')\" title=\"Right align\">\n        <span class=\"material-symbols-outlined\">format_align_right<\/span>\n      <\/button>\n      <button class=\"tool-btn\" onclick=\"insertChecklist()\" title=\"Checklist\">\n        <span class=\"material-symbols-outlined\">checklist<\/span>\n      <\/button>\n      <button id=\"btn-ul\" class=\"tool-btn\" onclick=\"execCmd('insertUnorderedList')\" title=\"Bulleted list\">\n        <span class=\"material-symbols-outlined\">format_list_bulleted<\/span>\n      <\/button>\n      <button id=\"btn-ol\" class=\"tool-btn\" onclick=\"execCmd('insertOrderedList')\" title=\"Numbered list\">\n        <span class=\"material-symbols-outlined\">format_list_numbered<\/span>\n      <\/button>\n      <button class=\"tool-btn\" onclick=\"clearFormatting()\" title=\"Clear formatting (Ctrl+\\)\">\n        <span class=\"material-symbols-outlined\">format_clear<\/span>\n      <\/button>\n    <\/div>\n  <\/div>\n\n  <!-- ================= HORIZONTAL RULER ================= -->\n  <div id=\"ruler-container\">\n    <div id=\"ruler-track\">\n      <div id=\"ruler-left-shade\" class=\"ruler-margin-shade left-0\" style=\"width: 96px;\"><\/div>\n      <div id=\"ruler-right-shade\" class=\"ruler-margin-shade right-0\" style=\"width: 96px;\"><\/div>\n      <canvas id=\"ruler-canvas\" width=\"816\" height=\"24\" class=\"block w-full h-full\"><\/canvas>\n      <div id=\"handle-left-margin\" class=\"margin-handle\" style=\"left: 96px;\" title=\"Left margin (1.00 in)\">\n        <div class=\"bar\"><\/div>\n        <div class=\"triangle\"><\/div>\n      <\/div>\n      <div id=\"handle-right-margin\" class=\"margin-handle\" style=\"left: 720px;\" title=\"Right margin (1.00 in)\">\n        <div class=\"bar\"><\/div>\n        <div class=\"triangle\"><\/div>\n      <\/div>\n    <\/div>\n  <\/div>\n\n  <!-- ================= MAIN BODY AREA ================= -->\n  <div class=\"flex-1 flex overflow-hidden relative\">\n\n    <!-- LEFT COLLAPSIBLE OUTLINE SIDEBAR -->\n    <aside id=\"left-outline-sidebar\" class=\"w-60 bg-[#f9fbfd] border-r border-transparent hover:border-[#e0e3e7] flex-shrink-0 flex flex-col transition-all duration-200 z-10 hidden md:flex\">\n      <div class=\"p-3 flex items-center justify-between\">\n        <button onclick=\"toggleOutlineSidebar()\" class=\"w-8 h-8 rounded-full hover:bg-gray-200/80 flex items-center justify-center text-[#444746]\" title=\"Close outline\">\n          <span class=\"material-symbols-outlined\">arrow_back<\/span>\n        <\/button>\n        <span class=\"text-xs font-medium uppercase tracking-wider text-[#5f6368]\">Outline &amp; Code<\/span>\n      <\/div>\n\n      <div class=\"px-3 pb-2\">\n        <div class=\"flex items-center justify-between px-3 py-2 rounded-full bg-[#d3e3fd] text-[#041e49] text-sm font-medium\">\n          <span class=\"flex items-center gap-2 truncate\">\n            <span class=\"material-symbols-outlined text-[18px]\">article<\/span>\n            <span class=\"truncate\">Main Document<\/span>\n          <\/span>\n        <\/div>\n      <\/div>\n\n      <div class=\"px-4 pt-2 pb-1 flex items-center justify-between\">\n        <span class=\"text-xs font-medium text-[#444746]\">Headings &amp; Snippets<\/span>\n      <\/div>\n\n      <div id=\"outline-list\" class=\"flex-1 overflow-y-auto px-3 py-1 space-y-0.5 text-[13px] text-[#444746]\"><\/div>\n    <\/aside>\n\n    <!-- Re-open Outline Button -->\n    <button id=\"btn-open-outline\" onclick=\"toggleOutlineSidebar()\" class=\"fixed left-4 top-[148px] w-9 h-9 rounded-full bg-white shadow border border-gray-200 hover:bg-gray-100 flex items-center justify-center text-[#444746] z-20 md:hidden\" title=\"Show outline\">\n      <span class=\"material-symbols-outlined\">list<\/span>\n    <\/button>\n\n    <!-- CENTER US LETTER PAPER WORKSPACE -->\n    <main id=\"workspace-scroll\" onclick=\"handleWorkspaceClick(event)\">\n      <div id=\"paper-wrapper\"><\/div>\n\n      <!-- Add Page Action Bar -->\n      <div id=\"add-page-bar\" class=\"mt-5 flex items-center gap-2\">\n        <button onclick=\"addNewPage()\" class=\"px-4 py-1.5 rounded-full bg-white hover:bg-[#edf2fa] border border-[#dadce0] text-xs font-medium text-[#0b57d0] shadow-2xs flex items-center gap-1.5 transition\">\n          <span class=\"material-symbols-outlined text-[16px]\">add<\/span>\n          <span>Add page<\/span>\n        <\/button>\n      <\/div>\n    <\/main>\n\n    <!-- RIGHT COMMENTS SIDEBAR -->\n    <aside id=\"right-comments-sidebar\" class=\"w-80 bg-[#f9fbfd] border-l border-[#e0e3e7] flex-shrink-0 flex flex-col transition-all duration-200 z-10 hidden\">\n      <div class=\"p-3.5 border-b border-[#e0e3e7] flex items-center justify-between\">\n        <div class=\"flex items-center gap-2 font-medium text-[#1f1f1f] text-sm\">\n          <span class=\"material-symbols-outlined text-[#0b57d0]\">comment<\/span>\n          <span>Comments<\/span>\n        <\/div>\n        <div class=\"flex items-center gap-1\">\n          <button onclick=\"openCommentComposer()\" class=\"px-2.5 py-1 rounded-full bg-[#c2e7ff] hover:bg-[#b3d7ef] text-[#001d35] text-xs font-medium transition\">\n            + Comment\n          <\/button>\n          <button onclick=\"toggleCommentsSidebar()\" class=\"w-7 h-7 rounded-full hover:bg-gray-200 flex items-center justify-center text-[#444746]\">\n            <span class=\"material-symbols-outlined text-[18px]\">close<\/span>\n          <\/button>\n        <\/div>\n      <\/div>\n\n      <div id=\"comment-composer\" class=\"p-3 bg-white m-3 rounded-xl shadow-sm border border-[#c4c7c5] hidden\">\n        <div class=\"flex items-center gap-2 mb-2\">\n          <div class=\"w-6 h-6 rounded-full bg-[#0b57d0] text-white text-xs flex items-center justify-center font-medium\">A<\/div>\n          <span class=\"text-xs font-medium text-[#1f1f1f]\">You<\/span>\n        <\/div>\n        <div id=\"comment-quote-preview\" class=\"text-xs text-[#5f6368] border-l-2 border-[#f9ab00] pl-2 mb-2 italic truncate hidden\"><\/div>\n        <textarea id=\"comment-input\" rows=\"2\" placeholder=\"Comment or add others with @\" class=\"w-full text-sm border border-gray-300 rounded-lg p-2 outline-none focus:border-[#0b57d0] resize-none\"><\/textarea>\n        <div class=\"flex justify-end gap-2 mt-2\">\n          <button onclick=\"cancelCommentComposer()\" class=\"px-3 py-1 rounded-full text-xs font-medium text-[#0b57d0] hover:bg-blue-50\">Cancel<\/button>\n          <button onclick=\"submitComment()\" class=\"px-3.5 py-1 rounded-full text-xs font-medium bg-[#0b57d0] text-white hover:bg-[#0842a0]\">Comment<\/button>\n        <\/div>\n      <\/div>\n\n      <div id=\"comments-list\" class=\"flex-1 overflow-y-auto p-3 space-y-3\"><\/div>\n    <\/aside>\n  <\/div>\n\n  <!-- ================= FLOATING LIVE STATUS PILL ================= -->\n  <div id=\"status-pill\" onclick=\"openModal('word-count-modal')\" class=\"fixed bottom-4 left-4 bg-white/95 backdrop-blur border border-[#e0e3e7] shadow-sm hover:shadow rounded-full px-3.5 py-1.5 text-xs text-[#444746] flex items-center gap-3 cursor-pointer z-20 transition\" title=\"Click for word & code metrics\">\n    <span id=\"live-word-count\">0 words<\/span>\n    <span class=\"text-gray-300\">|<\/span>\n    <span id=\"live-code-lines\" class=\"font-mono text-[#0b57d0] font-medium\">0 lines of code<\/span>\n    <span class=\"text-gray-300 hidden sm:inline\">|<\/span>\n    <span id=\"live-page-est\" class=\"hidden sm:inline\">1 page<\/span>\n  <\/div>\n\n  <input type=\"file\" id=\"import-file-input\" accept=\".html,.htm,.txt,.md,.py,.js,.css,.sql,.json\" class=\"hidden\" onchange=\"handleFileImport(event)\" />\n\n  <div id=\"toast-notification\" class=\"fixed bottom-5 right-5 bg-[#323232] text-white text-sm px-4 py-2.5 rounded-lg shadow-lg opacity-0 pointer-events-none transition-opacity duration-200 z-50\">\n    Notification message\n  <\/div>\n\n  <!-- ================= MODALS ================= -->\n  <div id=\"modal-backdrop\" onclick=\"closeAllModals()\" class=\"fixed inset-0 bg-black/40 items-center justify-center z-50 p-4 hidden\">\n\n    <!-- SHARE MODAL -->\n    <div id=\"share-modal\" class=\"modal-card bg-white rounded-3xl shadow-xl max-w-md w-full p-6 hidden\" onclick=\"event.stopPropagation()\">\n      <div class=\"flex items-center justify-between mb-4\">\n        <h3 class=\"text-xl font-normal text-[#1f1f1f] truncate pr-2\">Share \"<span id=\"share-doc-title\">Untitled document<\/span>\"<\/h3>\n        <button onclick=\"closeAllModals()\" class=\"w-8 h-8 rounded-full hover:bg-gray-100 flex items-center justify-center text-[#444746]\">\n          <span class=\"material-symbols-outlined\">close<\/span>\n        <\/button>\n      <\/div>\n      <input type=\"text\" placeholder=\"Add people, groups, and calendar events\" class=\"w-full border border-[#747775] focus:border-[#0b57d0] focus:border-2 rounded-lg px-3.5 py-2.5 text-sm outline-none mb-4\" />\n      <div class=\"mb-6\">\n        <div class=\"text-xs font-medium text-[#444746] mb-2\">People with access<\/div>\n        <div class=\"flex items-center justify-between py-1.5\">\n          <div class=\"flex items-center gap-3\">\n            <div class=\"w-8 h-8 rounded-full bg-[#0b57d0] text-white flex items-center justify-center text-sm font-medium\">A<\/div>\n            <div>\n              <div class=\"text-sm font-medium text-[#1f1f1f]\">You<\/div>\n              <div class=\"text-xs text-[#5f6368]\">Saved in this browser<\/div>\n            <\/div>\n          <\/div>\n          <span class=\"text-xs text-[#5f6368]\">Owner<\/span>\n        <\/div>\n      <\/div>\n      <div class=\"flex items-center justify-between\">\n        <button onclick=\"copyShareLink()\" class=\"px-4 py-2 rounded-full border border-[#747775] hover:bg-blue-50 text-[#0b57d0] text-sm font-medium flex items-center gap-1.5 transition\">\n          <span class=\"material-symbols-outlined text-[18px]\">link<\/span> Copy link\n        <\/button>\n        <button onclick=\"closeAllModals()\" class=\"px-6 py-2 rounded-full bg-[#0b57d0] hover:bg-[#0842a0] text-white text-sm font-medium transition\">Done<\/button>\n      <\/div>\n    <\/div>\n\n    <!-- LINK MODAL -->\n    <div id=\"link-modal\" class=\"modal-card bg-white rounded-2xl shadow-xl max-w-sm w-full p-5 hidden\" onclick=\"event.stopPropagation()\">\n      <h3 class=\"text-lg font-medium text-[#1f1f1f] mb-3\">Insert link<\/h3>\n      <div class=\"space-y-3\">\n        <div>\n          <label class=\"block text-xs text-[#444746] mb-1\">Text<\/label>\n          <input id=\"link-text-input\" type=\"text\" placeholder=\"Link display text\" class=\"w-full border border-gray-300 focus:border-[#0b57d0] rounded-lg px-3 py-2 text-sm outline-none\" />\n        <\/div>\n        <div>\n          <label class=\"block text-xs text-[#444746] mb-1\">Link URL<\/label>\n          <input id=\"link-url-input\" type=\"url\" placeholder=\"https://example.com\" class=\"w-full border border-gray-300 focus:border-[#0b57d0] rounded-lg px-3 py-2 text-sm outline-none\" />\n        <\/div>\n      <\/div>\n      <div class=\"flex justify-end gap-2 mt-5\">\n        <button onclick=\"closeAllModals()\" class=\"px-4 py-1.5 rounded-full text-sm font-medium text-[#0b57d0] hover:bg-blue-50\">Cancel<\/button>\n        <button onclick=\"confirmInsertLink()\" class=\"px-5 py-1.5 rounded-full text-sm font-medium bg-[#0b57d0] text-white hover:bg-[#0842a0]\">Apply<\/button>\n      <\/div>\n    <\/div>\n\n    <!-- IMAGE MODAL -->\n    <div id=\"image-modal\" class=\"modal-card bg-white rounded-2xl shadow-xl max-w-md w-full p-5 hidden\" onclick=\"event.stopPropagation()\">\n      <h3 class=\"text-lg font-medium text-[#1f1f1f] mb-3\">Insert image<\/h3>\n      <div class=\"space-y-4\">\n        <div>\n          <label class=\"block text-xs font-medium text-[#444746] mb-1\">Upload from computer<\/label>\n          <input id=\"image-file-input\" type=\"file\" accept=\"image/*\" class=\"w-full text-sm text-gray-600 file:mr-3 file:py-1.5 file:px-4 file:rounded-full file:border-0 file:text-xs file:font-medium file:bg-[#c2e7ff] file:text-[#001d35] hover:file:bg-[#b3d7ef] cursor-pointer\" />\n        <\/div>\n        <div>\n          <label class=\"block text-xs font-medium text-[#444746] mb-1\">Or by URL<\/label>\n          <input id=\"image-url-input\" type=\"url\" placeholder=\"https://...\" class=\"w-full border border-gray-300 focus:border-[#0b57d0] rounded-lg px-3 py-2 text-sm outline-none\" />\n        <\/div>\n      <\/div>\n      <div class=\"flex justify-end gap-2 mt-5\">\n        <button onclick=\"closeAllModals()\" class=\"px-4 py-1.5 rounded-full text-sm font-medium text-[#0b57d0] hover:bg-blue-50\">Cancel<\/button>\n        <button onclick=\"confirmInsertImage()\" class=\"px-5 py-1.5 rounded-full text-sm font-medium bg-[#0b57d0] text-white hover:bg-[#0842a0]\">Insert<\/button>\n      <\/div>\n    <\/div>\n\n    <!-- TABLE MODAL -->\n    <div id=\"table-modal\" class=\"modal-card bg-white rounded-2xl shadow-xl max-w-xs w-full p-5 hidden\" onclick=\"event.stopPropagation()\">\n      <h3 class=\"text-lg font-medium text-[#1f1f1f] mb-3\">Insert table<\/h3>\n      <div class=\"grid grid-cols-2 gap-3\">\n        <div>\n          <label class=\"block text-xs text-[#444746] mb-1\">Rows<\/label>\n          <input id=\"table-rows-input\" type=\"number\" min=\"1\" max=\"20\" value=\"3\" class=\"w-full border border-gray-300 rounded-lg px-3 py-1.5 text-sm outline-none focus:border-[#0b57d0]\" />\n        <\/div>\n        <div>\n          <label class=\"block text-xs text-[#444746] mb-1\">Columns<\/label>\n          <input id=\"table-cols-input\" type=\"number\" min=\"1\" max=\"12\" value=\"3\" class=\"w-full border border-gray-300 rounded-lg px-3 py-1.5 text-sm outline-none focus:border-[#0b57d0]\" />\n        <\/div>\n      <\/div>\n      <div class=\"flex justify-end gap-2 mt-5\">\n        <button onclick=\"closeAllModals()\" class=\"px-4 py-1.5 rounded-full text-sm font-medium text-[#0b57d0] hover:bg-blue-50\">Cancel<\/button>\n        <button onclick=\"confirmInsertTable()\" class=\"px-5 py-1.5 rounded-full text-sm font-medium bg-[#0b57d0] text-white hover:bg-[#0842a0]\">Insert<\/button>\n      <\/div>\n    <\/div>\n\n    <!-- WORD & CODE COUNT MODAL -->\n    <div id=\"word-count-modal\" class=\"modal-card bg-white rounded-2xl shadow-xl max-w-xs w-full p-6 hidden\" onclick=\"event.stopPropagation()\">\n      <h3 class=\"text-xl font-normal text-[#1f1f1f] mb-4\">Document &amp; Code Metrics<\/h3>\n      <div class=\"divide-y divide-gray-200 text-sm\">\n        <div class=\"py-2.5 flex justify-between\"><span class=\"text-[#444746]\">Pages<\/span><span id=\"wc-pages\" class=\"font-medium\">1<\/span><\/div>\n        <div class=\"py-2.5 flex justify-between\"><span class=\"text-[#444746]\">Prose Words<\/span><span id=\"wc-words\" class=\"font-medium\">0<\/span><\/div>\n        <div class=\"py-2.5 flex justify-between\"><span class=\"text-[#444746]\">Characters<\/span><span id=\"wc-chars\" class=\"font-medium\">0<\/span><\/div>\n        <div class=\"py-2.5 flex justify-between\"><span class=\"text-[#444746]\">Code Blocks<\/span><span id=\"wc-code-blocks\" class=\"font-medium text-[#0b57d0]\">0<\/span><\/div>\n        <div class=\"py-2.5 flex justify-between\"><span class=\"text-[#444746]\">Total Lines of Code<\/span><span id=\"wc-code-lines\" class=\"font-medium text-[#0b57d0]\">0<\/span><\/div>\n      <\/div>\n      <div class=\"flex justify-end mt-5\">\n        <button onclick=\"closeAllModals()\" class=\"px-5 py-1.5 rounded-full text-sm font-medium bg-[#0b57d0] text-white hover:bg-[#0842a0]\">OK<\/button>\n      <\/div>\n    <\/div>\n\n    <!-- FIND & REPLACE MODAL -->\n    <div id=\"find-replace-modal\" class=\"modal-card bg-white rounded-2xl shadow-xl max-w-sm w-full p-5 hidden\" onclick=\"event.stopPropagation()\">\n      <div class=\"flex items-center justify-between mb-3\">\n        <h3 class=\"text-lg font-medium text-[#1f1f1f]\">Find and replace<\/h3>\n        <button onclick=\"closeAllModals()\" class=\"w-7 h-7 rounded-full hover:bg-gray-100 flex items-center justify-center\"><span class=\"material-symbols-outlined text-[18px]\">close<\/span><\/button>\n      <\/div>\n      <div class=\"space-y-3\">\n        <div>\n          <label class=\"block text-xs text-[#444746] mb-1\">Find<\/label>\n          <input id=\"find-input\" type=\"text\" placeholder=\"Search text...\" class=\"w-full border border-gray-300 rounded-lg px-3 py-1.5 text-sm outline-none focus:border-[#0b57d0]\" />\n        <\/div>\n        <div>\n          <label class=\"block text-xs text-[#444746] mb-1\">Replace with<\/label>\n          <input id=\"replace-input\" type=\"text\" placeholder=\"Replacement text...\" class=\"w-full border border-gray-300 rounded-lg px-3 py-1.5 text-sm outline-none focus:border-[#0b57d0]\" />\n        <\/div>\n      <\/div>\n      <div class=\"flex justify-end gap-2 mt-5\">\n        <button onclick=\"executeFindReplace(false)\" class=\"px-3.5 py-1.5 rounded-full text-xs font-medium border border-gray-300 hover:bg-gray-100 text-[#1f1f1f]\">Replace<\/button>\n        <button onclick=\"executeFindReplace(true)\" class=\"px-4 py-1.5 rounded-full text-xs font-medium bg-[#0b57d0] text-white hover:bg-[#0842a0]\">Replace all<\/button>\n      <\/div>\n    <\/div>\n\n    <!-- PAGE SETUP MODAL -->\n    <div id=\"page-setup-modal\" class=\"modal-card bg-white rounded-2xl shadow-xl max-w-sm w-full p-6 hidden\" onclick=\"event.stopPropagation()\">\n      <h3 class=\"text-xl font-normal text-[#1f1f1f] mb-4\">Page setup<\/h3>\n      <div class=\"space-y-4 text-sm\">\n        <div>\n          <label class=\"block text-xs font-medium text-[#444746] mb-1\">Page color<\/label>\n          <input id=\"page-color-input\" type=\"color\" value=\"#ffffff\" class=\"w-full h-9 rounded cursor-pointer border border-gray-300\" />\n        <\/div>\n        <div class=\"grid grid-cols-2 gap-3\">\n          <div>\n            <label class=\"block text-xs text-[#444746] mb-1\">Top / Bottom margin (in)<\/label>\n            <input id=\"margin-tb-input\" type=\"number\" step=\"0.25\" min=\"0.25\" max=\"2.5\" value=\"1\" class=\"w-full border border-gray-300 rounded-lg px-2.5 py-1.5 outline-none\" />\n          <\/div>\n          <div>\n            <label class=\"block text-xs text-[#444746] mb-1\">Left / Right margin (in)<\/label>\n            <input id=\"margin-lr-input\" type=\"number\" step=\"0.25\" min=\"0.25\" max=\"2.5\" value=\"1\" class=\"w-full border border-gray-300 rounded-lg px-2.5 py-1.5 outline-none\" />\n          <\/div>\n        <\/div>\n      <\/div>\n      <div class=\"flex justify-end gap-2 mt-6\">\n        <button onclick=\"closeAllModals()\" class=\"px-4 py-1.5 rounded-full text-sm font-medium text-[#0b57d0] hover:bg-blue-50\">Cancel<\/button>\n        <button onclick=\"applyPageSetup()\" class=\"px-5 py-1.5 rounded-full text-sm font-medium bg-[#0b57d0] text-white hover:bg-[#0842a0]\">OK<\/button>\n      <\/div>\n    <\/div>\n\n    <!-- TEMPLATES GALLERY MODAL -->\n    <div id=\"templates-modal\" class=\"modal-card bg-white rounded-2xl shadow-xl max-w-lg w-full p-6 hidden\" onclick=\"event.stopPropagation()\">\n      <div class=\"flex items-center justify-between mb-4\">\n        <h3 class=\"text-lg font-medium text-[#1f1f1f]\">Start from a template<\/h3>\n        <button onclick=\"closeAllModals()\" class=\"w-8 h-8 rounded-full hover:bg-gray-100 flex items-center justify-center\"><span class=\"material-symbols-outlined\">close<\/span><\/button>\n      <\/div>\n      <div class=\"grid grid-cols-1 sm:grid-cols-3 gap-3\">\n        <button onclick=\"applyTemplate('blank')\" class=\"border border-gray-200 hover:border-[#0b57d0] rounded-xl p-3 text-left transition\">\n          <div class=\"h-20 bg-gray-50 rounded mb-2 flex items-center justify-center text-[#0b57d0]\"><span class=\"material-symbols-outlined text-3xl\">add<\/span><\/div>\n          <div class=\"text-sm font-medium\">Blank<\/div>\n          <div class=\"text-xs text-gray-500\">Empty US Letter<\/div>\n        <\/button>\n        <button onclick=\"applyTemplate('coding')\" class=\"border border-gray-200 hover:border-[#0b57d0] rounded-xl p-3 text-left transition\">\n          <div class=\"h-20 bg-blue-50 rounded mb-2 flex items-center justify-center text-[#0b57d0]\"><span class=\"material-symbols-outlined text-3xl\">code_blocks<\/span><\/div>\n          <div class=\"text-sm font-medium\">Python &amp; JS Notes<\/div>\n          <div class=\"text-xs text-gray-500\">Live syntax blocks<\/div>\n        <\/button>\n        <button onclick=\"applyTemplate('rfc')\" class=\"border border-gray-200 hover:border-[#0b57d0] rounded-xl p-3 text-left transition\">\n          <div class=\"h-20 bg-emerald-50 rounded mb-2 flex items-center justify-center text-emerald-700\"><span class=\"material-symbols-outlined text-3xl\">architecture<\/span><\/div>\n          <div class=\"text-sm font-medium\">Engineering RFC<\/div>\n          <div class=\"text-xs text-gray-500\">API specs &amp; SQL<\/div>\n        <\/button>\n      <\/div>\n    <\/div>\n\n    <!-- SHORTCUTS MODAL -->\n    <div id=\"shortcuts-modal\" class=\"modal-card bg-white rounded-2xl shadow-xl max-w-md w-full p-6 hidden\" onclick=\"event.stopPropagation()\">\n      <div class=\"flex items-center justify-between mb-3\">\n        <h3 class=\"text-lg font-medium text-[#1f1f1f]\">Keyboard &amp; Markdown Shortcuts<\/h3>\n        <button onclick=\"closeAllModals()\" class=\"w-8 h-8 rounded-full hover:bg-gray-100 flex items-center justify-center\"><span class=\"material-symbols-outlined\">close<\/span><\/button>\n      <\/div>\n      <div class=\"divide-y divide-gray-100 text-sm max-h-72 overflow-y-auto\">\n        <div class=\"py-2 flex justify-between\"><span>Insert Code Block<\/span><kbd class=\"bg-gray-100 px-2 py-0.5 rounded text-xs\">Ctrl + Alt + C<\/kbd><\/div>\n        <div class=\"py-2 flex justify-between\"><span>Inline Code<\/span><kbd class=\"bg-gray-100 px-2 py-0.5 rounded text-xs\">Ctrl + E<\/kbd><\/div>\n        <div class=\"py-2 flex justify-between\"><span>Markdown Fenced Block<\/span><kbd class=\"bg-gray-100 px-2 py-0.5 rounded text-xs\">```py + Space/Enter<\/kbd><\/div>\n        <div class=\"py-2 flex justify-between\"><span>Markdown Inline Code<\/span><kbd class=\"bg-gray-100 px-2 py-0.5 rounded text-xs\">`code`<\/kbd><\/div>\n        <div class=\"py-2 flex justify-between\"><span>Indent inside Code Block<\/span><kbd class=\"bg-gray-100 px-2 py-0.5 rounded text-xs\">Tab<\/kbd><\/div>\n        <div class=\"py-2 flex justify-between\"><span>Find and Replace<\/span><kbd class=\"bg-gray-100 px-2 py-0.5 rounded text-xs\">Ctrl + H<\/kbd><\/div>\n        <div class=\"py-2 flex justify-between\"><span>Word &amp; Code Count<\/span><kbd class=\"bg-gray-100 px-2 py-0.5 rounded text-xs\">Ctrl + Shift + C<\/kbd><\/div>\n      <\/div>\n    <\/div>\n\n    <!-- VERSION HISTORY MODAL -->\n    <div id=\"history-modal\" class=\"modal-card bg-white rounded-2xl shadow-xl max-w-sm w-full p-5 hidden\" onclick=\"event.stopPropagation()\">\n      <div class=\"flex items-center justify-between mb-3\">\n        <h3 class=\"text-lg font-medium text-[#1f1f1f]\">Version history<\/h3>\n        <button onclick=\"closeAllModals()\" class=\"w-7 h-7 rounded-full hover:bg-gray-100 flex items-center justify-center\"><span class=\"material-symbols-outlined text-[18px]\">close<\/span><\/button>\n      <\/div>\n      <div id=\"history-list\" class=\"space-y-2 text-sm max-h-64 overflow-y-auto\"><\/div>\n    <\/div>\n\n  <\/div>\n\n  <!-- ================= APPLICATION JAVASCRIPT ================= -->\n  <script>\n    /* ==========================================================================\n       1. STATE & CONSTANTS\n       ========================================================================== */\n    const OWNER_ID = (window.frameElement?.dataset.owner || new URLSearchParams(location.search).get('owner') || 'personal').replace(/[^a-z0-9_-]/gi, '').toLowerCase();\n    const OWNER_NAME = OWNER_ID === 'nikhil' ? 'Nikhil' : OWNER_ID === 'akshat' ? 'Akshat' : 'Personal';\n    const STORAGE_KEY = `python-docs-workspace-v1-${OWNER_ID}`;\n\n    let appState = {\n      title: `${OWNER_NAME}'s Python Notes`,\n      starred: false,\n      headerText: '',\n      footerText: '',\n      pagesHTML: [],\n      marginLeftPx: 96,\n      marginRightPx: 96,\n      marginTopBottomPx: 24,\n      pageColor: '#ffffff',\n      autoColor: true,\n      ideDark: false,\n      comments: [],\n      snapshots: []\n    };\n\n    let currentSelectionRange = null;\n    let activeBodyElement = null;\n    let saveTimer = null;\n\n    const paperWrapper = document.getElementById('paper-wrapper');\n    const titleInput = document.getElementById('doc-title-input');\n\n    /* ==========================================================================\n       2. INITIALIZATION\n       ========================================================================== */\n    window.addEventListener('DOMContentLoaded', () => {\n      drawRulerTicks();\n      setupRulerDragHandles();\n      setupMenuBarDropdowns();\n      setupKeyboardShortcuts();\n      loadFromStorage();\n    });\n\n    /* ==========================================================================\n       3. MULTI-PAGE RENDERING & LOCAL STORAGE\n       ========================================================================== */\n    function loadFromStorage() {\n      try {\n        const raw = localStorage.getItem(STORAGE_KEY);\n        if (raw) {\n          const parsed = JSON.parse(raw);\n          appState = { ...appState, ...parsed };\n        } else {\n          appState.pagesHTML = ['<p><br><\/p>'];\n        }\n      } catch (err) {\n        console.error('Storage load error:', err);\n        appState.pagesHTML = ['<p><br><\/p>'];\n      }\n\n      if (!Array.isArray(appState.pagesHTML) || appState.pagesHTML.length === 0) {\n        appState.pagesHTML = ['<p><br><\/p>'];\n      }\n\n      titleInput.value = appState.title || `${OWNER_NAME}'s Python Notes`;\n      document.getElementById('owner-avatar').textContent = OWNER_NAME.slice(0, 1).toUpperCase();\n      document.title = `${appState.title} - Python Notes`;\n      updateStarUI();\n      applyIdeThemeUI();\n      applyAutoColorUI();\n      renderAllPages();\n      applyMarginsToCanvas();\n      updateWordCounts();\n      rebuildOutline();\n      renderComments();\n    }\n\n    function renderAllPages() {\n      paperWrapper.innerHTML = '';\n      appState.pagesHTML.forEach((html, pageIdx) => {\n        const sheet = createPageSheetElement(html, pageIdx, appState.pagesHTML.length);\n        paperWrapper.appendChild(sheet);\n      });\n      hydrateAllCodeCards();\n      activeBodyElement = paperWrapper.querySelector('.doc-body');\n    }\n\n    function createPageSheetElement(bodyHTML, index, totalPages) {\n      const sheet = document.createElement('div');\n      sheet.className = 'doc-sheet';\n      sheet.style.backgroundColor = appState.pageColor || '#ffffff';\n\n      const header = document.createElement('div');\n      header.className = 'doc-header-zone';\n      header.contentEditable = 'true';\n      header.textContent = appState.headerText || '';\n      header.addEventListener('input', () => {\n        appState.headerText = header.textContent;\n        document.querySelectorAll('.doc-header-zone').forEach((h) => {\n          if (h !== header) h.textContent = appState.headerText;\n        });\n        scheduleAutoSave();\n      });\n\n      const body = document.createElement('div');\n      body.className = 'doc-body';\n      body.contentEditable = 'true';\n      body.spellcheck = false;\n      body.innerHTML = bodyHTML;\n\n      body.addEventListener('focus', () => {\n        activeBodyElement = body;\n      });\n      body.addEventListener('mouseup', () => {\n        activeBodyElement = body;\n        saveSelection();\n        updateToolbarActiveStates();\n      });\n      body.addEventListener('keyup', (e) => {\n        activeBodyElement = body;\n        saveSelection();\n        handleMarkdownShortcuts(e, body);\n        updateToolbarActiveStates();\n        updateWordCounts();\n        rebuildOutline();\n        scheduleAutoSave();\n      });\n      body.addEventListener('input', () => {\n        updateWordCounts();\n        rebuildOutline();\n        scheduleAutoSave();\n      });\n\n      const footer = document.createElement('div');\n      footer.className = 'doc-footer-zone';\n      const footerLeft = document.createElement('span');\n      footerLeft.contentEditable = 'true';\n      footerLeft.className = 'outline-none';\n      footerLeft.textContent = appState.footerText || '';\n      footerLeft.addEventListener('input', () => {\n        appState.footerText = footerLeft.textContent;\n        scheduleAutoSave();\n      });\n\n      const footerRight = document.createElement('span');\n      footerRight.className = 'text-xs text-[#5f6368] select-none';\n      footerRight.textContent = `Page ${index + 1} of ${totalPages}`;\n\n      footer.appendChild(footerLeft);\n      footer.appendChild(footerRight);\n\n      sheet.appendChild(header);\n      sheet.appendChild(body);\n      sheet.appendChild(footer);\n      return sheet;\n    }\n\n    function addNewPage() {\n      closeAllDropdowns();\n      syncPagesFromDOM();\n      appState.pagesHTML.push('<p><br><\/p>');\n      renderAllPages();\n      applyMarginsToCanvas();\n      updateWordCounts();\n      saveToStorage();\n      const bodies = paperWrapper.querySelectorAll('.doc-body');\n      const lastBody = bodies[bodies.length - 1];\n      if (lastBody) {\n        lastBody.focus();\n        lastBody.scrollIntoView({ behavior: 'smooth', block: 'center' });\n      }\n      showToast(`Added Page ${appState.pagesHTML.length}`);\n    }\n\n    function syncPagesFromDOM() {\n      const bodies = paperWrapper.querySelectorAll('.doc-body');\n      if (bodies.length > 0) {\n        appState.pagesHTML = Array.from(bodies).map((body) => {\n          // Ensure textarea values are synced to attributes before serializing\n          body.querySelectorAll('.code-card').forEach((card) => {\n            const ta = card.querySelector('.code-textarea-layer');\n            if (ta) {\n              card.dataset.code = ta.value;\n            }\n          });\n          return body.innerHTML;\n        });\n      }\n    }\n\n    function scheduleAutoSave() {\n      setCloudStatus('saving');\n      clearTimeout(saveTimer);\n      saveTimer = setTimeout(() => {\n        saveToStorage();\n      }, 650);\n    }\n\n    function saveToStorage() {\n      try {\n        syncPagesFromDOM();\n        appState.title = titleInput.value.trim() || 'Untitled document';\n        document.title = `${appState.title} - Python Notes`;\n\n        const nowStr = new Date().toLocaleTimeString([], { hour: '2-digit', minute: '2-digit' });\n        if (appState.snapshots.length === 0 || appState.snapshots[0].time !== nowStr) {\n          appState.snapshots.unshift({\n            time: nowStr,\n            pagesHTML: [...appState.pagesHTML]\n          });\n          if (appState.snapshots.length > 10) appState.snapshots.pop();\n        }\n\n        localStorage.setItem(STORAGE_KEY, JSON.stringify(appState));\n        setCloudStatus('saved');\n      } catch (e) {\n        console.error('Save error:', e);\n        setCloudStatus('error');\n      }\n    }\n\n    function triggerManualSave() {\n      saveToStorage();\n      showToast('Saved on this device');\n    }\n\n    function setCloudStatus(status) {\n      const icon = document.getElementById('cloud-icon');\n      const text = document.getElementById('cloud-text');\n      if (status === 'saving') {\n        icon.textContent = 'sync';\n        icon.classList.add('animate-spin');\n        text.textContent = 'Saving...';\n      } else if (status === 'saved') {\n        icon.textContent = 'check_circle';\n        icon.classList.remove('animate-spin');\n        text.textContent = 'Saved on this device';\n      } else {\n        icon.textContent = 'cloud_off';\n        icon.classList.remove('animate-spin');\n        text.textContent = 'Could not save';\n      }\n    }\n\n    /* ==========================================================================\n       4. LIVE SYNTAX COLOR-CODING ENGINE & INTERACTIVE CODE BLOCKS\n       ========================================================================== */\n    function escapeHTML(str) {\n      return str\n        .replace(/&/g, '&amp;')\n        .replace(/<\/g, '&lt;')\n        .replace(/>/g, '&gt;')\n        .replace(/\"/g, '&quot;')\n        .replace(/'/g, '&#39;');\n    }\n\n    function detectLanguage(code) {\n      const trimmed = code.trim();\n      if (!trimmed) return 'python';\n      if (/^\\s*<!DOCTYPE html>|^\\s*<[a-zA-Z][^>]*>/.test(trimmed)) return 'html';\n      if (/^\\s*[\\{\\[]\\s*\"[^\"]+\"\\s*:/.test(trimmed)) return 'json';\n      if (/\\b(SELECT|INSERT\\s+INTO|UPDATE|DELETE\\s+FROM|CREATE\\s+TABLE|WHERE|GROUP\\s+BY)\\b/i.test(trimmed)) return 'sql';\n      if (/\\b(def\\s+\\w+\\s*\\(|elif\\b|print\\s*\\(|import\\s+\\w+|from\\s+\\w+\\s+import|#\\s*\\w+)/.test(trimmed) && !/;\\s*$/m.test(trimmed)) return 'python';\n      if (/#include\\s*<|std::|cout\\s*<<|int\\s+main\\s*\\(/.test(trimmed)) return 'cpp';\n      if (/^#!\\/bin\\/(bash|sh)|\\b(echo|sudo|apt-get|npm|pip|git)\\b/.test(trimmed)) return 'bash';\n      if (/^[.#]?[a-zA-Z0-9_-]+\\s*\\{[\\s\\S]*:[\\s\\S]*;\\s*\\}/m.test(trimmed) && !/\\b(function|const|let|var)\\b/.test(trimmed)) return 'css';\n      return 'javascript';\n    }\n\n    function highlightSyntax(code, lang) {\n      if (!appState.autoColor) {\n        return escapeHTML(code);\n      }\n\n      const effectiveLang = lang === 'auto' ? detectLanguage(code) : lang;\n      const escaped = escapeHTML(code);\n\n      if (effectiveLang === 'html') {\n        return escaped\n          .replace(/(&lt;!--[\\s\\S]*?--&gt;)/g, '<span class=\"tok-com\">$1<\/span>')\n          .replace(/(&lt;\\/?)([a-zA-Z0-9-]+)([\\s\\S]*?)(\\/?&gt;)/g, (m, open, tag, attrs, close) => {\n            const coloredAttrs = attrs.replace(/([a-zA-Z-]+)(=)(\"[^\"]*\"|'[^']*')/g, '<span class=\"tok-attr\">$1<\/span>$2<span class=\"tok-str\">$3<\/span>');\n            return `${open}<span class=\"tok-tag\">${tag}<\/span>${coloredAttrs}${close}`;\n          });\n      }\n\n      if (effectiveLang === 'json') {\n        return escaped\n          .replace(/(\"(\\\\u[a-zA-Z0-9]{4}|\\\\[^u]|[^\\\\\"])*\")(\\s*:)?/g, (match, p1, p2, colon) => {\n            if (colon) return `<span class=\"tok-attr\">${p1}<\/span>${colon}`;\n            return `<span class=\"tok-str\">${p1}<\/span>`;\n          })\n          .replace(/\\b(true|false|null)\\b/g, '<span class=\"tok-kw\">$1<\/span>')\n          .replace(/\\b(-?\\d+(?:\\.\\d+)?)\\b/g, '<span class=\"tok-num\">$1<\/span>');\n      }\n\n      if (effectiveLang === 'css') {\n        return escaped\n          .replace(/(\\/\\*[\\s\\S]*?\\*\\/)/g, '<span class=\"tok-com\">$1<\/span>')\n          .replace(/([a-zA-Z-]+)(\\s*:)/g, '<span class=\"tok-attr\">$1<\/span>$2')\n          .replace(/(#[0-9a-fA-F]{3,8}|\\b\\d+(?:px|rem|em|%|vh|vw|s)?\\b)/g, '<span class=\"tok-num\">$1<\/span>');\n      }\n\n      // Token-based single-pass regex for Python, JS, SQL, C++, Bash\n      const keywordsByLang = {\n        python: '\\\\b(def|return|if|elif|else|for|while|in|is|not|and|or|import|from|as|class|try|except|finally|with|lambda|pass|break|continue|True|False|None|yield|async|await)\\\\b',\n        javascript: '\\\\b(const|let|var|function|return|if|else|for|while|switch|case|break|continue|class|extends|new|try|catch|finally|throw|async|await|import|export|from|default|typeof|instanceof|true|false|null|undefined)\\\\b',\n        sql: '\\\\b(SELECT|FROM|WHERE|INSERT|INTO|VALUES|UPDATE|SET|DELETE|CREATE|TABLE|ALTER|DROP|JOIN|LEFT|RIGHT|INNER|ON|GROUP|BY|ORDER|ASC|DESC|LIMIT|AND|OR|NOT|NULL|PRIMARY|KEY)\\\\b',\n        cpp: '\\\\b(int|float|double|char|bool|void|auto|const|if|else|for|while|return|class|struct|public|private|namespace|using|template|typename|true|false|nullptr|include)\\\\b',\n        bash: '\\\\b(if|then|else|fi|for|do|done|while|case|esac|function|export|echo|exit|return|sudo|npm|npx|python|python3|git|cd|ls|mkdir|rm)\\\\b'\n      };\n\n      const kwPattern = keywordsByLang[effectiveLang] || keywordsByLang.javascript;\n      const flags = effectiveLang === 'sql' ? 'gi' : 'g';\n\n      const masterRegex = new RegExp(\n        [\n          '(#[^\\\\n]*|\\\\/\\\\/[^\\\\n]*|\\\\/\\\\*[\\\\s\\\\S]*?\\\\*\\\\/)', // 1: comments\n          '(\"(?:\\\\\\\\.|[^\"\\\\\\\\])*\"|\\'(?:\\\\\\\\.|[^\\'\\\\\\\\])*\\'|`(?:\\\\\\\\.|[^`\\\\\\\\])*`)', // 2: strings\n          kwPattern, // 3: keywords\n          '\\\\b(\\\\d+(?:\\\\.\\\\d+)?)\\\\b', // 4: numbers\n          '\\\\b([a-zA-Z_][a-zA-Z0-9_]*)(?=\\\\s*\\\\()' // 5: function calls\n        ].join('|'),\n        flags\n      );\n\n      return escaped.replace(masterRegex, (match, comment, str, kw, num, fn) => {\n        if (comment) return `<span class=\"tok-com\">${comment}<\/span>`;\n        if (str) return `<span class=\"tok-str\">${str}<\/span>`;\n        if (kw) return `<span class=\"tok-kw\">${kw}<\/span>`;\n        if (num) return `<span class=\"tok-num\">${num}<\/span>`;\n        if (fn) return `<span class=\"tok-fn\">${fn}<\/span>`;\n        return match;\n      });\n    }\n\n    function createCodeCardHTML(code = '', lang = 'auto') {\n      const id = 'code_' + Math.random().toString(36).slice(2, 9);\n      const safeAttr = code.replace(/\"/g, '&quot;');\n      return `<div class=\"code-card\" id=\"${id}\" contenteditable=\"false\" data-lang=\"${lang}\" data-code=\"${safeAttr}\"><\/div><p><br><\/p>`;\n    }\n\n    function hydrateAllCodeCards() {\n      document.querySelectorAll('.code-card').forEach((card) => {\n        hydrateSingleCodeCard(card);\n      });\n    }\n\n    function hydrateSingleCodeCard(card) {\n      const initialCode = card.dataset.code || '';\n      const initialLang = card.dataset.lang || 'auto';\n      const resolvedLang = initialLang === 'auto' ? detectLanguage(initialCode) : initialLang;\n\n      card.innerHTML = `\n        <div class=\"code-card-header\">\n          <div class=\"flex items-center gap-2\">\n            <span class=\"material-symbols-outlined text-[16px] text-[#0b57d0]\">terminal<\/span>\n            <select class=\"code-lang-select bg-transparent font-medium text-xs outline-none cursor-pointer rounded px-1 py-0.5 hover:bg-black/5\">\n              <option value=\"auto\" ${initialLang === 'auto' ? 'selected' : ''}>Auto (${resolvedLang.toUpperCase()})<\/option>\n              <option value=\"python\" ${initialLang === 'python' ? 'selected' : ''}>Python<\/option>\n              <option value=\"javascript\" ${initialLang === 'javascript' ? 'selected' : ''}>JavaScript<\/option>\n              <option value=\"html\" ${initialLang === 'html' ? 'selected' : ''}>HTML<\/option>\n              <option value=\"css\" ${initialLang === 'css' ? 'selected' : ''}>CSS<\/option>\n              <option value=\"sql\" ${initialLang === 'sql' ? 'selected' : ''}>SQL<\/option>\n              <option value=\"json\" ${initialLang === 'json' ? 'selected' : ''}>JSON<\/option>\n              <option value=\"cpp\" ${initialLang === 'cpp' ? 'selected' : ''}>C++<\/option>\n              <option value=\"bash\" ${initialLang === 'bash' ? 'selected' : ''}>Bash<\/option>\n            <\/select>\n            <span class=\"code-line-badge text-[11px] opacity-70\">1 line<\/span>\n          <\/div>\n          <div class=\"code-card-actions flex items-center gap-1\">\n            <button type=\"button\" class=\"btn-format-code px-2 py-0.5 rounded hover:bg-black/10 text-[11px] font-medium flex items-center gap-1\" title=\"Auto-indent & format\">\n              <span class=\"material-symbols-outlined text-[14px]\">auto_fix_high<\/span> Format\n            <\/button>\n            <button type=\"button\" class=\"btn-copy-code px-2 py-0.5 rounded hover:bg-black/10 text-[11px] font-medium flex items-center gap-1\" title=\"Copy code\">\n              <span class=\"material-symbols-outlined text-[14px]\">content_copy<\/span> Copy\n            <\/button>\n            <button type=\"button\" class=\"btn-delete-code p-1 rounded hover:bg-red-500/15 text-red-600 flex items-center\" title=\"Remove code block\">\n              <span class=\"material-symbols-outlined text-[14px]\">delete<\/span>\n            <\/button>\n          <\/div>\n        <\/div>\n        <div class=\"code-card-body\">\n          <div class=\"code-gutter\">1<\/div>\n          <div class=\"code-editor-stack\">\n            <pre class=\"code-highlight-layer\" aria-hidden=\"true\"><\/pre>\n            <textarea class=\"code-textarea-layer\" spellcheck=\"false\" placeholder=\"Type or paste code here for automatic syntax color-coding...\"><\/textarea>\n          <\/div>\n        <\/div>\n      `;\n\n      const textarea = card.querySelector('.code-textarea-layer');\n      const highlightLayer = card.querySelector('.code-highlight-layer');\n      const gutter = card.querySelector('.code-gutter');\n      const langSelect = card.querySelector('.code-lang-select');\n      const lineBadge = card.querySelector('.code-line-badge');\n\n      textarea.value = initialCode;\n\n      const syncCodeVisuals = () => {\n        const val = textarea.value;\n        card.dataset.code = val;\n        const selectedLang = langSelect.value;\n        card.dataset.lang = selectedLang;\n\n        if (selectedLang === 'auto') {\n          const detected = detectLanguage(val);\n          langSelect.options[0].textContent = `Auto (${detected.toUpperCase()})`;\n        }\n\n        const lines = val.split('\\n');\n        const lineCount = Math.max(1, lines.length);\n        gutter.innerHTML = Array.from({ length: lineCount }, (_, i) => i + 1).join('<br>');\n        lineBadge.textContent = `${lineCount} ${lineCount === 1 ? 'line' : 'lines'}`;\n\n        // Trailing newline ensures pre height matches textarea height\n        highlightLayer.innerHTML = highlightSyntax(val, selectedLang) + (val.endsWith('\\n') ? ' ' : '');\n        textarea.style.height = highlightLayer.offsetHeight + 'px';\n\n        updateWordCounts();\n        rebuildOutline();\n      };\n\n      textarea.addEventListener('input', () => {\n        syncCodeVisuals();\n        scheduleAutoSave();\n      });\n\n      textarea.addEventListener('keydown', (e) => {\n        if (e.key === 'Tab') {\n          e.preventDefault();\n          const start = textarea.selectionStart;\n          const end = textarea.selectionEnd;\n          textarea.value = textarea.value.substring(0, start) + '  ' + textarea.value.substring(end);\n          textarea.selectionStart = textarea.selectionEnd = start + 2;\n          syncCodeVisuals();\n          scheduleAutoSave();\n        }\n      });\n\n      langSelect.addEventListener('change', () => {\n        syncCodeVisuals();\n        scheduleAutoSave();\n      });\n\n      card.querySelector('.btn-format-code').addEventListener('click', () => {\n        const lang = langSelect.value === 'auto' ? detectLanguage(textarea.value) : langSelect.value;\n        if (lang === 'json') {\n          try {\n            textarea.value = JSON.stringify(JSON.parse(textarea.value), null, 2);\n            showToast('Formatted JSON');\n          } catch (e) {\n            showToast('Invalid JSON syntax');\n          }\n        } else {\n          textarea.value = textarea.value\n            .split('\\n')\n            .map((l) => l.replace(/\\s+$/, ''))\n            .join('\\n')\n            .trim();\n          showToast('Cleaned whitespace & indentation');\n        }\n        syncCodeVisuals();\n        scheduleAutoSave();\n      });\n\n      card.querySelector('.btn-copy-code').addEventListener('click', () => {\n        textarea.select();\n        document.execCommand('copy');\n        window.getSelection().removeAllRanges();\n        showToast('Code copied to clipboard');\n      });\n\n      card.querySelector('.btn-delete-code').addEventListener('click', () => {\n        card.remove();\n        updateWordCounts();\n        rebuildOutline();\n        scheduleAutoSave();\n        showToast('Removed code block');\n      });\n\n      // Initial render pass\n      requestAnimationFrame(syncCodeVisuals);\n    }\n\n    function insertCodeBlock(presetCode = '', presetLang = null) {\n      closeAllDropdowns();\n      const targetBody = activeBodyElement || paperWrapper.querySelector('.doc-body');\n      if (!targetBody) return;\n\n      const lang = presetLang || document.getElementById('default-code-lang').value || 'auto';\n      const sample = presetCode || (lang === 'python'\n        ? '# Python function with automatic syntax colors\\ndef calculate_bmi(weight_kg, height_m):\\n    bmi = round(weight_kg / (height_m ** 2), 2)\\n    return f\"BMI Score: {bmi}\"\\n\\nprint(calculate_bmi(72, 1.78))'\n        : '// Type or paste code here\\nfunction greetDeveloper(name) {\\n  const message = `Hello, ${name}!`;\\n  console.log(message);\\n  return true;\\n}');\n\n      restoreSelection();\n      targetBody.focus();\n      document.execCommand('insertHTML', false, createCodeCardHTML(sample, lang));\n      hydrateAllCodeCards();\n      updateWordCounts();\n      rebuildOutline();\n      scheduleAutoSave();\n      showToast('Inserted live syntax-colored code block');\n    }\n\n    function toggleInlineCode() {\n      closeAllDropdowns();\n      const targetBody = activeBodyElement || paperWrapper.querySelector('.doc-body');\n      if (!targetBody) return;\n      targetBody.focus();\n\n      const sel = window.getSelection();\n      if (sel && !sel.isCollapsed) {\n        const text = sel.toString();\n        document.execCommand('insertHTML', false, `<code class=\"doc-inline-code\">${escapeHTML(text)}<\/code>&nbsp;`);\n      } else {\n        document.execCommand('insertHTML', false, `<code class=\"doc-inline-code\">inlineCode()<\/code>&nbsp;`);\n      }\n      scheduleAutoSave();\n    }\n\n    function convertSelectionToCodeBlock() {\n      closeAllDropdowns();\n      const sel = window.getSelection();\n      if (!sel || sel.isCollapsed) {\n        showToast('Select text in the document first');\n        return;\n      }\n      const selectedText = sel.toString();\n      document.execCommand('insertHTML', false, createCodeCardHTML(selectedText, 'auto'));\n      hydrateAllCodeCards();\n      updateWordCounts();\n      rebuildOutline();\n      scheduleAutoSave();\n      showToast('Converted selection into syntax-colored code block');\n    }\n\n    /* Markdown Fenced Code (```lang) & Inline Backtick (`code`) Shortcuts */\n    function handleMarkdownShortcuts(e, bodyEl) {\n      if (e.key !== ' ' && e.key !== 'Enter') return;\n      const sel = window.getSelection();\n      if (!sel || !sel.rangeCount) return;\n      const node = sel.anchorNode;\n      if (!node || node.nodeType !== Node.TEXT_NODE) return;\n\n      const text = node.textContent || '';\n      const fenceMatch = text.match(/^\\s*```([a-zA-Z0-9+#-]*)\\s*$/);\n      if (fenceMatch) {\n        const rawLang = (fenceMatch[1] || 'auto').toLowerCase();\n        const langMap = { js: 'javascript', py: 'python', ts: 'javascript', sh: 'bash' };\n        const lang = langMap[rawLang] || rawLang || 'auto';\n        const blockEl = node.parentElement && node.parentElement !== bodyEl ? node.parentElement : null;\n        if (blockEl) {\n          blockEl.outerHTML = createCodeCardHTML('', lang);\n          hydrateAllCodeCards();\n          const cards = bodyEl.querySelectorAll('.code-card');\n          const newest = cards[cards.length - 1];\n          if (newest) newest.querySelector('.code-textarea-layer').focus();\n          scheduleAutoSave();\n        }\n        return;\n      }\n\n      // Inline `code` conversion\n      const inlineMatch = text.match(/`([^`]+)`\\s$/);\n      if (inlineMatch) {\n        const replaced = text.replace(/`([^`]+)`\\s$/, `<code class=\"doc-inline-code\">${escapeHTML(inlineMatch[1])}<\/code> `);\n        const span = document.createElement('span');\n        span.innerHTML = replaced;\n        node.parentNode.replaceChild(span, node);\n        scheduleAutoSave();\n      }\n    }\n\n    function toggleAutoColor() {\n      closeAllDropdowns();\n      appState.autoColor = !appState.autoColor;\n      applyAutoColorUI();\n      hydrateAllCodeCards();\n      saveToStorage();\n      showToast(appState.autoColor ? 'Live syntax color-coding enabled' : 'Syntax color-coding paused');\n    }\n\n    function applyAutoColorUI() {\n      const label = document.getElementById('auto-color-label');\n      if (label) {\n        label.textContent = appState.autoColor ? 'Auto-Color: ON' : 'Auto-Color: OFF';\n      }\n    }\n\n    function toggleIdeTheme() {\n      closeAllDropdowns();\n      appState.ideDark = !appState.ideDark;\n      applyIdeThemeUI();\n      saveToStorage();\n      showToast(appState.ideDark ? 'Code blocks switched to One Dark Pro' : 'Code blocks switched to GitHub Light');\n    }\n\n    function applyIdeThemeUI() {\n      document.body.classList.toggle('ide-dark', !!appState.ideDark);\n      const icon = document.getElementById('ide-theme-icon');\n      if (icon) {\n        icon.textContent = appState.ideDark ? 'light_mode' : 'dark_mode';\n      }\n    }\n\n    /* ==========================================================================\n       5. RICH TEXT FORMATTING & TOOLBAR HELPERS\n       ========================================================================== */\n    function saveSelection() {\n      const sel = window.getSelection();\n      if (sel && sel.rangeCount > 0) {\n        const range = sel.getRangeAt(0);\n        if (paperWrapper.contains(range.commonAncestorContainer)) {\n          currentSelectionRange = range.cloneRange();\n        }\n      }\n    }\n\n    function restoreSelection() {\n      if (currentSelectionRange) {\n        const sel = window.getSelection();\n        sel.removeAllRanges();\n        sel.addRange(currentSelectionRange);\n      } else if (activeBodyElement) {\n        activeBodyElement.focus();\n      }\n    }\n\n    function execCmd(command, value = null) {\n      closeAllDropdowns();\n      if (activeBodyElement) activeBodyElement.focus();\n      document.execCommand(command, false, value);\n      updateToolbarActiveStates();\n      rebuildOutline();\n      scheduleAutoSave();\n    }\n\n    function applyHeadingStyle(styleVal) {\n      if (activeBodyElement) activeBodyElement.focus();\n      if (styleVal === 'P') {\n        document.execCommand('formatBlock', false, 'P');\n      } else if (['H1', 'H2', 'H3'].includes(styleVal)) {\n        document.execCommand('formatBlock', false, styleVal);\n      } else if (styleVal === 'TITLE') {\n        document.execCommand('formatBlock', false, 'DIV');\n        const block = getSelectedBlockElement();\n        if (block) block.className = 'doc-title-style';\n      } else if (styleVal === 'SUBTITLE') {\n        document.execCommand('formatBlock', false, 'DIV');\n        const block = getSelectedBlockElement();\n        if (block) block.className = 'doc-subtitle-style';\n      }\n      rebuildOutline();\n      scheduleAutoSave();\n    }\n\n    function getSelectedBlockElement() {\n      const sel = window.getSelection();\n      if (!sel || !sel.rangeCount) return null;\n      let node = sel.anchorNode;\n      while (node && !node.classList?.contains('doc-body')) {\n        if (node.nodeType === 1 && ['P', 'DIV', 'H1', 'H2', 'H3', 'LI'].includes(node.tagName)) {\n          return node;\n        }\n        node = node.parentNode;\n      }\n      return null;\n    }\n\n    function applyFontFamily(font) {\n      execCmd('fontName', font);\n    }\n\n    function stepFontSize(delta) {\n      const input = document.getElementById('font-size-input');\n      let current = parseInt(input.value, 10) || 11;\n      current = Math.max(6, Math.min(96, current + delta));\n      input.value = current;\n      applyFontSizePt(current);\n    }\n\n    function applyFontSizePt(pt) {\n      const sizePt = Math.max(6, Math.min(96, parseInt(pt, 10) || 11));\n      if (activeBodyElement) activeBodyElement.focus();\n      const sel = window.getSelection();\n      if (sel && !sel.isCollapsed) {\n        document.execCommand('fontSize', false, '7');\n        paperWrapper.querySelectorAll('font[size=\"7\"]').forEach((f) => {\n          const span = document.createElement('span');\n          span.style.fontSize = `${sizePt}pt`;\n          span.innerHTML = f.innerHTML;\n          f.parentNode.replaceChild(span, f);\n        });\n      } else {\n        const block = getSelectedBlockElement();\n        if (block) block.style.fontSize = `${sizePt}pt`;\n      }\n      scheduleAutoSave();\n    }\n\n    function applyTextColor(hex) {\n      document.getElementById('text-color-bar').style.backgroundColor = hex;\n      execCmd('foreColor', hex);\n    }\n\n    function applyHighlightColor(hex) {\n      document.getElementById('highlight-color-bar').style.backgroundColor = hex;\n      execCmd('hiliteColor', hex);\n    }\n\n    function clearFormatting() {\n      closeAllDropdowns();\n      if (activeBodyElement) activeBodyElement.focus();\n      document.execCommand('removeFormat', false, null);\n      document.execCommand('formatBlock', false, 'P');\n      const block = getSelectedBlockElement();\n      if (block) block.removeAttribute('class');\n      updateToolbarActiveStates();\n      rebuildOutline();\n      scheduleAutoSave();\n    }\n\n    function insertChecklist() {\n      if (activeBodyElement) activeBodyElement.focus();\n      const html = `<ul class=\"docs-checklist\"><li><input type=\"checkbox\" onchange=\"toggleChecklistItem(this)\"><span>Action item<\/span><\/li><\/ul><p><br><\/p>`;\n      document.execCommand('insertHTML', false, html);\n      scheduleAutoSave();\n    }\n\n    function toggleChecklistItem(checkbox) {\n      const li = checkbox.closest('li');\n      if (li) li.classList.toggle('checked', checkbox.checked);\n      scheduleAutoSave();\n    }\n\n    function updateToolbarActiveStates() {\n      try {\n        document.getElementById('btn-bold').classList.toggle('active', document.queryCommandState('bold'));\n        document.getElementById('btn-italic').classList.toggle('active', document.queryCommandState('italic'));\n        document.getElementById('btn-underline').classList.toggle('active', document.queryCommandState('underline'));\n        document.getElementById('btn-ul').classList.toggle('active', document.queryCommandState('insertUnorderedList'));\n        document.getElementById('btn-ol').classList.toggle('active', document.queryCommandState('insertOrderedList'));\n        document.getElementById('btn-align-left').classList.toggle('active', document.queryCommandState('justifyLeft'));\n        document.getElementById('btn-align-center').classList.toggle('active', document.queryCommandState('justifyCenter'));\n        document.getElementById('btn-align-right').classList.toggle('active', document.queryCommandState('justifyRight'));\n      } catch (e) {}\n    }\n\n    /* ==========================================================================\n       6. RULER, ZOOM & MARGINS\n       ========================================================================== */\n    function setZoom(scaleStr) {\n      const scale = parseFloat(scaleStr) || 1;\n      paperWrapper.style.transform = `scale(${scale})`;\n      document.getElementById('ruler-track').style.transform = `scaleX(${scale})`;\n    }\n\n    function drawRulerTicks() {\n      const canvas = document.getElementById('ruler-canvas');\n      const ctx = canvas.getContext('2d');\n      ctx.clearRect(0, 0, canvas.width, canvas.height);\n      ctx.strokeStyle = '#9aa0a6';\n      ctx.fillStyle = '#5f6368';\n      ctx.font = '10px Roboto, sans-serif';\n      ctx.textAlign = 'center';\n\n      const totalEighths = 8.5 * 8;\n      for (let i = 1; i < totalEighths; i++) {\n        const x = i * 12;\n        if (i % 8 === 0) {\n          ctx.fillText((i / 8).toString(), x, 15);\n        } else if (i % 4 === 0) {\n          ctx.beginPath();\n          ctx.moveTo(x, 7);\n          ctx.lineTo(x, 17);\n          ctx.stroke();\n        } else {\n          ctx.beginPath();\n          ctx.moveTo(x, 10);\n          ctx.lineTo(x, 14);\n          ctx.stroke();\n        }\n      }\n    }\n\n    function setupRulerDragHandles() {\n      const leftHandle = document.getElementById('handle-left-margin');\n      const rightHandle = document.getElementById('handle-right-margin');\n      const rulerTrack = document.getElementById('ruler-track');\n      let dragging = null;\n\n      leftHandle.addEventListener('mousedown', (e) => { e.preventDefault(); dragging = 'left'; });\n      rightHandle.addEventListener('mousedown', (e) => { e.preventDefault(); dragging = 'right'; });\n\n      window.addEventListener('mousemove', (e) => {\n        if (!dragging) return;\n        const rect = rulerTrack.getBoundingClientRect();\n        const scale = rect.width / 816;\n        const relX = Math.round((e.clientX - rect.left) / scale);\n\n        if (dragging === 'left') {\n          appState.marginLeftPx = Math.max(24, Math.min(300, relX));\n        } else if (dragging === 'right') {\n          appState.marginRightPx = Math.max(24, Math.min(300, 816 - relX));\n        }\n        applyMarginsToCanvas();\n      });\n\n      window.addEventListener('mouseup', () => {\n        if (dragging) {\n          dragging = null;\n          scheduleAutoSave();\n        }\n      });\n    }\n\n    function applyMarginsToCanvas() {\n      const leftPx = appState.marginLeftPx;\n      const rightPx = appState.marginRightPx;\n      const tbPx = appState.marginTopBottomPx || 24;\n\n      document.querySelectorAll('.doc-body').forEach((body) => {\n        body.style.paddingLeft = `${leftPx}px`;\n        body.style.paddingRight = `${rightPx}px`;\n        body.style.paddingTop = `${tbPx}px`;\n      });\n      document.querySelectorAll('.doc-header-zone, .doc-footer-zone').forEach((zone) => {\n        zone.style.paddingLeft = `${leftPx}px`;\n        zone.style.paddingRight = `${rightPx}px`;\n      });\n\n      document.getElementById('ruler-left-shade').style.width = `${leftPx}px`;\n      document.getElementById('ruler-right-shade').style.width = `${rightPx}px`;\n      document.getElementById('handle-left-margin').style.left = `${leftPx}px`;\n      document.getElementById('handle-right-margin').style.left = `${816 - rightPx}px`;\n    }\n\n    /* ==========================================================================\n       7. OUTLINE SIDEBAR (HEADINGS + CODE SNIPPETS)\n       ========================================================================== */\n    function toggleOutlineSidebar() {\n      closeAllDropdowns();\n      const sidebar = document.getElementById('left-outline-sidebar');\n      const check = document.getElementById('check-outline');\n      const isHidden = sidebar.classList.contains('hidden');\n      sidebar.classList.toggle('hidden', !isHidden);\n      sidebar.classList.toggle('flex', isHidden);\n      check.classList.toggle('opacity-0', !isHidden);\n    }\n\n    function toggleRuler() {\n      closeAllDropdowns();\n      const ruler = document.getElementById('ruler-container');\n      const check = document.getElementById('check-ruler');\n      const hidden = ruler.classList.toggle('hidden');\n      check.classList.toggle('opacity-0', hidden);\n    }\n\n    function rebuildOutline() {\n      const outlineList = document.getElementById('outline-list');\n      const nodes = paperWrapper.querySelectorAll('.doc-title-style, .doc-subtitle-style, h1, h2, h3, .code-card');\n\n      if (nodes.length === 0) {\n        outlineList.innerHTML = `<p class=\"text-xs text-[#747775] italic px-2 py-2\">Headings and code blocks will appear here.<\/p>`;\n        return;\n      }\n\n      outlineList.innerHTML = '';\n      nodes.forEach((el, i) => {\n        const item = document.createElement('div');\n        if (el.classList.contains('code-card')) {\n          const rawLang = el.dataset.lang || 'auto';\n          const lang = (rawLang === 'auto' ? detectLanguage(el.dataset.code || '') : rawLang).toUpperCase();\n          const firstLine = (el.dataset.code || '').split('\\n')[0].trim().slice(0, 26) || `Snippet #${i + 1}`;\n          item.className = 'py-1.5 pl-3 pr-2 rounded-r-full hover:bg-[#e8eaed] cursor-pointer truncate transition flex items-center gap-1.5 text-xs font-mono text-[#0b57d0]';\n          item.innerHTML = `<span class=\"px-1.5 py-0.2 bg-[#d3e3fd] rounded text-[10px] font-semibold\">${escapeHTML(lang)}<\/span><span class=\"truncate\">${escapeHTML(firstLine)}<\/span>`;\n        } else {\n          const text = el.textContent.trim();\n          if (!text) return;\n          let indentClass = 'pl-2 font-medium text-[#1f1f1f]';\n          if (el.tagName === 'H2' || el.classList.contains('doc-subtitle-style')) indentClass = 'pl-5 text-[#444746]';\n          else if (el.tagName === 'H3') indentClass = 'pl-8 text-xs text-[#5f6368]';\n          item.className = `py-1.5 pr-2 rounded-r-full hover:bg-[#e8eaed] cursor-pointer truncate transition ${indentClass}`;\n          item.textContent = text;\n        }\n\n        item.onclick = () => {\n          el.scrollIntoView({ behavior: 'smooth', block: 'center' });\n        };\n        outlineList.appendChild(item);\n      });\n    }\n\n    /* ==========================================================================\n       8. INSERT ELEMENTS & COMMENTS\n       ========================================================================== */\n    function confirmInsertLink() {\n      const text = document.getElementById('link-text-input').value.trim();\n      let url = document.getElementById('link-url-input').value.trim();\n      if (!url) return showToast('Please enter a valid URL');\n      if (!/^https?:\\/\\//i.test(url)) url = 'https://' + url;\n\n      closeAllModals();\n      restoreSelection();\n      document.execCommand('insertHTML', false, `<a href=\"${url}\" target=\"_blank\" rel=\"noopener noreferrer\">${escapeHTML(text || url)}<\/a>&nbsp;`);\n      scheduleAutoSave();\n    }\n\n    function confirmInsertImage() {\n      const fileInput = document.getElementById('image-file-input');\n      const urlInput = document.getElementById('image-url-input').value.trim();\n\n      if (fileInput.files && fileInput.files[0]) {\n        const reader = new FileReader();\n        reader.onload = (e) => {\n          insertImageTag(e.target.result);\n          fileInput.value = '';\n        };\n        reader.readAsDataURL(fileInput.files[0]);\n        closeAllModals();\n      } else if (urlInput) {\n        insertImageTag(urlInput);\n        document.getElementById('image-url-input').value = '';\n        closeAllModals();\n      } else {\n        showToast('Select an image file or paste an image URL');\n      }\n    }\n\n    function insertImageTag(src) {\n      const safeSrc = String(src || '').trim();\n      if (!/^https?:\\/\\//i.test(safeSrc) && !/^data:image\\/(png|jpeg|gif|webp);base64,/i.test(safeSrc)) {\n        showToast('Use an image link or choose an image file');\n        return;\n      }\n      restoreSelection();\n      const image = document.createElement('img');\n      image.src = safeSrc;\n      image.alt = 'Inserted image';\n      image.style.cssText = 'max-width:100%;margin:8px 0';\n      const holder = document.createElement('div'); holder.appendChild(image);\n      document.execCommand('insertHTML', false, holder.innerHTML + '<p><br><\/p>');\n      scheduleAutoSave();\n    }\n\n    function confirmInsertTable() {\n      const rows = Math.max(1, Math.min(20, parseInt(document.getElementById('table-rows-input').value, 10) || 3));\n      const cols = Math.max(1, Math.min(12, parseInt(document.getElementById('table-cols-input').value, 10) || 3));\n      closeAllModals();\n      restoreSelection();\n\n      let html = '<table><tbody>';\n      for (let r = 0; r < rows; r++) {\n        html += '<tr>' + '<td><br><\/td>'.repeat(cols) + '<\/tr>';\n      }\n      html += '<\/tbody><\/table><p><br><\/p>';\n      document.execCommand('insertHTML', false, html);\n      scheduleAutoSave();\n    }\n\n    function insertHorizontalLine() {\n      closeAllDropdowns();\n      if (activeBodyElement) activeBodyElement.focus();\n      document.execCommand('insertHTML', false, '<hr style=\"border:0; border-top:1px solid #dadce0; margin:14px 0;\"><p><br><\/p>');\n      scheduleAutoSave();\n    }\n\n    function insertCurrentDate() {\n      closeAllDropdowns();\n      const dateStr = new Date().toLocaleDateString('en-US', { month: 'short', day: 'numeric', year: 'numeric' });\n      restoreSelection();\n      document.execCommand('insertText', false, `\ud83d\udcc5 ${dateStr} `);\n      scheduleAutoSave();\n    }\n\n    function toggleCommentsSidebar() {\n      closeAllDropdowns();\n      const sidebar = document.getElementById('right-comments-sidebar');\n      const check = document.getElementById('check-comments');\n      const isHidden = sidebar.classList.contains('hidden');\n      sidebar.classList.toggle('hidden', !isHidden);\n      sidebar.classList.toggle('flex', isHidden);\n      check.classList.toggle('opacity-0', !isHidden);\n    }\n\n    function openCommentComposer() {\n      closeAllDropdowns();\n      saveSelection();\n      const sidebar = document.getElementById('right-comments-sidebar');\n      sidebar.classList.remove('hidden');\n      sidebar.classList.add('flex');\n\n      const composer = document.getElementById('comment-composer');\n      const quotePreview = document.getElementById('comment-quote-preview');\n      composer.classList.remove('hidden');\n\n      const selectedText = currentSelectionRange ? currentSelectionRange.toString().trim() : '';\n      if (selectedText) {\n        quotePreview.textContent = `\"${selectedText}\"`;\n        quotePreview.classList.remove('hidden');\n      } else {\n        quotePreview.classList.add('hidden');\n      }\n      document.getElementById('comment-input').value = '';\n      document.getElementById('comment-input').focus();\n    }\n\n    function cancelCommentComposer() {\n      document.getElementById('comment-composer').classList.add('hidden');\n    }\n\n    function submitComment() {\n      const text = document.getElementById('comment-input').value.trim();\n      if (!text) return;\n\n      const commentId = 'cmt_' + Date.now();\n      let quoted = '';\n      if (currentSelectionRange && !currentSelectionRange.collapsed) {\n        quoted = currentSelectionRange.toString().trim();\n        try {\n          const mark = document.createElement('span');\n          mark.className = 'doc-comment-highlight';\n          mark.dataset.commentId = commentId;\n          mark.appendChild(currentSelectionRange.extractContents());\n          currentSelectionRange.insertNode(mark);\n        } catch (e) {}\n      }\n\n      appState.comments.unshift({\n        id: commentId,\n        author: 'You',\n        time: new Date().toLocaleTimeString([], { hour: '2-digit', minute: '2-digit' }),\n        quote: quoted,\n        text\n      });\n\n      cancelCommentComposer();\n      renderComments();\n      saveToStorage();\n      showToast('Comment added');\n    }\n\n    function resolveComment(id) {\n      appState.comments = appState.comments.filter((c) => c.id !== id);\n      const highlight = paperWrapper.querySelector(`[data-comment-id=\"${id}\"]`);\n      if (highlight) {\n        const parent = highlight.parentNode;\n        while (highlight.firstChild) parent.insertBefore(highlight.firstChild, highlight);\n        parent.removeChild(highlight);\n      }\n      renderComments();\n      saveToStorage();\n      showToast('Comment resolved');\n    }\n\n    function renderComments() {\n      const list = document.getElementById('comments-list');\n      const badge = document.getElementById('comment-badge');\n      if (appState.comments.length === 0) {\n        badge.classList.add('hidden');\n        list.innerHTML = `<div class=\"text-center py-8 text-xs text-[#5f6368]\">Select text and click <strong>+ Comment<\/strong> to review code or prose.<\/div>`;\n        return;\n      }\n      badge.classList.remove('hidden');\n      list.innerHTML = appState.comments.map((c) => `\n        <div class=\"bg-white p-3 rounded-xl border border-[#e0e3e7] shadow-2xs\">\n          <div class=\"flex items-center justify-between mb-1.5\">\n            <div class=\"flex items-center gap-2\">\n              <div class=\"w-6 h-6 rounded-full bg-[#0b57d0] text-white text-xs flex items-center justify-center font-medium\">A<\/div>\n              <div>\n                <div class=\"text-xs font-medium text-[#1f1f1f]\">${escapeHTML(c.author)}<\/div>\n                <div class=\"text-[10px] text-[#5f6368]\">${escapeHTML(c.time)}<\/div>\n              <\/div>\n            <\/div>\n            <button onclick=\"resolveComment('${c.id}')\" class=\"w-7 h-7 rounded-full hover:bg-green-50 text-[#0b57d0] flex items-center justify-center\" title=\"Resolve\">\n              <span class=\"material-symbols-outlined text-[18px]\">check<\/span>\n            <\/button>\n          <\/div>\n          ${c.quote ? `<div class=\"text-xs text-[#5f6368] border-l-2 border-[#f9ab00] pl-2 my-1.5 italic truncate\">\"${escapeHTML(c.quote)}\"<\/div>` : ''}\n          <p class=\"text-sm text-[#1f1f1f] mt-1\">${escapeHTML(c.text)}<\/p>\n        <\/div>\n      `).join('');\n    }\n\n    /* ==========================================================================\n       9. METRICS, TEMPLATES, IMPORT & EXPORT\n       ========================================================================== */\n    function updateWordCounts() {\n      let proseWords = 0;\n      let totalChars = 0;\n      let codeBlocks = 0;\n      let codeLines = 0;\n\n      paperWrapper.querySelectorAll('.doc-body').forEach((body) => {\n        const clone = body.cloneNode(true);\n        clone.querySelectorAll('.code-card').forEach((card) => {\n          codeBlocks++;\n          const code = card.dataset.code || '';\n          if (code.trim()) codeLines += code.split('\\n').length;\n          card.remove();\n        });\n        const text = clone.innerText || '';\n        const trimmed = text.trim();\n        proseWords += trimmed ? trimmed.split(/\\s+/).length : 0;\n        totalChars += text.replace(/\\n/g, '').length;\n      });\n\n      const pageCount = appState.pagesHTML.length || 1;\n      document.getElementById('live-word-count').textContent = `${proseWords} ${proseWords === 1 ? 'word' : 'words'}`;\n      document.getElementById('live-code-lines').textContent = `${codeLines} ${codeLines === 1 ? 'line' : 'lines'} of code`;\n      document.getElementById('live-page-est').textContent = `${pageCount} ${pageCount === 1 ? 'page' : 'pages'}`;\n\n      document.getElementById('wc-pages').textContent = pageCount;\n      document.getElementById('wc-words').textContent = proseWords;\n      document.getElementById('wc-chars').textContent = totalChars;\n      document.getElementById('wc-code-blocks').textContent = codeBlocks;\n      document.getElementById('wc-code-lines').textContent = codeLines;\n    }\n\n    function getDefaultCodingTemplateHTML() {\n      const pyCode = [\n        '# Day 2: Arithmetic, Rounding & String Indexing',\n        'print(20 + 10)      # Addition -> 30',\n        'print(200 // 100)   # Floor division -> 2',\n        'print(2 ** 3)       # Exponent -> 8',\n        '',\n        '# Rounding floating-point values',\n        'bmi = 84.21331 / 3',\n        'print(f\"Rounded BMI: {round(bmi, 2)}\")',\n        '',\n        '# String indexing',\n        'greeting = \"Hello\"',\n        'print(greeting[0], greeting[-1])'\n      ].join('\\n');\n\n      const jsCode = [\n        '// Live JavaScript syntax highlighting',\n        'function binarySearch(arr, target) {',\n        '  let left = 0, right = arr.length - 1;',\n        '  while (left <= right) {',\n        '    const mid = Math.floor((left + right) / 2);',\n        '    if (arr[mid] === target) return mid;',\n        '    arr[mid] < target ? (left = mid + 1) : (right = mid - 1);',\n        '  }',\n        '  return -1;',\n        '}'\n      ].join('\\n');\n\n      return `\n        <div class=\"doc-title-style\">Python &amp; Algorithms \u2014 Study Notes<\/div>\n        <div class=\"doc-subtitle-style\">Personal coding notes with automatic syntax colors<\/div>\n        <p>Write normal prose anywhere on the page, or type <code class=\"doc-inline-code\">\\`\\`\\`py<\/code> + <strong>Space<\/strong> to insert a live syntax-highlighted code block.<\/p>\n        <h2>1. Python Basics &amp; Math Operators<\/h2>\n        ${createCodeCardHTML(pyCode, 'python')}\n        <h2>2. JavaScript Algorithm Reference<\/h2>\n        ${createCodeCardHTML(jsCode, 'javascript')}\n        <h3>Study Checklist<\/h3>\n        <ul class=\"docs-checklist\">\n          <li><input type=\"checkbox\" checked onchange=\"toggleChecklistItem(this)\"><span>Practice PEMDAS order of operations &amp; floor division<\/span><\/li>\n          <li><input type=\"checkbox\" onchange=\"toggleChecklistItem(this)\"><span>Test switching between GitHub Light and One Dark Pro themes<\/span><\/li>\n        <\/ul>\n      `;\n    }\n\n    function applyTemplate(type) {\n      closeAllModals();\n      closeAllDropdowns();\n      if (type === 'blank') {\n        newDocument();\n        return;\n      } else if (type === 'coding') {\n        titleInput.value = 'Python Fundamentals & Algorithms \u2014 Day 2';\n        appState.pagesHTML = ['<p><br><\/p>'];\n      } else if (type === 'rfc') {\n        titleInput.value = 'Engineering RFC \u2014 User Authentication API';\n        const sqlSample = 'CREATE TABLE users (\\n  id SERIAL PRIMARY KEY,\\n  email VARCHAR(255) UNIQUE NOT NULL,\\n  created_at TIMESTAMP DEFAULT NOW()\\n);';\n        appState.pagesHTML = [`\n          <div class=\"doc-title-style\">RFC-014: Authentication Service<\/div>\n          <div class=\"doc-subtitle-style\">Status: Draft \u2022 Author: You<\/div>\n          <h2>Overview<\/h2>\n          <p>This specification outlines the database schema and token validation pipeline for the v2 authentication service.<\/p>\n          <h2>Database Schema (PostgreSQL)<\/h2>\n          ${createCodeCardHTML(sqlSample, 'sql')}\n        `];\n      }\n      renderAllPages();\n      applyMarginsToCanvas();\n      updateWordCounts();\n      rebuildOutline();\n      saveToStorage();\n      showToast('Template loaded');\n    }\n\n    function newDocument() {\n      closeAllDropdowns();\n      titleInput.value = 'Untitled document';\n      appState.pagesHTML = ['<p><br><\/p>'];\n      appState.comments = [];\n      renderAllPages();\n      applyMarginsToCanvas();\n      renderComments();\n      rebuildOutline();\n      updateWordCounts();\n      saveToStorage();\n      showToast('Created new blank document');\n    }\n\n    function makeCopy() {\n      closeAllDropdowns();\n      titleInput.value = `Copy of ${titleInput.value}`;\n      saveToStorage();\n      showToast(`Created \"${titleInput.value}\"`);\n    }\n\n    function downloadDoc(format) {\n      closeAllDropdowns();\n      syncPagesFromDOM();\n      const safeTitle = (titleInput.value.trim() || 'Untitled_document').replace(/[^a-z0-9_\\- ]/gi, '_');\n      let blob, filename;\n\n      if (format === 'html') {\n        const combined = appState.pagesHTML.join('<hr/>');\n        const docStr = '<!DOCTYPE html><html><head><meta charset=\"UTF-8\"><title>' +\n          escapeHTML(titleInput.value) +\n          '<\/title><style>body{font-family:Arial,sans-serif;max-width:816px;margin:40px auto;padding:0 24px;line-height:1.4;}pre{background:#f6f8fa;padding:12px;border-radius:8px;font-family:monospace;}<\/style><\/head><body>' +\n          combined +\n          '<\/body><\/html>';\n        blob = new Blob([docStr], { type: 'text/html;charset=utf-8' });\n        filename = `${safeTitle}.html`;\n      } else if (format === 'md') {\n        const mdLines = [`# ${titleInput.value}\\n`];\n        paperWrapper.querySelectorAll('.doc-body').forEach((body) => {\n          body.childNodes.forEach((node) => {\n            if (node.nodeType === 1 && node.classList.contains('code-card')) {\n              const lang = node.dataset.lang === 'auto' ? detectLanguage(node.dataset.code || '') : node.dataset.lang;\n              mdLines.push('```' + lang + '\\n' + (node.dataset.code || '') + '\\n```\\n');\n            } else if (node.textContent && node.textContent.trim()) {\n              mdLines.push(node.textContent.trim() + '\\n');\n            }\n          });\n        });\n        blob = new Blob([mdLines.join('\\n')], { type: 'text/markdown;charset=utf-8' });\n        filename = `${safeTitle}.md`;\n      } else {\n        const txt = Array.from(paperWrapper.querySelectorAll('.doc-body')).map((b) => b.innerText).join('\\n\\n--- Page Break ---\\n\\n');\n        blob = new Blob([txt], { type: 'text/plain;charset=utf-8' });\n        filename = `${safeTitle}.txt`;\n      }\n\n      const url = URL.createObjectURL(blob);\n      const a = document.createElement('a');\n      a.href = url;\n      a.download = filename;\n      document.body.appendChild(a);\n      a.click();\n      document.body.removeChild(a);\n      URL.revokeObjectURL(url);\n      showToast(`Downloaded ${filename}`);\n    }\n\n    function handleFileImport(event) {\n      const file = event.target.files[0];\n      if (!file) return;\n      const reader = new FileReader();\n      reader.onload = (e) => {\n        const content = e.target.result;\n        const ext = file.name.split('.').pop().toLowerCase();\n        titleInput.value = file.name.replace(/\\.[^/.]+$/, '');\n        const codeExts = ['py', 'js', 'css', 'sql', 'json', 'cpp', 'sh'];\n        if (codeExts.includes(ext)) {\n          const langMap = { py: 'python', js: 'javascript', sh: 'bash' };\n          appState.pagesHTML = [`<div class=\"doc-title-style\">${escapeHTML(file.name)}<\/div>${createCodeCardHTML(content, langMap[ext] || ext)}`];\n        } else if (ext === 'html' || ext === 'htm') {\n          const parsed = new DOMParser().parseFromString(content, 'text/html');\n          parsed.querySelectorAll('script, iframe, object, embed, form, meta, link').forEach((el) => el.remove());\n          parsed.body.querySelectorAll('*').forEach((el) => {\n            [...el.attributes].forEach((attr) => {\n              if (/^on/i.test(attr.name) || ((attr.name === 'href' || attr.name === 'src') && /^\\s*javascript:/i.test(attr.value))) el.removeAttribute(attr.name);\n            });\n          });\n          appState.pagesHTML = [parsed.body.innerHTML];\n        } else {\n          appState.pagesHTML = [content.split('\\n').map((line) => `<p>${escapeHTML(line) || '<br>'}<\/p>`).join('')];\n        }\n        renderAllPages();\n        applyMarginsToCanvas();\n        rebuildOutline();\n        updateWordCounts();\n        saveToStorage();\n        showToast(`Opened \"${file.name}\"`);\n      };\n      reader.readAsText(file);\n      event.target.value = '';\n    }\n\n    /* ==========================================================================\n       10. FIND & REPLACE, PAGE SETUP, MENUS, MODALS & SHORTCUTS\n       ========================================================================== */\n    function executeFindReplace(replaceAll) {\n      const findStr = document.getElementById('find-input').value;\n      const replaceStr = document.getElementById('replace-input').value;\n      if (!findStr) return;\n\n      let count = 0;\n      paperWrapper.querySelectorAll('.doc-body').forEach((body) => {\n        if (body.innerHTML.includes(findStr)) {\n          if (replaceAll) {\n            body.innerHTML = body.innerHTML.split(findStr).join(replaceStr);\n            count++;\n          } else if (count === 0) {\n            body.innerHTML = body.innerHTML.replace(findStr, replaceStr);\n            count++;\n          }\n        }\n      });\n\n      hydrateAllCodeCards();\n      updateWordCounts();\n      scheduleAutoSave();\n      showToast(count > 0 ? `Updated matches for \"${findStr}\"` : `No matches found for \"${findStr}\"`);\n    }\n\n    function applyPageSetup() {\n      appState.pageColor = document.getElementById('page-color-input').value;\n      const tbIn = parseFloat(document.getElementById('margin-tb-input').value) || 1;\n      const lrIn = parseFloat(document.getElementById('margin-lr-input').value) || 1;\n      appState.marginTopBottomPx = Math.round(tbIn * 24);\n      appState.marginLeftPx = Math.round(lrIn * 96);\n      appState.marginRightPx = Math.round(lrIn * 96);\n\n      document.querySelectorAll('.doc-sheet').forEach((s) => { s.style.backgroundColor = appState.pageColor; });\n      applyMarginsToCanvas();\n      closeAllModals();\n      saveToStorage();\n      showToast('Page setup updated');\n    }\n\n    function selectAllDoc() {\n      closeAllDropdowns();\n      if (activeBodyElement) activeBodyElement.focus();\n      document.execCommand('selectAll', false, null);\n    }\n\n    function copyShareLink() {\n      const tempInput = document.createElement('input');\n      tempInput.value = window.location.href;\n      document.body.appendChild(tempInput);\n      tempInput.select();\n      document.execCommand('copy');\n      document.body.removeChild(tempInput);\n      showToast('Link copied to clipboard');\n    }\n\n    function toggleStar() {\n      appState.starred = !appState.starred;\n      updateStarUI();\n      saveToStorage();\n      showToast(appState.starred ? 'Added to Starred' : 'Removed from Starred');\n    }\n\n    function updateStarUI() {\n      const icon = document.getElementById('star-icon');\n      icon.classList.toggle('filled', appState.starred);\n      icon.classList.toggle('text-amber-500', appState.starred);\n    }\n\n    function toggleFullScreen() {\n      closeAllDropdowns();\n      if (!document.fullscreenElement) document.documentElement.requestFullscreen().catch(() => {});\n      else document.exitFullscreen().catch(() => {});\n    }\n\n    function toggleVoiceTyping() {\n      closeAllDropdowns();\n      const SpeechRecognition = window.SpeechRecognition || window.webkitSpeechRecognition;\n      if (!SpeechRecognition) return showToast('Voice typing not supported in this browser');\n      const recognition = new SpeechRecognition();\n      recognition.lang = 'en-US';\n      recognition.onstart = () => showToast('\ud83c\udf99\ufe0f Listening...');\n      recognition.onresult = (event) => {\n        const transcript = event.results[0][0].transcript;\n        if (activeBodyElement) activeBodyElement.focus();\n        document.execCommand('insertText', false, transcript + ' ');\n        scheduleAutoSave();\n      };\n      recognition.start();\n    }\n\n    function setupMenuBarDropdowns() {\n      document.querySelectorAll('.menu-btn').forEach((btn) => {\n        btn.addEventListener('click', (e) => {\n          e.stopPropagation();\n          const panel = document.getElementById(btn.getAttribute('data-menu'));\n          const isOpen = panel.classList.contains('open');\n          closeAllDropdowns();\n          if (!isOpen) {\n            panel.classList.add('open');\n            btn.classList.add('active');\n          }\n        });\n        btn.addEventListener('mouseenter', () => {\n          if (document.querySelector('.dropdown-panel.open')) {\n            const panel = document.getElementById(btn.getAttribute('data-menu'));\n            if (!panel.classList.contains('open')) {\n              closeAllDropdowns();\n              panel.classList.add('open');\n              btn.classList.add('active');\n            }\n          }\n        });\n      });\n      document.addEventListener('click', closeAllDropdowns);\n    }\n\n    function closeAllDropdowns() {\n      document.querySelectorAll('.dropdown-panel').forEach((p) => p.classList.remove('open'));\n      document.querySelectorAll('.menu-btn').forEach((b) => b.classList.remove('active'));\n    }\n\n    function openModal(modalId) {\n      closeAllDropdowns();\n      saveSelection();\n      const backdrop = document.getElementById('modal-backdrop');\n      document.querySelectorAll('.modal-card').forEach((m) => m.classList.add('hidden'));\n\n      if (modalId === 'link-modal') {\n        document.getElementById('link-text-input').value = currentSelectionRange ? currentSelectionRange.toString().trim() : '';\n        document.getElementById('link-url-input').value = '';\n      } else if (modalId === 'history-modal') {\n        const list = document.getElementById('history-list');\n        list.innerHTML = appState.snapshots.length === 0\n          ? '<div class=\"text-xs text-gray-500\">Current version (auto-saved)<\/div>'\n          : appState.snapshots.map((snap, idx) => `\n              <div class=\"p-2.5 rounded-lg border border-gray-200 hover:bg-blue-50 flex items-center justify-between\">\n                <div>\n                  <div class=\"font-medium text-xs\">${idx === 0 ? 'Current version' : 'Revision'} \u2022 ${snap.time}<\/div>\n                  <div class=\"text-[11px] text-gray-500\">You<\/div>\n                <\/div>\n                <button onclick=\"restoreSnapshot(${idx})\" class=\"text-xs text-[#0b57d0] font-medium hover:underline\">Restore<\/button>\n              <\/div>\n            `).join('');\n      }\n\n      backdrop.classList.remove('hidden');\n      backdrop.classList.add('flex');\n      document.getElementById(modalId).classList.remove('hidden');\n    }\n\n    function restoreSnapshot(index) {\n      const snap = appState.snapshots[index];\n      if (snap && snap.pagesHTML) {\n        appState.pagesHTML = [...snap.pagesHTML];\n        renderAllPages();\n        applyMarginsToCanvas();\n        rebuildOutline();\n        updateWordCounts();\n        saveToStorage();\n        closeAllModals();\n        showToast(`Restored version from ${snap.time}`);\n      }\n    }\n\n    function closeAllModals() {\n      const backdrop = document.getElementById('modal-backdrop');\n      backdrop.classList.add('hidden');\n      backdrop.classList.remove('flex');\n      document.querySelectorAll('.modal-card').forEach((m) => m.classList.add('hidden'));\n    }\n\n    let toastTimeout = null;\n    function showToast(msg) {\n      const toast = document.getElementById('toast-notification');\n      toast.textContent = msg;\n      toast.classList.remove('opacity-0');\n      clearTimeout(toastTimeout);\n      toastTimeout = setTimeout(() => toast.classList.add('opacity-0'), 2600);\n    }\n\n    function handleWorkspaceClick(e) {\n      if (e.target.id === 'workspace-scroll' && activeBodyElement) {\n        activeBodyElement.focus();\n      }\n    }\n\n    titleInput.addEventListener('input', scheduleAutoSave);\n    titleInput.addEventListener('blur', () => {\n      if (!titleInput.value.trim()) titleInput.value = 'Untitled document';\n      saveToStorage();\n    });\n\n\n    function importLegacyNotebook(raw, owner) {\n      if (owner !== OWNER_ID || localStorage.getItem(STORAGE_KEY) || !raw) return;\n      try {\n        const legacyPages = JSON.parse(raw);\n        if (!Array.isArray(legacyPages) || !legacyPages.length) return;\n        appState.title = `${OWNER_NAME}'s Python Notes`;\n        appState.pagesHTML = legacyPages.map((page) => {\n          const heading = [page.concept, page.day ? `Day ${page.day}` : '', page.filename].filter(Boolean).map(escapeHTML);\n          let noteHTML = '';\n          if (page.notes) {\n            const parsed = new DOMParser().parseFromString(String(page.notes), 'text/html');\n            parsed.querySelectorAll('script, iframe, object, embed, form').forEach((el) => el.remove());\n            parsed.body.querySelectorAll('*').forEach((el) => [...el.attributes].forEach((attr) => { if (/^on/i.test(attr.name)) el.removeAttribute(attr.name); }));\n            noteHTML = parsed.body.innerHTML || `<p>${escapeHTML(page.notes).replace(/\\n/g, '<br>')}<\/p>`;\n          }\n          const oldCode = page.code || (Array.isArray(page.lines) ? page.lines.join('\\n') : '');\n          const codeHTML = oldCode.trim() ? createCodeCardHTML(oldCode, 'python') : '';\n          return `${heading.length ? `<h2>${heading.join(' \u00b7 ')}<\/h2>` : ''}${noteHTML}${codeHTML || '<p><br><\/p>'}`;\n        });\n        titleInput.value = appState.title;\n        renderAllPages(); applyMarginsToCanvas(); updateWordCounts(); rebuildOutline(); saveToStorage();\n        showToast('Your earlier notes were moved into this workspace');\n      } catch (error) { console.warn('Could not import earlier notebook pages:', error); }\n    }\n    window.addEventListener('message', (event) => {\n      if (event.source !== window.parent || event.data?.type !== 'legacy-python-notebook') return;\n      importLegacyNotebook(event.data.raw, event.data.owner);\n    });\n\n    function setupKeyboardShortcuts() {\n      document.addEventListener('keydown', (e) => {\n        const mod = e.ctrlKey || e.metaKey;\n        if (mod && e.altKey && e.key.toLowerCase() === 'c') {\n          e.preventDefault();\n          insertCodeBlock();\n        } else if (mod && e.key.toLowerCase() === 'e') {\n          e.preventDefault();\n          toggleInlineCode();\n        } else if (mod && e.key.toLowerCase() === 'k') {\n          e.preventDefault();\n          openModal('link-modal');\n        } else if (mod && e.altKey && e.key.toLowerCase() === 'm') {\n          e.preventDefault();\n          openCommentComposer();\n        } else if (mod && e.key.toLowerCase() === 'h') {\n          e.preventDefault();\n          openModal('find-replace-modal');\n        } else if (mod && e.shiftKey && e.key.toLowerCase() === 'c') {\n          e.preventDefault();\n          openModal('word-count-modal');\n        } else if (mod && e.key === '\\\\') {\n          e.preventDefault();\n          clearFormatting();\n        } else if (mod && e.key === '/') {\n          e.preventDefault();\n          openModal('shortcuts-modal');\n        } else if (mod && e.key === 'Enter') {\n          e.preventDefault();\n          addNewPage();\n        } else if (e.key === 'Escape') {\n          closeAllModals();\n          closeAllDropdowns();\n        }\n      });\n    }\n  <\/script>\n<\/body>\n<\/html>";

    document.querySelectorAll(".docs-workspace-frame").forEach(frame => {
      frame.addEventListener("load", () => {
        let raw = null;
        try { raw = localStorage.getItem(`python-notebook-${frame.dataset.owner}-v1`); } catch {}
        frame.contentWindow.postMessage({ type: "legacy-python-notebook", owner: frame.dataset.owner, raw }, "*");
      });
      frame.srcdoc = PYTHON_NOTES_WORKSPACE_HTML;
    });
    const appViews = [...document.querySelectorAll(".app-view")];
    function showAppView(id, updateHash = true) {
      if (!appViews.some(view => view.id === id)) return;
      appViews.forEach(view => { view.hidden = view.id !== id; });
      document.querySelectorAll("[data-view]").forEach(control => {
        control.setAttribute("aria-pressed", String(control.dataset.view === id));
      });
      if (updateHash) history.replaceState(null, "", "#" + id);
      window.scrollTo({ top: 0, behavior: "smooth" });
    }
    document.addEventListener("click", event => {
      const control = event.target.closest("[data-view]");
      if (!control) return;
      event.preventDefault();
      showAppView(control.dataset.view);
    });
    const requestedView = location.hash.slice(1);
    showAppView(appViews.some(view => view.id === requestedView) ? requestedView : "cheatsheet-view", false);
  </script>
</body>
</html>
