# BHEH's AdminPanelFetcher

<p align="center">
<a href="https://www.blackhatethicalhacking.com"><img src="https://www.blackhatethicalhacking.com/wp-content/uploads/2022/06/BHEH_logo.png" width="300px" alt="BHEH"></a>
</p>

<p align="center">

**If you think you can hide your Admin Panel, think again... Find it with AdminPanelFetcher.**

</p>

---

**AdminPanelFetcher** is written by **Chris "SaintDruG" Abou-Chabke** from **Black Hat Ethical Hacking** and is designed specifically for **Red Teams**, **Offensive Security Experts**, and **Bug Bounty Hunters** looking to discover hidden or obscured admin panels efficiently.

---

<p align="center">
<img src="https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExdnFyZDBza3luMnl2c2gwNDcwMmp3YTY5YnA0dWI0ZjBocmR2Z3J0byZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/11shDO8NnZDYpa/giphy.gif" width="500px" alt="Matrix Animation">
</p>


---

## Description

**AdminPanelFetcher** is a professional-grade tool to find hidden admin panels on web applications.  
Instead of bundling a static wordlist and bloating the tool, it **fetches an updated admin panel wordlist** directly from our GitHub repository.

- This keeps the tool **lightweight** and **easy to maintain**.
- Whenever we update the hosted wordlist, **the tool automatically benefits**, without needing to update the script itself.

**Key technical improvements:**
- Multithreaded scanning using curl
- Proper HTTPS and `www.` handling to fix SSL issues
- Real redirect following (`-L` curl flag) bypasses WAFs and Cloudflare protections
- No proxychains/Tor dependency (due to their unreliability for professional offensive operations)
- Optional randomized User-Agent headers (`-ua`) to simulate real traffic

AdminPanelFetcher focuses on **speed**, **reliability**, and **accuracy** while staying very simple to operate.

---

## The Flow Behind It

- **Fetch Updated Wordlist**  
  Downloads the latest `magic_admin_paths.txt` from GitHub automatically.

- **Prepare Target Domain**  
  Adds `www.` if missing, forces HTTPS, solving common SSL and cert mismatch problems.

- **Build and Launch Curl Requests**  
  Constructs lightweight curl calls to quickly test admin paths with correct flags.

- **Multithreaded Scanning**  
  Scans many paths at once using multiple threads to improve speed.

- **Color-Coded Result Parsing**  
  Displays results with colors based on HTTP response codes for easy reading:
  - 200 (OK) in green
  - 301/302 (Redirects) in cyan
  - 403 (Forbidden) in yellow
  - 404 (Not Found) in red
  - Other codes in magenta

- **Log Successful Admin Panels**  
  Admin panels found (200 OK) are automatically saved inside a folder under `results/{target_domain}/found_panels.txt`.

---

## Features

- Lightweight and portable (single Python3 script)
- Automatic admin paths updates from GitHub
- Bypasses Cloudflare and WordPress redirects properly
- Realistic User-Agent randomization with `-ua`
- Multithreaded scanning (default 5 threads, customizable)
- SSL/TLS handling built-in (always uses HTTPS + www)
- Color-coded live scan results
- Only real 200 OK pages saved
- Fancy banners, motivational quotes, rainbow CLI styling
- Over 10,000+ Wordlists Specifically Aimed for Admin Panel Search

---

## Screenshots

![1](https://github.com/user-attachments/assets/bcf6126f-9eee-455a-8429-d0ecd8026ba7)
![2](https://github.com/user-attachments/assets/88ff852a-c643-479e-9583-ce17a4a09487)



---

# Compatibility: 

This tool has been tested on Kali Linux

---

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/blackhatethicalhacking/AdminPanelFetcher.git
   cd AdminPanelFetcher
   ```

2. Make the installer executable:
   ```bash
   chmod +x installer.sh
   ```

3. Run the installer:
   ```bash
   ./installer.sh
   ```

---

## What installer.sh does

- Updates APT repositories
- Installs system packages:
  - `curl`
  - `toilet`
  - `lolcat`
- Installs required Python3 libraries:
  - `requests`
  - `termcolor`
  - `urllib3`
- Makes `admin_panel_fetcher.py` executable automatically

After installation, simply run:

```bash
./admin_panel_fetcher.py -t example.com -th 10
```

Optionally with randomized User-Agent:

```bash
./admin_panel_fetcher.py -t example.com -th 10 -ua
```

---

# Disclaimer

This tool is provided for educational and research purpose only. The author of this project are no way responsible for any misuse of this tool. 
We use it to test under NDA agreements with clients and their consents for pentesting purposes and we never encourage to misuse or take responsibility for any damage caused !

<h2 align="center">
  <a href="https://store.blackhatethicalhacking.com/" target="_blank">BHEH Official Merch</a>
</h2>

<p align="center">
Introducing our Merch Store, designed for the Offensive Security community. Explore a curated collection of apparel and drinkware, perfect for both professionals and enthusiasts. Our selection includes premium t-shirts, hoodies, and mugs, each featuring bold hacking-themed slogans and graphics that embody the spirit of red teaming and offensive security. 
Hack with style and showcase your dedication to hacker culture with gear that’s as dynamic and resilient as you are. 😊
</p>

<p align="center">

<img src="https://github.com/blackhatethicalhacking/blackhatethicalhacking/blob/main/Merch_Promo.gif" width="540px" height="540">
  </p>

