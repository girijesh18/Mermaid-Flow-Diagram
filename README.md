# Local Mermaid Diagram Creator

A simple, powerful, self-contained HTML application that allows you to render Mermaid.js diagrams locally and export them as high-resolution PNG images. No need for external websites, subscriptions, or an internet connection after the initial page load.

## 🚀 Features

*   **Fully Local & Private**: Runs entirely in your browser. Your data and diagrams never leave your computer.
*   **High-Resolution Export**: Export diagrams at any resolution using a simple scale factor—no more blurry screenshots!
*   **Live Preview**: Instantly see your diagram update as you type.
*   **Single File Solution**: The entire tool is one `.html` file. Easy to save, share, and use anywhere.
*   **Error Handling**: Provides clear feedback if your Mermaid syntax is incorrect.

## 🛠️ How to Use

1.  **Download**: Save the `mermaid-creator.html` file to your local machine.
2.  **Open**: Open the file in a modern web browser (like Chrome, Firefox, or Edge).
3.  **Create**: Paste your Mermaid diagram code into the text area on the left.
4.  **Set Quality**: Adjust the **Resolution Scale** value. A higher number (e.g., `8` or `10`) results in a larger, higher-quality PNG file.
5.  **Generate**: Click the **Generate Diagram** button to see your flowchart in the preview pane.
6.  **Download**: Click the **Download as PNG** button to save the final image to your computer.

## ⚙️ How It Works

The application leverages a combination of standard web technologies to provide a seamless experience:

*   **HTML**: Structures the user interface, including the code editor, control buttons, and the diagram preview area.
*   **CSS**: Provides the clean, modern styling for the application, ensuring it is responsive and easy to use.
*   **JavaScript**: Powers the core logic of the application.
    *   **Mermaid.js Library**: The script dynamically loads the Mermaid.js library from a CDN. This library is responsible for parsing the Mermaid syntax and converting it into an SVG (Scalable Vector Graphic) image.
    *   **DOM Manipulation**: When you click "Generate Diagram," the script takes the code from the text area, uses the Mermaid API to render the SVG, and injects it into the preview pane.

#### Canvas API for Export

To create a high-resolution PNG, we can't just save the SVG. Instead, the script performs the following steps when you click "Download":

1.  It reads the dimensions of the generated SVG.
2.  It creates a new, hidden `<canvas>` element in memory, scaled up by the **Resolution Scale** factor.
3.  It draws the SVG onto this larger canvas, effectively rasterizing it at a high resolution. A white background is added to ensure transparency isn't an issue.
4.  Finally, it converts the canvas content into a PNG data URL and triggers a download link, saving the high-quality image to your device.

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](https://github.com/your-username/your-repository/issues) if you want to contribute.

## 📄 License

This project is licensed under the MIT License. See the [LICENSE.md](LICENSE.md) file for details.
