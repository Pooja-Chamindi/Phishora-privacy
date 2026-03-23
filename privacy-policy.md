# Phishora – Privacy Policy

**Last updated: March 2026**

## Overview

Phishora is a browser extension for phishing website detection using hybrid machine learning. This privacy policy explains what data the extension collects, how it is used, and how it is protected.

## What Data Does Phishora Collect?

Phishora collects the following data **only when the user clicks the "Analyze Website" button**:

- **URL of the active tab** — The web address of the currently visited website is read to extract structural features (such as URL length, HTTPS status, number of subdomains, and special character counts) for phishing classification.
- **Redirect counts** — The extension monitors HTTP redirect events within the active tab session to count normal redirects and self-redirects. Redirect chaining is a common phishing technique and these counts are used as classification features.
- **User feedback** — If the user voluntarily clicks the Yes/No feedback buttons, the prediction result and the user's correction are recorded to improve the adaptive learning model.

## How Is the Data Used?

- URL features and redirect counts are sent **only to a local prediction server running on the user's own machine** (localhost:5000) for phishing analysis.
- The hybrid machine learning model (Random Forest + Deep Neural Network + Adaptive Random Forest) analyses the extracted features and returns a classification verdict.
- User feedback is used to incrementally train the Adaptive Random Forest model for improved detection accuracy over time.

## What Data Is Stored?

- **Scan history** (last 100 analyses) is stored locally on the user's device using `chrome.storage.local`. This includes the URL, prediction result, confidence scores, and timestamp.
- **Adaptive learning state** (sample count, drift events, model weight) is stored on the local server's file system.
- **No data is stored on any external server, cloud service, or remote database.**

## Data Sharing

Phishora does **NOT**:

- Send any user data to external servers, third parties, or cloud services
- Use any data for advertising, analytics, tracking, or profiling
- Sell, transfer, or share user data with any third party
- Collect browsing history beyond the single URL being analysed

All processing happens entirely on the user's local machine.

## Data Security

- All communication between the browser extension and the prediction server occurs over localhost (127.0.0.1), ensuring no data leaves the user's machine.
- No personal information (names, emails, passwords, form data) is collected at any point.

## Permissions Used

| Permission | Purpose |
|------------|---------|
| `tabs` | Read the URL of the active tab for phishing analysis |
| `activeTab` | Access the current tab when the user initiates analysis |
| `webRequest` | Monitor redirect events to count URL redirects for classification |
| `webNavigation` | Detect new page navigations to reset redirect counters |
| `storage` | Store scan history locally on the user's device |
| `host_permissions: <all_urls>` | Enable redirect monitoring across all domains, as phishing sites can exist on any domain |

## User Rights

- Users can clear their scan history at any time by clearing Chrome extension storage
- Users can uninstall the extension at any time to remove all locally stored data
- No account or registration is required to use Phishora

## Limited Use Disclosure

The use of information received from Google APIs adheres to the Chrome Web Store User Data Policy, including the Limited Use requirements.

## Changes to This Policy

Any changes to this privacy policy will be reflected in an updated version of this document with a revised "Last updated" date.

## Contact

For questions or concerns about this privacy policy, please contact:

**Pooja Chamindi Malagala**  
Email: poojachamindi2001@gmail.com

---

*This privacy policy applies to the Phishora browser extension published on the Chrome Web Store.*
