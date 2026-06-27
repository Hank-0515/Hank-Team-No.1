<!DOCTYPE html>
<html lang="zh-TW">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>台股技術分析預測工具</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght@300;400;500;700&family=JetBrains+Mono:wght@400;600&display=swap');

  :root {
    --bg: #0a0f1e;
    --surface: #111827;
    --card: #1a2235;
    --border: #1e3050;
    --accent-up: #00e5a0;
    --accent-down: #ff4d6d;
    --accent-neutral: #4db8ff;
    --accent-warn: #ffc14d;
    --text: #e8edf5;
    --text-dim: #6b7fa3;
    --text-mid: #a0b0cc;
    --glow-up: rgba(0,229,160,0.15);
    --glow-down: rgba(255,77,109,0.15);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Noto Sans TC', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(77,184,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(77,184,255,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    position: relative;
    z-index: 1;
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 20px 60px;
  }

  /* Header */
  header {
    padding: 40px 0 30px;
    border-bottom: 1px solid var(--border);
    margin-bottom: 36px;
  }

  .header-top {
    display: flex;
    align-items: flex-start;
    gap: 16px;
    margin-bottom: 10px;
  }

  .logo-badge {
    background: linear-gradient(135deg, #4db8ff, #00e5a0);
    border-radius: 10px;
    width: 44px;
    height: 44px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 22px;
    flex-shrink: 0;
    margin-top: 2px;
  }

  h1 {
    font-size: 28px;
    font-weight: 700;
    letter-spacing: -0.5px;
    line-height: 1.2;
  }

  h1 span {
    background: linear-gradient(90deg, #4db8ff, #00e5a0);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .subtitle {
    font-size: 13px;
    color: var(--text-dim);
    margin-top: 6px;
    line-height: 1.6;
  }

  .disclaimer-banner {
    margin-top: 14px;
    padding: 10px 14px;
    background: rgba(255,193,77,0.08);
    border: 1px solid rgba(255,193,77,0.25);
    border-radius: 8px;
    font-size: 12px;
    color: var(--accent-warn);
    display: flex;
    gap: 8px;
    align-items: flex-start;
  }

  /* Input Section */
  .input-section {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 28px;
    margin-bottom: 28px;
  }

  .section-label {
    font-size: 11px;
    font-weight: 500;
    letter-spacing: 1.5px;
    color: var(--accent-neutral);
    text-transform: uppercase;
    margin-bottom: 18px;
  }

  .input-grid {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr auto;
    gap: 14px;
    align-items: end;
  }

  @media (max-width: 720px) {
    .input-grid { grid-template-columns: 1fr 1fr; }
    .btn-analyze { grid-column: 1 / -1; }
  }

  .field label {
    display: block;
    font-size: 12px;
    color: var(--text-dim);
    margin-bottom: 8px;
    font-weight: 500;
  }

  .field input, .field select {
    width: 100%;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 11px 14px;
    color: var(--text);
    font-size: 14px;
    font-family: inherit;
    outline: none;
    transition: border-color 0.2s, box-shadow 0.2s;
  }

  .field input:focus, .field select:focus {
    border-color: var(--accent-neutral);
    box-shadow: 0 0 0 3px rgba(77,184,255,0.12);
  }

  .field input::placeholder { color: var(--text-dim); }

  .field select option { background: var(--card); }

  .btn-analyze {
    background: linear-gradient(135deg, #4db8ff, #00e5a0);
    border: none;
    border-radius: 10px;
    padding: 11px 28px;
    color: #0a0f1e;
    font-size: 14px;
    font-weight: 700;
    cursor: pointer;
    font-family: inherit;
    transition: opacity 0.2s, transform 0.1s;
    white-space: nowrap;
    height: 42px;
  }

  .btn-analyze:hover { opacity: 0.85; }
  .btn-analyze:active { transform: scale(0.97); }
  .btn-analyze:disabled { opacity: 0.4; cursor: not-allowed; }

  /* Quick picks */
  .quick-picks {
    margin-top: 14px;
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    align-items: center;
  }

  .quick-label {
    font-size: 12px;
    color: var(--text-dim);
  }

  .quick-chip {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 4px 10px;
    font-size: 12px;
    color: var(--text-mid);
    cursor: pointer;
    font-family: 'JetBrains Mono', monospace;
    transition: border-color 0.2s, color 0.2s;
  }

  .quick-chip:hover {
    border-color: var(--accent-neutral);
    color: var(--accent-neutral);
  }

  /* Loading */
  #loading {
    display: none;
    text-align: center;
    padding: 60px 20px;
  }

  .spinner {
    width: 44px;
    height: 44px;
    border: 3px solid var(--border);
    border-top-color: var(--accent-neutral);
    border-radius: 50%;
    animation: spin 0.8s linear infinite;
    margin: 0 auto 16px;
  }

  @keyframes spin { to { transform: rotate(360deg); } }

  .loading-text {
    color: var(--text-dim);
    font-size: 14px;
  }

  /* Result */
  #result { display: none; }

  /* Score Card */
  .score-card {
    background: var(--card);
    border-radius: 16px;
    padding: 28px;
    margin-bottom: 20px;
    border: 1px solid var(--border);
    position: relative;
    overflow: hidden;
  }

  .score-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 3px;
    background: linear-gradient(90deg, var(--accent-neutral), var(--accent-up));
  }

  .score-card.bullish { border-color: rgba(0,229,160,0.3); }
  .score-card.bullish::before { background: linear-gradient(90deg, #00e5a0, #4db8ff); }
  .score-card.bearish { border-color: rgba(255,77,109,0.3); }
  .score-card.bearish::before { background: linear-gradient(90deg, #ff4d6d, #ffc14d); }
  .score-card.neutral { border-color: rgba(255,193,77,0.3); }
  .score-card.neutral::before { background: linear-gradient(90deg, #ffc14d, #4db8ff); }

  .score-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    gap: 16px;
    margin-bottom: 20px;
    flex-wrap: wrap;
  }

  .stock-name-block .stock-code {
    font-family: 'JetBrains Mono', monospace;
    font-size: 28px;
    font-weight: 600;
    color: var(--text);
  }

  .stock-name-block .stock-fullname {
    font-size: 14px;
    color: var(--text-dim);
    margin-top: 3px;
  }

  .score-meter {
    text-align: right;
  }

  .score-num {
    font-family: 'JetBrains Mono', monospace;
    font-size: 48px;
    font-weight: 600;
    line-height: 1;
  }

  .score-num.bullish { color: var(--accent-up); }
  .score-num.bearish { color: var(--accent-down); }
  .score-num.neutral { color: var(--accent-warn); }

  .score-label {
    font-size: 12px;
    color: var(--text-dim);
    margin-top: 4px;
  }

  .verdict-badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 6px 14px;
    border-radius: 20px;
    font-size: 13px;
    font-weight: 700;
    letter-spacing: 0.5px;
    margin-bottom: 20px;
  }

  .verdict-badge.bullish { background: var(--glow-up); color: var(--accent-up); border: 1px solid rgba(0,229,160,0.3); }
  .verdict-badge.bearish { background: var(--glow-down); color: var(--accent-down); border: 1px solid rgba(255,77,109,0.3); }
  .verdict-badge.neutral { background: rgba(255,193,77,0.1); color: var(--accent-warn); border: 1px solid rgba(255,193,77,0.3); }

  /* Buy signal */
  .buy-signal-box {
    background: rgba(0,229,160,0.06);
    border: 1px solid rgba(0,229,160,0.2);
    border-radius: 12px;
    padding: 16px 20px;
    margin-bottom: 20px;
  }

  .buy-signal-box .bsb-title {
    font-size: 12px;
    color: var(--accent-up);
    font-weight: 600;
    letter-spacing: 1px;
    text-transform: uppercase;
    margin-bottom: 8px;
  }

  .buy-signal-box .bsb-content {
    font-size: 14px;
    color: var(--text);
    line-height: 1.7;
  }

  .buy-signal-box.wait {
    background: rgba(255,193,77,0.06);
    border-color: rgba(255,193,77,0.2);
  }

  .buy-signal-box.wait .bsb-title { color: var(--accent-warn); }

  .buy-signal-box.avoid {
    background: rgba(255,77,109,0.06);
    border-color: rgba(255,77,109,0.2);
  }

  .buy-signal-box.avoid .bsb-title { color: var(--accent-down); }

  /* Indicators grid */
  .indicators-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 12px;
    margin-bottom: 20px;
  }

  .indicator-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 14px 16px;
  }

  .ind-label {
    font-size: 11px;
    color: var(--text-dim);
    font-weight: 500;
    text-transform: uppercase;
    letter-spacing: 0.8px;
    margin-bottom: 6px;
  }

  .ind-value {
    font-family: 'JetBrains Mono', monospace;
    font-size: 18px;
    font-weight: 600;
    margin-bottom: 4px;
  }

  .ind-value.up { color: var(--accent-up); }
  .ind-value.down { color: var(--accent-down); }
  .ind-value.neutral { color: var(--accent-neutral); }
  .ind-value.warn { color: var(--accent-warn); }

  .ind-signal {
    font-size: 11px;
    color: var(--text-dim);
  }

  /* Bar progress */
  .signal-bar-wrap {
    margin-bottom: 20px;
  }

  .signal-bar-label {
    display: flex;
    justify-content: space-between;
    font-size: 12px;
    color: var(--text-dim);
    margin-bottom: 6px;
  }

  .signal-bar-track {
    height: 8px;
    background: var(--border);
    border-radius: 4px;
    overflow: hidden;
  }

  .signal-bar-fill {
    height: 100%;
    border-radius: 4px;
    transition: width 1s cubic-be
