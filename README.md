# simple-vault

Terminal zero-knowledge password vault with email-based reset (12-digit code to leafyprojects@outlook.com).

## Setup

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python vault.py init
```

## Usage

```bash
python vault.py add --name github --username myuser --password 'super-secret'
python vault.py list
python vault.py get --name github
python vault.py request-reset
python vault.py verify-reset --code 123456789012
```

## Notes
- Passwords are encrypted locally with PBKDF2 + Fernet.
- The master password is never stored.
- The reset flow wipes the local vault and requires a fresh master password.
- The email recipient defaults to leafyprojects@outlook.com.
