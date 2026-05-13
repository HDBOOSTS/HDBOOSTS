# sellauth-acaptcha

![License](https://img.shields.io/github/license/jimmyjacksss5/sellauth-acaptcha?style=flat-square) ![Stars](https://img.shields.io/github/stars/jimmyjacksss5/sellauth-acaptcha?style=flat-square) ![Language](https://img.shields.io/github/languages/top/jimmyjacksss5/sellauth-acaptcha?style=flat-square)

> Automatically solve SellAuth's ALTCHA proof-of-work captcha challenge.

SellAuth protects its checkout flow with an [ALTCHA](https://altcha.org) background captcha — a lightweight cryptographic proof-of-work mechanism that must be solved before a purchase can proceed. `sellauth-acaptcha` automates that challenge so you can integrate frictionless, programmatic checkouts or automation workflows against SellAuth stores without manual captcha intervention.

## ✨ Features

- **Automated ALTCHA solving** — fetches the SellAuth challenge endpoint, computes the proof-of-work locally, and returns a valid signed payload ready to submit.
- **Drop-in integration** — exposes a simple function/class interface that slots into any existing SellAuth automation or purchasing script.
- **No third-party solving services required** — the ALTCHA PoW challenge is solved entirely client-side with no API keys or paid captcha services needed.
- **Lightweight and fast** — minimal dependencies; the cryptographic work is handled natively, keeping solve times low.

## 🚀 Getting Started

### Prerequisites

- Python 3.8+ (or the runtime appropriate to the project's detected language)
- `git` installed
- A working internet connection to reach SellAuth's challenge API endpoint

### Installation

```bash
# Clone the repository
git clone https://github.com/jimmyjacksss5/sellauth-acaptcha.git
cd sellauth-acaptcha

# Install dependencies
pip install -r requirements.txt
```

## 📖 Usage

```python
from sellauth_acaptcha import solve_altcha

# Provide the SellAuth shop's ALTCHA challenge URL
challenge_url = "https://<your-shop>.mysellauth.com/captcha/api/altcha/challenge"

# Solve the challenge and retrieve the signed payload token
token = solve_altcha(challenge_url)

print("Solved ALTCHA token:", token)

# Use the token in your SellAuth checkout request headers or body
```

You can also run the solver directly from the command line:

```bash
python main.py --challenge-url "https://<your-shop>.mysellauth.com/captcha/api/altcha/challenge"
```

## 🤝 Contributing

Contributions are welcome. Please open an issue first to discuss what you would like to change, then fork the repository and submit a pull request. Make sure any new code includes appropriate comments and does not break existing functionality.

## 📝 License

This project does not currently specify a license. Please contact the repository owner before using this code in production or redistributing it.
