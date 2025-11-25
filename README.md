# Xbout (Userscript Version)

**Xbout** is a lightweight enhancement script for X (Twitter). It intuitively displays the account's **location (🌍)**, **posting device (📱)**, and **registration year (📅)** next to the user's name in tweets.

This version is a Userscript (Tampermonkey script) refactored from [the original Chrome extension](https://github.com/Yorkian/Xbout), deeply optimized for performance and anti-detection, supporting script managers like Tampermonkey and Violentmonkey.

## ⚙️ Example Display

```text
@elonmusk · Nov 24 · 🇺🇸｜🍎｜2009
```

*   **🇺🇸**: Account location is in the United States
*   **🍎**: Sent using iPhone
*   **2009**: Registered in 2009

## ✨ Main Features

*   **🌍 Location Display**: Automatically converts the account's geographical location information into corresponding flag emojis (supports 100+ countries/regions).
*   **📱 Device Recognition**: Identifies and displays the source device of the tweet:
    *   🍎 Apple (iPhone, iPad, Mac)
    *   🤖 Android
    *   💻 Web (Browser)
*   **📅 Registration Year**: Shows the year the account joined X (Twitter) (e.g., 2009).
*   **🚫 Ad Marking**: Automatically identifies and marks promoted tweets (Ad).
*   **🌗 Dark Mode**: Perfectly adapts to X's light, dim, and dark modes.

## 🚀 Performance & Optimization (v1.9+)

Compared to traditional extensions, this script version includes several core optimizations designed to provide a smoother and safer experience:

1.  **Smart On-Demand Loading (Intersection Observer)**:
    *   Requests data only when tweets appear in the screen's viewable area, significantly reducing network requests and improving page scrolling smoothness.
2.  **Anti-Detection Mechanism**:
    *   **Random Delays**: Adds 2-4 second random intervals between requests to simulate human behavior.
    *   **Rate Limit Handling**: Automatically detects API rate limits (429 errors), pauses requests for 5 minutes upon triggering to prevent temporary account blocking.
3.  **Efficient Caching System**:
    *   Data cache time extended to **7 days**, greatly reducing duplicate requests.
    *   Uses `GM_setValue` / `GM_getValue` for persistent storage, retaining data across sessions.
4.  **Dynamic Query ID Acquisition**:
    *   Automatically captures the latest GraphQL Query ID from network requests, ensuring the API interface remains valid long-term without frequent script updates.

## 📥 Installation Method

1.  **Install Manager**:
    *   First, install a userscript manager in your browser. It is recommended to use [Tampermonkey](https://www.tampermonkey.net/) or [Violentmonkey](https://violentmonkey.github.io/).
2.  **Install Script**:
    *   Visit [Greasy Fork](https://greasyfork.org/zh-CN/scripts/556898-xbout-userscript) and click install.
    *   Or directly download the `xbout.user.js` file from this project and drag it into the browser's extension management page.
3.  **Usage**:
    *   Visit [x.com](https://x.com) or [twitter.com](https://twitter.com), and the script will run automatically.



## 🛠️ Technical Details

*   **Data Source**:
    *   Fetches public account information through X's GraphQL API (`AboutAccountQuery`).
    *   Utilizes `IntersectionObserver` and `MutationObserver` to monitor DOM changes.
*   **Permission Description**:
    *   `GM_addStyle`: Injects styles.
    *   `GM_getValue` / `GM_setValue`: Reads and writes local cache.
    *   The script only runs on `x.com` and `twitter.com` domains.

## 📄 License

MIT License
