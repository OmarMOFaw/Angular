# Angular Version 21: Complete Zero to Hero Guide

> **A comprehensive, step-by-step guide for absolute beginners with no prior web development experience**

---

## Table of Contents

1. [Before You Begin: Essential Background](#1-before-you-begin-essential-background)
2. [Understanding the Web: How Websites Work](#2-understanding-the-web-how-websites-work)
3. [The Building Blocks: HTML, CSS, and JavaScript](#3-the-building-blocks-html-css-and-javascript)
4. [What is a Framework? Why Angular?](#4-what-is-a-framework-why-angular)
5. [Setting Up Your Development Environment](#5-setting-up-your-development-environment)
6. [Your First Angular Application](#6-your-first-angular-application)
7. [Understanding Angular Architecture](#7-understanding-angular-architecture)
8. [Components: The Heart of Angular](#8-components-the-heart-of-angular)
9. [Templates and Data Binding](#9-templates-and-data-binding)
10. [Directives: Extending HTML](#10-directives-extending-html)
11. [Services and Dependency Injection](#11-services-and-dependency-injection)
12. [Routing and Navigation](#12-routing-and-navigation)
13. [Forms and User Input](#13-forms-and-user-input)
14. [HTTP and API Communication](#14-http-and-api-communication)
15. [State Management](#15-state-management)
16. [Signals: Modern Reactivity in Angular](#16-signals-modern-reactivity-in-angular)
17. [Standalone Components](#17-standalone-components)
18. [Testing Your Application](#18-testing-your-application)
19. [Performance Optimization](#19-performance-optimization)
20. [Deployment: Sharing Your App with the World](#20-deployment-sharing-your-app-with-the-world)
21. [What's New in Angular 21](#21-whats-new-in-angular-21)
22. [Next Steps and Resources](#22-next-steps-and-resources)

---

## 1. Before You Begin: Essential Background

### What is Programming?

Programming is the act of giving instructions to a computer. Just like you might give someone directions to your house, you give a computer step-by-step instructions to accomplish a task. These instructions are written in a **programming language**.

Think of it like this:
- **Human languages** (English, Spanish, etc.) → Communication between people
- **Programming languages** (JavaScript, Python, etc.) → Communication with computers

### What is Software Development?

Software development is the process of:
1. **Planning** what you want to build
2. **Writing code** (the instructions)
3. **Testing** to make sure it works
4. **Deploying** (making it available to users)
5. **Maintaining** and improving over time

### What is Web Development?

Web development specifically focuses on building websites and web applications. It's divided into three main areas:

```
┌─────────────────────────────────────────────────────────────────┐
│                        WEB DEVELOPMENT                          │
├─────────────────────┬─────────────────────┬─────────────────────┤
│     FRONT-END       │      BACK-END       │     FULL-STACK      │
│  (What users see)   │  (Server logic)     │  (Both combined)    │
│                     │                     │                     │
│  • HTML/CSS/JS      │  • Databases        │  • Everything!      │
│  • Angular          │  • APIs             │                     │
│  • React            │  • Node.js          │                     │
│  • Vue              │  • Python/Java      │                     │
└─────────────────────┴─────────────────────┴─────────────────────┘
```

**Angular is a front-end framework** – it helps you build what users see and interact with in their web browser.

---

## 2. Understanding the Web: How Websites Work

### The Client-Server Model

When you visit a website, here's what happens:

```
┌──────────────┐                              ┌──────────────┐
│              │  1. Request (I want page X)  │              │
│    CLIENT    │ ──────────────────────────▶  │    SERVER    │
│  (Your       │                              │  (Remote     │
│   Browser)   │  ◀────────────────────────── │   Computer)  │
│              │  2. Response (Here's page X) │              │
└──────────────┘                              └──────────────┘
```

1. **Client (You)**: Your web browser (Chrome, Firefox, Safari, etc.)
2. **Server**: A powerful computer somewhere in the world that stores websites
3. **Request**: When you type a URL, your browser asks the server for that page
4. **Response**: The server sends back the files (HTML, CSS, JavaScript)

### What is a URL?

A URL (Uniform Resource Locator) is a web address. Let's break one down:

```
    https://www.example.com:443/products/shoes?color=red#reviews
    └─┬─┘   └──────┬──────┘└┬┘ └─────┬─────┘ └────┬────┘ └──┬──┘
      │           │        │       │             │         │
   Protocol    Domain    Port    Path         Query     Fragment
   (secure)   (address)        (location)   (filters)  (section)
```

### How Browsers Render Pages

When your browser receives files from a server:

```
Step 1: Parse HTML → Create DOM (Document Object Model)
              ↓
Step 2: Parse CSS → Create CSSOM (CSS Object Model)
              ↓
Step 3: Combine DOM + CSSOM → Render Tree
              ↓
Step 4: Layout → Calculate positions
              ↓
Step 5: Paint → Display pixels on screen
```

---

## 3. The Building Blocks: HTML, CSS, and JavaScript

Before learning Angular, you need to understand the three core technologies of the web.

### HTML: The Structure

**HTML (HyperText Markup Language)** defines the structure and content of a webpage. Think of it as the skeleton of a house.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>My First Page</title>
  </head>
  <body>
    <header>
      <h1>Welcome to My Website</h1>
      <nav>
        <a href="/home">Home</a>
        <a href="/about">About</a>
      </nav>
    </header>
    
    <main>
      <article>
        <h2>Article Title</h2>
        <p>This is a paragraph of text.</p>
        <img src="photo.jpg" alt="A description">
      </article>
    </main>
    
    <footer>
      <p>&copy; 2024 My Website</p>
    </footer>
  </body>
</html>
```

**Key HTML Concepts:**

| Element | Purpose | Example |
|---------|---------|---------|
| `<h1>` to `<h6>` | Headings | `<h1>Main Title</h1>` |
| `<p>` | Paragraph | `<p>Some text here</p>` |
| `<a>` | Link | `<a href="url">Click me</a>` |
| `<img>` | Image | `<img src="pic.jpg" alt="desc">` |
| `<div>` | Container | `<div>Group of elements</div>` |
| `<span>` | Inline container | `<span>Inline text</span>` |
| `<button>` | Clickable button | `<button>Click</button>` |
| `<input>` | User input | `<input type="text">` |
| `<form>` | Form container | `<form>...</form>` |
| `<ul>`, `<ol>`, `<li>` | Lists | `<ul><li>Item</li></ul>` |

### CSS: The Style

**CSS (Cascading Style Sheets)** controls how HTML elements look. Think of it as the paint, decorations, and design of a house.

```css
/* This is a CSS comment */

/* Selecting by element */
body {
  font-family: Arial, sans-serif;
  background-color: #f5f5f5;
  margin: 0;
  padding: 0;
}

/* Selecting by class (.) */
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

/* Selecting by ID (#) */
#main-header {
  background-color: #333;
  color: white;
  padding: 1rem;
}

/* Selecting nested elements */
.nav-menu a {
  color: white;
  text-decoration: none;
  margin-right: 15px;
}

/* Hover state */
.nav-menu a:hover {
  text-decoration: underline;
}

/* Responsive design - different styles for different screen sizes */
@media (max-width: 768px) {
  .container {
    padding: 10px;
  }
}
```

**Key CSS Concepts:**

| Property | What it does | Example |
|----------|--------------|---------|
| `color` | Text color | `color: blue;` |
| `background-color` | Background | `background-color: #fff;` |
| `font-size` | Text size | `font-size: 16px;` |
| `margin` | Outside spacing | `margin: 10px;` |
| `padding` | Inside spacing | `padding: 20px;` |
| `border` | Element border | `border: 1px solid black;` |
| `display` | Layout behavior | `display: flex;` |
| `position` | Positioning | `position: relative;` |
| `width/height` | Dimensions | `width: 100%;` |

### JavaScript: The Behavior

**JavaScript** makes web pages interactive. Think of it as the electrical wiring, plumbing, and smart home features of a house.

```javascript
// Variables - storing data
let userName = "Alice";          // Can be changed
const birthYear = 1990;          // Cannot be changed
var oldWay = "avoid this";       // Old syntax (avoid)

// Data Types
let text = "Hello";              // String
let number = 42;                 // Number
let decimal = 3.14;              // Number (JS doesn't distinguish)
let isActive = true;             // Boolean
let nothing = null;              // Null
let notDefined = undefined;      // Undefined
let list = [1, 2, 3];           // Array
let person = {                   // Object
  name: "Alice",
  age: 30
};

// Functions - reusable blocks of code
function greet(name) {
  return `Hello, ${name}!`;
}

// Arrow functions (modern syntax)
const greetArrow = (name) => `Hello, ${name}!`;

// Calling a function
console.log(greet("Bob")); // Output: Hello, Bob!

// Conditionals
if (age >= 18) {
  console.log("Adult");
} else if (age >= 13) {
  console.log("Teenager");
} else {
  console.log("Child");
}

// Loops
for (let i = 0; i < 5; i++) {
  console.log(i); // 0, 1, 2, 3, 4
}

// Array methods
const numbers = [1, 2, 3, 4, 5];
const doubled = numbers.map(n => n * 2);        // [2, 4, 6, 8, 10]
const evens = numbers.filter(n => n % 2 === 0); // [2, 4]
const sum = numbers.reduce((a, b) => a + b, 0); // 15

// DOM Manipulation (before frameworks)
const button = document.querySelector('#myButton');
button.addEventListener('click', () => {
  alert('Button clicked!');
});
```

### TypeScript: JavaScript with Superpowers

Angular uses **TypeScript**, which is JavaScript with added features, most importantly **types**:

```typescript
// JavaScript (no types)
let name = "Alice";
name = 42; // No error, but might cause bugs later

// TypeScript (with types)
let name: string = "Alice";
name = 42; // ERROR! Type 'number' is not assignable to type 'string'

// Type annotations
let age: number = 25;
let isStudent: boolean = true;
let hobbies: string[] = ["reading", "coding"];

// Interface - defining object shapes
interface User {
  id: number;
  name: string;
  email: string;
  isActive?: boolean; // Optional property (?)
}

// Using the interface
const user: User = {
  id: 1,
  name: "Alice",
  email: "alice@example.com"
};

// Function with types
function add(a: number, b: number): number {
  return a + b;
}

// Class with types
class Person {
  name: string;
  private age: number; // Only accessible within the class
  
  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }
  
  greet(): string {
    return `Hello, I'm ${this.name}`;
  }
}
```

**Why TypeScript?**
- Catches errors before running the code
- Better code editor support (autocomplete, hints)
- Makes large codebases easier to maintain
- Self-documenting code

---

## 4. What is a Framework? Why Angular?

### Understanding Frameworks

A **framework** is a pre-built collection of code that provides structure and common functionality for building applications.

**Analogy**: Building a house from scratch vs. buying a prefab house
- **From scratch**: You decide everything – foundation, walls, plumbing, electrical
- **Prefab (framework)**: Structure is provided, you customize and add your features

### Framework vs. Library

```
┌─────────────────────────────────────────────────────────────┐
│                        LIBRARY                               │
│  • YOU are in control                                        │
│  • You call the library when needed                          │
│  • Example: You're cooking, use a cookbook for one recipe    │
│  • Examples: Lodash, Axios, Moment.js                        │
└─────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────┐
│                       FRAMEWORK                              │
│  • FRAMEWORK is in control                                   │
│  • Framework calls your code                                 │
│  • Example: Cooking show - follow the structure, add flair   │
│  • Examples: Angular, React, Vue                             │
└─────────────────────────────────────────────────────────────┘
```

### Why Use Angular?

Angular provides solutions for:

1. **Component-Based Architecture**: Build UI from reusable pieces
2. **Data Binding**: Automatically sync data between UI and code
3. **Routing**: Navigate between pages without full reload
4. **Forms Handling**: Easy form creation and validation
5. **HTTP Client**: Communicate with servers/APIs
6. **Dependency Injection**: Manage and share code efficiently
7. **Testing**: Built-in testing utilities
8. **CLI**: Command-line tools for scaffolding and building

### Angular vs. Other Frameworks

| Feature | Angular | React | Vue |
|---------|---------|-------|-----|
| Type | Full Framework | Library | Framework |
| Language | TypeScript | JavaScript | JavaScript |
| Learning Curve | Steeper | Moderate | Gentle |
| Architecture | Opinionated | Flexible | Flexible |
| Company | Google | Meta | Community |
| Best For | Enterprise apps | Flexible projects | Quick prototypes |

### A Brief History of Angular

```
Timeline:
─────────────────────────────────────────────────────────────────────
2010 │ AngularJS (1.x) - The original, JavaScript-based
     │
2016 │ Angular 2 - Complete rewrite in TypeScript
     │
2017-│ Angular 4-8 - Incremental improvements
2019 │ (Note: v3 was skipped to align version numbers)
     │
2020 │ Angular 9-11 - Ivy renderer (faster, smaller)
     │
2021-│ Angular 12-15 - Standalone components, improved DX
2023 │
     │
2024 │ Angular 16-18 - Signals, improved SSR, zoneless preview
     │
2025 │ Angular 19-21 - Full signals integration, zoneless by default
─────────────────────────────────────────────────────────────────────
```

---

## 5. Setting Up Your Development Environment

### Prerequisites

Before installing Angular, you need:

#### 1. Node.js and npm

**Node.js** is a JavaScript runtime that allows JavaScript to run outside the browser.
**npm** (Node Package Manager) helps install and manage JavaScript packages.

```bash
# Check if Node.js is installed
node --version
# Should show v20.x.x or higher for Angular 21

# Check if npm is installed
npm --version
# Should show 10.x.x or higher

# If not installed, download from: https://nodejs.org/
# Choose the LTS (Long Term Support) version
```

#### 2. A Code Editor

Recommended: **Visual Studio Code (VS Code)**
- Download from: https://code.visualstudio.com/
- Install these extensions:
  - Angular Language Service
  - Prettier - Code formatter
  - ESLint
  - Material Icon Theme (optional, but nice)

#### 3. A Terminal

- **Windows**: PowerShell, Command Prompt, or Windows Terminal
- **macOS**: Terminal or iTerm2
- **Linux**: Any terminal emulator

### Installing Angular CLI

The **Angular CLI (Command Line Interface)** is a tool that helps create, develop, and build Angular applications.

```bash
# Install Angular CLI globally
npm install -g @angular/cli

# Verify installation
ng version

# You should see output like:
#      _                      _                 ____ _     ___
#     / \   _ __   __ _ _   _| | __ _ _ __     / ___| |   |_ _|
#    / △ \ | '_ \ / _` | | | | |/ _` | '__|   | |   | |    | |
#   / ___ \| | | | (_| | |_| | | (_| | |      | |___| |___ | |
#  /_/   \_\_| |_|\__, |\__,_|_|\__,_|_|       \____|_____|___|
#                 |___/
#
#  Angular CLI: 21.x.x
#  Node: 20.x.x
#  Package Manager: npm 10.x.x
```

### Understanding npm Commands

| Command | What it does |
|---------|--------------|
| `npm install` | Install all dependencies listed in package.json |
| `npm install <package>` | Install a specific package |
| `npm install -g <package>` | Install globally (available everywhere) |
| `npm install -D <package>` | Install as dev dependency |
| `npm uninstall <package>` | Remove a package |
| `npm update` | Update packages |
| `npm run <script>` | Run a script defined in package.json |

### Understanding the Angular CLI Commands

| Command | What it does |
|---------|--------------|
| `ng new <name>` | Create a new Angular project |
| `ng serve` | Start development server |
| `ng generate component <name>` | Create a new component |
| `ng generate service <name>` | Create a new service |
| `ng build` | Build for production |
| `ng test` | Run unit tests |
| `ng e2e` | Run end-to-end tests |
| `ng add <package>` | Add a library to your project |
| `ng update` | Update Angular and dependencies |

---

## 6. Your First Angular Application

### Creating a New Project

```bash
# Create a new Angular project
ng new my-first-app

# You'll be asked several questions:
# ? Which stylesheet format would you like to use? → CSS (for beginners)
# ? Do you want to enable Server-Side Rendering (SSR)? → No (for now)
# ? Would you like to use the new zoneless change detection? → No (for now)

# Navigate into the project
cd my-first-app

# Start the development server
ng serve

# Open your browser to http://localhost:4200
```

### Project Structure Explained

```
my-first-app/
├── node_modules/           # Downloaded packages (don't edit)
├── src/                    # Your source code
│   ├── app/               # Application code
│   │   ├── app.component.ts      # Main component logic
│   │   ├── app.component.html    # Main component template
│   │   ├── app.component.css     # Main component styles
│   │   ├── app.component.spec.ts # Main component tests
│   │   ├── app.config.ts         # Application configuration
│   │   └── app.routes.ts         # Application routes
│   ├── index.html         # Main HTML file
│   ├── main.ts            # Application entry point
│   └── styles.css         # Global styles
├── public/                # Static assets (images, etc.)
├── angular.json           # Angular CLI configuration
├── package.json           # Project dependencies and scripts
├── tsconfig.json          # TypeScript configuration
└── README.md             # Project documentation
```

### Understanding Each File

#### `src/index.html` - The Entry Point

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>MyFirstApp</title>
  <base href="/">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="icon" type="image/x-icon" href="favicon.ico">
</head>
<body>
  <!-- This is where Angular inserts your app -->
  <app-root></app-root>
</body>
</html>
```

#### `src/main.ts` - Bootstrap the Application

```typescript
import { bootstrapApplication } from '@angular/platform-browser';
import { appConfig } from './app/app.config';
import { AppComponent } from './app/app.component';

// This starts your Angular application
bootstrapApplication(AppComponent, appConfig)
  .catch((err) => console.error(err));
```

#### `src/app/app.component.ts` - Your First Component

```typescript
import { Component } from '@angular/core';
import { RouterOutlet } from '@angular/router';

@Component({
  selector: 'app-root',           // HTML tag name
  standalone: true,               // Self-contained component
  imports: [RouterOutlet],        // Dependencies
  templateUrl: './app.component.html',  // HTML template file
  styleUrl: './app.component.css'       // CSS styles file
})
export class AppComponent {
  title = 'my-first-app';         // Component data
}
```

### Making Your First Change

Let's modify the app to display something custom:

#### Step 1: Edit `app.component.ts`

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  standalone: true,
  imports: [],
  templateUrl: './app.component.html',
  styleUrl: './app.component.css'
})
export class AppComponent {
  // Properties (data)
  title = 'My Learning Journey';
  name = 'Angular Explorer';
  currentDate = new Date();
  
  // Methods (actions)
  greet(): string {
    return `Welcome to ${this.title}!`;
  }
}
```

#### Step 2: Edit `app.component.html`

```html
<div class="container">
  <header>
    <h1>{{ title }}</h1>
    <p>Hello, {{ name }}!</p>
  </header>
  
  <main>
    <p>{{ greet() }}</p>
    <p>Today is: {{ currentDate.toLocaleDateString() }}</p>
    
    <button (click)="name = 'Angular Master'">
      Level Up!
    </button>
  </main>
</div>
```

#### Step 3: Edit `app.component.css`

```css
.container {
  max-width: 800px;
  margin: 0 auto;
  padding: 2rem;
  font-family: Arial, sans-serif;
}

header {
  text-align: center;
  margin-bottom: 2rem;
}

h1 {
  color: #dd0031;
}

button {
  background-color: #dd0031;
  color: white;
  border: none;
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
  border-radius: 4px;
}

button:hover {
  background-color: #c3002f;
}
```

Save all files and check your browser - it automatically refreshes!

---

## 7. Understanding Angular Architecture

### The Big Picture

```
┌─────────────────────────────────────────────────────────────────────┐
│                        ANGULAR APPLICATION                          │
│                                                                     │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐                 │
│  │  Component  │  │  Component  │  │  Component  │                 │
│  │  ┌───────┐  │  │  ┌───────┐  │  │  ┌───────┐  │                 │
│  │  │Template│  │  │  │Template│  │  │  │Template│  │                 │
│  │  └───────┘  │  │  └───────┘  │  │  └───────┘  │                 │
│  └─────────────┘  └─────────────┘  └─────────────┘                 │
│         │                │                │                         │
│         └────────────────┼────────────────┘                         │
│                          │                                          │
│                    ┌─────▼─────┐                                    │
│                    │  Services │ ◄──── Dependency Injection         │
│                    └───────────┘                                    │
│                          │                                          │
│         ┌────────────────┼────────────────┐                         │
│         ▼                ▼                ▼                         │
│   ┌──────────┐    ┌──────────┐    ┌──────────┐                     │
│   │  Router  │    │   HTTP   │    │  Forms   │                     │
│   └──────────┘    └──────────┘    └──────────┘                     │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### Core Concepts Overview

| Concept | What it is | Analogy |
|---------|------------|---------|
| **Component** | Building block of UI | A LEGO brick |
| **Template** | HTML view of component | The visible part of the brick |
| **Directive** | Extends HTML behavior | Special instructions for bricks |
| **Service** | Shared logic/data | A utility toolbox |
| **Dependency Injection** | How services are provided | Tool delivery system |
| **Module** | Group of related code | A box of related bricks |
| **Router** | Navigation handler | GPS for your app |
| **Pipe** | Data transformation | A filter or translator |

### How Components Relate

```
                    ┌─────────────────┐
                    │   AppComponent  │  (Root)
                    │    (app-root)   │
                    └────────┬────────┘
                             │
           ┌─────────────────┼─────────────────┐
           │                 │                 │
    ┌──────▼──────┐   ┌──────▼──────┐   ┌──────▼──────┐
    │   Header    │   │   Sidebar   │   │    Main     │
    │  Component  │   │  Component  │   │  Component  │
    └─────────────┘   └─────────────┘   └──────┬──────┘
                                               │
                               ┌───────────────┼───────────────┐
                               │               │               │
                        ┌──────▼──────┐ ┌──────▼──────┐ ┌──────▼──────┐
                        │  ProductList │ │   Product   │ │  Product    │
                        │  Component   │ │  Component  │ │  Component  │
                        └─────────────┘ └─────────────┘ └─────────────┘
```

---

## 8. Components: The Heart of Angular

### What is a Component?

A component is a **self-contained piece of the user interface** that includes:
1. **Logic** (TypeScript class)
2. **View** (HTML template)
3. **Styles** (CSS)

Think of components like custom HTML tags you create.

### Anatomy of a Component

```typescript
// product.component.ts
import { Component, Input, Output, EventEmitter } from '@angular/core';

@Component({
  // 1. Metadata - tells Angular about this component
  selector: 'app-product',              // How to use: <app-product></app-product>
  standalone: true,                     // Self-contained (Angular 21 default)
  imports: [],                          // Other components/directives used
  templateUrl: './product.component.html',
  styleUrl: './product.component.css'
})
export class ProductComponent {
  // 2. Properties - data the component uses
  @Input() product!: Product;           // Data coming IN from parent
  @Output() addToCart = new EventEmitter<Product>(); // Data going OUT to parent
  
  quantity = 1;
  
  // 3. Methods - actions the component can perform
  incrementQuantity(): void {
    this.quantity++;
  }
  
  decrementQuantity(): void {
    if (this.quantity > 1) {
      this.quantity--;
    }
  }
  
  onAddToCart(): void {
    this.addToCart.emit(this.product);
  }
}

// Define what a Product looks like
interface Product {
  id: number;
  name: string;
  price: number;
  imageUrl: string;
}
```

### Creating Components with the CLI

```bash
# Generate a new component
ng generate component components/product

# Shorthand
ng g c components/product

# This creates:
# src/app/components/product/
#   ├── product.component.ts
#   ├── product.component.html
#   ├── product.component.css
#   └── product.component.spec.ts
```

### Component Lifecycle Hooks

Components go through a lifecycle. Angular provides hooks to run code at specific moments:

```typescript
import { 
  Component, 
  OnInit, 
  OnChanges, 
  OnDestroy,
  SimpleChanges 
} from '@angular/core';

@Component({...})
export class MyComponent implements OnInit, OnChanges, OnDestroy {
  
  // Called when input properties change
  ngOnChanges(changes: SimpleChanges): void {
    console.log('Input changed:', changes);
  }
  
  // Called once after component is initialized
  ngOnInit(): void {
    console.log('Component initialized');
    // Good place to fetch initial data
  }
  
  // Called just before component is destroyed
  ngOnDestroy(): void {
    console.log('Component being destroyed');
    // Good place to clean up subscriptions, timers, etc.
  }
}
```

**Lifecycle Order:**

```
┌─────────────────────────────────────────────────────────────┐
│  1. constructor()      → Class instantiated                 │
│  2. ngOnChanges()      → Input properties set/changed       │
│  3. ngOnInit()         → Component initialized              │
│  4. ngDoCheck()        → Change detection runs              │
│  5. ngAfterContentInit() → Content projected                │
│  6. ngAfterContentChecked() → Projected content checked     │
│  7. ngAfterViewInit()  → View initialized                   │
│  8. ngAfterViewChecked() → View checked                     │
│  9. ngOnDestroy()      → Component about to be destroyed    │
└─────────────────────────────────────────────────────────────┘
```

**Most commonly used:**
- `ngOnInit` - Initialize data, fetch from server
- `ngOnChanges` - React to input changes
- `ngOnDestroy` - Clean up resources

---

## 9. Templates and Data Binding

### What is Data Binding?

Data binding is the automatic synchronization of data between the component class and its template.

### Types of Data Binding

```
┌─────────────────────────────────────────────────────────────────────┐
│                        DATA BINDING                                  │
├──────────────────────┬──────────────────────────────────────────────┤
│  INTERPOLATION       │  {{ expression }}                            │
│  (One-way: TS → HTML)│  Display data from component                 │
├──────────────────────┼──────────────────────────────────────────────┤
│  PROPERTY BINDING    │  [property]="expression"                     │
│  (One-way: TS → HTML)│  Bind to element/component property          │
├──────────────────────┼──────────────────────────────────────────────┤
│  EVENT BINDING       │  (event)="handler()"                         │
│  (One-way: HTML → TS)│  Respond to user actions                     │
├──────────────────────┼──────────────────────────────────────────────┤
│  TWO-WAY BINDING     │  [(ngModel)]="property"                      │
│  (Both directions)   │  Sync input with property                    │
└──────────────────────┴──────────────────────────────────────────────┘
```

### 1. Interpolation `{{ }}`

Displays component data in the template:

```typescript
// Component
export class UserComponent {
  userName = 'Alice';
  age = 25;
  
  getFullName(): string {
    return `${this.userName} Smith`;
  }
}
```

```html
<!-- Template -->
<h1>Hello, {{ userName }}!</h1>
<p>Age: {{ age }}</p>
<p>Full name: {{ getFullName() }}</p>
<p>Next year you'll be {{ age + 1 }}</p>
```

### 2. Property Binding `[ ]`

Binds data to element properties:

```typescript
// Component
export class ImageComponent {
  imageUrl = 'https://example.com/photo.jpg';
  imageAlt = 'Profile photo';
  isButtonDisabled = true;
}
```

```html
<!-- Template -->
<!-- Binding to standard HTML properties -->
<img [src]="imageUrl" [alt]="imageAlt">
<button [disabled]="isButtonDisabled">Submit</button>

<!-- Binding to CSS classes -->
<div [class.active]="isActive">Toggle me</div>
<div [class]="dynamicClasses">Multiple classes</div>

<!-- Binding to styles -->
<div [style.color]="textColor">Colored text</div>
<div [style.fontSize.px]="fontSize">Sized text</div>
```

### 3. Event Binding `( )`

Responds to user interactions:

```typescript
// Component
export class CounterComponent {
  count = 0;
  
  increment(): void {
    this.count++;
  }
  
  decrement(): void {
    this.count--;
  }
  
  handleInput(event: Event): void {
    const input = event.target as HTMLInputElement;
    console.log('User typed:', input.value);
  }
  
  handleKeydown(event: KeyboardEvent): void {
    if (event.key === 'Enter') {
      console.log('Enter pressed!');
    }
  }
}
```

```html
<!-- Template -->
<button (click)="increment()">+</button>
<span>{{ count }}</span>
<button (click)="decrement()">-</button>

<!-- Passing the event object -->
<input (input)="handleInput($event)" />

<!-- Keyboard events -->
<input (keydown)="handleKeydown($event)" />
<input (keydown.enter)="handleEnter()" /> <!-- Shortcut! -->

<!-- Mouse events -->
<div (mouseenter)="onHover()" (mouseleave)="onLeave()">
  Hover me
</div>
```

### 4. Two-Way Binding `[( )]`

Combines property and event binding for forms:

```typescript
// Component
import { Component } from '@angular/core';
import { FormsModule } from '@angular/forms';

@Component({
  selector: 'app-form',
  standalone: true,
  imports: [FormsModule],  // Required for ngModel
  template: `
    <input [(ngModel)]="searchTerm" placeholder="Search...">
    <p>You're searching for: {{ searchTerm }}</p>
  `
})
export class FormComponent {
  searchTerm = '';
}
```

**Behind the scenes, `[(ngModel)]="searchTerm"` is equivalent to:**

```html
<input [ngModel]="searchTerm" (ngModelChange)="searchTerm = $event">
```

### Template Reference Variables

Access elements directly in the template:

```html
<!-- Create a reference with # -->
<input #nameInput type="text" placeholder="Enter your name">
<button (click)="greet(nameInput.value)">Greet</button>

<!-- Reference components too -->
<app-timer #timer></app-timer>
<button (click)="timer.start()">Start Timer</button>
<button (click)="timer.stop()">Stop Timer</button>
```

---

## 10. Directives: Extending HTML

### What are Directives?

Directives are instructions that tell Angular to do something to a DOM element. Think of them as special HTML attributes.

### Types of Directives

```
┌─────────────────────────────────────────────────────────────┐
│                       DIRECTIVES                             │
├───────────────────┬─────────────────────────────────────────┤
│  COMPONENTS       │  Directives with templates               │
│                   │  Example: <app-header></app-header>      │
├───────────────────┼─────────────────────────────────────────┤
│  STRUCTURAL       │  Change DOM layout (add/remove elements) │
│                   │  Examples: @if, @for, @switch            │
├───────────────────┼─────────────────────────────────────────┤
│  ATTRIBUTE        │  Change appearance/behavior              │
│                   │  Examples: ngClass, ngStyle, custom      │
└───────────────────┴─────────────────────────────────────────┘
```

### Built-in Control Flow (Angular 21)

Angular 21 uses the new control flow syntax:

#### `@if` - Conditional Rendering

```typescript
// Component
export class UserComponent {
  isLoggedIn = false;
  user = { name: 'Alice', role: 'admin' };
}
```

```html
<!-- Template -->
@if (isLoggedIn) {
  <p>Welcome back, {{ user.name }}!</p>
  
  @if (user.role === 'admin') {
    <button>Admin Panel</button>
  }
} @else {
  <p>Please log in to continue.</p>
  <button>Login</button>
}
```

#### `@for` - Looping

```typescript
// Component
export class ListComponent {
  items = [
    { id: 1, name: 'Apple', price: 1.5 },
    { id: 2, name: 'Banana', price: 0.75 },
    { id: 3, name: 'Orange', price: 2.0 }
  ];
}
```

```html
<!-- Template -->
<ul>
  @for (item of items; track item.id) {
    <li>
      {{ item.name }} - ${{ item.price }}
    </li>
  } @empty {
    <li>No items available</li>
  }
</ul>

<!-- With index and other context variables -->
@for (item of items; track item.id; let i = $index; let first = $first; let last = $last) {
  <div [class.first]="first" [class.last]="last">
    {{ i + 1 }}. {{ item.name }}
  </div>
}
```

**Available context variables in `@for`:**
- `$index` - Current index (0-based)
- `$first` - True if first item
- `$last` - True if last item
- `$even` - True if index is even
- `$odd` - True if index is odd
- `$count` - Total number of items

#### `@switch` - Multiple Conditions

```typescript
// Component
export class StatusComponent {
  status: 'loading' | 'success' | 'error' | 'idle' = 'idle';
}
```

```html
<!-- Template -->
@switch (status) {
  @case ('loading') {
    <div class="spinner">Loading...</div>
  }
  @case ('success') {
    <div class="success">Data loaded successfully!</div>
  }
  @case ('error') {
    <div class="error">Something went wrong.</div>
  }
  @default {
    <div>Click to load data.</div>
  }
}
```

### Attribute Directives

#### `ngClass` - Dynamic CSS Classes

```typescript
// Component
export class StyleComponent {
  isActive = true;
  isDisabled = false;
  currentTheme = 'dark';
}
```

```html
<!-- Single class toggle -->
<div [ngClass]="{'active': isActive, 'disabled': isDisabled}">
  Styled content
</div>

<!-- Using string -->
<div [ngClass]="currentTheme + '-theme'">
  Themed content
</div>

<!-- Using array -->
<div [ngClass]="['base-class', isActive ? 'active' : 'inactive']">
  Multiple classes
</div>
```

#### `ngStyle` - Dynamic Inline Styles

```typescript
// Component
export class ColorComponent {
  textColor = 'blue';
  fontSize = 18;
  backgroundColor = '#f0f0f0';
}
```

```html
<!-- Multiple styles -->
<div [ngStyle]="{
  'color': textColor,
  'font-size.px': fontSize,
  'background-color': backgroundColor
}">
  Dynamically styled text
</div>
```

### Creating Custom Directives

```typescript
// highlight.directive.ts
import { Directive, ElementRef, HostListener, Input } from '@angular/core';

@Directive({
  selector: '[appHighlight]',  // Usage: <p appHighlight>Text</p>
  standalone: true
})
export class HighlightDirective {
  @Input() appHighlight = 'yellow';  // Default color
  @Input() textColor = 'black';
  
  constructor(private el: ElementRef) {}
  
  @HostListener('mouseenter') onMouseEnter() {
    this.highlight(this.appHighlight, this.textColor);
  }
  
  @HostListener('mouseleave') onMouseLeave() {
    this.highlight('', '');
  }
  
  private highlight(bgColor: string, textColor: string) {
    this.el.nativeElement.style.backgroundColor = bgColor;
    this.el.nativeElement.style.color = textColor;
  }
}
```

```html
<!-- Using the custom directive -->
<p appHighlight>Hover to highlight yellow</p>
<p appHighlight="lightblue">Hover to highlight blue</p>
<p appHighlight="pink" textColor="white">Pink with white text</p>
```

---

## 11. Services and Dependency Injection

### What is a Service?

A **service** is a class that handles business logic, data fetching, or shared functionality. Services keep components lean and focused on the UI.

**Without services:**
```
Component A ─┐
             │  Each component fetches its own data
Component B ─┤  = Duplicate code, inconsistent data
             │
Component C ─┘
```

**With services:**
```
Component A ─┐
             │     ┌─────────────┐     ┌──────────┐
Component B ─┼────▶│   Service   │────▶│   API    │
             │     └─────────────┘     └──────────┘
Component C ─┘     Centralized logic   External data
```

### Creating a Service

```bash
# Generate a service
ng generate service services/user

# Shorthand
ng g s services/user
```

```typescript
// user.service.ts
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root'  // Available throughout the app
})
export class UserService {
  private users: User[] = [
    { id: 1, name: 'Alice', email: 'alice@example.com' },
    { id: 2, name: 'Bob', email: 'bob@example.com' }
  ];
  
  getAllUsers(): User[] {
    return this.users;
  }
  
  getUserById(id: number): User | undefined {
    return this.users.find(user => user.id === id);
  }
  
  addUser(user: User): void {
    this.users.push(user);
  }
  
  deleteUser(id: number): void {
    this.users = this.users.filter(user => user.id !== id);
  }
}

interface User {
  id: number;
  name: string;
  email: string;
}
```

### What is Dependency Injection (DI)?

**Dependency Injection** is a design pattern where a class receives its dependencies from external sources rather than creating them itself.

**Without DI (bad):**
```typescript
class Car {
  private engine: Engine;
  
  constructor() {
    // Car creates its own engine - tightly coupled!
    this.engine = new Engine();
  }
}
```

**With DI (good):**
```typescript
class Car {
  constructor(private engine: Engine) {
    // Engine is provided externally - loosely coupled!
  }
}
```

### Using Services in Components

```typescript
// user-list.component.ts
import { Component, OnInit } from '@angular/core';
import { UserService } from '../services/user.service';

@Component({
  selector: 'app-user-list',
  standalone: true,
  template: `
    <ul>
      @for (user of users; track user.id) {
        <li>{{ user.name }} ({{ user.email }})</li>
      }
    </ul>
  `
})
export class UserListComponent implements OnInit {
  users: User[] = [];
  
  // Angular automatically provides the service
  constructor(private userService: UserService) {}
  
  ngOnInit(): void {
    this.users = this.userService.getAllUsers();
  }
}
```

### Using `inject()` Function (Modern Approach)

Angular 21 prefers the `inject()` function over constructor injection:

```typescript
import { Component, OnInit, inject } from '@angular/core';
import { UserService } from '../services/user.service';

@Component({...})
export class UserListComponent implements OnInit {
  private userService = inject(UserService);
  users: User[] = [];
  
  ngOnInit(): void {
    this.users = this.userService.getAllUsers();
  }
}
```

### Providing Services at Different Levels

```typescript
// 1. Root level (most common) - one instance for entire app
@Injectable({
  providedIn: 'root'
})
export class GlobalService {}

// 2. Component level - new instance per component
@Component({
  providers: [LocalService]  // Each component gets its own instance
})
export class MyComponent {}
```

---

## 12. Routing and Navigation

### What is Routing?

Routing allows users to navigate between different views/pages in your application without full page reloads.

### Setting Up Routes

```typescript
// app.routes.ts
import { Routes } from '@angular/router';

import { HomeComponent } from './pages/home/home.component';
import { AboutComponent } from './pages/about/about.component';
import { ProductsComponent } from './pages/products/products.component';
import { ProductDetailComponent } from './pages/product-detail/product-detail.component';
import { NotFoundComponent } from './pages/not-found/not-found.component';

export const routes: Routes = [
  // Basic route
  { path: '', component: HomeComponent },
  { path: 'about', component: AboutComponent },
  { path: 'products', component: ProductsComponent },
  
  // Route with parameter
  { path: 'products/:id', component: ProductDetailComponent },
  
  // Redirect
  { path: 'home', redirectTo: '', pathMatch: 'full' },
  
  // Wildcard (404 page) - must be last!
  { path: '**', component: NotFoundComponent }
];
```

```typescript
// app.config.ts
import { ApplicationConfig } from '@angular/core';
import { provideRouter } from '@angular/router';
import { routes } from './app.routes';

export const appConfig: ApplicationConfig = {
  providers: [
    provideRouter(routes)
  ]
};
```

### Router Outlet

The `<router-outlet>` is a placeholder where routed components are displayed:

```typescript
// app.component.ts
import { Component } from '@angular/core';
import { RouterOutlet, RouterLink, RouterLinkActive } from '@angular/router';

@Component({
  selector: 'app-root',
  standalone: true,
  imports: [RouterOutlet, RouterLink, RouterLinkActive],
  template: `
    <nav>
      <a routerLink="/" routerLinkActive="active" 
         [routerLinkActiveOptions]="{exact: true}">Home</a>
      <a routerLink="/about" routerLinkActive="active">About</a>
      <a routerLink="/products" routerLinkActive="active">Products</a>
    </nav>
    
    <main>
      <router-outlet></router-outlet>  <!-- Components display here -->
    </main>
  `,
  styles: [`
    nav a.active {
      font-weight: bold;
      color: #dd0031;
    }
  `]
})
export class AppComponent {}
```

### Accessing Route Parameters

```typescript
// product-detail.component.ts
import { Component, OnInit, inject } from '@angular/core';
import { ActivatedRoute } from '@angular/router';

@Component({
  selector: 'app-product-detail',
  standalone: true,
  template: `
    <h1>Product {{ productId }}</h1>
  `
})
export class ProductDetailComponent implements OnInit {
  private route = inject(ActivatedRoute);
  productId: string = '';
  
  ngOnInit(): void {
    // Get route parameter
    this.productId = this.route.snapshot.paramMap.get('id') ?? '';
    
    // Or subscribe to changes
    this.route.paramMap.subscribe(params => {
      this.productId = params.get('id') ?? '';
    });
  }
}
```

### Programmatic Navigation

```typescript
import { Component, inject } from '@angular/core';
import { Router } from '@angular/router';

@Component({...})
export class SomeComponent {
  private router = inject(Router);
  
  goToProduct(id: number): void {
    // Navigate by URL
    this.router.navigate(['/products', id]);
    
    // Or with query parameters
    this.router.navigate(['/products'], {
      queryParams: { category: 'electronics', sort: 'price' }
    });
  }
  
  goBack(): void {
    // Navigate back (requires Location service)
    window.history.back();
  }
}
```

### Lazy Loading Routes

Lazy loading loads route modules only when needed, improving initial load time:

```typescript
// app.routes.ts
export const routes: Routes = [
  { path: '', component: HomeComponent },
  
  // Lazy loaded routes
  {
    path: 'admin',
    loadComponent: () => import('./pages/admin/admin.component')
      .then(m => m.AdminComponent)
  },
  {
    path: 'dashboard',
    loadChildren: () => import('./pages/dashboard/dashboard.routes')
      .then(m => m.dashboardRoutes)
  }
];
```

### Route Guards

Guards protect routes based on conditions:

```typescript
// auth.guard.ts
import { inject } from '@angular/core';
import { Router, CanActivateFn } from '@angular/router';
import { AuthService } from './auth.service';

export const authGuard: CanActivateFn = (route, state) => {
  const authService = inject(AuthService);
  const router = inject(Router);
  
  if (authService.isLoggedIn()) {
    return true;
  }
  
  // Redirect to login
  router.navigate(['/login'], { queryParams: { returnUrl: state.url } });
  return false;
};

// Using the guard in routes
export const routes: Routes = [
  {
    path: 'dashboard',
    component: DashboardComponent,
    canActivate: [authGuard]  // Protected route
  }
];
```

---

## 13. Forms and User Input

### Two Approaches to Forms

Angular provides two ways to handle forms:

| Feature | Template-Driven | Reactive |
|---------|-----------------|----------|
| Form model | Template (HTML) | Component (TypeScript) |
| Validation | Directives | Functions |
| Complexity | Simple forms | Complex forms |
| Testing | Harder | Easier |
| Control | Less | More |

### Template-Driven Forms

Easier for simple forms, defined mainly in HTML:

```typescript
// contact.component.ts
import { Component } from '@angular/core';
import { FormsModule, NgForm } from '@angular/forms';

@Component({
  selector: 'app-contact',
  standalone: true,
  imports: [FormsModule],
  template: `
    <form #contactForm="ngForm" (ngSubmit)="onSubmit(contactForm)">
      
      <div class="form-group">
        <label for="name">Name</label>
        <input 
          type="text" 
          id="name"
          name="name"
          [(ngModel)]="formData.name"
          required
          minlength="3"
          #name="ngModel"
        >
        @if (name.invalid && name.touched) {
          <span class="error">
            @if (name.errors?.['required']) {
              Name is required.
            }
            @if (name.errors?.['minlength']) {
              Name must be at least 3 characters.
            }
          </span>
        }
      </div>
      
      <div class="form-group">
        <label for="email">Email</label>
        <input 
          type="email" 
          id="email"
          name="email"
          [(ngModel)]="formData.email"
          required
          email
          #email="ngModel"
        >
        @if (email.invalid && email.touched) {
          <span class="error">Please enter a valid email.</span>
        }
      </div>
      
      <div class="form-group">
        <label for="message">Message</label>
        <textarea
          id="message"
          name="message"
          [(ngModel)]="formData.message"
          required
          #message="ngModel"
        ></textarea>
      </div>
      
      <button type="submit" [disabled]="contactForm.invalid">
        Send Message
      </button>
      
    </form>
  `
})
export class ContactComponent {
  formData = {
    name: '',
    email: '',
    message: ''
  };
  
  onSubmit(form: NgForm): void {
    if (form.valid) {
      console.log('Form data:', this.formData);
      // Send to server...
      form.reset();
    }
  }
}
```

### Reactive Forms

More powerful for complex forms, defined in TypeScript:

```typescript
// register.component.ts
import { Component, inject } from '@angular/core';
import { 
  ReactiveFormsModule, 
  FormBuilder, 
  Validators,
  AbstractControl,
  ValidationErrors 
} from '@angular/forms';

@Component({
  selector: 'app-register',
  standalone: true,
  imports: [ReactiveFormsModule],
  template: `
    <form [formGroup]="registerForm" (ngSubmit)="onSubmit()">
      
      <div class="form-group">
        <label>Username</label>
        <input type="text" formControlName="username">
        @if (registerForm.get('username')?.invalid && 
             registerForm.get('username')?.touched) {
          <span class="error">
            Username is required (3-20 characters).
          </span>
        }
      </div>
      
      <div class="form-group">
        <label>Email</label>
        <input type="email" formControlName="email">
      </div>
      
      <div formGroupName="passwords">
        <div class="form-group">
          <label>Password</label>
          <input type="password" formControlName="password">
        </div>
        
        <div class="form-group">
          <label>Confirm Password</label>
          <input type="password" formControlName="confirmPassword">
        </div>
        
        @if (registerForm.get('passwords')?.errors?.['passwordMismatch']) {
          <span class="error">Passwords must match.</span>
        }
      </div>
      
      <div class="form-group">
        <label>
          <input type="checkbox" formControlName="acceptTerms">
          I accept the terms and conditions
        </label>
      </div>
      
      <button type="submit" [disabled]="registerForm.invalid">
        Register
      </button>
      
      <pre>Form Value: {{ registerForm.value | json }}</pre>
      <pre>Form Valid: {{ registerForm.valid }}</pre>
      
    </form>
  `
})
export class RegisterComponent {
  private fb = inject(FormBuilder);
  
  registerForm = this.fb.group({
    username: ['', [
      Validators.required,
      Validators.minLength(3),
      Validators.maxLength(20)
    ]],
    email: ['', [Validators.required, Validators.email]],
    passwords: this.fb.group({
      password: ['', [Validators.required, Validators.minLength(8)]],
      confirmPassword: ['', Validators.required]
    }, { validators: this.passwordMatchValidator }),
    acceptTerms: [false, Validators.requiredTrue]
  });
  
  // Custom validator
  passwordMatchValidator(control: AbstractControl): ValidationErrors | null {
    const password = control.get('password');
    const confirmPassword = control.get('confirmPassword');
    
    if (password?.value !== confirmPassword?.value) {
      return { passwordMismatch: true };
    }
    return null;
  }
  
  onSubmit(): void {
    if (this.registerForm.valid) {
      console.log('Form submitted:', this.registerForm.value);
    }
  }
}
```

---

## 14. HTTP and API Communication

### What is an API?

**API (Application Programming Interface)** is a way for your application to communicate with a server to send or receive data.

```
┌─────────────┐     HTTP Request      ┌─────────────┐
│   Angular   │ ───────────────────▶  │   Server    │
│     App     │                       │   (API)     │
│             │ ◀───────────────────  │             │
└─────────────┘     HTTP Response     └─────────────┘

Request Methods:
  GET    - Retrieve data
  POST   - Create new data
  PUT    - Update existing data
  DELETE - Remove data
  PATCH  - Partial update
```

### Setting Up HttpClient

```typescript
// app.config.ts
import { ApplicationConfig } from '@angular/core';
import { provideRouter } from '@angular/router';
import { provideHttpClient } from '@angular/common/http';
import { routes } from './app.routes';

export const appConfig: ApplicationConfig = {
  providers: [
    provideRouter(routes),
    provideHttpClient()  // Add this!
  ]
};
```

### Creating a Data Service

```typescript
// product.service.ts
import { Injectable, inject } from '@angular/core';
import { HttpClient, HttpErrorResponse } from '@angular/common/http';
import { Observable, throwError } from 'rxjs';
import { catchError, map } from 'rxjs/operators';

export interface Product {
  id: number;
  name: string;
  price: number;
  description: string;
}

@Injectable({
  providedIn: 'root'
})
export class ProductService {
  private http = inject(HttpClient);
  private apiUrl = 'https://api.example.com/products';
  
  // GET all products
  getProducts(): Observable<Product[]> {
    return this.http.get<Product[]>(this.apiUrl).pipe(
      catchError(this.handleError)
    );
  }
  
  // GET single product
  getProduct(id: number): Observable<Product> {
    return this.http.get<Product>(`${this.apiUrl}/${id}`).pipe(
      catchError(this.handleError)
    );
  }
  
  // POST - Create new product
  createProduct(product: Omit<Product, 'id'>): Observable<Product> {
    return this.http.post<Product>(this.apiUrl, product).pipe(
      catchError(this.handleError)
    );
  }
  
  // PUT - Update product
  updateProduct(id: number, product: Product): Observable<Product> {
    return this.http.put<Product>(`${this.apiUrl}/${id}`, product).pipe(
      catchError(this.handleError)
    );
  }
  
  // DELETE - Remove product
  deleteProduct(id: number): Observable<void> {
    return this.http.delete<void>(`${this.apiUrl}/${id}`).pipe(
      catchError(this.handleError)
    );
  }
  
  // Error handling
  private handleError(error: HttpErrorResponse): Observable<never> {
    let errorMessage = 'An error occurred';
    
    if (error.error instanceof ErrorEvent) {
      // Client-side error
      errorMessage = `Error: ${error.error.message}`;
    } else {
      // Server-side error
      errorMessage = `Error Code: ${error.status}\nMessage: ${error.message}`;
    }
    
    console.error(errorMessage);
    return throwError(() => new Error(errorMessage));
  }
}
```

### Using the Service in a Component

```typescript
// product-list.component.ts
import { Component, OnInit, inject } from '@angular/core';
import { ProductService, Product } from '../services/product.service';

@Component({
  selector: 'app-product-list',
  standalone: true,
  template: `
    @if (loading) {
      <div class="loading">Loading products...</div>
    }
    
    @if (error) {
      <div class="error">{{ error }}</div>
    }
    
    @if (!loading && !error) {
      <div class="products">
        @for (product of products; track product.id) {
          <div class="product-card">
            <h3>{{ product.name }}</h3>
            <p>\${{ product.price }}</p>
            <button (click)="deleteProduct(product.id)">Delete</button>
          </div>
        } @empty {
          <p>No products found.</p>
        }
      </div>
    }
  `
})
export class ProductListComponent implements OnInit {
  private productService = inject(ProductService);
  
  products: Product[] = [];
  loading = false;
  error = '';
  
  ngOnInit(): void {
    this.loadProducts();
  }
  
  loadProducts(): void {
    this.loading = true;
    this.error = '';
    
    this.productService.getProducts().subscribe({
      next: (products) => {
        this.products = products;
        this.loading = false;
      },
      error: (err) => {
        this.error = err.message;
        this.loading = false;
      }
    });
  }
  
  deleteProduct(id: number): void {
    this.productService.deleteProduct(id).subscribe({
      next: () => {
        this.products = this.products.filter(p => p.id !== id);
      },
      error: (err) => {
        this.error = err.message;
      }
    });
  }
}
```

### Understanding Observables

**Observables** are streams of data that arrive over time. They're like promises but more powerful.

```typescript
import { Observable, of, interval, from } from 'rxjs';
import { map, filter, take, switchMap, debounceTime } from 'rxjs/operators';

// Creating observables
const simple$ = of(1, 2, 3, 4, 5);          // Emit values immediately
const timer$ = interval(1000);               // Emit every second
const fromArray$ = from([1, 2, 3]);          // From array

// Using operators
simple$.pipe(
  map(x => x * 2),           // Transform: [2, 4, 6, 8, 10]
  filter(x => x > 5)         // Filter: [6, 8, 10]
).subscribe(value => console.log(value));

// Real-world example: Search with debounce
searchInput$.pipe(
  debounceTime(300),         // Wait 300ms after user stops typing
  switchMap(term =>          // Cancel previous request, start new one
    this.http.get(`/api/search?q=${term}`)
  )
).subscribe(results => {
  this.searchResults = results;
});
```

---

## 15. State Management

### What is State?

**State** is the data that your application needs to function. It includes:
- User information (logged in? name? preferences?)
- UI state (which tab is active? is the menu open?)
- Data from the server (products, orders, etc.)

### Component State

Each component can manage its own state:

```typescript
@Component({...})
export class CounterComponent {
  // Local state
  count = 0;
  
  increment() { this.count++; }
  decrement() { this.count--; }
}
```

### Sharing State Between Components

#### Parent to Child: `@Input()`

```typescript
// parent.component.ts
@Component({
  template: `<app-child [message]="parentMessage"></app-child>`
})
export class ParentComponent {
  parentMessage = 'Hello from parent!';
}

// child.component.ts
@Component({
  template: `<p>{{ message }}</p>`
})
export class ChildComponent {
  @Input() message = '';
}
```

#### Child to Parent: `@Output()`

```typescript
// child.component.ts
@Component({
  template: `<button (click)="sendMessage()">Send to Parent</button>`
})
export class ChildComponent {
  @Output() messageEvent = new EventEmitter<string>();
  
  sendMessage() {
    this.messageEvent.emit('Hello from child!');
  }
}

// parent.component.ts
@Component({
  template: `
    <app-child (messageEvent)="receiveMessage($event)"></app-child>
    <p>{{ receivedMessage }}</p>
  `
})
export class ParentComponent {
  receivedMessage = '';
  
  receiveMessage(message: string) {
    this.receivedMessage = message;
  }
}
```

#### Unrelated Components: Service with Subject

```typescript
// message.service.ts
import { Injectable } from '@angular/core';
import { BehaviorSubject, Observable } from 'rxjs';

@Injectable({ providedIn: 'root' })
export class MessageService {
  private messageSubject = new BehaviorSubject<string>('Initial message');
  
  // Observable that components can subscribe to
  message$: Observable<string> = this.messageSubject.asObservable();
  
  // Method to update the message
  updateMessage(message: string): void {
    this.messageSubject.next(message);
  }
}

// Any component can now:
// - Read: this.messageService.message$.subscribe(msg => ...)
// - Write: this.messageService.updateMessage('New message')
```

---

## 16. Signals: Modern Reactivity in Angular

### What are Signals?

**Signals** are a new way to handle reactive data in Angular 21. They're simpler than Observables for many use cases.

```typescript
import { Component, signal, computed, effect } from '@angular/core';

@Component({
  selector: 'app-counter',
  standalone: true,
  template: `
    <h1>Count: {{ count() }}</h1>
    <h2>Double: {{ doubleCount() }}</h2>
    <button (click)="increment()">+</button>
    <button (click)="decrement()">-</button>
    <button (click)="reset()">Reset</button>
  `
})
export class CounterComponent {
  // Create a signal with initial value
  count = signal(0);
  
  // Computed signal - automatically updates when count changes
  doubleCount = computed(() => this.count() * 2);
  
  constructor() {
    // Effect - runs whenever signals it reads change
    effect(() => {
      console.log(`Count changed to: ${this.count()}`);
    });
  }
  
  increment() {
    // Update signal value
    this.count.update(value => value + 1);
  }
  
  decrement() {
    this.count.update(value => value - 1);
  }
  
  reset() {
    // Set signal to specific value
    this.count.set(0);
  }
}
```

### Signals vs Observables

| Feature | Signals | Observables |
|---------|---------|-------------|
| Complexity | Simple | More complex |
| Synchronous | Yes | Can be async |
| Current value | Always has one | May not have one |
| Subscription | Not needed in templates | Need async pipe |
| Use case | UI state, simple data | HTTP, events, streams |

### Signal Patterns

#### Object Signals

```typescript
interface User {
  name: string;
  age: number;
}

// Object signal
const user = signal<User>({ name: 'Alice', age: 30 });

// Update entire object
user.set({ name: 'Bob', age: 25 });

// Update partial (using update)
user.update(current => ({ ...current, age: current.age + 1 }));
```

#### Array Signals

```typescript
const items = signal<string[]>(['apple', 'banana']);

// Add item
items.update(current => [...current, 'cherry']);

// Remove item
items.update(current => current.filter(item => item !== 'banana'));
```

#### Input Signals (Angular 21)

```typescript
import { Component, input } from '@angular/core';

@Component({
  selector: 'app-greeting',
  template: `<h1>Hello, {{ name() }}!</h1>`
})
export class GreetingComponent {
  // Required input signal
  name = input.required<string>();
  
  // Optional input signal with default
  greeting = input('Hello');
}
```

#### Output Signals (Angular 21)

```typescript
import { Component, output } from '@angular/core';

@Component({
  selector: 'app-button',
  template: `<button (click)="handleClick()">Click me</button>`
})
export class ButtonComponent {
  // Output signal
  clicked = output<void>();
  
  handleClick() {
    this.clicked.emit();
  }
}
```

---

## 17. Standalone Components

### What are Standalone Components?

In Angular 21, **standalone components** are the default. They're self-contained and don't require NgModules.

### Before: NgModule-based (Legacy)

```typescript
// app.module.ts (OLD WAY)
@NgModule({
  declarations: [
    AppComponent,
    HeaderComponent,
    FooterComponent
  ],
  imports: [
    BrowserModule,
    FormsModule,
    HttpClientModule
  ],
  bootstrap: [AppComponent]
})
export class AppModule {}
```

### Now: Standalone (Angular 21)

```typescript
// header.component.ts
@Component({
  selector: 'app-header',
  standalone: true,  // Self-contained!
  imports: [RouterLink],  // Import what you need
  template: `
    <header>
      <a routerLink="/">Home</a>
    </header>
  `
})
export class HeaderComponent {}

// app.component.ts
@Component({
  selector: 'app-root',
  standalone: true,
  imports: [HeaderComponent, RouterOutlet],  // Import components directly
  template: `
    <app-header></app-header>
    <router-outlet></router-outlet>
  `
})
export class AppComponent {}
```

### Benefits of Standalone Components

1. **Simpler** - No NgModule boilerplate
2. **Tree-shakable** - Unused components aren't bundled
3. **Lazy-loadable** - Easy to lazy load individual components
4. **Self-documenting** - Dependencies are explicit

---

## 18. Testing Your Application

### Types of Testing

```
┌─────────────────────────────────────────────────────────────┐
│                      TESTING PYRAMID                         │
│                                                             │
│                         /\                                  │
│                        /  \         E2E Tests               │
│                       /────\        (Few, Slow, Expensive)  │
│                      /      \                               │
│                     /────────\      Integration Tests       │
│                    /          \     (Some)                  │
│                   /────────────\                            │
│                  /              \   Unit Tests              │
│                 /────────────────\  (Many, Fast, Cheap)     │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Unit Testing with Jest/Jasmine

Angular uses **Jasmine** (testing framework) and **Karma** (test runner) by default, though many projects now use **Jest**.

```typescript
// counter.component.spec.ts
import { ComponentFixture, TestBed } from '@angular/core/testing';
import { CounterComponent } from './counter.component';

describe('CounterComponent', () => {
  let component: CounterComponent;
  let fixture: ComponentFixture<CounterComponent>;
  
  beforeEach(async () => {
    await TestBed.configureTestingModule({
      imports: [CounterComponent]
    }).compileComponents();
    
    fixture = TestBed.createComponent(CounterComponent);
    component = fixture.componentInstance;
    fixture.detectChanges();
  });
  
  it('should create', () => {
    expect(component).toBeTruthy();
  });
  
  it('should start with count of 0', () => {
    expect(component.count()).toBe(0);
  });
  
  it('should increment count', () => {
    component.increment();
    expect(component.count()).toBe(1);
  });
  
  it('should decrement count', () => {
    component.count.set(5);
    component.decrement();
    expect(component.count()).toBe(4);
  });
  
  it('should display count in template', () => {
    component.count.set(42);
    fixture.detectChanges();
    
    const compiled = fixture.nativeElement as HTMLElement;
    expect(compiled.querySelector('h1')?.textContent).toContain('42');
  });
});
```

### Testing Services

```typescript
// user.service.spec.ts
import { TestBed } from '@angular/core/testing';
import { HttpClientTestingModule, HttpTestingController } from '@angular/common/http/testing';
import { UserService } from './user.service';

describe('UserService', () => {
  let service: UserService;
  let httpMock: HttpTestingController;
  
  beforeEach(() => {
    TestBed.configureTestingModule({
      imports: [HttpClientTestingModule],
      providers: [UserService]
    });
    
    service = TestBed.inject(UserService);
    httpMock = TestBed.inject(HttpTestingController);
  });
  
  afterEach(() => {
    httpMock.verify(); // Ensure no outstanding requests
  });
  
  it('should fetch users', () => {
    const mockUsers = [
      { id: 1, name: 'Alice' },
      { id: 2, name: 'Bob' }
    ];
    
    service.getUsers().subscribe(users => {
      expect(users.length).toBe(2);
      expect(users).toEqual(mockUsers);
    });
    
    const req = httpMock.expectOne('/api/users');
    expect(req.request.method).toBe('GET');
    req.flush(mockUsers);
  });
});
```

### Running Tests

```bash
# Run all tests
ng test

# Run tests once (CI mode)
ng test --watch=false

# Run tests with coverage
ng test --code-coverage

# Run specific test file
ng test --include=**/counter.component.spec.ts
```

---

## 19. Performance Optimization

### Change Detection Strategies

```typescript
import { Component, ChangeDetectionStrategy } from '@angular/core';

@Component({
  selector: 'app-product',
  changeDetection: ChangeDetectionStrategy.OnPush,  // Optimized!
  template: `...`
})
export class ProductComponent {}
```

**OnPush** only checks the component when:
- An `@Input()` reference changes
- An event originates from the component
- An Observable linked with `async` pipe emits
- Manual trigger with `ChangeDetectorRef`

### Lazy Loading

Load features only when needed:

```typescript
// app.routes.ts
export const routes: Routes = [
  {
    path: 'admin',
    loadComponent: () => import('./admin/admin.component')
      .then(m => m.AdminComponent)
  }
];
```

### TrackBy in Loops

Help Angular identify items efficiently:

```html
@for (item of items; track item.id) {
  <app-item [data]="item"></app-item>
}
```

### Virtual Scrolling

For long lists, render only visible items:

```typescript
import { Component } from '@angular/core';
import { ScrollingModule } from '@angular/cdk/scrolling';

@Component({
  selector: 'app-list',
  standalone: true,
  imports: [ScrollingModule],
  template: `
    <cdk-virtual-scroll-viewport itemSize="50" class="viewport">
      <div *cdkVirtualFor="let item of items" class="item">
        {{ item }}
      </div>
    </cdk-virtual-scroll-viewport>
  `,
  styles: [`
    .viewport {
      height: 400px;
    }
    .item {
      height: 50px;
    }
  `]
})
export class ListComponent {
  items = Array.from({ length: 10000 }, (_, i) => `Item ${i}`);
}
```

### Image Optimization

Use Angular's built-in image directive:

```typescript
import { NgOptimizedImage } from '@angular/common';

@Component({
  imports: [NgOptimizedImage],
  template: `
    <img 
      ngSrc="/assets/photo.jpg" 
      width="400" 
      height="300"
      priority
    >
  `
})
```

---

## 20. Deployment: Sharing Your App with the World

### Building for Production

```bash
# Build optimized production bundle
ng build

# Output is in the dist/ folder
# These are static files you can host anywhere!
```

### Build Optimization

```json
// angular.json (already configured for production)
{
  "configurations": {
    "production": {
      "budgets": [
        {
          "type": "initial",
          "maximumWarning": "500kb",
          "maximumError": "1mb"
        }
      ],
      "outputHashing": "all"
    }
  }
}
```

### Deployment Options

#### 1. Static Hosting (Simplest)

**Netlify, Vercel, GitHub Pages, Firebase Hosting**

```bash
# Example: Deploy to Netlify
npm install -g netlify-cli
ng build
netlify deploy --prod --dir=dist/my-app
```

#### 2. Server-Side Rendering (SSR)

For better SEO and initial load performance:

```bash
# Add SSR to existing project
ng add @angular/ssr

# Build with SSR
ng build

# Run the server
node dist/my-app/server/server.mjs
```

#### 3. Docker

```dockerfile
# Dockerfile
FROM node:20-alpine as build
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build

FROM nginx:alpine
COPY --from=build /app/dist/my-app/browser /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

---

## 21. What's New in Angular 21

### Key Features in Angular 21

> **Note**: Angular follows semantic versioning and releases major versions approximately every 6 months. Angular 21 represents the continued evolution of the framework.

#### 1. Zoneless Change Detection (Stable)

Angular 21 makes zoneless applications production-ready:

```typescript
// app.config.ts
import { ApplicationConfig } from '@angular/core';
import { provideExperimentalZonelessChangeDetection } from '@angular/core';

export const appConfig: ApplicationConfig = {
  providers: [
    provideExperimentalZonelessChangeDetection()
  ]
};
```

Benefits:
- Smaller bundle size (no zone.js)
- Better performance
- Simpler mental model

#### 2. Signal-Based Components (Default)

Signals are now the primary reactivity model:

```typescript
@Component({
  template: `
    <h1>{{ title() }}</h1>
    <p>Count: {{ count() }}</p>
  `
})
export class AppComponent {
  title = input.required<string>();
  count = signal(0);
  doubleCount = computed(() => this.count() * 2);
}
```

#### 3. Enhanced Control Flow

The new control flow syntax is now the standard:

```html
@if (user()) {
  <p>Welcome, {{ user().name }}!</p>
} @else {
  <p>Please log in.</p>
}

@for (item of items(); track item.id) {
  <app-item [item]="item" />
} @empty {
  <p>No items found.</p>
}

@switch (status()) {
  @case ('loading') { <spinner /> }
  @case ('error') { <error-message /> }
  @default { <content /> }
}
```

#### 4. Improved Developer Experience

- **Faster builds** with improved compilation
- **Better error messages** with more context
- **Enhanced DevTools** integration
- **Improved HMR** (Hot Module Replacement)

#### 5. Resource API (New)

A new way to handle async data:

```typescript
import { resource } from '@angular/core';

@Component({...})
export class UserComponent {
  userId = input.required<number>();
  
  userResource = resource({
    request: () => ({ id: this.userId() }),
    loader: async ({ request }) => {
      const response = await fetch(`/api/users/${request.id}`);
      return response.json();
    }
  });
  
  // Use in template
  // userResource.value() - the data
  // userResource.isLoading() - loading state
  // userResource.error() - error state
}
```

#### 6. Linked Signals

Create signals that react to other signals:

```typescript
import { signal, linkedSignal } from '@angular/core';

const items = signal(['apple', 'banana', 'cherry']);

// Automatically updates when items changes
const selectedItem = linkedSignal(() => items()[0]);

// Can still be manually set
selectedItem.set('banana');
```

---

## 22. Next Steps and Resources

### Learning Path

```
┌─────────────────────────────────────────────────────────────────────┐
│                        YOUR ANGULAR JOURNEY                          │
│                                                                     │
│  BEGINNER ────────────────────────────────────────────▶ ADVANCED   │
│                                                                     │
│  ┌─────────────┐   ┌─────────────┐   ┌─────────────┐   ┌─────────┐ │
│  │ Basics      │──▶│ Core        │──▶│ Advanced    │──▶│ Expert  │ │
│  │ HTML/CSS/JS │   │ Components  │   │ State Mgmt  │   │ Arch    │ │
│  │ TypeScript  │   │ Services    │   │ Performance │   │ Testing │ │
│  │ CLI         │   │ Routing     │   │ SSR         │   │ CI/CD   │ │
│  └─────────────┘   └─────────────┘   └─────────────┘   └─────────┘ │
│       Week 1-2         Week 3-4         Week 5-8        Ongoing    │
└─────────────────────────────────────────────────────────────────────┘
```

### Practice Projects

1. **Todo App** - CRUD operations, local storage
2. **Weather App** - API calls, async data
3. **Blog Platform** - Routing, forms, authentication
4. **E-commerce Store** - State management, cart, checkout
5. **Real-time Chat** - WebSockets, signals

### Official Resources

- 📚 **Angular Documentation**: [angular.dev](https://angular.dev)
- 🎓 **Angular Tutorial**: [angular.dev/tutorials](https://angular.dev/tutorials)
- 📝 **Angular Blog**: [blog.angular.dev](https://blog.angular.dev)
- 💻 **GitHub**: [github.com/angular/angular](https://github.com/angular/angular)

### Community Resources

- **Stack Overflow**: Tag `angular`
- **Discord**: Angular Community
- **Reddit**: r/Angular
- **YouTube**: Angular channel

### Recommended Libraries

| Category | Library | Purpose |
|----------|---------|---------|
| UI | Angular Material | Google's component library |
| UI | PrimeNG | Rich UI components |
| UI | Tailwind CSS | Utility-first CSS |
| State | NgRx | Redux-style state management |
| State | Akita | Simpler state management |
| Forms | Formly | Dynamic forms |
| Testing | Cypress | E2E testing |
| Testing | Spectator | Simplified testing |

### Best Practices Summary

1. ✅ **Use standalone components** (default in Angular 21)
2. ✅ **Prefer signals** for component state
3. ✅ **Use services** for shared logic and data
4. ✅ **Implement lazy loading** for large apps
5. ✅ **Write tests** for critical functionality
6. ✅ **Follow the style guide** at angular.dev
7. ✅ **Keep components small** and focused
8. ✅ **Use TypeScript strictly** (enable strict mode)
9. ✅ **Handle errors gracefully** in HTTP calls
10. ✅ **Optimize for performance** with OnPush and trackBy

---

## Congratulations! 🎉

You've completed the Zero to Hero guide for Angular 21! You now understand:

- ✅ Web fundamentals (HTML, CSS, JavaScript, TypeScript)
- ✅ Angular architecture and components
- ✅ Data binding and templates
- ✅ Directives and control flow
- ✅ Services and dependency injection
- ✅ Routing and navigation
- ✅ Forms (template-driven and reactive)
- ✅ HTTP communication
- ✅ Signals and reactivity
- ✅ Testing strategies
- ✅ Performance optimization
- ✅ Deployment

**Remember**: The best way to learn is by doing. Start building projects, make mistakes, and keep learning!

---

*Created with ❤️ for Angular learners everywhere*
