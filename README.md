# OTPX FB TOOL (Terminal & Termux Edition)
> **High-Performance Multi-Threaded Facebook Automation Suite**  
> *Engineered for Android Termux & Linux Environments*

---

## ⚡ Quick Start (Termux / Linux)

Run the following commands in your Termux or Linux terminal:

```bash
# 1. Update packages & install Git, Python and C/Crypto libraries
pkg update && pkg upgrade -y
pkg install -y git python python-cryptography libsodium

# 2. Clone the repository
git clone https://github.com/DEV-MITUL/OTPX.git

# 3. Enter the project directory
cd OTPX

# 4. Upgrade pip & install dependencies
pip install --upgrade pip
pip install -r requirements.txt

# 5. Set execution permission & Run
chmod +x otpx
./otpx
```

---

## 🎮 How to Run

### Interactive Dashboard (Recommended)
```bash
./otpx
```
*Opens the interactive dashboard menu to select modes, configure target numbers & proxies, set worker threads, and launch live execution.*

### Command Line Mode (Direct Execution)
```bash
# Mode 1: Forgot Password Recovery OTP
./otpx --mode forgot -n numbers.txt -p proxies.txt -w 10

# Mode 2: New Account Registration OTP
./otpx --mode register -n numbers.txt -p proxies.txt -w 8 --password "Pass@1234"

# Mode 3: Web Confirmation & Password Reset
./otpx --mode confirm -n numbers.txt -p proxies.txt -w 5

# Mode 4: Fast Number / Account Filter (Live vs New No-OTP)
./otpx --mode filter -n numbers.txt -p proxies.txt -w 10
```

---

## ⚙️ Features & Modes

| Mode | Flag | Description |
|:---|:---|:---|
| **Forgot Password** | `--mode forgot` | Target search & SMS recovery OTP dispatch. |
| **Registration** | `--mode register` | Account creation & SMS verification dispatch. |
| **Web Confirm** | `--mode confirm` | Verification confirmation & automated password reset. |
| **Number Filter** | `--mode filter` | Super fast Facebook account lookup without OTP (`found.txt` vs `not_found.txt`). |

---

## 📄 File Formats

### 1. Target Numbers (`numbers.txt`)
Put one phone number per line (international or local format):
```text
+8801712345678
+33752211680
01812345678
```

### 2. Proxies (`proxies.txt`)
Supports HTTP, HTTPS, SOCKS4, and SOCKS5 (with or without auth):
```text
http://user:pass@ip:port
socks5://127.0.0.1:9050
ip:port:user:pass
ip:port
```

---

## 🔐 License Activation

The software requires hardware-bound license activation:

1. Launch `./otpx` to view your unique **Device ID (HWID)**.
2. Send your Device ID to the bot or admin to receive your license key:
   - **Telegram Bot**: [@otpx_license_bot](https://t.me/otpx_license_bot)
   - **Admin**: [@mitul_islam](https://t.me/mitul_islam)
3. Enter your license key in the prompt or use CLI:
   ```bash
   ./otpx -k OTPX-XXXX-XXXX-XXXX
   ```

---

## 📊 Output Files

All results are automatically saved in the `output/` directory:
- `output/otp_sent.txt` — Real-time list of successful OTP dispatches.
- `output/found.txt` / `output/pc.txt` — Numbers with active Facebook accounts (Filter mode).
- `output/not_found.txt` / `output/new.txt` — Fresh numbers with no Facebook account (Filter mode).
- `output/error.txt` — Numbers that encountered network/rate-limit errors.
- `output/created_accounts.txt` — Saved credentials (Registration mode).

---

## 👤 Support & Contact
- **Developer**: [@mitul_islam](https://t.me/mitul_islam)
- **License Bot**: [@otpx_license_bot](https://t.me/otpx_license_bot)
