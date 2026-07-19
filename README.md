[🌐 English](README.md) | [🇫🇷 Français](README.fr.md) 

# NEXUS-WP (v0.3-Alpha)
> Modular operating system, isolated code integrator and SaaS control console for WordPress.

NEXUS-WP is a universal engineering and optimization framework for WordPress. Designed to bypass the limitations of classic themes and page builders, it combines a lightweight local execution engine, a streamlined administration console, and a highly secure SaaS coupling to automate data rendering, custom script integration, and unified Cloud backups.

---

## 🚀 THE 4 PILLARS OF NEXUS-WP

### 1. The Workshop (Code Edition & Generators)
The Workshop is the customization and development environment of the extension. It guarantees absolute isolation between the system core and your modifications.

*   **Isolated Code Integrator (PHP, CSS, JS)**: Inject custom scripts independently from the factory infrastructure (`nx-users-*`).
    *   *Scope Security*: Automatically injects WordPress core security directives on created PHP files to prevent direct execution via URL.
    *   *Revision Backup Rotation (FIFO)*: Generates a local backup copy (`.bak`) before each write, with an intelligent rolling rotation limited to 3 revisions per type to preserve disk space.
    *   *Helper Tools (Prettycode & Minify)*: Built-in optimization tools to instantly reformat (indent) or compress (minify) your CSS and JS codes.
*   **Component Generator (Hub Cards)**: Design responsive and adaptive grid templates (`half`, `third`, `full`) with a synchronized real-time preview viewport (`NEXUS-SYNC`).
    *   *Master Shortcode `[nexus_card id="X"]`*: Calls the component, loads its factory structure, and dynamically resolves its variables (redirects, targets, logo display).
*   **Semantic Shortcode Generator**: Convert your custom Workshop structures into reusable shortcodes without touching any PHP code.

---

### 2. The Arsenal (Ready-to-Use Widgets)
The Arsenal gathers a catalog of built-in tools activatable in one click to override and correct the behavior of your theme or third-party plugins:

*   **Hygiene & Structure**: Lightweight scripts for dynamic toolbar hiding, global search optimizations, or smart sidebars.
*   **Design & Templates (Factory Overrides)**:
    *   *Elementor Optimizations*: Responsive grid improvements and background blur effects (*glassmorphism*).
    *   *Badges Styling*: Solid designs and elegant hover transitions for expertises, statuses, or ratings.
    *   *AJAX Search*: Contrast improvements and asymmetrical titles for the search widget.
    *   *Enhanced Pagination*: Dynamic observation script (`MutationObserver`) and active styling.
    *   *Placeholder Images*: Automatically generates dynamic text watermarks on default fallback images if the featured image is missing.

---

### 3. The Universal Data Engine (`[nx_field]`)
NEXUS-WP integrates a universal routing engine for data extraction, formatting, and security, using a single shortcode `[nx_field]` equipped with 14 logical gates:

1.  **`text`**: Extraction and formatting of strings (phones, currencies) with built-in array-conversion crash protection.
2.  **`wysiwyg`**: Rendering of rich text paragraphs with recursive parsing of nested shortcodes.
3.  **`link`**: Dynamic button generator (phone, email, WhatsApp, web) with library icons and fallback management.
4.  **`fallback`**: Empty content interceptor (displays alternative text or the content enclosed between the shortcode tags).
5.  **`taxonomy`**: Renders hierarchical taxonomy badges with a child-priority algorithm.
6.  **`class`**: Dynamic concatenation of CSS classes based on the current post's taxonomy slugs.
7.  **`contact`**: Structured contacts parser (detects and converts emails and phones within a string separated by a delimiter).
8.  **`list`**: Generates badge grids based on multiple distinct fields.
9.  **`url`**: Extraction of the current canonical page URL.
10. **`related`**: Asymmetrical relational query engine to list related post IDs.
11. **`icon`**: Multi-library icon injector (FontAwesome, Bootstrap Icons, Dashicons).
12. **`if`** & **`nx_if`**: Conditional logical gates to display content only if a value exists (or if it doesn't exist via the `not="true"` attribute).
13. **`image`**: Adaptive image manager with fallback image and automatic ALT text based on the active post's title.
14. **`term_list`**: Raw list of taxonomic terms without exclusions for tag displays.

---

### 4. Logistics & Nexus Cloud (The SaaS Engine)
The Logistics pillar connects the local extension to the central NEXUS SaaS infrastructure via an ultra-lightweight and asynchronous encrypted protocol:

*   **Onboarding Connection**: The user logs in using standard credentials (Email/Password) within a secure SaaS Iframe. The central server validates access, generates the technical token, and safely transmits it to WordPress.
*   **RAM Quotas Security**: The system relies on a unified security signature masked in volatile memory (RAM), preventing any local manual tampering of license quotas.
*   **Database Transaction Lock**: Before any write operation to the local database (saving licenses, global options, or Workshop configurations), the system validates the structural integrity of the registry. If the file is corrupted or incomplete, the transaction is immediately aborted to protect the site from crashes.
*   **Cloud Backups & Restores**: Compress the entire local workspace into ZIP format and send it asynchronously to your dedicated NEXUS Cloud space (up to 100 TB of mutualized storage) to secure your configurations in 1 click.
*   **Diagnostics & Server Health Console**: Displays real-time server metrics (PHP version, write permissions of the storage directory, active `OpenSSL` and `ZipArchive` extensions, network connection test) to ease technical support.

---

## 🛠️ ETHICAL ONBOARDING BEHAVIOR

*   **Automatic Redirect**: As soon as the extension is activated, a secure routing process cleanly redirects the user to the License tab (SaaS authentication Iframe).
*   **Welcome Modal (Positive Incitement)**: A warm and unique welcome modal opens to reassure the user about the free mode (Mega Free) and explain the value of the Cloud connection to secure their work for free.
*   **Ethical Deactivation (Gentle Goodbye)**: If the plugin is deactivated, no intrusive survey comes to bother the user. A polite and ethical modal warns them of the loss of their local files (if they are not backed up in their NEXUS Cloud) and wishes them a prompt return.
