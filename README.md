# SIPP Portfolio Optimiser

A secure, local-first web application designed to help you manage and rebalance your Self-Invested Personal Pension (SIPP) portfolio. This tool calculates the necessary Buy and Sell orders to align your current holdings with your target strategic allocation.

## Features

### 📊 Strategic Portfolio Management
- **Asset Tracking:** Input your current units held and live prices for various assets (e.g., Fidelity Index World, iShares S&P 500, Gold, Silver).
- **Target Allocation:** Define target percentages for each asset in your portfolio.
- **Cash Management:** Include available cash in your portfolio total to ensure accurate rebalancing.

### ⚖️ Automated Rebalancing
- **Real-time Calculations:** Instantly sees how your portfolio value changes as you update prices and units.
- **Actionable Insights:** The app automatically calculates the difference between your current holding and your target value.
- **Buy/Sell Recommendations:** Clear indicators show exactly how much of each asset you need to buy or sell to return to your target allocation.

### 🔒 Zero-Knowledge Security
- **Client-Side Encryption:** Your financial data is encrypted directly in your browser using **AES-GCM** (Advanced Encryption Standard).
- **Secure Key Derivation:** Your access code is never stored. Instead, it is used to derive an encryption key using **PBKDF2** (Password-Based Key Derivation Function 2).
- **Local Storage:** Encrypted data is stored in your browser's `localStorage`. No data is ever sent to a remote server. You own your data.

### 🎨 Modern Interface
- **Clean UI:** Built with a modern, glassmorphism-inspired design using Tailwind CSS.
- **Interactive:** Smooth animations and transitions for a pleasant user experience.

## Getting Started

1.  **Download:** Clone this repository or simply download the `index.html` file.
2.  **Open:** Double-click `index.html` to open it in your modern web browser (Chrome, Firefox, Safari, Edge).
    *   *Note: An internet connection is required initially to load the styling framework (Tailwind CSS).*

## Usage Guide

### 1. Initial Setup (Secure Gateway)
- When you first open the app, you will be prompted to create an **Access Code**.
- Choose a secure code/password. This code is used to encrypt your data.
- **Important:** If you forget this code, your data cannot be recovered, as the encryption key is derived from it.

### 2. Inputting Data
- **Available Cash:** Enter the amount of uninvested cash you have in your SIPP account.
- **Assets:** For each asset row:
    - **Units Held:** Enter the number of units you currently own.
    - **Live Price:** Enter the current market price per unit.
- The app will automatically calculate the **Portfolio Value** and compare it to your **Target** allocation.

### 3. Reviewing Actions
- Look at the **Action** column.
- **Green (BUY):** Indicates you are underweight in this asset. The amount shown is how much you need to invest.
- **Red (SELL):** Indicates you are overweight in this asset. The amount shown is the value you should sell to rebalance.
- **Balanced:** Your holding is close enough to the target (within a small margin).

### 4. Saving & Locking
- Click the **Save & Lock** button in the header.
- Your data (cash and asset details) will be encrypted and saved to your browser.
- The page will reload, returning you to the secure gateway.

### 5. Wiping Data
- If you wish to reset the application and delete all stored data, click the **Wipe Local Database** button at the bottom of the dashboard.
- This will clear your encrypted data and your access code hash from `localStorage`.

## Technical Details

- **Single Page Application (SPA):** The entire app is contained within a single HTML file.
- **Styling:** Uses [Tailwind CSS](https://tailwindcss.com/) via CDN.
- **Cryptography:** Uses the browser's native [Web Crypto API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Crypto_API).
    - **Encryption:** AES-GCM (256-bit key)
    - **Key Derivation:** PBKDF2 (SHA-256, 100,000 iterations)

## Disclaimer

**This tool is for informational and educational purposes only.** It does not constitute financial advice. Investment values can go down as well as up. Always do your own research or consult with a qualified financial advisor before making investment decisions. The authors of this software are not responsible for any financial losses incurred from using this tool.
