<!-- Cover Image -->
<p align="center">
  <img src="https://github.com/user-attachments/assets/2e06cf33-10e4-4471-9d1c-8dc02199d473" alt="Whiteboard Cover" width="600"/>


</p>

---

# 🚀 Building a Real-Time Collaborative Whiteboard with React & Socket.IO

**By [Shrived00](https://github.com/Shrived00)** · 🗓️ *April 19, 2025* · ⏱️ *5 min read*

Have you ever wanted to build a tool like Miro or Google Jamboard? In this post, I’ll walk you through how I created a **real-time collaborative whiteboard** using **React**, **Socket.IO**, and **Rough.js**.

---

## 💡 The Idea

The goal was to allow multiple users to draw on a canvas **simultaneously** and see each other's updates in **real time**. Think of it as a minimalist digital whiteboard for brainstorming and sketching ideas with friends or colleagues.

---

## 🛠️ Tech Stack

- **React**: For the frontend UI  
- **Socket.IO**: For real-time communication  
- **Rough.js**: To give the whiteboard a hand-drawn look  
- **Express + Node.js**: As the backend server  
- **Zustand**: For state management

---

## 🧱 Features

- ✍️ Pencil, Rectangle, and Circle drawing tools  
- 🖱️ Hover and move individual elements  
- 🔁 Undo/Redo support  
- 🧽 Clear canvas option  
- 🔗 Shareable room links for collaboration  
- 🧠 State management with Zustand

---

## 🌐 Real-Time with Socket.IO

Every time a user draws, the coordinates and shape details are emitted to the server. Other clients in the same room receive these updates and redraw the element locally. It feels *instant*.

```js
socket.emit("draw", { id, type, coordinates, color });
