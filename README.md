🤖 Telegram Group Guardian

[![Python Version](https://img.shields.io/badge/python-3.9%2B-blue.svg)](https://www.python.org/downloads/)
[![python-telegram-bot](https://img.shields.io/badge/python--telegram--bot-22.5-green.svg)](https://docs.python-telegram-bot.org/en/v22.5/)
[![Telethon](https://img.shields.io/badge/telethon-1.36%2B-orange.svg)](https://docs.telethon.dev/)
[![License](https://img.shields.io/badge/license-MIT-yellow.svg)](LICENSE)

---

✨ Features

Category	Features	
👮 Moderation	`<code>`Ban, Kick, Mute, Warn users`</code>` • `<code>`Automatic anti-spam`</code>` • `<code>`Flood control`</code>` • `<code>`Username/Blacklist filters`</code>`	
🎉 Automation	`<code>`Custom welcome/goodbye messages`</code>` • `<code>`Auto-delete messages`</code>` • `<code>`Scheduled announcements`</code>` • `<code>`Anti-link spam`</code>`	
🔐 Security	`<code>`CAPTCHA verification`</code>` • `<code>`New user restrictions`</code>` • `<code>`Admin action logging`</code>` • `<code>`Backup and restore`</code>`	
📊 Analytics	`<code>`User activity tracking`</code>` • `<code>`Command usage stats`</code>` • `<code>`Report dashboard`</code>` • `<code>`Growth metrics`</code>`	
⚡ Performance	`<code>`Async/await architecture`</code>` • `<code>`PostgreSQL/MongoDB support`</code>` • `<code>`Redis caching`</code>` • `<code>`Docker ready`</code>`	

---

🚀 Quick Start

Prerequisites

```bash
# Python 3.9 or newer required
python3 --version  # Should show 3.9+

# Install Poetry (recommended) or use pip
pip install poetry
```

Installation

```bash
# Clone the repository
git clone https://github.com/your-username/telegram-group-guardian.git
cd telegram-group-guardian

# Install dependencies
poetry install

# Or with pip
pip install -r requirements.txt
```

Configuration

Create a `.env` file in the root directory:

```bash
# Required: Telegram Bot Token (from @BotFather)
TELEGRAM_BOT_TOKEN="123456:ABC-DEF1234ghIkl-zyx57W2v1u123ew11"

# Required: Telethon API credentials (from https://my.telegram.org)
TELEGRAM_API_ID="123456"
TELEGRAM_API_HASH="your_api_hash_here"

# Optional: Database URL (defaults to SQLite)
DATABASE_URL="postgresql://user:password@localhost:5432/botdb"

# Optional: Redis for caching
REDIS_URL="redis://localhost:6379/0"

# Optional: Logging channel ID
LOG_CHANNEL_ID="-1001234567890"

# Optional: Admin user IDs (comma-separated)
ADMIN_IDS="123456789,987654321"
```

---

💡 Usage

Running the Bot

```bash
# Development mode with auto-reload
poetry run python bot.py

# Production mode with gunicorn
poetry run gunicorn bot:main -w 1 -k uvicorn.workers.UvicornWorker

# Or using Docker
docker-compose up -d
```

Basic Commands

Command	Usage	Permission	
`/help`	Show all available commands	All users	
`/warn @username`	Warn a user	Admins	
`/ban @username [reason]`	Ban a user permanently	Admins	
`/mute @username [duration]`	Mute a user (e.g., 30m, 2h, 1d)	Admins	
`/kick @username`	Kick a user from group	Admins	
`/unban @username`	Unban a user	Admins	
`/settings`	View group settings	Admins	
`/report`	Report a message to admins	All users	

Inline Admin Panel

Type `@MissCutieBot` in any chat to access the inline admin panel for quick moderation actions without leaving the chat.

---

🏗️ Architecture

```mermaid
graph TD
    A[Telegram API] --> B[python-telegram-bot];
    A --> C[Telethon Client];
    B --> D[Bot Core];
    C --> D;
    D --> E[Database Layer];
    D --> F[Redis Cache];
    D --> G[Logging System];
    E --> H[Admin Panel];
    F --> H;
    G --> I[Log Channel];
    H --> J[User Actions];
```

Tech Stack

- Framework: `python-telegram-bot` v22.5 (Async API)
- Telegram MTProto: `Telethon` v1.36+
- Database: SQLAlchemy (PostgreSQL/SQLite)
- Caching: Redis
- Configuration: `pydantic-settings`
- Logging: `structlog` with JSON output
- Containerization: Docker & Docker Compose

---

📸 Screenshots

---

🔧 Configuration Guide

Advanced Settings

Edit `config/settings.toml` to customize:

```toml
[moderation]
max_warnings = 3
spam_threshold = 5
flood_limit = 10  # messages per minute
auto_delete_duration = 300  # seconds

[welcome]
enabled = true
message_template = "Welcome {mention}! Please read the rules."
captcha_enabled = true
captcha_timeout = 300
restrict_new_users = true

[anti_spam]
delete_links = false
allowed_domains = ["youtube.com", "github.com"]
max_mentions = 5
block_forwarded_channels = true
```

---

🤝 Contributing

1. Fork the project
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

Please read `CONTRIBUTING.md` for details on our code of conduct and development process.

---

📄 License

This project is licensed under the GNU General Public License V3 License - see the [LICENSE](LICENSE) file for details.

---

🆘 Support

- 📖 Documentation: [https://misscutie.readthedocs.io](https://MissCutie.readthedocs.io)
- 💬 Discussions: [GitHub Discussions](https://github.com/saifalisew1508/MissCutie/discussions)
- 🐛 Issues: [GitHub Issues](https://github.com/saifalisew1508/MissCutie/issues)
- 📢 Updates: Follow [@BotXNews](https://t.me/BotXNews)

---

---

📝 Changelog

v2.5.0 (2025-12-??)
- ✅ Upgraded to `python-telegram-bot` v22.5
- 🚀 Added native asyncio support
- 🔒 Enhanced security with rate limiting
- 📊 New analytics dashboard
- 🐛 Bug fixes and performance improvements
