# OOkul_task

![image](https://github.com/user-attachments/assets/f93ec020-f3e4-4520-8015-a3290996cf72)

# KML Viewer

This is a React-based KML Viewer application built with Vite. It allows users to upload and visualize KML files containing geographical data such as placemarks, line strings, and multi-line strings.

## 🚀 Features
- Load and parse KML files
- Display summary statistics (Placemark, LineString, MultiLineString count)
- Interactive UI with buttons for viewing summary and details
- Uses Vite for fast development and HMR (Hot Module Replacement)

## 🛠️ Installation

1. Clone the repository:
   ```sh
   git clone https://github.com/your-username/kml-viewer.git
   cd kml-viewer
   ```

2. Install dependencies:
   ```sh
   npm install
   ```

3. Start the development server:
   ```sh
   npm run dev
   ```

4. Open the app in your browser:
   ```
   http://localhost:5173/
   ```

## 📂 Project Structure
```
📦 kml-viewer
├── 📂 public         # Static assets
├── 📂 src
│   ├── 📂 components
│   │   ├── 📂 ui
│   │   │   ├── Button.jsx
│   │   │   ├── Card.jsx
│   │   │   ├── index.js  # Exports UI components
│   ├── 📂 utils
│   │   ├── fileReader.jsx
│   ├── 📂 pages
│   ├── App.jsx
│   ├── main.jsx
├── 📄 vite.config.js
├── 📄 package.json
└── 📄 README.md
```

## 📌 Key Files
- **`src/components/ui/Button.jsx`**: Button component.
- **`src/components/ui/Card.jsx`**: Card component for displaying content.
- **`src/utils/fileReader.jsx`**: Function to read and parse uploaded KML files.
- **`src/KMLViewer.jsx`**: Main component handling KML file upload and display.
- **`vite.config.js`**: Configuration for Vite, including alias setup.

## ⚠️ Common Issues & Fixes

### 1. JSX Syntax Not Enabled
**Error:** `The JSX syntax extension is not currently enabled`

**Fix:** Ensure your `vite.config.js` includes React plugin:
```js
import { defineConfig } from "vite";
import react from "@vitejs/plugin-react";

export default defineConfig({
  plugins: [react()],
  resolve: {
    alias: {
      "@": "/src",
    },
  },
});
```

### 2. Module Not Found (`@/utils/fileReader`)
**Error:** `Failed to resolve import` for `@/utils/fileReader`

**Fix:**
- Ensure `fileReader.jsx` exists in `src/utils/`
- Use `.jsx` extension in imports:
  ```js
  import { readFile } from "@/utils/fileReader.jsx";
  ```

### 3. UI Components Not Found (`@/components/ui`)
**Error:** `Cannot resolve @/components/ui`

**Fix:** Add an `index.js` in `src/components/ui/`:
```js
export { default as Button } from "./Button.jsx";
export { default as Card } from "./Card.jsx";
```
Then, update imports:
```js
import { Button, Card } from "@/components/ui";
```

## ✅ Contributing
1. Fork the repository
2. Create a new branch (`git checkout -b feature-branch`)
3. Commit your changes (`git commit -m "Added new feature"`)
4. Push to the branch (`git push origin feature-branch`)
5. Open a Pull Request

## 📜 License
This project is licensed under the MIT License.

