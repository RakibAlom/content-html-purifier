# Content HTML Purifier 🚀

This is a versatile, client-side web application designed to help you clean and manage HTML content with ease. It features a robust WYSIWYG editor, a precise HTML purifier, and a simple note-taking system, all within a single HTML file for ultimate portability.

Whether you're pasting messy content from Google Docs, a webpage, or any other source, this tool will strip away unwanted inline styles, extraneous attributes, and non-semantic tags, leaving you with clean, professional, and semantic HTML.

---

## ✨ Features

* **WYSIWYG Editor:** A rich text editor that lets you format your content (bold, italic, lists, headings, links, images, etc.) visually.
* **HTML Purification:** Automatically cleans pasted HTML and provides a dedicated view for the purified source code.
* **Note Management:** Create, save, load, rename, and delete multiple notes directly in your browser's local storage. Your notes persist even after you close the browser.
* **Source Code Toggle:** Seamlessly switch between the visual editor and the raw HTML source code. You can edit the source directly and apply changes.
* **Link Editor:** A convenient pop-up interface for easily adding, editing, and removing hyperlinks within your content.
* **Responsive Design:** Optimized for both desktop and mobile devices, ensuring a smooth editing experience on any screen size.
* **Single File Deployment:** The entire application is self-contained in one `index.html` file, making it incredibly easy to use and share.

---

## 🚀 How to Use

This tool is designed for simplicity. You don't need any complex setup or installation.

1.  **Download/Save:** Simply download the `index.html` file or copy its entire content and save it as `index.html` on your computer.
2.  **Open in Browser:** Double-click the `index.html` file, or drag and drop it into your web browser. The application will open directly.

### Managing Notes

* **Create New Note:** Click the "**New Note**" button in the left sidebar to start a fresh, empty note.
* **Select Note:** Click on any note title in the sidebar to load its content into the editor. The active note will be highlighted.
* **Rename Note:** Hover over a note in the sidebar and click the **pencil icon** (✎) to rename it.
* **Delete Note:** Hover over a note and click the **trash can icon** (🗑️) to delete it. You'll be asked for confirmation.

### Editing Content

* **Type Directly:** Just start typing in the main editor area.
* **Formatting:** Use the toolbar buttons at the top of the editor to apply formatting like **Bold**, *Italic*, Underline, Bullet Lists, Numbered Lists, Headings, and more.
* **Pasting Content (Automatic Purification):**
    * Copy HTML content from any source (e.g., a webpage, Google Docs, Word document).
    * Paste it directly into the editor area (`Ctrl+V` or `Cmd+V`).
    * The tool will **automatically purify** the pasted HTML, removing unwanted styles and attributes, and inserting clean, semantic HTML into your document.
* **Inserting Links:**
    * Select the text you want to turn into a link.
    * Click the "**Link**" button in the toolbar.
    * A small pop-up editor will appear. Enter the URL (e.g., `https://example.com`) and click the checkmark (✓) to apply.
    * To edit an existing link, click on the linked text in the editor. The link editor will pop up, allowing you to change the URL or remove the link.
    * To remove a link, click on the linked text, then click the cross (✕) button in the link editor.

### Working with Source Code

* **Show Source Code:** Click the "**Show Source Code**" button in the top-right of the editor toolbar. The visual editor will hide, and a text area displaying the cleaned HTML source will appear.
* **Edit Source Code:** You can directly modify the HTML in the source code text area.
* **Apply Changes:** After making edits in the source code, click the "**Apply Changes & Hide Source**" button at the bottom of the source code view to update the visual editor and switch back.

---

## 🧹 How the HTML is Cleaned/Purified

The tool employs a robust `purifyHtml` function that meticulously processes your HTML content to ensure it's clean, semantic, and free from common bloat. Here's a detailed breakdown of the purification steps:

1.  **HTML Comment Removal:**
    * All HTML comments (``) are identified and completely removed from the document.

2.  **Attribute Stripping & Specific Tag Handling:**
    * A comprehensive list of attributes known to cause styling conflicts or unnecessary bloat are removed from *all* elements. This includes: `style`, `class`, `id`, `data-mce-style`, `data-font-weight`, `lang`, `dir`, `align`, `valign`, `border`, `cellspacing`, `cellpadding`, `width`, `height`, `background`, `bgcolor`, `color`, `face`, `size`, `role`, `aria-hidden`, `tabindex`, `itemprop`, `itemscope`, `itemtype`, `xml:lang`, `contenteditable`.
    * **Links (`<a>` tags):** Only essential attributes like `href`, `target`, `title`, and `rel` are preserved. External links (`href` not originating from the current domain) are automatically given `target="_blank"` and `rel="noopener noreferrer"` for security and best practice.
    * **Images (`<img>` tags):** Only `src`, `alt`, and `title` attributes are retained.

3.  **Unwrapping Redundant Tags:**
    * Specific tags that often carry unnecessary formatting or semantic weight from external sources are unwrapped. This means their content is moved directly to their parent, and the tags themselves are removed. This applies to:
        * `<font>`
        * `<center>`
        * `<span>` (Spans are aggressively unwrapped regardless of remaining attributes, as they are often used for inline styling that is stripped anyway).

4.  **Empty Tag Removal:**
    * Empty block-level elements (`<p>`, `<h1>` to `<h6>`, `<ul>`, `<ol>`, `<li>`, `<blockquote>`, `<div>`, `<td>`, `<th>`) are removed if they contain no meaningful content (i.e., no text and no non-empty child elements, excluding `<br>`, `<img>`, `hr`).
    * Some inline tags (`<a>`, `<strong>`, `<em>`, `<b>`, `i>`, `<s>`, `<u>`) are also removed if they become completely empty after purification.

5.  **Clean-up of `<br>` Tags:**
    * Leading and trailing `<br>` tags within block elements (like `<p>`, `<div>`, headings, list items, etc.) are removed to prevent excessive line breaks.

6.  **Consecutive/Misplaced `<br>` Tag Refinement (String-based):**
    * Multiple consecutive `<br>` tags are reduced to a single `<br>`.
    * `<br>` tags immediately followed or preceded by block-level HTML tags are removed, as the block tags inherently provide line breaks.

This systematic approach ensures that your HTML output is lean, semantically correct, and ready for integration into any clean web environment.

---

## 📱 Mobile Responsiveness

The tool is designed with mobile users in mind. The layout adjusts automatically for smaller screens, and interactions like button sizing and editor scrolling are optimized to provide a comfortable editing experience on smartphones and tablets.

---

## 🤝 Contribution / Development

This tool is provided as a single `index.html` file, making it easy to inspect, modify, and extend. Feel free to adapt it to your specific needs. If you make improvements, consider sharing them back!

---

## 📄 License

This project is open-source and available under the [MIT License](https://opensource.org/licenses/MIT).

---

## 👨‍💻 Author

Developed by [Rakib Alom](https://rakibalom.com/)