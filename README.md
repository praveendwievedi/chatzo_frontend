# Chatzo Frontend

This document outlines the structure and components of the **Chatzo** application's frontend. It provides an overview of the technologies, folder structure, and key components to aid in development and maintenance.

---

## Technologies Used

- **Framework**: React (with Vite bundler)
- **State Management**: Redux or Context API (specify your choice)
- **Styling**: TailwindCSS, CSS Modules, or Styled Components (specify your choice)
- **HTTP Client**: Axios or Fetch API
- **Other Tools**:
  - React Router for navigation
  - ESLint and Prettier for code quality

---

## Folder Structure

Here is the suggested folder structure for the Chatzo frontend:

```plaintext
/src
  |-- /assets
  |   |-- Images, fonts, and static files
  |
  |-- /components
  |   |-- Shared reusable components
  |   |-- Example: Button.jsx, Navbar.jsx
  |
  |-- /pages
  |   |-- Individual screens/pages
  |   |-- Example: Home.jsx, ChatRoom.jsx, Profile.jsx
  |
  |-- /hooks
  |   |-- Custom React hooks
  |   |-- Example: useChat.js, useAuth.js
  |
  |-- /context
  |   |-- Context API providers and state logic
  |
  |-- /services
  |   |-- API calls and service-related logic
  |   |-- Example: authService.js, chatService.js
  |
  |-- /styles
  |   |-- Global and component-specific styles
  |   |-- Example: global.css, themes.css
  |
  |-- /utils
  |   |-- Utility functions and helpers
  |   |-- Example: formatDate.js, validateInput.js
  |
  |-- App.jsx
  |-- main.jsx
  |-- index.css
```

---

## Key Components

### 1. **Navbar**
   - Displays navigation links.
   - Includes options for user authentication (login/logout).

### 2. **Chat Room**
   - Core feature where users can send and receive messages in real time.
   - Displays chat history and active participants.

### 3. **Profile**
   - Allows users to view and edit their profiles.
   - Upload profile pictures and manage settings.

### 4. **Authentication**
   - Login and signup forms.
   - Implements user authentication flow.

### 5. **Error Boundary**
   - A component to handle unexpected UI crashes gracefully.

---

## Key Features

1. **Real-Time Chat**
   - Leverages WebSockets for real-time communication.

2. **User Authentication**
   - Secure login and signup using JWT or OAuth.

3. **Responsive Design**
   - Mobile-first design for a seamless user experience on all devices.

4. **Custom Hooks**
   - Example: `useChat` for managing chat state, `useAuth` for handling authentication.

5. **API Integration**
   - Interacts with backend services to fetch and send data.

---

## Example Code Snippet

Here is an example of a simple `ChatInput` component:

```jsx
import React, { useState } from "react";

const ChatInput = ({ onSendMessage }) => {
  const [message, setMessage] = useState("");

  const handleSend = () => {
    if (message.trim()) {
      onSendMessage(message);
      setMessage("");
    }
  };

  return (
    <div className="chat-input">
      <input
        type="text"
        value={message}
        onChange={(e) => setMessage(e.target.value)}
        placeholder="Type a message..."
      />
      <button onClick={handleSend}>Send</button>
    </div>
  );
};

export default ChatInput;
```

---

## Running the Frontend

1. **Install Dependencies**
   ```bash
   npm install
   ```

2. **Run the Development Server**
   ```bash
   npm run dev
   ```

3. **Build for Production**
   ```bash
   npm run build
   ```

4. **Preview Production Build**
   ```bash
   npm run preview
   ```

---

## Contribution Guidelines

- Follow the coding standards defined in `.eslintrc` and `.prettierrc`.
- Always write clear and concise commit messages.
- Use descriptive names for components, variables, and functions.
- Ensure the application is fully responsive and accessible.

---

## Future Enhancements

- Add dark mode toggle.
- Implement message reactions and typing indicators.
- Optimize performance with lazy loading and code splitting.
