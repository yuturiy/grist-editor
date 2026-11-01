# Grist Markdown Editor

A custom [Grist](https://www.getgrist.com/) widget for editing a table's Markdown text with a WYSIWYG editor powered by [Toast UI Editor](https://github.com/nhn/tui.editor).

## Features

- Edit Markdown in WYSIWYG mode or switch to Markdown.
- Supports headings, formatting, lists, task lists, quotes, tables, links, and code blocks.
- Automatically saves changes to the selected record after a short pause or when the editor loses focus.
- Opens supported links (`http`, `https`, `mailto`, and `tel`) in a new tab.
- Converts a pasted plain-text URL into a clickable link.

## Add the widget to Grist

1. Host `index.html` somewhere Grist can access, such as GitHub Pages or another static web host.
2. In your document, add a **Custom widget** and set its URL to the hosted `index.html`.
3. Grant the widget **Full access** so it can update records.
4. In the widget's **Visible columns** settings, map **Markdown text** to the table's Text column.
5. Select a record to edit its Markdown content.

The widget expects one mapped Text column. Its internal column name is `Content`; Grist supplies the mapped column ID, which the widget uses to read and update the selected record.

## Development

This is a static HTML widget. No build step or package installation is required. The editor and Grist plugin API are loaded from their public CDNs when the page loads.

To develop locally, serve this directory over HTTP and configure the Grist custom widget to use the served `index.html`. For deployment, publish the updated file to your static host and reload the widget in Grist.
