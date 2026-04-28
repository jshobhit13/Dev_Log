# ⚛️ React Basics Learning

![React](https://img.shields.io/badge/React-18-blue?logo=react)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6-yellow?logo=javascript)
![Status](https://img.shields.io/badge/Status-Learning-green)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

## 📖 About the Project

This repository is a beginner-friendly guide to learning **React.js**. It focuses on building a strong foundation by practicing core concepts through simple components and examples.

---

## 🎯 Goals

* Understand React fundamentals
* Learn component-based architecture
* Work with state and props
* Handle events and user interactions
* Build reusable UI components

---

## 🛠️ Tech Stack

* React.js
* JavaScript (ES6+)
* HTML5
* CSS3

---

## 📚 Concepts Covered

* Components (Functional)
* JSX
* Props
* State (`useState`)
* Event Handling
* Conditional Rendering
* Lists & Keys
* Forms (Controlled Components)

---

## 📂 Folder Structure

```
react-basics/
│── public/
│── src/
│   ├── components/
│   │   ├── Counter.js
│   │   ├── Navbar.js
│   │   └── Form.js
│   ├── App.js
│   ├── index.js
│   └── styles.css
│── package.json
```

---

## ⚙️ Getting Started

### Clone the repository

```
git clone https://github.com/your-username/react-basics.git
```

### Navigate to the project

```
cd react-basics
```

### Install dependencies

```
npm install
```

### Run the application

```
npm start
```

---

## 💡 Example Component

```jsx
import React, { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div style={{ textAlign: "center" }}>
      <h2>Count: {count}</h2>
      <button onClick={() => setCount(count + 1)}>
        Increase
      </button>
    </div>
  );
}

export default Counter;
```

---

## 🚀 Future Improvements

* Learn advanced hooks (`useEffect`, `useContext`)
* Add routing using React Router
* Build mini projects (Todo App, Weather App)

---

## 🤝 Contributing

Feel free to fork this repository and improve it with your own components or ideas.

---

## 📄 License

This project is licensed under the MIT License.
