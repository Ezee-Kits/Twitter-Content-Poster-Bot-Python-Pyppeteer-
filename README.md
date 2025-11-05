# <svg xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" width="100" height="100" viewBox="0 0 50 50">
<path d="M 11 4 C 7.134 4 4 7.134 4 11 L 4 39 C 4 42.866 7.134 46 11 46 L 39 46 C 42.866 46 46 42.866 46 39 L 46 11 C 46 7.134 42.866 4 39 4 L 11 4 z M 13.085938 13 L 21.023438 13 L 26.660156 21.009766 L 33.5 13 L 36 13 L 27.789062 22.613281 L 37.914062 37 L 29.978516 37 L 23.4375 27.707031 L 15.5 37 L 13 37 L 22.308594 26.103516 L 13.085938 13 z M 16.914062 15 L 31.021484 35 L 34.085938 35 L 19.978516 15 L 16.914062 15 z"></path>
</svg> Twitter Content Poster Bot (Python + Pyppeteer)

## 🧠 Overview
The **Twitter Content Poster Bot** is a high-performance automation system built with **Python** and **Pyppeteer**, capable of automatically posting tweets with **text, images, and videos** — no manual input required!  

Using your **saved Chrome profile**, it logs into Twitter seamlessly, writes your tweet (text or media), and posts it instantly.  
This bot mimics real human behavior, handles file uploads, and supports CSV-based data entry for organized bulk posting.  

It’s designed for **social media managers**, **business owners**, and **content creators** who want full control over Twitter automation without risking account bans or repetitive manual work.

---

## ⚡ Key Features
- 🧠 **AI-like Human Simulation:** Uses randomized delays, scrolling, and natural mouse movements.  
- 💬 **Automatic Text Posting:** Writes your tweet content automatically.  
- 🖼️ **Image & Video Uploads:** Easily attach up to 4 images per post.  
- 📄 **CSV Integration:** Reads your media and text data from CSV files for automated scheduling.  
- 🔒 **Secure Login:** Uses your cloned Chrome user data directory, so you never need to log in manually.  
- 🕶️ **Anti-Detection Mode:** Includes stealth arguments that bypass automation detection.  
- ⚙️ **Cross-Platform Support:** Works on Windows, Linux, or Android (via Termux).  
- 🧩 **Modular Design:** Divided into `Twitter.py`, `posting.py`, and `func.py` for flexible development.  

---

## 📁 Folder Structure
```
TwitterBot/
│
├── func.py              # Utility functions for clicks, scrolling, and file handling
├── Twitter.py           # Core Twitter automation logic
├── posting.py           # Main script that launches browser and triggers automation
├── data/
│   └── post_data.csv    # CSV containing tweet text and image paths
└── README.md
```

---

## 🧩 How It Works (Step-by-Step)
1. **Clone or Download the Repository**
   ```bash
   git clone https://github.com/yourusername/TwitterPosterBot.git
   cd TwitterPosterBot
   ```

2. **Install Requirements**
   ```bash
   pip install pyppeteer pandas pyperclip bs4 lxml
   ```

3. **Clone Your Chrome Profile**
   - Go to your Chrome user data directory.  
   - Copy your main profile folder (for example: `Default`) to another directory.  
   - In `posting.py`, set:
     ```python
     'userDataDir': r"C:\Users\HP\Desktop\ChromeProfileClone"
     ```

4. **Prepare Your CSV File**
   Example `post_data.csv`:
   ```csv
   PRODUCT_PIC_URLS
   ["C:\\Users\\HP\\Pictures\\tweet1.jpg", "C:\\Users\\HP\\Pictures\\tweet2.jpg"]
   ```

5. **Run the Bot**
   ```bash
   python posting.py
   ```

6. **What Happens Next**
   - Bot opens Twitter using your cloned profile.  
   - Clicks **“Post”** button.  
   - Inserts your tweet text automatically from clipboard.  
   - Uploads up to four images.  
   - Posts the tweet — all hands-free!  

---

## 🧠 Technical Breakdown
### `Twitter.py`
Handles the **core posting logic**:
- Opens tweet composer.  
- Pastes your tweet content.  
- Uploads media via file selector.  
- Clicks the **Post** button.  
- Uses `pyperclip` and `asyncio` for human-like input.  

### `posting.py`
- Launches **Pyppeteer** with Chrome executable.  
- Connects to your user profile for persistent login.  
- Opens Twitter and calls the bot from `Twitter.py`.  

### `func.py`
Includes all reusable utilities:
- `css_click_center()` / `xpath_click_center()` for reliable clicking.  
- `css_scroll_center()` / `xpath_scroll_center()` for scrolling elements into view.  
- `drop_duplicate()`, `saving_files()`, `create_dir()` for data management.  
- `click_checkboxes()` for optional checkbox automation.  

---

## 💬 Example Tweet Content
Inside `Twitter.py`:
```python
text_content = f'''

####### ENTER PRODUCT INFORMATIONS HERE DESCRIPTIONS ########

'''
```
Replace this section dynamically with your product or tweet description pulled from a DataFrame or your CSV.

---

## 🧩 Example Console Output
```
[OK] Clicked center of '[data-testid="SideNav_NewTweet_Button"]'
[OK] Tweet text pasted successfully
[OK] Uploaded 2 images
[OK] Clicked 'Post' button
✅ Tweet successfully posted!
```

---

## 🧰 Tech Stack
| Tool | Purpose |
|------|----------|
| **Python 3.9+** | Main programming language |
| **Pyppeteer** | Browser automation |
| **Asyncio** | Handles async tasks and delays |
| **Pandas** | Reads CSV and handles datasets |
| **Pyperclip** | Copies text to clipboard for pasting |
| **BeautifulSoup + LXML** | Optional parsing for webpage structures |

---

## 📱 Running on Android (Optional)
You can run the bot on **Android** using **Termux** and remote Chrome debugging:
1. Install Chrome on Android.  
2. Enable remote debugging.  
3. Connect via Pyppeteer using:
   ```python
   browser = await connect({"browserURL": "http://127.0.0.1:9222"})
   ```
4. Execute `posting.py` — your bot now runs directly from your phone!  

---

## 💡 Tips & Notes
- Always use a cloned Chrome profile to avoid security flags.  
- Adjust sleep delays (`asyncio.sleep()`) for smoother execution.  
- Keep the Chrome executable path accurate.  
- Update your selectors/XPaths if Twitter UI changes.  

---

## 📈 Future Upgrades
- 🔁 **Bulk Tweet Scheduling** with CSV time fields.  
- 📅 **Auto-Post at Specific Times** using `asyncio` scheduling.  
- 🎥 **Video Upload Support.**  
- 💬 **Reply or Retweet Automation.**  
- 📊 **Analytics Dashboard** to track tweet history.  

---

## 👨‍💻 Author
**Peter (Ezee Kits)**  
📺 YouTube: [@Ezee_Kits](https://www.youtube.com/@Ezee_Kits)  
💬 Topics: Python, Automation, Technology, DIY, and Engineering  

---

## ⚖️ License
This project is open-source under the **MIT License**.  
You are free to modify, use, and distribute it for educational or personal use.  

---

## ✨ Short SEO Description
A powerful **Twitter Content Poster Bot** built with **Python + Pyppeteer**.  
Automatically posts tweets (text, images, and videos) using your Chrome profile — safe, fast, and human-like. Perfect for creators, marketers, and developers automating Twitter posting.
