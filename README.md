# Code Alone 11: Chat App

## Overview

In this assignment, you will write the JavaScript for a chat interface. You are **not allowed to modify the HTML or CSS files**. Everything must be done with JavaScript:

- Adding event listeners.
- Switching active channels.
- Populating messages dynamically.

5 points of extra credit will be awarded for implementing sending messages (updating both the screen and the chatData object).  

---

## Requirements

1. **Channel Selection**
   - There are multiple channels listed on the page.
   - When a user clicks on a channel:
     - The previously active channel should lose its "active" state.
     - The clicked channel should become active.
     - Messages for that channel should populate the chat window.
     - The header should update to show the current channel’s name.

2. **Message Display**
   - Each message shows:
     - Sender’s name.
     - Message text.
   - Messages from the user should be styled differently (CSS class provided).
   - Use the existing template element to create messages dynamically.
   - Old messages should be removed when switching channels.

3. **Sending Messages (Extra Credit)**
   - Users can type a message and click a send button.
   - The new message should:
     - Be added to the correct channel in your chat data object.
     - Display immediately in the chat window.
     - Be styled as a user message.
     - Clear the input box.

---

## Suggested Functions

You should structure your JavaScript into clear, reusable functions. Here are suggestions:

### 1. `changeChannel`
- **Purpose:** Handles switching the active channel.
- **Steps:**
  - Remove the "active" class from the currently active channel.
  - - Hint: Search the DOM for the element and use the `classList.remove` function. 
  - Add the "active" class to the clicked channel. 
  - - Hint: Use the event
  - Update the header with the channel’s name.
  - Call a function to populate messages for that channel.

### 2. `populateMessages`
- **Purpose:** Clears existing messages and fills the chat window with messages from the specified channel.
- **Steps:**
  - Accept a channel name as a parameter.
  - Remove all message elements currently in the chat container.
  - Loop through the messages in the specified channel’s array within the object.
  - For each message:
    - Use the provided `<template>` element to create a new message element.
    - Fill in the sender and message text.
    - If it’s from the user, apply the special styling.
    - Append the new element to the chat container.

### 3. `initializeEventListeners`
- **Purpose:** Adds all required event listeners to your page elements.
- **Steps:**
  - Select all channel elements and attach a click listener that calls `changeChannel`.
  - (Extra credit) Attach a click listener to the send button that calls `sendMessage`.
- **Note:** You cannot manually add IDs or modify HTML. Use only what is already provided in the HTML structure. If you want additional IDs you will need to add them dynamically.

### 4. `sendMessage` (Extra Credit)
- **Purpose:** Sends a message typed by the user.
- **Steps:**
  - Figuring this out is the extra credit. Make sure both the message window and the `chatData` object are updated.

---

## Constraints

- You **cannot** modify the HTML or CSS.
- Do **not** manually add IDs or classes; use only what exists.
- You **can** add IDs and classes dynamically using JavaScript.
- All changes must be done dynamically via JavaScript.
