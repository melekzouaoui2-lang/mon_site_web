<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>NovaBank — Connexion (exemple)</title>
<style>
  :root {
    --bg: #f3f5f8;
    --card-bg: #ffffff;
    --text: #1a1f36;
    --muted: #6b7280;
    --primary: #1d4ed8;
    --primary-hover: #1e40af;
    --border: #d1d5db;
    --error: #dc2626;
    color-scheme: light dark;
  }
  @media (prefers-color-scheme: dark) {
    :root:not([data-theme="light"]) {
      --bg: #0f1420;
      --card-bg: #1a2030;
      --text: #e5e7eb;
      --muted: #9aa3b2;
      --primary: #3b82f6;
      --primary-hover: #60a5fa;
      --border: #333c4e;
    }
  }
  :root[data-theme="dark"] {
    --bg: #0f1420;
    --card-bg: #1a2030;
    --text: #e5e7eb;
    --muted: #9aa3b2;
    --primary: #3b82f6;
    --primary-hover: #60a5fa;
    --border: #333c4e;
  }
  * { box-sizing: border-box; }
  html, body {
    height: 100%;
    margin: 0;
  }
  body {
    background: var(--bg);
    color: var(--text);
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Arial, sans-serif;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 24px;
    padding-top: calc(24px + env(safe-area-inset-top, 0px));
    padding-bottom: calc(24px + env(safe-area-inset-bottom, 0px));
  }
  .card {
    background: var(--card-bg);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 32px;
    width: 100%;
    max-width: 380px;
    box-shadow: 0 10px 30px rgba(0,0,0,0.08);
  }
  .logo {
    display: flex;
    align-items: center;
    gap: 8px;
    margin-bottom: 24px;
    font-weight: 700;
    font-size: 1.2rem;
    color: var(--primary);
  }
  .logo-icon {
    width: 28px; height: 28px;
    border-radius: 8px;
    background: var(--primary);
    display: flex; align-items: center; justify-content: center;
    color: white; font-size: 0.9rem;
    object-fit: cover;
  }
  h1 {
    font-size: 1.1rem;
    margin: 0 0 4px;
  }
  p.sub {
    color: var(--muted);
    font-size: 0.9rem;
    margin: 0 0 24px;
  }
  label {
    display: block;
    font-size: 0.85rem;
    margin-bottom: 6px;
    color: var(--text);
  }
  .field {
    margin-bottom: 16px;
  }
  input[type="text"],
  input[type="password"] {
    width: 100%;
    padding: 11px 12px;
    border: 1px solid var(--border);
    border-radius: 8px;
    background: transparent;
    color: var(--text);
    font-size: 0.95rem;
    outline: none;
    transition: border-color 0.15s;
  }
  input:focus {
    border-color: var(--primary);
  }
  .error {
    color: var(--error);
    font-size: 0.8rem;
    margin-top: 6px;
    display: none;
  }
  .error.show { display: block; }
  button {
    width: 100%;
    padding: 12px;
    background: var(--primary);
    color: white;
    border: none;
    border-radius: 8px;
    font-size: 0.95rem;
    font-weight: 600;
    cursor: pointer;
    margin-top: 8px;
    transition: background 0.15s;
  }
  button:hover { background: var(--primary-hover); }
  .foot {
    text-align: center;
    margin-top: 18px;
    font-size: 0.82rem;
    color: var(--muted);
  }
  .notice {
    margin-top: 20px;
    padding: 10px 12px;
    border-radius: 8px;
    background: rgba(29,78,216,0.08);
    color: var(--muted);
    font-size: 0.75rem;
    line-height: 1.4;
  }
</style>
</head>
<body>
  <div class="card">
    <div class="logo">
      <img src="logo.jpg" alt="Logo NovaBank" class="logo-icon">
      BIAT
    </div>
    <h1>Connexion à votre compte</h1>
    <p class="sub">Entrez vos identifiants pour continuer</p>

    <form id="loginForm" novalidate>
      <div class="field">
        <label for="username">Identifiant</label>
        <input type="text" id="username" name="username" autocomplete="username" required>
      </div>
      <div class="field">
        <label for="password">Mot de passe</label>
        <input type="password" id="password" name="password" autocomplete="current-password" required>
        <div class="error" id="errorMsg">Veuillez remplir les deux champs.</div>
      </div>
      <button type="submit">Se connecter</button>
    </form>

    <div class="foot">Mot de passe oublié ? Créer un compte</div>

    
  </div>

<script>
  document.getElementById('loginForm').addEventListener('submit', function(e) {
    e.preventDefault();
    const user = document.getElementById('username').value.trim();
    const pass = document.getElementById('password').value.trim();
    const err = document.getElementById('errorMsg');
    if (!user || !pass) {
      err.classList.add('show');
      return;
    }
    err.classList.remove('show');
    alert('Exemple uniquement : aucune authentification réelle n\'est effectuée.');
  });
</script>
</body>
</html>
