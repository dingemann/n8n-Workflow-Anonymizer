# 🔒 n8n Workflow Anonymizer

![Tech Stack](https://img.shields.io/badge/Tech-HTML%2FCSS%2FJS-blue?style=for-the-badge)
![Privacy First](https://img.shields.io/badge/Privacy-100%25%20Local-brightgreen?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-purple?style=for-the-badge)

A privacy-first, single-page web application to automatically find and replace sensitive data in your n8n workflow JSON files. Perfect for safely sharing your workflows on GitHub, in forums, or with colleagues.

**It runs entirely in your browser. No data is ever uploaded or stored.**

---



## 🤔 Why This Tool?

Sharing n8n workflows is a great way to collaborate and get help, but they often contain sensitive information like API keys, credential IDs, and personal identifiers. Manually cleaning these files is tedious, error-prone, and risky.

This tool automates the process, providing a fast, reliable, and secure way to anonymize your workflows with confidence.

## ✨ Key Features

*   **100% Browser-Based:** All processing happens locally on your machine. Your files and data never leave your browser.
*   **Zero Dependencies:** It's a single HTML file. No installation, no build tools, no `npm install`. Just download and open.
*   **Automatic Detection:** Intelligently finds sensitive data based on common n8n patterns and keywords.
*   **Interactive Control:** Review all potential changes in a clear mapping table and choose what to anonymize with simple checkboxes.
*   **Comprehensive Reports:** Download the cleaned JSON workflow and a Markdown report detailing every change made.
*   **Modern UI:** Clean, minimalist interface with both Light and Dark modes.
*   **Drag & Drop:** A quick and easy way to load your workflow file.

## 🚀 How to Use

1.  **Download:** Grab the `anonymizer.html` file from this repository.
2.  **Open:** Open the file in any modern web browser (Chrome, Firefox, Safari, Edge).
3.  **Upload:** Drag and drop your n8n workflow `.json` file onto the designated area, or click to select it from your computer.
4.  **Review & Customize:** The app will instantly analyze the file.
    *   Review the summary of found data.
    *   Use the checkboxes to enable or disable anonymization for specific categories.
    *   Inspect the detailed "Mapping Preview" table to see every proposed change.
5.  **Download:**
    *   Click **"Download Anonymized JSON"** to get the cleaned file.
    *   Click **"Download Mapping Report"** for a Markdown file documenting the changes.

## 🔎 What It Anonymizes

The tool is designed to detect and replace the following types of sensitive information:

| Data Type | Example Field Paths & Patterns | Placeholder |
| :--- | :--- | :--- |
| **Credential IDs & Names** | `credentials.openAiApi.id`<br>`credentials.googleSheetsOAuth2Api.name` | `YOUR_OPENAI_CREDENTIAL_ID`<br>`Your Google Sheets Credential` |
| **API Keys & Tokens** | `parameters.apiKey.value`<br>`headerParameters[].value` where `name` is `x-api-key` or `Authorization`<br>`queryParameters[].value` where `name` is `key` or `cx` | `YOUR_API_KEY`<br>`Bearer YOUR_BEARER_TOKEN` |
| **Google Document IDs** | `parameters.documentId.value`<br>ID extracted from `parameters.documentId.cachedResultUrl` | An empty string (`""`) |
| **Instance & Metadata** | `meta.instanceId`<br>Root-level `id`<br>`settings.errorWorkflow` | `YOUR_N8N_INSTANCE_ID`<br>`YOUR_WORKFLOW_ID`<br>An empty string (`""`) |
| **Email Addresses** | Any string matching an email pattern found in values. | `your-email@example.com` |

## 🛡️ Privacy & Security

This is the most important feature of the tool.

*   **Everything is Local:** The application logic runs entirely within your web browser using JavaScript.
*   **No Server Communication:** Your files, their contents, and any derived data are **never** sent to a server. You can verify this by checking the network tab in your browser's developer tools.
*   **Offline Use:** Once you've downloaded the `anonymizer.html` file, you can disconnect from the internet and the tool will still work perfectly.
*   **Open Source:** The complete source code is in a single, easy-to-read file. You can inspect it yourself to be 100% sure of what it does.

## 🛠️ Technology Stack

*   **HTML5**
*   **CSS3** (with CSS Variables for easy theming)
*   **Vanilla JavaScript (ES6+)**

This project was intentionally built without any frameworks, libraries, or build steps to ensure it is lightweight, transparent, and universally runnable.

## 🤝 Contributing

Feedback and contributions are welcome! If you find a bug, have a suggestion for a new feature, or identify a pattern of sensitive data that isn't being caught, please [open an issue](https://github.com/YOUR_USERNAME/YOUR_REPO/issues).

## 📄 License

This project is licensed under the Creative Commons Zero (CC0). See the [LICENSE](LICENSE) file for details.
