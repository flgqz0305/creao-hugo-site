---
date: '2024-10-04T15:27:58+08:00'
draft: false
title: 'Building a QR Code Generator Web App with ChatGPT: A Journey from Marketing to Coding Success'
# cover:
#     image: img/post1.jpg
#     alt: 'This is a post image'
#     caption: 'Created by ChatGPT'
tags: ['artificial intelligence', 'gen ai']
categories: ['tech']
author: ["Clark Gao"]
---
![alt](/image.png)

## Introduction: The Beginning of My QR Code Journey

It all started with a simple need. I was working on a **marketing campaign** and wanted to use **QR codes** to make it easy for customers to access a landing page. However, as I began searching for QR code generation tools online, I quickly realized that most services charge a fee for features like color customization and high-quality downloads.

Frustrated with the paywalls, I thought, "Why should I pay for something I can build myself?" As a developer with some experience, I knew building a QR code generator wasn’t rocket science. Plus, I had heard of platforms like **Cursor** and **Replit**, which promised to help developers code without needing to write a lot of code. However, when I explored these tools, I found that setting them up felt like more effort than I wanted to invest for this project.

That’s when it hit me: why not try **ChatGPT**? I’d heard about how useful AI could be for coding assistance, and I was curious if it could help me build a functioning web app without having to do all the heavy lifting. So, I decided to experiment. This blog post documents how I successfully built a QR code generator web app with ChatGPT's assistance, the lessons I learned, and how you can do it too.

---

## Setting Up the Basics: Tools You'll Need

Before we dive into the coding, let's make sure you have the **basic setup** ready. Even though ChatGPT can provide a lot of the code, you'll still need a few essential tools to get started:

### **1. Text Editor**

You’ll need a simple text editor to write your code. Some popular options include:

- **VS Code**: A powerful, free code editor with a lot of features for web development.
- **Sublime Text**: A lightweight, fast editor perfect for small projects.
- **Notepad++**: Another free and easy-to-use option, especially for beginners.

### **2. Web Browser**

For testing your app, you’ll need a browser like **Google Chrome** or **Firefox**. Most modern browsers have built-in developer tools that will help you test and debug your web app.

### **3. Running Your HTML**

Once you have your code written, you’ll want to open it in your browser. Here’s a simple way to run the app locally:

1. **Write the HTML file**: Save your file as `index.html` in a folder on your computer.
2. **Open in Browser**: Double-click on the `index.html` file or drag it into a browser window. This will run your static HTML file directly.
3. If you want a more robust way to run your app, you can use a tool like Python or a Node.js server, but for this basic setup, you can just open the HTML file directly in your browser.

---

## Building the QR Code Generator Web App with ChatGPT

With my tools set up and my goal defined, I turned to ChatGPT to help me write the code for a QR code generator. Here's how the process unfolded.

### 1. **Establishing the Basic Structure**

To begin, I asked ChatGPT for a basic HTML page setup with an input field and a button to generate the QR code. Here’s the initial structure ChatGPT suggested:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>QR Code Generator</title>
</head>
<body>
    <div id="wrapper">
        <input type="text" id="url-input" placeholder="Enter the URL here">
        <button id="generate-btn">Generate QR Code</button>
        <div id="qr-container"></div>
    </div>
</body>
</html>

```

I copied this code into my text editor and saved it as `index.html`. After opening it in my browser, I could see the basic interface, though the QR code functionality wasn’t there yet. But this was a great start!

### 2. **Integrating a QR Code Library**

Next, I needed to generate the QR codes. ChatGPT introduced me to a JavaScript library called **QRious**. This library makes it easy to generate QR codes in the browser. ChatGPT provided a script tag to include the library and gave me code to generate a QR code based on the URL input.

```html
<!-- Include QRious Library -->
<script src="<https://cdn.jsdelivr.net/npm/qrious@4.0.2/dist/qrious.min.js>"></script>

<script>
    document.getElementById('generate-btn').addEventListener('click', function() {
        var url = document.getElementById('url-input').value.trim();
        if (url === '') {
            alert('Please enter a URL.');
            return;
        }

        var qr = new QRious({
            element: document.getElementById('qr-container'),
            value: url,
            size: 256,
        });
    });
</script>

```

With this code, users could now enter a URL, click "Generate QR Code," and see a QR code appear on the screen. It worked like magic!

### 3. **Adding Color Customization**

As a marketer, I wanted more than just black-and-white QR codes. I asked ChatGPT how I could let users change the color of their QR codes, and it suggested adding a color picker input:

```html
<input type="color" id="color-input" value="#000000">

```

ChatGPT then modified the QRious initialization to use the color selected by the user:

```jsx
var qr = new QRious({
    element: document.getElementById('qr-container'),
    value: url,
    size: 256,
    foreground: document.getElementById('color-input').value,
});

```

This added a fun level of interactivity and allowed users to customize the QR code to their branding or style preferences.

### 4. **Implementing Animation Effects**

To make the app more engaging, I wanted to add animations to the QR code generation process. I asked ChatGPT for ideas, and it introduced me to **anime.js**, a JavaScript library for creating animations. We decided to animate the QR code pieces as they appeared on the screen.

```html
<!-- Include anime.js Library -->
<script src="<https://cdnjs.cloudflare.com/ajax/libs/animejs/3.2.1/anime.min.js>"></script>

```

We added an animation that would make the QR code pieces "break apart" and then come together again:

```jsx
// Animation code using anime.js
anime({
    targets: '#qr-container canvas',
    scale: [0, 1],
    duration: 2000,
    easing: 'easeInOutQuad'
});

```

This made the app feel more dynamic and exciting for users.

### 5. **Adding Download Functionality**

To complete the functionality, I needed a way for users to download their QR code once it was generated. ChatGPT helped me add a download button:

```html
<button id="download-btn">Download QR Code</button>

```

And provided JavaScript code to trigger the download:

```jsx
document.getElementById('download-btn').addEventListener('click', function() {
    var canvas = document.querySelector('#qr-container canvas');
    var link = document.createElement('a');
    link.href = canvas.toDataURL('image/png');
    link.download = 'qr_code.png';
    link.click();
});

```

Now, users could not only generate but also download their custom QR codes.

---

## Deploying the Web App on Vercel

With the core features in place, it was time to deploy the app. ChatGPT recommended using **Vercel**, a platform designed for easily deploying web applications. After pushing the code to a GitHub repository and linking it with Vercel, I was able to deploy the app live with just a few clicks.

**Check out the live app here:** [QR Code Generator Web App](https://qr-code-generator-nine-umber.vercel.app/)

---

## Final Product Features

- **QR Code Generation:** Users can input a URL to generate a QR code.
- **Color Customization:** Users can select from various colors for their QR code.
- **Engaging Animation:** The QR code pieces animate upon generation, enhancing the user experience.
- **Downloadable QR Codes:** Users can download their customized QR codes as PNG files.

---

## Conclusion

Building this QR code generator web app was an enriching experience that combined coding, creativity, and problem-solving. Leveraging ChatGPT not only made the development process smoother but also provided a learning opportunity to deepen my understanding of web technologies.

If you're embarking on a coding project, I highly recommend utilizing AI tools like ChatGPT. Whether you're a beginner or an experienced developer, it can provide valuable insights, troubleshoot issues, and inspire innovative solutions.

---

## Share Your Thoughts

I'd love to hear your feedback or experiences with similar projects. Feel free to try it out and share your thoughts!

---

**Happy Coding!**