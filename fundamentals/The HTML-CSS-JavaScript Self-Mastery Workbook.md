# The HTML-CSS-JavaScript Self-Mastery Workbook

---

## Table of Contents

- [💻 Prerequisites](#-prerequisites)
- [How to Use This Workbook](#how-to-use-this-workbook)
- [🌱 Philosophy Behind This Workbook](#-philosophy-behind-this-workbook)
- [HTML](#html)
  - [Section 1: What is HTML? Understanding Web Documents](#section-1-what-is-html-understanding-web-documents)
  - [Section 2: Structuring Content with HTML](#section-2-structuring-content-with-html)
  - [Section 3: Links, Images & Media](#section-3-links-images--media)
  - [Section 4: Forms & User Input](#section-4-forms--user-input)
  - [Section 5: Tables & Structured Data](#section-5-tables--structured-data)
  - [Section 6: Semantic HTML & Accessibility](#section-6-semantic-html--accessibility)
- [CSS](#css)
  - [🟢 Beginner: What is CSS? Styling Basics](#-beginner-what-is-css-styling-basics)
  - [🟡 Intermediate: Layout & Positioning](#-intermediate-layout--positioning)
  - [🔵 Advanced: Responsive Design & Performance](#-advanced-responsive-design--performance)
  - [🔴 Expert: CSS Architecture & Scale](#-expert-css-architecture--scale)
- [JavaScript](#javascript)
  - [Section 1: What is JavaScript? Your First Program](#section-1-what-is-javascript-your-first-program)
  - [Section 2: Variables & Data Types](#section-2-variables--data-types)
  - [Section 3: Making Decisions with Control Flow](#section-3-making-decisions-with-control-flow)
  - [Section 4: Functions - Organizing Your Code](#section-4-functions---organizing-your-code)
  - [Section 5: Objects & Arrays - Storing Data](#section-5-objects--arrays---storing-data)
  - [Section 6: Asynchronous JavaScript - Waiting for Things](#section-6-asynchronous-javascript---waiting-for-things)
  - [Section 7: DOM - Making Pages Interactive](#section-7-dom---making-pages-interactive)
  - [Section 8: Modern JavaScript Features](#section-8-modern-javascript-features)

---

## 💻 Prerequisites

Before starting this workbook, you only need some **basic computer knowledge** and a few essential tools. Don't worry — nothing advanced is required.

### ✅ What You Should Already Know

- How to create, save, and open files/folders on your computer
- How to use a web browser (Chrome, Firefox, or Edge)
- How to copy and paste text
- Basic curiosity and willingness to experiment

### ✅ What You Need Installed

- A code editor like **Visual Studio Code (VSCode)** (free)
- A modern **web browser** (Chrome, Firefox, or Edge)

### ✅ Helpful Skills (You'll Use Them Often Here)

- Open browser **DevTools** (right-click → Inspect)
- Type simple searches into Google (e.g., _"HTML table example"_)
- Read answers on MDN Web Docs or Stack Overflow
- Use ChatGPT (or another AI) to ask for explanations/examples

---

## How to Use This Workbook

This document is **not a textbook**. It will not hand you the answers.

Instead, it gives you the **right questions to ask yourself** — questions every developer must be able to answer to master the topic at a global standard.

### Here's how to use it effectively:

#### 1. Ask Yourself First

- Before looking things up, try to explain the answer in your own words
- If you can't, that's fine — it means you found a gap in your knowledge
- If a new question pops up in your own mind that's not in here, that's your curiosity leading you deeper — write it down and explore it

#### 2. Leverage All Resources

- Use Google, Stack Overflow, and ChatGPT to research
- Read documentation, articles, and examples
- Find a way to practice and produce results
- Experiment! Break things and see what happens

#### 3. Learn by Doing

- Each section has project exercises
- Completing these exercises forces you to practice and discover the answers naturally
- Don't skip them — doing is how you'll turn "theory" into mastery

#### 4. Reflect and Explain

- After finding an answer, try teaching it back:
  - Explain to a friend, or a fellow developer
  - Write notes in your own words
  - Or even record yourself explaining
- If you can explain clearly, you've truly learned it

#### 5. Iterate and Improve

- Revisit questions regularly
- As you grow, your answers will become deeper and more precise

---

## 🌱 Philosophy Behind This Workbook

### This is a **"find the answer within yourself"** document — the web development version.

- The **questions** represent the knowledge every web developer must internalize

- **Be curious** → always ask "why does this work this way?"

- The **resources** (Google, Stack Overflow, ChatGPT) are your tools — but the true goal is that **the understanding lives inside you**, not just in your search history

- The **exercises** are opportunities to struggle, explore, and discover

- **Expect mistakes** → debugging is how you learn

- **Reflect** → explain new concepts in your own words

### Questions Grow With You

This workbook starts with the absolute basics:

- **Foundational questions** - What is this? Why does it exist?
- **How-to questions** - How do I use this?
- **Deep questions** - Why does it behave this way?
- **Scenario questions** - How do I solve this real problem?

By the time you've asked and answered everything here — and built the exercises — you won't just "know HTML, CSS, and JavaScript." **You'll understand them so deeply that you can build, debug, and explain any project with confidence.**

---

# HTML

---

## Section 1: What is HTML? Understanding Web Documents

### Understanding HTML

- What is HTML, and what problem does it solve? (Why can't we just open a Word document in a browser?)
- When you visit a website, what is your browser actually reading and displaying?
- What does "markup language" mean? How is it different from a programming language?
- Why do we need a special language just to structure content?
- What does "HyperText" mean in HTML? What makes it different from plain text?

### Document Structure Basics

- What does `<!DOCTYPE html>` tell the browser? What happens if you forget it?
- Every HTML document has `<html>`, `<head>`, and `<body>` tags. Why are there three parts? What goes in each one?
- You write text directly in a file and open it in a browser. You write the same text in an HTML file with `<html>` tags. What's the difference in how the browser displays them?
- What's the difference between opening a `.txt` file and a `.html` file in a browser?

### Tags and Elements

- What are "tags"? Why do most tags come in pairs (opening and closing)?
- You write `<p>Hello` but forget to close it with `</p>`. Does it still work? What problems might this cause?
- Some tags don't have closing tags (like `<br>` and `<img>`). Why? What makes them different?
- What's the difference between `<div>` and `<span>`? Try putting each on a page — how do they display differently?
- What are "attributes" in HTML tags? How do you add them to a tag?

### Your First HTML Page

- How do you create an HTML file? What extension does it need?
- You create a file called `index.html` and double-click it. What happens?
- How do you view the HTML source code of any website you visit?
- What does "View Page Source" show you? How is it different from the pretty website you see?

### Build It: Your First "Hello World" Webpage

Create your very first HTML document:

**Requirements:**

1. Create a new file called `index.html`
2. Add the basic HTML structure:

   - `<!DOCTYPE html>` declaration
   - `<html>` tags wrapping everything
   - `<head>` section with a `<title>`
   - `<body>` section with content

3. Inside the `<body>`, add:

   - A heading that says "Hello World"
   - A paragraph introducing yourself
   - A `<div>` with some text
   - A `<span>` with some text
   - A line break (`<br>`)

4. Open the file in your browser and view it
5. Right-click and "View Page Source" — see your code!

**Experiment:**

- What happens if you forget the closing `</html>` tag?
- What happens if you put content in the `<head>` instead of `<body>`?
- Try removing the `<!DOCTYPE html>` — does anything change?
- What happens if you nest tags incorrectly: `<p><div></p></div>`?

### Reflection

After building:

- Why do browsers need a special language (HTML) to display content?
- What's the purpose of having `<head>` and `<body>` as separate sections?
- When might you use `<div>` versus `<span>`?
- Why do some tags need closing tags and others don't?

---

## Section 2: Structuring Content with HTML

### The Problem

You have text content — paragraphs, headings, lists, quotes — and you need to structure it so browsers and search engines understand what each piece means. Without structure, everything is just plain text with no hierarchy or meaning.

### Headings and Hierarchy

- What are heading tags (`<h1>` through `<h6>`)? Why are there six levels?
- You have a blog post with a title, section titles, and subsection titles. Which heading tags should you use for each?
- What happens if you use `<h1>` for your main title and then `<h4>` for the next heading? Does it work? What problems might it cause?
- How do screen readers use headings to help blind users navigate a page?
- Can you have multiple `<h1>` tags on one page? Should you?

### Paragraphs and Text Formatting

- What's the difference between `<p>` and `<br>`? When should you use each?
- You want to make some text bold. You could use `<b>` or `<strong>`. What's the difference? When does it matter?
- What's the difference between `<i>` and `<em>`? They both make text italic — so why have both?
- How do you highlight text like a marker would on paper?
- How do you show text that's been deleted or added (like in a document with tracked changes)?

### Lists and Structured Content

- What's the difference between ordered lists (`<ol>`) and unordered lists (`<ul>`)?
- Your list has nested sub-lists (a list inside a list). How do you create this structure?
- When should you use a list versus separate paragraphs?
- What is a description list (`<dl>`)? When would you use it?

### Grouping Content

- What's the difference between `<div>` and `<section>`?
- You have related content that belongs together. When do you use `<div>` versus `<section>` versus `<article>`?
- What does `<header>`, `<footer>`, `<nav>`, and `<main>` do?
- Why use semantic tags instead of just `<div>` everywhere?

### Build It: Blog Post Page

Create a structured blog post webpage:

**Requirements:**

1. **Document Structure**

   - Proper HTML5 structure with DOCTYPE
   - `<head>` with title and meta tags
   - `<body>` with semantic tags

2. **Content Hierarchy**

   - Main heading (`<h1>`) for the article title
   - At least 3 section headings (`<h2>`)
   - At least 2 subsection headings (`<h3>`)
   - Multiple paragraphs under each section

3. **Lists**

   - One ordered list (numbered steps)
   - One unordered list (bullet points)
   - One nested list (list inside a list)

4. **Text Formatting**

   - Bold/strong text
   - Italic/emphasized text
   - Highlighted text
   - Deleted/added text

5. **Semantic Structure**
   - `<header>` for the article header
   - `<nav>` for navigation links
   - `<main>` for main content
   - `<article>` for the blog post
   - `<section>` for each major section
   - `<footer>` for author info

**Experiment:**

- Use only `<div>` tags — does it still work? What's missing?
- Skip heading levels (h1 → h4) — what happens?
- Nest lists 3 levels deep
- Try different text formatting combinations

### Reflection

After building:

- Why is proper heading hierarchy important?
- How do semantic tags make your HTML more meaningful?
- When should you use a list instead of separate paragraphs?
- How does semantic HTML help accessibility?

---

## Section 3: Links, Images & Media

### Understanding Links

- What makes the web "hyper" text? What do links do?
- What is the `<a>` tag? What does it stand for?
- What's the difference between a relative path (`./about.html`) and an absolute path (`https://example.com/about`)?
- You click a link and it opens in a new tab. How does that work? (Hint: `target` attribute)
- What happens if you create a link without an `href` attribute?

### Working with Images

- What's the `<img>` tag? Why doesn't it need a closing tag?
- What are `src` and `alt` attributes? Why is `alt` important?
- You add an image but it doesn't show up. What might be wrong?
- What's the difference between JPG, PNG, and SVG images? When do you use each?
- How do you control image size? With HTML attributes or CSS?

### Media Elements

- What's the difference between `<img>`, `<video>`, and `<audio>`?
- How do you add video to a webpage?
- What does the `controls` attribute do on video/audio elements?
- How do you make a video autoplay? Why might this be a bad idea?
- What's an `<iframe>` and when would you use it?

### Build It: Portfolio Page

Create a personal portfolio page with links, images, and media:

**Requirements:**

1. **Navigation**

   - Navigation menu with links to different sections
   - Links that jump to different parts of the same page (anchors)
   - External link to your GitHub/LinkedIn (opens in new tab)

2. **Images**

   - Profile picture with appropriate `alt` text
   - Gallery of 3-6 project screenshots
   - Use relative paths for local images

3. **Media**

   - Embed a YouTube video (using `<iframe>`)
   - Or add a local video file using `<video>`

4. **Link Variety**
   - Internal links (navigation within the page)
   - External links (to other websites)
   - Email link (`mailto:`)
   - Download link (link to a PDF resume)

**Experiment:**

- Remove `alt` text from images — use a screen reader to see the problem
- Try broken image links — what does the browser show?
- Link to a non-existent page — what happens?
- Try embedding different video platforms (YouTube, Vimeo)

### Reflection

After building:

- Why is `alt` text crucial for accessibility?
- When should you use relative vs absolute paths?
- How do links connect the entire web together?
- What are the trade-offs of autoplay media?

---

## Section 4: Forms & User Input

### Understanding Forms

- What is a form? Why do websites need them?
- What does the `<form>` tag do?
- What's the difference between `method="get"` and `method="post"`?
- Where does the form data go when you submit? (Hint: `action` attribute)
- What happens if you submit a form without an `action` attribute?

### Input Types

- What are the different `<input>` types? (text, email, password, number, etc.)
- You need to collect an email address. Why use `type="email"` instead of `type="text"`?
- What's the difference between `<input>` and `<textarea>`?
- How do radio buttons differ from checkboxes? When do you use each?
- What does `placeholder` text do? Is it the same as `value`?

### Labels and Accessibility

- What is a `<label>` and why is it important?
- How do you connect a label to an input field?
- You click on "Username" and the input field focuses. How does that work?
- Why is the `for` attribute on labels important for accessibility?

### Form Validation

- What does the `required` attribute do?
- How do you make a field required?
- What's the difference between client-side and server-side validation?
- What does `pattern` attribute do for input validation?
- How do you set min/max values for number inputs?

### Buttons and Submission

- What's the difference between `<button>` and `<input type="submit">`?
- What's the difference between `type="submit"`, `type="button"`, and `type="reset"`?
- You press Enter in a form. What happens? Why?

### Build It: Contact Form

Create a fully functional contact form:

**Requirements:**

1. **Form Structure**

   - Form with appropriate action and method
   - Proper semantic HTML structure

2. **Input Fields**

   - Name (text input, required)
   - Email (email input, required)
   - Phone number (tel input, optional)
   - Subject (dropdown select)
   - Message (textarea, required)
   - Newsletter checkbox (optional)

3. **Labels & Accessibility**

   - Every input has a label
   - Labels properly connected with `for` attribute
   - Placeholder text where appropriate

4. **Validation**

   - Required fields marked with `required`
   - Email validation
   - Minimum message length

5. **Buttons**
   - Submit button
   - Reset button

**Experiment:**

- Submit the form without filling required fields — what happens?
- Remove labels — try navigating with Tab key
- Try different input types (date, color, range)
- Add multiple radio buttons with same `name` — what happens?

### Reflection

After building:

- Why is form validation important on both client and server?
- How do labels improve accessibility?
- When should you use GET vs POST methods?
- Why validate email format on the client side?

---

## Section 5: Tables & Structured Data

### Understanding Tables

- What is an HTML table? When should you use one?
- You have data with rows and columns (like a spreadsheet). How do you display it?
- Why shouldn't you use tables for layout? (What should you use instead?)
- What's the difference between `<table>`, `<tr>`, `<td>`, and `<th>`?

### Table Structure

- How do you create table headers versus regular cells?
- What do `<thead>`, `<tbody>`, and `<tfoot>` do? Are they required?
- How do you make a cell span multiple columns? Multiple rows?
- How do you add a caption to a table?

### Table Accessibility

- Why are table headers (`<th>`) important for screen readers?
- What does the `scope` attribute do on `<th>` elements?
- How do screen readers navigate tables?

### Build It: Data Table

Create a structured data table:

**Requirements:**

1. **Basic Table Structure**

   - Table with `<thead>`, `<tbody>`, and `<tfoot>`
   - At least 5 rows and 4 columns
   - Table caption

2. **Headers**

   - Column headers using `<th>`
   - Proper `scope` attributes

3. **Advanced Features**

   - One cell that spans multiple columns
   - One cell that spans multiple rows
   - Footer row with totals/summary

4. **Content Ideas**
   - Product pricing table
   - Schedule/timetable
   - Comparison table
   - Gradebook

**Experiment:**

- Remove `<thead>` and `<tbody>` — does it still work?
- Try complex colspan/rowspan combinations
- Use a screen reader to navigate the table
- Style the table with CSS (borders, colors)

### Reflection

After building:

- When should you use a table versus other HTML elements?
- How do proper table headers help accessibility?
- What makes a table easy to read and understand?

---

## Section 6: Semantic HTML & Accessibility

### Understanding Semantics

- What does "semantic" mean in HTML?
- Why use `<article>` instead of `<div>`? They look the same!
- How do semantic tags help search engines understand your content?
- What's the difference between `<section>`, `<article>`, and `<div>`?

### Semantic Structure Elements

- What is `<header>` used for? Can you have multiple headers on one page?
- What goes in `<nav>`? Should every link be in a nav?
- What's the difference between `<aside>` and `<section>`?
- What does `<main>` represent? Should you have multiple main elements?
- When should you use `<figure>` and `<figcaption>`?

### Accessibility Basics

- What is web accessibility? Why does it matter?
- What are screen readers and how do they interact with HTML?
- What does ARIA stand for? When do you need it?
- What's the difference between semantic HTML and ARIA attributes?

### Accessible Practices

- Why is proper heading hierarchy important for accessibility?
- How do `alt` attributes help blind users?
- What makes a link accessible? (Hint: descriptive link text)
- Why should you avoid "click here" as link text?
- What's the difference between hiding content visually vs hiding from screen readers?

### Form Accessibility

- Why must every input have a label?
- What do screen readers announce for form inputs?
- How do you provide helpful error messages?
- What makes a form easy to navigate with a keyboard?

### Build It: Accessible Blog Layout

Create a fully semantic and accessible blog page:

**Requirements:**

1. **Semantic Structure**

   - `<header>` with site title and navigation
   - `<nav>` with proper link structure
   - `<main>` containing the primary content
   - `<article>` for blog posts
   - `<aside>` for related links/info
   - `<footer>` with copyright and links

2. **Proper Heading Hierarchy**

   - Only one `<h1>` (page title)
   - Logical h2, h3, h4 structure
   - No skipped heading levels

3. **Accessible Media**

   - All images have descriptive `alt` text
   - Decorative images use `alt=""`
   - Figures use `<figure>` and `<figcaption>`

4. **Accessible Links**

   - Descriptive link text (not "click here")
   - External links indicate they open in new tab

5. **Keyboard Navigation**
   - Can navigate entire page with Tab key
   - Focus states are visible
   - Logical tab order

**Experiment:**

- Navigate your page using only the keyboard (Tab, Enter)
- Use a screen reader to experience your page
- Remove all semantic tags — replace with divs — what's lost?
- Add ARIA labels where needed

### Reflection

After building:

- How does semantic HTML improve accessibility?
- Why is heading hierarchy so important?
- What makes a website easy to navigate for keyboard users?
- How do screen readers experience your websites?

---

# CSS

---

## 🟢 Beginner: What is CSS? Styling Basics

### Understanding CSS

- What is CSS and what problem does it solve?
- You have HTML with no CSS. What does it look like?
- Why is styling separate from content?
- What does "Cascading Style Sheets" mean? What's "cascading"?

### Adding CSS to HTML

- What are the three ways to add CSS to HTML?
- What's the difference between inline styles, internal stylesheets, and external stylesheets?
- Which method is best? Why?
- How do you link an external CSS file to HTML?

### CSS Syntax

- What's the basic structure of a CSS rule?
- What are selectors, properties, and values?
- You write `color: blue;` — what's the property? What's the value?
- How do you add comments in CSS?

### Basic Selectors

- How do you select an element by tag name?
- How do you select by class? (Hint: `.classname`)
- How do you select by ID? (Hint: `#idname`)
- What's the difference between class and ID selectors?
- Can multiple elements have the same class? The same ID?

### Text Styling

- How do you change text color?
- How do you change font size?
- How do you change font family?
- What's the difference between `font-weight: bold` and `font-weight: 700`?
- How do you align text (left, center, right)?

### Colors

- What are the different ways to specify colors in CSS?
- What's the difference between named colors, hex codes, RGB, and RGBA?
- How do you make a color semi-transparent?
- What does the "A" in RGBA stand for?

### Box Model Basics

- What is the CSS box model?
- What's the difference between `margin` and `padding`?
- You want space inside a box — margin or padding?
- You want space outside a box — margin or padding?
- How do you add a border?

### Build It: Styled Blog Post

Take your HTML blog post from earlier and style it with CSS:

**Requirements:**

1. **External Stylesheet**

   - Create a separate CSS file
   - Link it to your HTML

2. **Typography**

   - Choose and apply a font family
   - Style headings differently from paragraphs
   - Set appropriate font sizes
   - Adjust line height for readability

3. **Colors**

   - Define a color scheme (3-4 colors)
   - Style headings with color
   - Add a background color
   - Style links with color

4. **Box Model**

   - Add padding to content sections
   - Add margins between sections
   - Add borders where appropriate

5. **Classes**
   - Create reusable classes (`.highlight`, `.warning`, etc.)
   - Apply multiple classes to elements

**Experiment:**

- Change all margins to padding — what changes?
- Remove all CSS — see the unstyled HTML
- Use only inline styles — how does it compare?
- Try different color formats (hex, rgb, named)

### Reflection

After building:

- Why is external CSS better than inline styles?
- How does the box model affect layout?
- What makes text readable and pleasant to read?
- Why use classes instead of styling every element individually?

---

## 🟡 Intermediate: Layout & Positioning

### Understanding Layout

- What's the default layout of HTML elements?
- What's the difference between block and inline elements?
- How do `<div>` (block) and `<span>` (inline) behave differently?
- What does `display: block`, `display: inline`, and `display: inline-block` do?

### Positioning

- What are the different position values? (static, relative, absolute, fixed, sticky)
- What's the difference between `position: relative` and `position: absolute`?
- How do `top`, `right`, `bottom`, `left` work with positioning?
- You want an element to stay at the top of the page when scrolling. How?
- What's the difference between `fixed` and `sticky` positioning?

### Flexbox

- What problem does Flexbox solve?
- How do you create a flex container?
- What's the difference between `flex-direction: row` and `flex-direction: column`?
- How do you center items with Flexbox?
- What do `justify-content` and `align-items` do?
- What's the difference between `flex-wrap: wrap` and `flex-wrap: nowrap`?

### Grid

- What problem does CSS Grid solve?
- How is Grid different from Flexbox?
- How do you create a grid container?
- What do `grid-template-columns` and `grid-template-rows` do?
- How do you create a responsive grid?
- What's the difference between `fr` units and pixels?

### Float (Legacy)

- What does `float` do? Is it still used?
- What problems did float have that Flexbox/Grid solve?
- What does `clear` do with floats?
- When might you still use float?

### Build It: Responsive Layout

Create a responsive page layout using modern CSS:

**Requirements:**

1. **Header Layout (Flexbox)**

   - Logo on the left
   - Navigation menu on the right
   - Centered vertically

2. **Main Content (Grid)**

   - Sidebar on the left (300px)
   - Main content area (flexible)
   - Right sidebar (250px)

3. **Card Layout (Flexbox or Grid)**

   - Gallery of cards
   - Cards wrap to new rows
   - Equal height cards

4. **Footer (Flexbox)**

   - Three columns of links
   - Evenly spaced

5. **Positioning Practice**
   - Fixed header that stays at top
   - Sticky sidebar that stays visible when scrolling
   - "Back to top" button in bottom-right corner

**Experiment:**

- Change flex-direction — see the layout change
- Adjust grid columns (2, 3, 4 columns)
- Try different justify-content values
- Remove positioning — see the difference

### Reflection

After building:

- When should you use Flexbox vs Grid?
- How does Flexbox make layouts easier than old methods?
- What makes a layout responsive?
- How does positioning create layered layouts?

---

## 🔵 Advanced: Responsive Design & Performance

### Understanding Responsive Design

- What is responsive design? Why is it important?
- What's the difference between responsive and adaptive design?
- What's mobile-first design?
- Why design for mobile first instead of desktop first?

### Media Queries

- What are media queries?
- How do you write a media query for mobile devices?
- What's the difference between `min-width` and `max-width`?
- How do you target different screen sizes?
- What's the viewport meta tag? Why is it crucial for mobile?

### Responsive Units

- What's the difference between `px`, `em`, `rem`, `%`, `vw`, `vh`?
- When should you use `rem` instead of `px`?
- How do viewport units (`vw`, `vh`) work?
- What's the difference between `em` and `rem`?

### Responsive Images

- How do you make images responsive?
- What does `max-width: 100%` do to images?
- What's the difference between `<img>` `srcset` and CSS media queries?
- How do you serve different images for different screen sizes?

### CSS Variables

- What are CSS custom properties (variables)?
- How do you define a CSS variable?
- How do you use a CSS variable?
- Why use CSS variables instead of hardcoded values?
- How do CSS variables help with theming?

### Animations & Transitions

- What's the difference between transitions and animations?
- How do you create a smooth hover effect?
- What's a CSS keyframe animation?
- How do you control animation timing?
- What properties can you animate? Which should you avoid for performance?

### Build It: Fully Responsive Site

Create a multi-page website that works on all devices:

**Requirements:**

1. **Mobile-First Approach**

   - Design for mobile (320px) first
   - Add breakpoints for tablet (768px) and desktop (1024px)

2. **Responsive Navigation**

   - Hamburger menu on mobile
   - Horizontal menu on desktop
   - Smooth transitions

3. **Responsive Grid**

   - 1 column on mobile
   - 2 columns on tablet
   - 3-4 columns on desktop

4. **Responsive Typography**

   - Font sizes scale with screen size
   - Comfortable reading width (max-width on paragraphs)

5. **Responsive Images**

   - Images scale properly
   - Different images for mobile/desktop (optional)

6. **CSS Variables Theme**

   - Define color scheme with CSS variables
   - Easy to change entire theme

7. **Animations**
   - Smooth transitions on hover
   - Fade-in animation on page load
   - Animated hamburger menu

**Experiment:**

- View on different device sizes in DevTools
- Change breakpoints — see when layout breaks
- Modify CSS variables — see theme change instantly
- Test animations on different browsers

### Reflection

After building:

- Why is mobile-first approach beneficial?
- How do media queries enable responsive design?
- What makes typography readable on different devices?
- How can CSS variables improve maintainability?

---

## 🔴 Expert: CSS Architecture & Scale

### Understanding CSS at Scale

- What problems arise when CSS grows large?
- What is CSS specificity? How does it cause problems?
- What's the difference between specificity and the cascade?
- How do you organize CSS for large projects?

### Naming Conventions

- What is BEM (Block Element Modifier)?
- Why use naming conventions?
- How does BEM help avoid specificity issues?
- What are other CSS naming methodologies?

### CSS Preprocessors

- What are CSS preprocessors (Sass, Less)?
- What features do preprocessors add to CSS?
- What are variables, nesting, mixins, and functions?
- Do you need preprocessors with modern CSS?

### Performance

- How does CSS affect page load performance?
- What's the "critical CSS" concept?
- How do unused CSS styles affect performance?
- What's render blocking CSS?
- How do you optimize CSS delivery?

### Modern CSS Features

- What are CSS Container Queries?
- How do they differ from media queries?
- What's the `:has()` selector?
- What's CSS Cascade Layers?

### Build It: Design System

Create a scalable design system with CSS:

**Requirements:**

1. **CSS Architecture**

   - Organized file structure
   - Logical separation of concerns
   - Reusable components

2. **Design Tokens (CSS Variables)**

   - Color palette
   - Typography scale
   - Spacing scale
   - Shadow styles

3. **Component Library**

   - Buttons (primary, secondary, ghost)
   - Cards
   - Forms
   - Navigation
   - Modals/Dialogs

4. **Utility Classes**

   - Spacing utilities
   - Typography utilities
   - Color utilities
   - Layout utilities

5. **Documentation**
   - Style guide page
   - Component examples
   - Usage guidelines

**Experiment:**

- Change design tokens — see system update
- Use BEM naming consistently
- Measure CSS file size
- Test reusability of components

### Reflection

After building:

- How does organization improve maintainability?
- Why are design systems important?
- How do naming conventions prevent specificity wars?
- What makes CSS scalable for large teams?

---

# JavaScript

---

## Section 1: What is JavaScript? Your First Program

### Understanding JavaScript

- What is JavaScript? What problems does it solve?
- What's the difference between HTML, CSS, and JavaScript?
- HTML structures content, CSS styles it — what does JavaScript do?
- Why is it called "Java"Script? Is it related to Java?
- Where does JavaScript run? (Browser? Server? Both?)

### Your First Program

- How do you add JavaScript to an HTML page?
- What are the three ways to include JavaScript?
- What's the difference between inline, internal, and external JavaScript?
- Where should you put the `<script>` tag? Why does it matter?
- What does `console.log()` do?

### The Console

- What is the browser console?
- How do you open the developer console?
- What kinds of messages appear in the console?
- Why is `console.log()` useful for debugging?
- What's the difference between `console.log()`, `console.error()`, and `console.warn()`?

### Basic Syntax

- What's the difference between `let`, `const`, and `var`?
- Why do statements end with semicolons?
- Are semicolons required? What happens without them?
- What are comments? How do you write them?
- What's the difference between `//` and `/* */` comments?

### Build It: Interactive Hello World

Create your first JavaScript program:

**Requirements:**

1. **Setup**

   - Create HTML file with a `<script>` tag
   - Or link external JavaScript file

2. **Console Output**

   - Log "Hello World" to console
   - Log your name
   - Log the current date/time
   - Log multiple things in one line

3. **Variables**

   - Create variables with `let` and `const`
   - Store your name, age, and favorite color
   - Log the variables

4. **Basic Interaction**

   - Use `alert()` to show a message
   - Use `prompt()` to ask for user's name
   - Log the user's response

5. **Comments**
   - Add comments explaining what your code does
   - Use both single-line and multi-line comments

**Experiment:**

- What happens if you use a variable before declaring it?
- Try changing a `const` variable — what error?
- Remove all semicolons — does it still work?
- Put `<script>` in different places — how does it affect execution?

### Reflection

After building:

- How does JavaScript make websites interactive?
- Why have both `let` and `const`?
- When is the console useful?
- What's the best way to include JavaScript in a page?

---

## Section 2: Variables & Data Types

### Understanding Variables

- What is a variable? Why do we need them?
- You want to store a user's name. How do you do it?
- What's the difference between declaring and assigning a variable?
- Can you declare a variable without assigning it a value?
- What happens when you try to use an undeclared variable?

### Naming Variables

- What are the rules for naming variables?
- Can a variable name start with a number?
- Should variable names be camelCase, snake_case, or PascalCase?
- What makes a good variable name?
- Can you use JavaScript keywords as variable names?

### Data Types

- What are the different data types in JavaScript?
- What's the difference between primitive and reference types?
- What are the primitive types? (string, number, boolean, null, undefined, symbol, bigint)
- How do you check the type of a variable? (Hint: `typeof`)

### Strings

- What is a string?
- What's the difference between `"double quotes"`, `'single quotes'`, and `` `backticks` ``?
- How do you include a quote inside a string?
- How do you combine strings? (concatenation)
- What's string interpolation with template literals?

### Numbers

- How does JavaScript handle numbers?
- What's the difference between integers and floats in JavaScript? (Trick question!)
- How do you do basic math operations?
- What happens when you divide by zero?
- What is `NaN`? How do you check for it?

### Booleans

- What is a boolean?
- What are the only two boolean values?
- What's the difference between `true` and `"true"`?
- How do you check if something is true or false?

### Null and Undefined

- What's the difference between `null` and `undefined`?
- When does a variable have value `undefined`?
- When would you use `null`?
- Are `null` and `undefined` equal? (Hint: `==` vs `===`)

### Type Conversion

- What's the difference between `"5"` and `5`?
- What happens when you do `"5" + 5`?
- What happens when you do `"5" - 5`?
- How do you convert a string to a number?
- How do you convert a number to a string?
- What is type coercion?

### Build It: Personal Information Program

Create a program that works with different data types:

**Requirements:**

1. **String Variables**

   - Store name, favorite food, favorite quote
   - Use string concatenation
   - Use template literals
   - Log formatted output

2. **Number Variables**

   - Store age, height (in cm), weight (in kg)
   - Calculate BMI (weight / height² )
   - Calculate age in months
   - Log the results

3. **Boolean Variables**

   - Store isStudent, hasJob, canDrive
   - Log the boolean values
   - Use booleans in simple conditions

4. **Type Conversion**

   - Convert strings to numbers
   - Convert numbers to strings
   - Show the difference between `==` and `===`
   - Demonstrate type coercion

5. **User Input**
   - Use `prompt()` to get user input
   - Convert string input to numbers
   - Calculate something with the input

**Experiment:**

- What's `"5" + 5`? What's `"5" - 5`? Why different?
- What's `true + true`? What's `true + false`?
- Try `typeof null` — what does it return? Why is this weird?
- What happens when you do math with `undefined`?

### Reflection

After building:

- Why does JavaScript have different data types?
- What problems can type coercion cause?
- When should you use `===` instead of `==`?
- How do you choose between `let` and `const`?

---

## Section 3: Making Decisions with Control Flow

### Understanding Conditions

- What is control flow?
- How do you make your program do different things based on conditions?
- What is a condition? What makes it true or false?

### If Statements

- What does an `if` statement do?
- How do you write an if statement?
- What goes inside the parentheses `()`? What goes inside the curly braces `{}`?
- Can you have an `if` without an `else`?
- What's the difference between `else if` and a separate `if`?

### Comparison Operators

- What are the comparison operators? (`>`, `<`, `>=`, `<=`, `==`, `===`, `!=`, `!==`)
- What's the difference between `==` and `===`?
- Why is `===` considered safer?
- How do you check if something is NOT equal?
- Can you compare strings? How does JavaScript compare them?

### Logical Operators

- What are the logical operators? (`&&`, `||`, `!`)
- What does `&&` (AND) do? When is it true?
- What does `||` (OR) do? When is it true?
- What does `!` (NOT) do?
- How do you combine multiple conditions?
- What's the difference between `||` and `&&` in terms of evaluation?

### Truthy and Falsy

- What values are "falsy" in JavaScript?
- What makes a value "truthy"?
- Why does `if ("hello")` execute but `if ("")` doesn't?
- Is `0` truthy or falsy? What about `"0"`?
- How do you convert a value to boolean?

### Switch Statements

- What is a switch statement?
- When should you use `switch` instead of multiple `if/else`?
- What does `break` do in a switch?
- What happens if you forget `break`?
- When would you want fall-through behavior?

### Ternary Operator

- What is the ternary operator?
- How is `condition ? true : false` different from `if/else`?
- When should you use ternary instead of if/else?
- Can you nest ternary operators? Should you?

### Build It: Interactive Quiz or Decision Tree

Create a program that makes decisions based on user input:

**Requirements:**

1. **Basic If/Else**

   - Ask user their age
   - Respond differently based on age ranges
   - Use `if`, `else if`, and `else`

2. **Comparison Practice**

   - Compare numbers
   - Compare strings
   - Use both `==` and `===`
   - Show the difference

3. **Logical Operators**

   - Check multiple conditions with `&&`
   - Check alternative conditions with `||`
   - Use `!` to negate conditions

4. **Switch Statement**

   - Ask for day of the week
   - Give different message for each day
   - Use proper break statements

5. **Ternary Operator**

   - Use ternary for simple true/false decisions
   - Example: `const message = age >= 18 ? "Adult" : "Minor"`

6. **Real Application**
   - Create a simple quiz or decision tree
   - Multiple questions
   - Give final result based on answers
   - Example: "What programming language should you learn?"

**Experiment:**

- Remove `break` from switch — see fall-through
- Compare `5 == "5"` vs `5 === "5"`
- Try `if (0)` vs `if ("0")` vs `if (false)`
- Chain multiple logical operators
- Use ternary inside template literal: `` `Welcome back ${isLoggedIn ? user : "Guest"}` ``

**Example Quiz Structure:**

```javascript
// Ask 3-5 questions
// Store answers
// Use if/else to determine result
// Example: "You should learn JavaScript!"
```

**Example Decision Tree:**

```javascript
// "Where should I eat?"
// Ask: Do you want fast food? (yes/no)
// Ask: What's your budget? (cheap/medium/expensive)
// Ask: What cuisine? (italian/chinese/mexican)
// Give recommendation based on answers
```

### Reflection

After building:

- How do if statements make programs interactive?
- When should you use switch versus if/else?
- Why is `===` safer than `==`?
- What makes code readable when you have many conditions?

---

## Section 4: Functions - Organizing Your Code

### Understanding Functions

- What is a function? Why do we need them?
- Your code calculates tax three times. How do functions help?
- What does "DRY" mean? (Don't Repeat Yourself)
- What makes functions reusable?

### Creating Functions

- How do you create a function?
- What's the difference between function declaration and function expression?
- What does `function greet() {}` do?
- How do you run (call/invoke) a function?
- What happens if you write the function name without `()`?

### Parameters and Arguments

- What are parameters? What are arguments?
- You write `function greet(name)` - what is `name`?
- You call `greet("Alice")` - what is `"Alice"`?
- Can functions have multiple parameters?
- What happens if you call a function with too few arguments? Too many?

### Return Values

- What does `return` do?
- Your function calculates something. How do you get the result out?
- What's the difference between `console.log()` inside a function and `return`?
- What happens after a `return` statement?
- Can you use a function's return value in another function?

### Arrow Functions

- What are arrow functions?
- How is `const add = (a, b) => a + b` different from `function add(a, b) { return a + b }`?
- When can you omit the curly braces in arrow functions?
- When can you omit the `return` keyword?
- Why do people like arrow functions?

### Scope

- What is scope?
- What's the difference between global and local variables?
- You create a variable inside a function. Can you access it outside?
- You create a variable outside and use it inside a function. Does it work?
- What happens if inner and outer variables have the same name?

### Understanding Closures

- What happens when a function "remembers" variables from its outer scope?
- Why can inner functions access outer function variables?

**Scenario: The Counter Mystery**

```javascript
function createCounter() {
  let count = 0;
  return function () {
    count++;
    return count;
  };
}

const counter1 = createCounter();
console.log(counter1()); // 1
console.log(counter1()); // 2
const counter2 = createCounter();
console.log(counter2()); // 1
```

**Explore:**

- Why does `count` keep increasing?
- How does the inner function remember `count`?
- Why is `count` not accessible from outside?
- Why do `counter1` and `counter2` have separate counts?
- What is a closure?

**Scenario: The Loop Problem**

```javascript
// Problem: This doesn't work as expected
for (var i = 0; i < 3; i++) {
  setTimeout(function () {
    console.log(i);
  }, 100);
}
// Logs: 3, 3, 3 (not 0, 1, 2)

// Why? How do you fix it?
```

**Explore:**

- Why does it log 3 three times?
- What's the value of `i` when the timeouts execute?
- How would using `let` instead of `var` fix this?
- How could you fix it using closures?
- What's the difference in how `var` and `let` are scoped?

### Build It: Function Toolkit & Closure Exercises

Create a collection of reusable functions and explore closures:

**Requirements:**

**Part 1: Basic Functions**

1. **Basic Math Functions**

   - Create functions for add, subtract, multiply, divide
   - Each takes two numbers and returns result
   - Call each function and log results

2. **Functions with Parameters**

   - `greet(name)` - takes name, returns greeting
   - `calculateAge(birthYear)` - returns current age
   - `isEven(number)` - returns true if even
   - `max(a, b)` - returns the larger number

3. **Functions that Return Values**

   - `calculateTax(amount, rate)` - returns tax amount
   - `calculateTotal(price, quantity)` - returns total
   - `getGrade(score)` - returns letter grade
   - Use return values in other calculations

4. **Arrow Functions**

   - Convert some regular functions to arrow functions
   - Create one-liner arrow functions
   - Compare syntax with regular functions

5. **Function Composition**

   - Use one function's return value as another's input
   - Create `calculateTotalWithTax(price, quantity, taxRate)`
   - Call multiple functions in sequence

6. **Interactive Calculator**
   - Ask user to choose operation (+, -, \*, /)
   - Ask for two numbers
   - Call appropriate function
   - Show result

**Part 2: Closure Exercises**

1. **Create a Counter**

   ```javascript
   function createCounter() {
     // Your code here
     // Return functions: increment(), decrement(), getCount()
   }

   const counter = createCounter();
   counter.increment(); // count is now 1
   counter.increment(); // count is now 2
   console.log(counter.getCount()); // 2
   counter.decrement(); // count is now 1
   ```

2. **Create a Secret Keeper**

   ```javascript
   function createSecret(secret) {
     // Your code here
     // Return functions: getSecret(password), changeSecret(newSecret, password)
   }

   const mySecret = createSecret("my password is 1234");
   mySecret.getSecret("wrong"); // "Access denied"
   mySecret.getSecret("password"); // "my password is 1234"
   ```

3. **Create a Bank Account**

   ```javascript
   function createBankAccount(initialBalance) {
     // Your code here
     // Return functions: deposit(amount), withdraw(amount), getBalance()
     // Balance should be private (not accessible from outside)
   }

   const account = createBankAccount(100);
   account.deposit(50); // balance is now 150
   account.withdraw(30); // balance is now 120
   console.log(account.getBalance()); // 120
   // account.balance should be undefined (private)
   ```

4. **Create a Personal Greeter**

   ```javascript
   function createGreeter(name) {
     // Your code here
     // Return a function that remembers the name
   }

   const greetJohn = createGreeter("John");
   greetJohn("morning"); // "Good morning, John!"
   greetJohn("evening"); // "Good evening, John!"
   ```

**Experiment:**

- Call a function before declaring it - what happens?
- Return multiple times in one function
- Access a local variable from outside the function
- Create a function without return - what does it return?
- Arrow function with multiple statements - need curly braces?
- Try to access `count` from outside `createCounter` - what happens?
- Create multiple counters - do they share the same count?
- Change `var` to `let` in the loop problem - does it fix it?

### Reflection

After building:

- How do functions make code easier to maintain?
- Why is it important to return values rather than just console.log?
- When should you use arrow functions versus regular functions?
- How does scope protect variables?
- What is a closure and why is it useful?
- How do closures enable private variables?
- When does a closure get created?

---

## Section 5: Objects & Arrays - Storing Data

### Understanding Objects

- What is an object? Why do we need them?
- You have a user with name, email, age. How do you store related data together?
- What are properties? What are keys and values?
- How is an object like a real-world object?

### Creating and Using Objects

- How do you create an object?
- What's the difference between `{}` and `[]`?
- You write `let user = { name: "Alice", age: 25 }` - what does this create?
- How do you access properties? (Dot notation: `user.name`)
- How do you access properties with brackets? (Bracket notation: `user["name"]`)
- When must you use bracket notation instead of dot notation?

### Modifying Objects

- How do you add a new property to an existing object?
- How do you change a property's value?
- How do you delete a property?
- Can you add properties after creating the object?

### Understanding Arrays

- What is an array? Why do we need them?
- You have 100 students. Should you create 100 variables?
- How is an array different from an object?
- What is an index? Why do arrays start at 0?

### Creating and Using Arrays

- How do you create an array?
- You write `let colors = ["red", "green", "blue"]` - what does this create?
- How do you access the first item? The second item?
- What happens if you try to access index 99 in an array of 3 items?
- How do you find how many items are in an array?

### Modifying Arrays

- How do you add an item to the end of an array?
- How do you add an item to the beginning?
- How do you remove the last item?
- How do you remove the first item?
- Can you change an item at a specific index?

### Arrays of Objects

- Can you put objects inside an array?
- You have an array of user objects. How do you access the first user's name?
- Why is this pattern so common?

### Looping Through Arrays

**Basic Loops:**

- How do you loop through every item in an array?
- What does a `for` loop look like for arrays?
- What's the difference between `for` and `while` loops?

**Understanding Array Methods:**

Now we'll learn modern, cleaner ways to work with arrays.

#### forEach - Visiting Each Item

- What does `forEach` do?
- How is it different from a `for` loop?
- When should you use `forEach`?

**Explore:**

```javascript
const numbers = [1, 2, 3, 4, 5];

// Old way with for loop
for (let i = 0; i < numbers.length; i++) {
  console.log(numbers[i]);
}

// Modern way with forEach
numbers.forEach(function (number) {
  console.log(number);
});

// Even cleaner with arrow function
numbers.forEach((number) => console.log(number));
```

- What does the callback function receive?
- Can you access the index in forEach?
- Does forEach return anything?

#### map - Transforming Every Item

- What does `map` do?
- You have an array of numbers and want to double each one. How?
- What does map return?

**Scenario: Converting Data**

```javascript
const prices = [10, 20, 30, 40];

// You want to add tax (10%) to each price
// Old way with for loop
const withTax = [];
for (let i = 0; i < prices.length; i++) {
  withTax.push(prices[i] * 1.1);
}

// Modern way with map
const withTax = prices.map((price) => price * 1.1);
```

**Explore:**

- What does the callback function receive?
- What does the callback function return?
- What does `map` itself return?
- Does `map` modify the original array?
- Why is `map` cleaner than a for loop?

**More Examples:**

```javascript
const names = ["alice", "bob", "charlie"];
// How do you uppercase all names?

const numbers = [1, 2, 3, 4, 5];
// How do you create an array of squares?

const users = [
  {name: "Alice", age: 25},
  {name: "Bob", age: 30},
];
// How do you get just the names?
```

#### filter - Keeping Only Some Items

- What does `filter` do?
- You have an array of numbers and want only the even ones. How?
- What does filter return?

**Scenario: Finding Matches**

```javascript
const ages = [12, 18, 25, 16, 30, 14];

// You want only adults (18+)
// Old way with for loop
const adults = [];
for (let i = 0; i < ages.length; i++) {
  if (ages[i] >= 18) {
    adults.push(ages[i]);
  }
}

// Modern way with filter
const adults = ages.filter((age) => age >= 18);
```

**Explore:**

- What does the callback function return?
- What happens if no items match?
- Does `filter` modify the original array?
- Can you filter objects based on their properties?

**More Examples:**

```javascript
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
// How do you get only odd numbers?

const words = ["hello", "hi", "goodbye", "hey"];
// How do you get words longer than 3 characters?

const users = [
  {name: "Alice", active: true},
  {name: "Bob", active: false},
  {name: "Charlie", active: true},
];
// How do you get only active users?
```

#### find - Finding One Item

- What does `find` do?
- How is it different from `filter`?
- What happens if multiple items match?
- What happens if no items match?

**Scenario: Looking Up Data**

```javascript
const users = [
  {id: 1, name: "Alice"},
  {id: 2, name: "Bob"},
  {id: 3, name: "Charlie"},
];

// Find user with id 2
const user = users.find((u) => u.id === 2);
console.log(user); // { id: 2, name: "Bob" }

// Find user that doesn't exist
const missing = users.find((u) => u.id === 999);
console.log(missing); // undefined
```

**Explore:**

- When should you use `find` vs `filter`?
- How do you check if find found something?
- What's `findIndex` and how is it different?

#### reduce - Accumulating a Result

- What does `reduce` do?
- Why is it called "reduce"?
- What's an accumulator?

**Scenario: Calculating Totals**

```javascript
const prices = [10, 20, 30, 40];

// Calculate total
// Old way with for loop
let total = 0;
for (let i = 0; i < prices.length; i++) {
  total += prices[i];
}

// Modern way with reduce
const total = prices.reduce((sum, price) => sum + price, 0);
```

**Explore:**

- What are the two parameters to the callback? (accumulator, current value)
- What's the second argument to reduce? (initial value)
- What does reduce return?
- What happens if you don't provide an initial value?

**More Examples:**

```javascript
const numbers = [1, 2, 3, 4, 5];
// How do you multiply all numbers together?

const words = ["Hello", " ", "World"];
// How do you combine them into one string?

const items = [
  {name: "Apple", price: 1},
  {name: "Banana", price: 2},
];
// How do you calculate total price?
```

#### some & every - Testing Conditions

- What does `some` do? What does `every` do?
- How are they different?

**Scenario: Checking Conditions**

```javascript
const ages = [12, 16, 18, 25, 30];

// Are there any adults?
const hasAdults = ages.some((age) => age >= 18); // true

// Are all of them adults?
const allAdults = ages.every((age) => age >= 18); // false
```

**Explore:**

- What does the callback return?
- What do `some` and `every` themselves return?
- When does `some` stop checking?
- When does `every` stop checking?

#### Chaining Array Methods

**Scenario: Complex Data Processing**

```javascript
const users = [
  {name: "Alice", age: 25, active: true},
  {name: "Bob", age: 17, active: false},
  {name: "Charlie", age: 30, active: true},
  {name: "Diana", age: 22, active: true},
];

// Get names of active adults, in uppercase
const result = users
  .filter((user) => user.active) // Only active users
  .filter((user) => user.age >= 18) // Only adults
  .map((user) => user.name.toUpperCase()); // Get names in uppercase

console.log(result); // ["ALICE", "CHARLIE", "DIANA"]
```

**Explore:**

- How does chaining work?
- What does each method return?
- Can you chain in any order?
- Which order is most efficient?

### Build It: Data Processing Application

Create a program that works with arrays and objects:

**Requirements:**

**Part 1: Basic Arrays and Objects**

1. **Single Student Object**

   - Create a student object with: name, age, grade, subjects array
   - Access and log each property
   - Add a new property (email)
   - Change the grade
   - Delete a property

2. **Student Array**

   - Create an array of 5 student objects
   - Access individual students by index
   - Access specific properties of specific students
   - Show the first student's name
   - Show the last student's grade

3. **Array Operations**

   - Add a new student to the array
   - Remove a student from the array
   - Count how many students there are
   - Find a student by name (using find method)

**Part 2: Array Methods Practice**

1. **forEach Practice**

   - Loop through all students and log their names
   - Loop through and log "Name: Age"
   - Loop through and do something with each student

2. **map Practice**

   ```javascript
   // Create array of just student names
   const names = students.map((student) => student.name);

   // Create array with formatted strings
   const formatted = students.map(
     (student) => `${student.name} (${student.age})`
   );

   // Give everyone a 5-point grade boost
   const boosted = students.map((student) => ({
     ...student,
     grade: student.grade + 5,
   }));
   ```

3. **filter Practice**

   ```javascript
   // Get only students with grade >= 80
   const topStudents = students.filter((student) => student.grade >= 80);

   // Get only students older than 18
   const adults = students.filter((student) => student.age > 18);

   // Get students whose name starts with 'A'
   const aNames = students.filter((student) => student.name.startsWith("A"));
   ```

4. **find Practice**

   ```javascript
   // Find student with specific name
   const alice = students.find((student) => student.name === "Alice");

   // Find first student with grade > 90
   const topStudent = students.find((student) => student.grade > 90);

   // Find student by ID (if you add id property)
   const student = students.find((s) => s.id === 3);
   ```

5. **reduce Practice**

   ```javascript
   // Calculate average grade
   const total = students.reduce((sum, student) => sum + student.grade, 0);
   const average = total / students.length;

   // Find highest grade
   const highest = students.reduce(
     (max, student) => (student.grade > max ? student.grade : max),
     0
   );

   // Count students by age group
   const ageGroups = students.reduce((groups, student) => {
     const group = student.age < 18 ? "minor" : "adult";
     groups[group] = (groups[group] || 0) + 1;
     return groups;
   }, {});
   ```

6. **some & every Practice**

   ```javascript
   // Are any students failing (grade < 60)?
   const hasFailing = students.some((student) => student.grade < 60);

   // Are all students passing (grade >= 60)?
   const allPassing = students.every((student) => student.grade >= 60);

   // Are all students adults?
   const allAdults = students.every((student) => student.age >= 18);
   ```

7. **Chaining Practice**

   ```javascript
   // Get names of passing students (grade >= 60), sorted
   const passingNames = students
     .filter((student) => student.grade >= 60)
     .map((student) => student.name)
     .sort();

   // Get average grade of adult students
   const adultAverage =
     students
       .filter((student) => student.age >= 18)
       .reduce((sum, student) => sum + student.grade, 0) /
     students.filter((student) => student.age >= 18).length;
   ```

**Part 3: Real Application**

Build a **Student Management System** that can:

1. Display all students
2. Filter students by:
   - Grade range (A, B, C, etc.)
   - Age group (minors, adults)
   - Passing/failing status
3. Calculate statistics:
   - Average grade
   - Highest/lowest grade
   - Number of passing students
4. Transform data:
   - Get list of all names
   - Format student data for display
   - Sort students by name or grade

**Experiment:**

- Try accessing `students[100]` - what happens?
- Try accessing `student.nonexistent` - what happens?
- What happens if you `map` over an empty array?
- What happens if `filter` finds no matches?
- What happens if `find` finds nothing?
- Try `reduce` without an initial value - what happens?
- Chain many methods together - what happens to performance?
- Use bracket notation with variables: `student[propertyName]`

### Reflection

After building:

- Why are objects better than separate variables for related data?
- Why are arrays better than numbered variables (user1, user2, user3)?
- When do you use objects versus arrays?
- How do you organize complex data structures?
- Why are array methods like `map` and `filter` cleaner than for loops?
- When should you use `forEach` vs `map` vs `filter`?
- How does method chaining make code more readable?
- What's the most useful array method you learned?

---

## Section 6: Asynchronous JavaScript - Waiting for Things

### Understanding Asynchronous Code

- What does "asynchronous" mean?
- Your code fetches data from a server. Does JavaScript wait for it?
- What's the difference between synchronous and asynchronous?
- Why can't JavaScript just pause and wait?

### Understanding Timing

- What does `setTimeout()` do?
- You write `setTimeout(function, 1000)` - what happens after 1 second?
- What does `setInterval()` do? How is it different?
- How do you stop a `setInterval`?

### Understanding Callbacks

- What is a callback function?
- You pass a function to `setTimeout` - when does it run?
- Why are callbacks needed for asynchronous operations?

### Understanding Promises

- What is a Promise?
- What are the three states of a Promise? (pending, fulfilled, rejected)
- What does `.then()` do?
- What does `.catch()` do?
- Why are Promises better than callbacks?

### Understanding Async/Await

- What does `async` do to a function?
- What does `await` do?
- How is `await` different from `.then()`?
- Can you use `await` outside an async function?
- How do you handle errors with async/await?

### Fetching Data

- What does `fetch()` do?
- How do you get data from an API?
- What does `.json()` do?
- Why do you need two awaits when fetching?

### Build It: Async Data Dashboard

Create a program using asynchronous JavaScript:

**Requirements:**

1. **Timing Basics**

   - Use `setTimeout` to show a message after 3 seconds
   - Use `setInterval` to show a message every 2 seconds
   - Create a countdown timer
   - Create a stopwatch

2. **Promises Practice**

   - Create a simple Promise that resolves after 2 seconds
   - Create a Promise that rejects with an error
   - Use `.then()` to handle success
   - Use `.catch()` to handle errors
   - Chain multiple `.then()`

3. **Async/Await**

   - Convert Promise chains to async/await
   - Create an async function that waits for something
   - Handle errors with try/catch
   - Call multiple async functions

4. **Fetch Data from API**

   - Fetch data from JSONPlaceholder API (free test API)
   - Get list of users
   - Get list of posts
   - Display the data in HTML
   - Show loading message while fetching

5. **Error Handling**

   - Handle network errors
   - Handle invalid responses
   - Show user-friendly error messages
   - Retry failed requests

6. **Interactive Features**
   - Search button that fetches data
   - Show loading spinner
   - Display results
   - Handle empty results

**API to use:** https://jsonplaceholder.typicode.com/users

**Experiment:**

- Try fetch without await - what happens?
- Try await without async - what error?
- Fetch a broken URL - how do you handle it?
- Make multiple fetches - are they parallel or sequential?
- Forget .json() - what do you get?

### Reflection

After building:

- Why does JavaScript need asynchronous code?
- What problems do Promises solve compared to callbacks?
- How does async/await make asynchronous code more readable?
- When do you need to handle errors in async code?

---

## Section 7: DOM - Making Pages Interactive

### Understanding the DOM

- What is the DOM?
- What does "Document Object Model" mean?
- How does JavaScript "see" your HTML?
- What's the difference between HTML and the DOM?

### Selecting Elements

- How do you select an element by ID?
- How do you select elements by class name?
- How do you select elements by tag name?
- What's the difference between `querySelector` and `querySelectorAll`?
- What does `querySelector` return if nothing is found?

### Modifying Content

- How do you change text inside an element?
- What's the difference between `textContent` and `innerHTML`?
- Why is `innerHTML` dangerous? (Security: XSS)
- How do you change an image's source?
- How do you change a link's href?

### Modifying Styles

- How do you change an element's color with JavaScript?
- How do you add/remove CSS classes?
- What's better: changing styles directly or adding/removing classes?
- How do you hide/show elements?

### Creating Elements

- How do you create a new HTML element with JavaScript?
- How do you add text to it?
- How do you add it to the page?
- What's the difference between `appendChild`, `append`, and `insertBefore`?

### Events

- What is an event?
- What does "click event" mean?
- How do you run code when someone clicks a button?
- What are common event types? (click, submit, keypress, mouseover)
- What is the `event` object?

### Event Listeners

- What does `addEventListener` do?
- How is it different from `onclick`?
- Can you add multiple event listeners to one element?
- How do you remove an event listener?

### Forms and Input

- How do you get the value from an input field?
- How do you prevent a form from submitting?
- What does `event.preventDefault()` do?
- How do you validate form input with JavaScript?

### Build It: Interactive To-Do List

Create a fully functional to-do list with the DOM:

**Requirements:**

1. **HTML Structure**

   - Input field for new to-dos
   - Button to add to-dos
   - Empty ul for the list
   - Heading and container

2. **Selecting Elements**

   - Select the input field
   - Select the button
   - Select the ul list
   - Store them in variables

3. **Adding To-Dos**

   - Click button to add new to-do
   - Create li element with JavaScript
   - Set text from input value
   - Append to ul
   - Clear input after adding

4. **Deleting To-Dos**

   - Add delete button to each to-do
   - Click delete to remove that to-do
   - Remove element from DOM

5. **Completing To-Dos**

   - Click to-do to mark as complete
   - Add/remove "completed" class
   - Use CSS to style completed items (line-through)

6. **Advanced Features**

   - Press Enter to add (not just button click)
   - Don't add empty to-dos (validation)
   - Count how many to-dos
   - Clear all completed button
   - Edit existing to-dos

7. **LocalStorage**
   - Save to-dos to localStorage
   - Load to-dos on page refresh
   - Keep to-dos persistent

**Experiment:**

- Try accessing elements before DOM loads
- Use innerHTML with user input (see XSS risk)
- Add event listener twice - what happens?
- Try event.target vs event.currentTarget
- Remove event listener - does it work?

### Reflection

After building:

- How does JavaScript make HTML interactive?
- Why is selecting elements the first step?
- When should you use `textContent` versus `innerHTML`?
- How do event listeners make websites responsive?

---

## Section 8: Modern JavaScript Features

### Understanding Modern JavaScript

- What is ES6? (ECMAScript 2015)
- Why did JavaScript need an update?
- What are modern JavaScript features?

### Template Literals

- What are template literals?
- What do backticks do?
- How do you put variables inside strings?
- What is string interpolation: `${variable}`?
- Can you put expressions inside `${}`?

### Destructuring

- What is destructuring?
- How do you extract object properties: `const { name, age } = user`?
- How do you extract array items: `const [first, second] = array`?
- Why is destructuring useful?
- Can you rename variables while destructuring?

### Spread Operator

- What is the spread operator: `...`?
- How do you copy an array: `const newArray = [...oldArray]`?
- How do you combine arrays: `[...array1, ...array2]`?
- How do you copy an object: `const newObj = {...oldObj}`?
- What's the difference between copying and referencing?

### Rest Parameters

- What are rest parameters?
- How do you accept unlimited arguments: `function sum(...numbers)`?
- What's the difference between spread and rest?
- When do you use rest parameters?

### Default Parameters

- What are default parameters?
- How do you set default values: `function greet(name = "Guest")`?
- What happens if you don't pass that argument?
- Can you use expressions as defaults?

### Modules

- What are JavaScript modules?
- What does `export` do?
- What does `import` do?
- How do you split code into multiple files?
- What's the difference between `export` and `export default`?

### Classes

- What are classes in JavaScript?
- How do you create a class?
- What is a constructor?
- How do you create an instance of a class?
- What are methods in classes?

### Build It: Modern JavaScript Todo App with Modules

Create a modular app using all modern features:

**Requirements:**

1. **Template Literals**

   - Use template literals for all strings
   - Create HTML with template literals
   - Put variables and expressions inside strings

2. **Destructuring Practice**

   - Destructure function parameters
   - Destructure objects from arrays
   - Rename while destructuring

3. **Spread and Rest**

   - Use spread to copy arrays/objects
   - Use spread to merge data
   - Use rest parameters in functions
   - Demonstrate immutable updates

4. **Default Parameters**

   - Create functions with optional parameters
   - Set meaningful defaults
   - Use defaults for configuration objects

5. **Classes**

   - Create a `Todo` class
   - Add constructor with properties
   - Add methods (complete, delete, edit)
   - Create instances of the class

6. **Modules**

   - Split code into files:
     - `Todo.js` (class)
     - `storage.js` (localStorage functions)
     - `ui.js` (DOM manipulation)
     - `app.js` (main logic)
   - Export from each module
   - Import in main file

7. **Put It All Together**
   - Create class instances
   - Use modern syntax throughout
   - Store/retrieve from localStorage
   - Clean, modular code

**File Structure:**

```
/js
  - Todo.js
  - storage.js
  - ui.js
  - app.js
index.html
```

**Experiment:**

- Try `import` without `export` - what error?
- Use old string concatenation vs template literals
- Compare copying with spread vs direct assignment
- Create a class without constructor
- Try to use rest parameter not as last parameter

### Reflection

After building:

- How do template literals improve code readability?
- Why is destructuring useful for function parameters?
- How do modules help organize large projects?
- What advantages do classes provide?

---

## 🎓 Congratulations!

You've completed the **HTML-CSS-JavaScript Self-Mastery Workbook**!

### What You've Mastered

**HTML:**
✅ Understanding what HTML is and why it exists  
✅ Structuring content semantically  
✅ Creating forms and collecting user input  
✅ Building accessible, screen-reader-friendly pages  
✅ Using semantic HTML for better SEO and accessibility

**CSS:**
✅ Understanding what CSS is and the cascade  
✅ Layout systems (Flexbox, Grid, positioning)  
✅ Responsive design for all screen sizes  
✅ CSS architecture for large projects  
✅ Performance optimization

**JavaScript:**
✅ Understanding what JavaScript is and where it runs  
✅ Variables, data types, and type coercion  
✅ Control flow and decision making  
✅ Functions, closures, and code organization  
✅ Objects and arrays for data storage  
✅ **Array methods (map, filter, reduce, forEach, find, some, every)**  
✅ Asynchronous programming  
✅ DOM manipulation and interactivity  
✅ Modern ES6+ features

### You're Ready For

After this workbook, you can:

- ✅ Build complete, interactive websites from scratch
- ✅ Understand and debug HTML, CSS, and JavaScript
- ✅ Work with modern JavaScript features and patterns
- ✅ **Process and transform data with array methods**
- ✅ **Create private state with closures**
- ✅ Make responsive, accessible websites

### What's Next?

#### Option 1: Advanced JavaScript

Continue to **"Advanced JavaScript Self-Mastery Workbook"** to master:

- Deep closures and scope chains
- Prototypes and inheritance
- Advanced async patterns
- Memory management
- Design patterns

**You're now fully prepared for this workbook!** You have all the prerequisite knowledge including array methods and closures.

#### Option 2: Framework Foundations

Continue to **"JavaScript Framework Foundations"** to learn:

- How frameworks work
- Component architecture
- State management
- Building your own mini-framework
- Then easily learn React, Vue, or Svelte

#### Option 3: Full-Stack Development

Continue to **"Development Environment & Servers"** to learn:

- Node.js and backends
- Databases
- APIs
- Deployment

### Keep Learning

- **Build projects** - The best way to learn is by doing
- **Read code** - Look at open source projects
- **Join communities** - Ask questions, help others
- **Stay curious** - Keep asking "why" and "how"

---
