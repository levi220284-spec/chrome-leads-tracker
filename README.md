# Leads Tracker

A simple Chrome extension for saving links you want to come back to later. Type or paste a link, or save whatever tab you currently have open, and it stays in a list inside the extension popup.

## Features

- Save a link by typing or pasting it into the input box
- Save the URL of your currently active tab with one click
- View all saved links in a simple list, each one clickable
- Delete all saved links at once
- Links persist between browser sessions using `localStorage`

## Installation (unpacked extension)

Chrome extensions in development aren't installed from the Chrome Web Store, they're loaded manually. Steps:

1. Clone this repository
   ```
   git clone https://github.com/levi220284-spec/leads-tracker-extension.git
   ```
2. Open Chrome and go to `chrome://extensions`
3. Turn on **Developer mode** (top right corner)
4. Click **Load unpacked**
5. Select the folder you just cloned
6. The extension icon should now appear in your toolbar

## File structure

```
leads-tracker-extension/
├── index.html      popup layout
├── style.css        popup styling
├── index.js         all the save/delete/render logic
└── manifest.json     extension config (name, permissions, popup)
```

## How it works

- `myLeads` is an array that holds all saved links
- On popup open, saved links are pulled out of `localStorage` and rendered into the list
- Every time a link is added or the list is cleared, the updated array is saved back into `localStorage` so it survives closing the popup
- `chrome.tabs.query` is used to grab the URL of the currently active tab when you click "Save this tab"

