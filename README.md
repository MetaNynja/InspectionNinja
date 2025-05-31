# Inspection Ninja

**Author**: MetaNynja ([@MetaNynja](https://x.com/MetaNynja))

**Live Demo**: [Inspection Ninja](https://metanynja.github.io/InspectionNinja/InspectionNinja.html)

## Overview

Inspection Ninja is a web-based tool designed to provide detailed analytics and insights into tokens on the XRP Ledger (XRPL). By entering an issuer address, users can explore various levels of token information through an intuitive interface. The tool connects to XRPL nodes, fetches real-time data, and presents it in a clean, modern UI with expandable sections for deeper insights. It leverages the `xrpl.js` library for XRPL interactions and `axios` for external API calls to services like DexScreener and xrpl.to.

The project is built with HTML, CSS, and JavaScript, featuring a responsive design with a sleek console-like interface. It supports multiple scope levels, allowing users to choose the depth of analysis, from basic token metrics to detailed transfer tracking and sniper detection.

## Features

- **Interactive Console**: Users input an XRPL issuer address to retrieve token data, displayed in a dynamic, scrollable console.
- **Scope Levels**: Five distinct analysis modes (Token Metrics, DEV Inspect, Tier 1 Transfers, Tier 2 Transfers, Snipers) provide varying depths of token insights.
- **Real-Time Data**: Fetches data from XRPL nodes and external APIs for up-to-date information.
- **Responsive Design**: A modern, Apple-inspired UI with smooth animations, expandable sections, and a dropdown menu for scope selection.
- **Error Handling**: Validates issuer addresses and handles connection timeouts or API errors gracefully.
- **External Links**: Provides clickable links to XRPSCAN for transaction and account details.

## Scope Levels

Inspection Ninja offers five scope levels, accessible via a dropdown menu, each providing a different level of detail about the token and its ecosystem:

### 1. Token Metrics (overview)
- **Purpose**: Provides a high-level overview of the token's key metrics.
- **Functionality**:
  - Displays the token's currency code (e.g., 3-character code or decoded hex).
  - Shows market cap and liquidity from DexScreener.
  - Presents the current token supply and total supply burned, with an expandable section for burn transactions.
  - Lists the top 10 holders with their balances, percentages, and XRP equivalents, expandable for details.
  - Identifies if the token is an "Anti-Sniper Token" based on its activation pattern.
- **Use Case**: Ideal for users seeking a quick snapshot of a token's market presence and holder distribution.

### 2. DEV Inspect (dev)
- **Purpose**: Extends Token Metrics to include detailed analysis of the developer's (activator's) activities.
- **Functionality**:
  - Includes all Token Metrics data.
  - Displays the developer wallet address, initial supply, and current balance (with percentage of total supply).
  - Shows total tokens sold, bought, and transferred by the developer, with expandable sections for each transaction type.
  - Provides XRP received or spent in trades and the number of unique addresses tokens were transferred to.
- **Use Case**: Useful for assessing developer activity, such as token sales or distribution patterns, to evaluate project transparency and behavior.

### 3. Tier 1 Transfers (tier1)
- **Purpose**: Analyzes the first layer of token transfers from the developer to other wallets.
- **Functionality**:
  - Includes all DEV Inspect data.
  - Tracks tokens transferred by the developer to other addresses.
  - Summarizes total tokens transferred, sold, and bought by these Tier 1 wallets, along with XRP received or spent.
  - Offers expandable sections for each Tier 1 wallet, showing their received tokens, sales, and purchases.
- **Use Case**: Helps users understand how tokens flow from the developer to initial recipients, useful for detecting potential insider trading or distribution strategies.

### 4. Tier 2 Transfers (tier2)
- **Purpose**: Extends analysis to the second layer of token transfers, from Tier 1 wallets to their recipients.
- **Functionality**:
  - Includes all Tier 1 Transfers data.
  - Tracks tokens transferred from Tier 1 wallets to Tier 2 wallets.
  - Summarizes total tokens transferred, sold, and bought by Tier 2 wallets, with XRP details.
  - Provides expandable sections for each Tier 2 wallet, detailing their received tokens, sales, and purchases.
- **Use Case**: Enables deeper tracking of token distribution, revealing how tokens propagate through the ecosystem, useful for identifying broader distribution patterns or potential market manipulation.

### 5. Snipers (snipers)
- **Purpose**: Identifies the first 10 accounts that purchased the token, often referred to as "snipers."
- **Functionality**:
  - Lists the first 10 payment transactions for the token, including purchaser address, XRP spent, and tokens received.
  - Provides a clickable table with links to XRPSCAN for transaction and account details.
  - Each row is expandable to show detailed purchaser analytics, including:
    - Current token balance.
    - Total tokens bought and sold.
    - XRP spent and received.
    - Net profit or loss in XRP.
- **Use Case**: Critical for traders and analysts looking to identify early buyers who may influence price movements or hold significant stakes.

## Installation and Usage

### Clone the Repository

```bash
git clone https://github.com/MetaNynja/InspectionNinja.git
```

### Open the HTML File

Navigate to the project directory and open InspectionNinja.html in a web browser.
Alternatively, view the live demo at [Inspection Ninja](https://metanynja.github.io/InspectionNinja/InspectionNinja.html).

### Usage

Select a scope level from the dropdown menu (default: Token Metrics).
Enter a valid XRPL issuer address in the input field.
Press Enter to fetch and display the data.
Click expandable links (e.g., [expand]) to view detailed transaction lists or holder information.
In the Snipers scope, click table rows to view purchaser details.

### Limitations

**API Rate Limits**: External APIs (DexScreener, xrpl.to) may have rate limits, potentially causing timeouts or incomplete data.
**XRPL Node Reliability**: The tool relies on public XRPL nodes, which may occasionally be slow or unavailable. A fallback node is included to mitigate this.
**Transaction Limits**: To prevent excessive load, the tool limits transaction fetches to 10,000 per query.
**Browser Compatibility**: Best viewed in modern browsers (Chrome, Firefox, Safari) due to CSS features like backdrop-filter.

### Contributing

Contributions are welcome! Please fork the repository, make changes, and submit a pull request. Ensure code follows the existing style and includes clear comments.### License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.### Contact

For questions or feedback, reach out to MetaNynja on X: [@MetaNynja](https://x.com/MetaNynja).
