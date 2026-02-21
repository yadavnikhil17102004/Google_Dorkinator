# 🕷️ Google Dorkinator v2.0

> _An aggressive OSINT and Reconnaissance engine for automated, multi-threaded Google Dorking._

## ⚡ What is this?

Google Dorkinator is a python-based intelligence gathering tool engineered to rapidly sequence complex search operators against Google's index. It automates the tedious process of manual dorking by introducing concurrency, proxy rotation, and WAF-bypass mechanisms.

**Why?** Because discovering exposed infrastructure, leaked credentials, or vulnerable subdomains requires high-volume querying that manual searches simply cannot scale to without getting rate-limited.

## 🛠 Weaponized Capabilities

- **Mass Execution:** Feed the engine a tactical list of dorks (`-D dorks.txt`) to execute hundreds of queries sequentially or concurrently.
- **WAF Evasion Subsystem:** Integrated logic to deliberately bypass aggressive Web Application Firewalls and CAPTCHA restrictions natively.
- **Tor Proxy Routing:** Instantly tunnel all outgoing reconnaissance traffic through the Tor network (`--proxy`) to obscure origin execution and bypass IP bans.
- **Visual Intelligence Mode:** Launch a live, automated browser session to visually extract targets and validate dork latency in real time.
- **High-Velocity Concurrency:** Spin up dedicated thread pools (`-t 10`) to significantly reduce the execution time of massive OSINT campaigns.

## 🚀 Deployment

**1. Clone the Arsenal:**

```bash
git clone https://github.com/yadavnikhil17102004/Google_Dorkinator.git
cd Google_Dorkinator
```

**2. Install Core Dependencies:**
_The engine relies heavily on external libraries for proxy handling and HTML parsing._

```bash
pip install -r requirements.txt
sudo apt install tor -y
```

## 💥 Execution Syntax

The engine is highly modular. Execute `python Gorker.py` with any combination of flags:

```bash
# Execute a single strict target query against a specific domain
python Gorker.py --dork "intitle:index.of" --domain "target.com"

# Launch a massive concurrent campaign using Tor routing and 10 threads
python Gorker.py --dorks-file massive_list.txt --threads 10 --proxy --verbose

# Bypass standard limitations
python Gorker.py --dork "ext:sql intext:password" --pre-automated-browsing
```

### Command Reference:

| Flag               | Function                                                              |
| :----------------- | :-------------------------------------------------------------------- |
| `-d, --domain`     | Scope the engagement to a strict target (e.g., `site:corporate.com`). |
| `-D, --dorks-file` | Load a payload file of multiple customized queries.                   |
| `-n, --number`     | Volume of results to extract per query (Default: 10).                 |
| `-t, --threads`    | Concurrency multiplier for high-speed scanning.                       |
| `--delay`          | Injected jitter/delay to evade heuristic rate-limiting.               |
| `--proxy`          | Force all traffic through the local Tor daemon.                       |

## ⚠️ Engagement Rules

This tool is strictly engineered for authorized OSINT gathering, bug bounty hunting, and penetration testing footprinting. Users are solely responsible for ensuring operations map strictly to defined scopes of engagement.
