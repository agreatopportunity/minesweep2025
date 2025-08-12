# CyberSweeper — Multiplayer-Ready Minesweeper with Flask API

**CyberSweeper** is a futuristic, themed Minesweeper game with:
- Flask backend for storing **high scores**, **statistics**, and **daily challenges**.
- A responsive HTML/JS front-end with WebAudio sound effects.
- API validation to reduce cheating.
- Easy theming for forks & custom branding.

---

## 🚀 Features
- **Classic gameplay** with difficulty modes (`easy`, `medium`, `hard`, `expert`).
- **Leaderboard & High Scores** stored on a server.
- **Daily challenge mode** with random seeds.
- **Game statistics** (win rates, best times, recent plays).
- **Cheat prevention**: move validation, realistic timing.
- **Mobile-friendly** UI.
- **Sound effects** powered by WebAudio (no assets required).

---

## 📂 Project Structure

```bash
├── backend/                 # Flask API
│   ├── app.py               # Main server entry
│   ├── minesweep\_api.py     # Minesweeper endpoints
│   ├── database.py          # DB connection helpers
│   └── ...
├── frontend/
│   ├── minesweep.html       # Game UI
│   ├── styles.css           # Theme styles
│   ├── game.js              # Core game logic
│   ├── api-integration.js   # API ↔ game bridge
│   └── ...
├── docs/
│   └── screenshot.png
└── README.md
````


## 🛠️ Setup & Installation

### 1. Clone the Repository
```bash
git clone https://github.com/YOURUSERNAME/cybersweeper.git
cd cybersweeper
````

### 2. Backend (Flask)

**Requirements**:

* Python 3.9+
* MySQL or MariaDB

Install dependencies:

```bash
pip install -r requirements.txt
```

Create a `.env` file in `backend/`:

```env
FLASK_ENV=production
DB_HOST=localhost
DB_USER=your_db_user
DB_PASSWORD=your_db_password
DB_NAME=cybersweeper
```

Initialize the database:

```bash
python app.py
```

On first run, tables will be auto-created.

Run the server:

```bash
flask run --host=0.0.0.0 --port=5000
```

Your API is now available at `http://localhost:5000`.

---

### 3. Frontend

Open `frontend/minesweep.html` in your browser **or** serve it from a static host (e.g., GitHub Pages, Nginx, Apache).

Update the `API_BASE` in `api-integration.js` to point to your backend:

```js
const API_BASE = 'https://your-server.com';
```

---

## 🔧 Customization

* **Theme Colors** → Edit `styles.css`.
* **Logo & Title** → Change `<title>` and header in `minesweep.html`.
* **Sound Effects** → Modify `sfx` section in `api-integration.js`.
* **Game Difficulty Settings** → Adjust `difficultySettings` in `game.js` or in backend daily challenge logic.

---

## 🌐 API Reference

The Flask backend exposes:

* `GET /api/minesweep/high_scores` — Top scores.
* `POST /api/minesweep/high_scores` — Save score.
* `GET /api/minesweep/statistics` — Stats overview.
* `GET /api/minesweep/daily_challenge` — Daily puzzle data.
* `POST /api/minesweep/validate_game` — Verify game authenticity.
* `GET /api/health` — Health check.


---

## 🤝 Contributing

Fork the repo, make changes, and submit a PR.

1. Fork this repository.
2. Create your feature branch:

   ```bash
   git checkout -b feature/my-feature
   ```
3. Commit changes:

   ```bash
   git commit -am 'Add some feature'
   ```
4. Push branch:

   ```bash
   git push origin feature/my-feature
   ```
5. Create a pull request.

---

## 📜 License

MIT License — feel free to use, modify, and share.

---

## 💡 Tips for Forkers

* You can rebrand the game easily — change styles, background images, and difficulty.
* Hosting on GitHub Pages + a free backend (Heroku, Render, Railway) makes it playable online.
* If you want a **single-player offline version**, disable API calls in `api-integration.js`.

---

**Have fun sweeping mines!**
