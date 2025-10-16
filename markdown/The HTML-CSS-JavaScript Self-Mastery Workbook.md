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

Before starting this workbook, you only need some **basic computer knowledge** and a few essential tools. Don't worry – nothing advanced is required.

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

Instead, it gives you the **right questions to ask yourself** – questions every developer must be able to answer to master the topic at a global standard.

### Here's how to use it effectively:

#### 1. Ask Yourself First

- Before looking things up, try to explain the answer in your own words
- If you can't, that's fine – it means you found a gap in your knowledge
- If a new question pops up in your own mind that's not in here, that's your curiosity leading you deeper – write it down and explore it

#### 2. Leverage All Resources

- Use Google, Stack Overflow, and ChatGPT to research
- Read documentation, articles, and examples
- Find a way to practice and produce results
- Experiment! Break things and see what happens

#### 3. Learn by Doing

- Each section has project exercises
- Completing these exercises forces you to practice and discover the answers naturally
- Don't skip them – doing is how you'll turn "theory" into mastery

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

### This is a **"find the answer within yourself"** document – the web development version.

- The **questions** represent the knowledge every web developer must internalize

- **Be curious** → always ask "why does this work this way?"

- The **resources** (Google, Stack Overflow, ChatGPT) are your tools – but the true goal is that **the understanding lives inside you**, not just in your search history

- The **exercises** are opportunities to struggle, explore, and discover

- **Expect mistakes** → debugging is how you learn

- **Reflect** → explain new concepts in your own words

### Questions Grow With You

This workbook starts with the absolute basics:

- **Foundational questions** - What is this? Why does it exist?
- **How-to questions** - How do I use this?
- **Deep questions** - Why does it behave this way?
- **Scenario questions** - How do I solve this real problem?

By the time you've asked and answered everything here – and built the exercises – you won't just "know HTML, CSS, and JavaScript." **You'll understand them so deeply that you can build, debug, and explain any project with confidence.**

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
- What's the difference between `<div>` and `<span>`? Try putting each on a page – how do they display differently?
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
5. Right-click and "View Page Source" – see your code!

**Experiment:**

- What happens if you forget the closing `</html>` tag?
- What happens if you put content in the `<head>` instead of `<body>`?
- Try removing the `<!DOCTYPE html>` – does anything change?
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

You have text content – paragraphs, headings, lists, quotes – and you need to structure it so browsers and search engines understand what each piece means. Without structure, everything is just plain text with no hierarchy or meaning.

### Headings and Hierarchy

- What are heading tags (`<h1>` through `<h6>`)? Why are there six levels?
- You have a blog post with a title, section titles, and subsection titles. Which heading tags should you use for each?
- What happens if you use `<h1>` for your main title and then `<h4>` for the next heading? Does it work? What problems might it cause?
- How do screen readers use headings to help blind users navigate a page?
- Can you have multiple `<h1>` tags on one page? Should you?

### Paragraphs and Text Formatting

- What's the difference between `<p>` and `<br>`? When should you use each?
- You want to make some text bold. You could use `<b>` or `<strong>`. What's the difference? When does it matter?
- What's the difference between `<i>` and `<em>`? They both make text italic – so why have both?
- How do you highlight text like a marker would on paper?
- How do you show text that's been deleted or added (like in a document with tracked changes)?

### Lists and Structured Content

- What's the difference between ordered lists (`<ol>`) and unordered lists (`<ul>`)?
- Your list has nested sub-lists (a list inside a list). How do you create this structure?
- When should you use a list versus separate paragraphs?
- What is a description list (`<dl>`)? When would you use it?

### Grouping Content

- What is a `<div>` and why is it called a "division"?
- You want to group some paragraphs together. Should you wrap them in a `<div>`, a `<section>`, or something else?
- What's the difference between `<div>` and `<section>`? Do they display differently?
- How do you add a line break between content sections?

### Build It: Blog Article About Yourself

Create a structured blog post introducing yourself:

**Requirements:**

1. **Document Title**

   - `<h1>` for the main title: "About Me"

2. **Sections with Headings**

   - Use `<h2>` for section titles: "My Background", "My Interests", "My Goals"
   - Use `<h3>` for subsections if needed

3. **Paragraphs**

   - Write at least 3 paragraphs about yourself
   - Use `<p>` tags properly
   - Use `<strong>` to emphasize important points
   - Use `<em>` for subtle emphasis

4. **Lists**

   - Create an ordered list of your top 5 goals
   - Create an unordered list of your hobbies
   - Create a nested list (maybe your hobbies with sub-items)

5. **Formatting**
   - Use `<mark>` to highlight one key phrase
   - Use `<del>` and `<ins>` to show something you changed your mind about
   - Use `<blockquote>` for a favorite quote
   - Use `<code>` if you mention any technical terms

**Experiment:**

- Try different heading levels – does the browser display them differently?
- Create a list with 3 levels of nesting
- Leave out closing tags – what happens?
- Use multiple `<br>` tags in a row – how does spacing work?

### Reflection

After building:

- Why is using heading hierarchy important beyond just making text bigger or smaller?
- When should you use semantic tags (`<strong>`, `<em>`) versus style tags (`<b>`, `<i>`)?
- How does proper structure help search engines understand your content?
- What makes a list more appropriate than paragraphs for certain content?

---

## Section 3: Links, Images & Media

### The Problem

Text-only pages are boring. You need to add images, videos, and links to other pages. The web is called the "web" because pages link to each other. Without links and media, you just have isolated documents.

### Understanding Links

- What is a hyperlink? What makes it "hyper"?
- What does the `<a>` tag stand for? (Hint: not "link")
- You want to link to another page. What attribute tells the browser where to go?
- What's the difference between `href="about.html"` and `href="https://google.com"`? (Relative vs absolute URLs)
- How do you make a link open in a new tab? Should you always do this?
- How do you create a link that jumps to a specific section on the same page?
- What's the difference between `<a>` and `<button>`? When should you use each?

### Working with Images

- What is the `<img>` tag? Why doesn't it have a closing tag?
- What does `src` stand for? What does this attribute do?
- You add an image, but it's way too big and breaks your layout. How do you control the size?
- What is `alt` text? Why is every image supposed to have it?
- Your image file doesn't exist or the path is wrong. What does the browser display?
- What's the difference between `<img>` and CSS `background-image`? When should you use each?

### Adding Videos and Audio

- How do you embed a video in your page with the `<video>` tag?
- What's the difference between embedding a video file and embedding a YouTube video?
- What are video controls? How do you add play/pause buttons?
- How do you add an audio player to your page?
- What's the purpose of including multiple `<source>` elements inside a `<video>` tag?

### Figures and Captions

- You have an image that needs a caption underneath. How do you group them together semantically?
- What's the difference between just putting text under an image versus using `<figure>` and `<figcaption>`?
- Can you use `<figure>` for things other than images?

### Build It: Personal Portfolio Page

Create a portfolio page with links and media:

**Requirements:**

1. **Navigation Links**

   - Create a navigation menu at the top
   - Link to different sections: Home, About, Projects, Contact
   - Use anchor links to jump to sections on the same page

2. **External Links**

   - Link to your social media profiles (or fake ones)
   - Make external links open in new tabs
   - Add at least 3 external links

3. **Images**

   - Add a profile picture (use placeholder if you don't have one)
   - Add at least 3 project images
   - Give every image meaningful `alt` text
   - Make sure images aren't ridiculously huge

4. **Figures with Captions**

   - Wrap your project images in `<figure>` tags
   - Add `<figcaption>` describing each project

5. **Media**
   - Embed a video (use a sample video file or YouTube embed)
   - Add video controls
   - (Optional) Add an audio file with a player

**Experiment:**

- What happens if you forget the `alt` attribute?
- Try setting image width with attributes vs CSS
- Break an image link – what does the browser show?
- Try different YouTube embed options
- Create a clickable image (put `<img>` inside `<a>`)

### Reflection

After building:

- Why does the web use hyperlinks? What would the internet be like without them?
- Why is `alt` text important beyond just accessibility?
- When should you link to another page versus create anchor links on the same page?
- What's the difference between embedding media and linking to it?

---

## Section 4: Forms & User Input

### The Problem

You need to collect information from users: login credentials, search queries, contact messages, survey responses. Forms are how users send data to your website. Understanding forms is essential for building interactive websites.

### Understanding Forms

- What is an HTML form? What happens when you submit a form?
- What does the `<form>` tag do? Why do you need it?
- What's the difference between `method="get"` and `method="post"`?
- What does the `action` attribute do? Where does form data go when submitted?
- What happens if you press Enter while typing in a form?

### Input Types

- What is an `<input>` tag? Why are there so many types?
- What's the difference between `type="text"`, `type="email"`, and `type="password"`?
- You want users to select a date. What input type do you use?
- What's the difference between radio buttons and checkboxes? When do you use each?
- How do you create a dropdown menu where users select one option?
- How do you create a large text area for longer messages?

### Labels and Accessibility

- What is a `<label>` tag? Why should every input have a label?
- You click on the label text and the input focuses. How does this work?
- What's the relationship between the label's `for` attribute and the input's `id`?
- Why is this relationship important for accessibility?

### Form Validation

- What does `required` do? Try submitting a form without filling in a required field.
- How do you set minimum and maximum values for a number input?
- What does the `pattern` attribute do? How do you validate an email format?
- What's the difference between HTML validation and JavaScript validation?
- How do you show users helpful error messages when validation fails?

### Buttons and Submission

- What's the difference between `<button>` and `<input type="button">`?
- What does `type="submit"` do? How is it different from a regular button?
- You have a form with multiple buttons. How do you prevent them all from submitting the form?
- What does `type="reset"` do? When is it useful?

### Build It: Contact Form with Validation

Create a working contact form:

**Requirements:**

1. **Form Structure**

   - Wrap everything in a `<form>` tag
   - Set appropriate `action` and `method`
   - Add a form title/heading

2. **Input Fields**

   - Name input (text type, required)
   - Email input (email type, required)
   - Phone number (tel type, optional)
   - Subject dropdown (select with multiple options)
   - Message textarea (required, at least 10 characters)

3. **Labels and Accessibility**

   - Every input has a label
   - Labels are connected with `for` and `id`
   - Add placeholder text for guidance

4. **Advanced Inputs**

   - Contact preference: radio buttons (Email, Phone, Either)
   - Newsletter signup: checkbox
   - Best time to contact: time picker
   - Date of inquiry: date picker

5. **Validation**

   - Mark required fields with `required`
   - Email must be valid format
   - Message must be at least 10 characters (minlength)
   - Phone must match a pattern (optional: use pattern attribute)

6. **Submission**
   - Submit button at the bottom
   - Reset button to clear the form
   - Try submitting – what happens?

**Experiment:**

- What happens when you submit without filling required fields?
- Try entering an invalid email – what does the browser do?
- Click on labels – do the inputs focus?
- Remove all labels – how does it affect usability?
- Try tabbing through the form – does it work logically?

### Reflection

After building:

- Why are labels important beyond just showing text next to inputs?
- What's the difference between client-side validation (HTML/JavaScript) and server-side validation?
- When should you use a checkbox versus radio buttons?
- How do forms make the web interactive rather than just informational?

---

## Section 5: Tables & Structured Data

### The Problem

You have data that naturally fits in rows and columns: price comparisons, schedules, statistics, grades, product specifications. Tables display this structured data clearly and let users scan and compare information efficiently.

### Understanding Tables

- What is a table? When should you use a table versus a list?
- What are the main parts of a table: `<table>`, `<tr>`, `<td>`, `<th>`?
- What does each abbreviation mean? (tr = table row, td = table data, th = table header)
- Why should you never use tables for page layout? (They used to be used this way – what changed?)

### Table Structure

- What's the difference between `<thead>`, `<tbody>`, and `<tfoot>`? Why have three sections?
- When should you use `<th>` versus `<td>`?
- How do you create a table with headers both at the top AND on the left side?
- What is the `scope` attribute? Why is it important for accessibility?

### Spanning Cells

- You want one cell to stretch across multiple columns. What attribute do you use?
- What's the difference between `colspan` and `rowspan`?
- You're creating a calendar table. How do you make cells span multiple days?
- What happens if your colspan/rowspan math doesn't add up correctly?

### Table Captions and Accessibility

- What is a `<caption>` element? Where does it go in the table?
- Why should tables have captions?
- How do screen readers announce table data? How does proper structure help?

### Build It: Student Grade Table

Create a comprehensive grade table:

**Requirements:**

1. **Basic Grade Table**

   - Table with student names, 3 assignment scores, midterm, final, and total
   - Use `<thead>` for header row with `<th>` elements
   - Use `<tbody>` for student data rows with `<td>` elements
   - Use `<tfoot>` for average row at the bottom
   - Add a `<caption>` describing the table

2. **Scope Attributes**

   - Add `scope="col"` to column headers
   - Add `scope="row"` to student names (if names are in first column)

3. **Spanning Cells**

   - Create a "Assignments" header that spans 3 columns
   - Create a "Exams" header that spans 2 columns
   - Group related columns with merged headers

4. **Styling Context** (using attributes)

   - Add alternating background colors using CSS or style attribute
   - Highlight the header row
   - Make the footer row stand out

5. **Second Table: Schedule**
   - Create a weekly class schedule
   - Days of week as columns
   - Time slots as rows
   - Use rowspan for classes longer than one period
   - Use colspan for classes across multiple days

**Experiment:**

- Try removing `<thead>` and `<tbody>` – does it still work?
- Make a cell span wrong (colspan="2" but you want 3 columns)
- Try nesting a table inside a table cell
- Remove all `<th>` tags and use `<td>` – how does it affect readability?

### Reflection

After building:

- When is a table the right choice versus a list or other structure?
- Why is semantic table structure important for accessibility?
- How does `scope` help screen reader users understand table relationships?
- What makes colspan and rowspan powerful but potentially confusing?

---

## Section 6: Semantic HTML & Accessibility

### The Problem

Two websites can look identical but be completely different in their HTML structure. One uses `<div>` for everything, the other uses semantic HTML. Search engines and screen readers can understand the semantic one but struggle with the `<div>`-soup. Accessibility isn't optional – it's a core requirement for professional web development.

### Understanding Semantic HTML

- What does "semantic" mean? How is `<header>` more semantic than `<div id="header">`?
- Why should you care about semantics if you can style a `<div>` to look like anything?
- How do search engines use semantic HTML to understand your page?
- What's wrong with using `<div>` and `<span>` for everything?

### Semantic Structure Elements

- What's the difference between `<div>` and `<section>`?
- When should you use `<article>` versus `<section>`?
- What is `<header>` for? Can you have multiple `<header>` elements?
- What goes in a `<nav>` element? Should all links be in `<nav>`?
- What is `<main>`? How many `<main>` elements should a page have?
- What is `<aside>` for? What kind of content belongs in it?
- What is `<footer>` for? Can you have multiple footers?

### Landmarks and Navigation

- What are "landmark" elements? How do screen reader users use them?
- How does a blind user jump directly to the main content of your page?
- What is a "skip to content" link? Why is it important?
- Why should your page have a logical heading structure?

### Accessibility Basics

- What does "accessibility" (a11y) mean in web development?
- Why should every image have an `alt` attribute?
- Your navigation uses icon buttons with no text. How do screen reader users know what they do?
- What is ARIA? When should you use ARIA attributes?
- What is keyboard navigation? Why must your site work without a mouse?
- What is focus? How do you make focus visible to keyboard users?

### ARIA Attributes

- What does `aria-label` do? When do you need it?
- What is `aria-hidden`? When should you hide content from screen readers?
- What are `aria-live` regions? When do you need them?
- What does `role` attribute do? When should you avoid using it?
- What is `aria-current`? How does it help with navigation?

### Build It: Accessible News Article Page

Create a complete, accessible news article:

**Requirements:**

1. **Semantic Structure**

   - `<header>` for the site header (logo, main navigation)
   - `<nav>` for navigation menu
   - `<main>` for the main content area (only one per page)
   - `<article>` for the news article
   - Multiple `<section>` elements within the article
   - `<aside>` for related links or sidebar
   - `<footer>` for copyright and footer links

2. **Heading Hierarchy**

   - One `<h1>` for the article title
   - `<h2>` for major sections
   - `<h3>` for subsections
   - No skipped heading levels

3. **Navigation**

   - Create a "Skip to main content" link at the very top
   - Navigation menu with current page indicated
   - Use semantic `<nav>` element
   - Add `aria-current="page"` to current page link

4. **Images and Media**

   - All images have descriptive `alt` text
   - Decorative images have `alt=""`
   - Use `<figure>` and `<figcaption>` for images with captions

5. **Forms (if included)**

   - All inputs have `<label>` elements
   - Error messages are associated with inputs
   - Required fields are marked

6. **Keyboard Navigation**

   - All interactive elements are reachable with Tab
   - Focus is visible (don't remove outline without replacement)
   - Logical tab order (top to bottom, left to right)

7. **ARIA Enhancements**

   - Add `aria-label` to icon buttons
   - Use `aria-live="polite"` for dynamic content updates
   - Use `aria-hidden="true"` for decorative icons

8. **Content**
   - Use `<strong>` and `<em>` for semantic emphasis, not just styling
   - Use `<time>` for dates with `datetime` attribute
   - Use `<address>` for contact information

**Testing Requirements:**

- Navigate the entire page using only the keyboard (Tab, Shift+Tab, Enter)
- Use a screen reader (NVDA on Windows, VoiceOver on Mac)
- Validate HTML with W3C validator
- Check with WAVE accessibility tool

**Experiment:**

- Replace semantic elements with `<div>` - how does screen reader experience change?
- Remove all `alt` attributes - what does screen reader announce?
- Remove focus indicators - can you navigate with keyboard?
- Skip heading levels (h1 to h4) - what problems does this cause?

### Reflection

After building:

- Why is semantic HTML important beyond just "looking the same"?
- How do search engines benefit from semantic structure?
- What's the difference between making something look accessible and actually being accessible?
- When should you use ARIA versus using semantic HTML?

---

# CSS

---

## 🟢 Beginner: What is CSS? Styling Basics

### Understanding CSS

- What is CSS, and what problem does it solve?
- Why is styling separated from HTML? What if they were combined?
- What does "Cascading Style Sheets" mean? What is "cascading"?
- What's the difference between presentation and structure?
- Before CSS existed, how did people make websites look good? Why did they need CSS?

### Adding CSS to HTML

- What are the three ways to add CSS to HTML? (Inline, Internal, External)
- You add `style="color: red"` directly to a tag. Where does this fall? When is this okay?
- You add `<style>` tags in the `<head>`. What is this called? When should you use it?
- You create a separate `styles.css` file and link it. How do you connect it to your HTML?
- What are the pros and cons of each method?
- Which method is best for a multi-page website? Why?

### CSS Syntax

- What is the basic syntax of a CSS rule? (selector, property, value)
- What's the difference between a selector, a property, and a value?
- You write `color: red` - which part is the property? Which is the value?
- What does the semicolon (`;`) do? What happens if you forget it?
- What do the curly braces (`{}`) do?
- How do you write comments in CSS?

### Selectors: Targeting Elements

- How do you select all `<p>` elements?
- How do you select an element with `id="header"`?
- How do you select elements with `class="button"`?
- What's the difference between `#header` and `.header`?
- Can multiple elements have the same class? Can multiple elements have the same ID?
- What's the difference between `.nav li` and `.nav > li`? (Descendant vs child)

### Basic Properties

- How do you change text color?
- How do you change background color?
- How do you change font size?
- How do you make text bold? Italic?
- How do you change which font is used?
- How do you add space inside an element? Outside an element?

### Understanding Specificity

- You have two rules targeting the same element with different colors. Which color wins?
- What makes one selector more "specific" than another?
- Why does `#header` win over `.header`?
- You have a rule on `p` and another on `.intro`. Which one applies to `<p class="intro">`?
- What is the specificity order: element, class, ID, inline style?
- How do you check which styles are actually applied to an element?

### The Cascade

- Three rules target the same element with the same specificity. Which one wins?
- What does "last one wins" mean?
- What is inheritance? Which properties inherit and which don't?
- Your `<body>` has `color: blue`. Does the color apply to all text on the page?

### Build It: Style Your Portfolio Page

Take your HTML portfolio from before and add CSS:

**Requirements:**

1. **Set Up CSS**

   - Create a `styles.css` file
   - Link it to your HTML with `<link>` in the `<head>`
   - Test that it's connected (change body background color)

2. **Typography**

   - Change the font family for the entire page
   - Style all headings with a different color
   - Make your `<h1>` bigger than the browser default
   - Change paragraph font size
   - Adjust line-height for readability

3. **Colors**

   - Set a background color for the page
   - Set a different background color for your header section
   - Make links a specific color
   - Change link color on hover

4. **Selectors Practice**

   - Use element selectors (all `<p>` tags)
   - Use class selectors (add classes to elements first)
   - Use ID selectors (add an ID to one element)
   - Use descendant selectors (`.nav a` for links inside navigation)

5. **Specificity Challenges**
   - Style a paragraph with a class differently from other paragraphs
   - Create a style conflict and see which rule wins
   - Use browser DevTools to inspect which styles are applied
   - Override a style by making a more specific selector

**Experiment:**

- Add inline styles - do they override your external CSS?
- Create two conflicting rules with the same specificity
- Make a typo in a property name - what happens?
- Try to style an element but your CSS doesn't apply - debug why
- Change the order of rules in your CSS - does anything change?

### Reflection

After building:

- Why is external CSS better than inline styles for large projects?
- How does the cascade decide which styles to apply?
- Why does specificity exist? What problems would occur without it?
- How do you debug CSS when styles don't apply as expected?

---

## 🟡 Intermediate: Layout & Positioning

### The Problem

Your elements stack vertically like a text document. You need elements side-by-side, centered, positioned exactly where you want them. You need grids, flexbox layouts, navigation bars, sidebars, and footers. Understanding layout is what separates a plain document from a real website design.

### Understanding the Box Model

- What is the CSS box model?
- What's the difference between content, padding, border, and margin?
- You set `width: 200px` on a div. Then you add `padding: 20px` and `border: 5px`. How wide is the div now?
- What does `box-sizing: border-box` do? How is it different from the default?
- What's the difference between margin and padding? When do you use each?
- How do you add spacing between elements? Inside elements?

### Display Types

- What does `display: block` mean? Which elements are block by default?
- What does `display: inline` mean? Which elements are inline by default?
- What's the difference between `display: inline-block` and `display: block`?
- Your `<span>` needs width and height. Does it work? Why or why not?
- What does `display: none` do? How is it different from `visibility: hidden`?

### Positioning

- What are the five position values? (static, relative, absolute, fixed, sticky)
- What is the default positioning for elements?
- What does `position: relative` do? Relative to what?
- What does `position: absolute` do? What is it positioned relative to?
- Your absolutely positioned div isn't where you expect. What's happening with the parent?
- What does `position: fixed` do? When would you use it?
- What does `position: sticky` do? How is it a hybrid of relative and fixed?
- What are `top`, `right`, `bottom`, `left` properties? When can you use them?

### Understanding Flexbox

- What problem does Flexbox solve?
- How do you make an element a flex container?
- What's the difference between `justify-content` and `align-items`?
- Your items are in a column instead of a row. What property controls direction?
- What does `flex-wrap` do? When do you need it?
- What's the difference between `flex-grow`, `flex-shrink`, and `flex-basis`?

### Understanding CSS Grid

- What problem does Grid solve that Flexbox doesn't?
- How do you create a grid container?
- What's the difference between `grid-template-columns` and `grid-template-rows`?
- How do you create a 3-column layout with Grid?
- What does `gap` do in Grid? How is it different from margin?
- What's the difference between `fr` units and percentages in Grid?
- How do you make an item span multiple columns or rows?

### Float and Clear

- What does `float` do? Why was it originally created?
- What's the "float collapse" problem?
- What does `clear` do?
- Why don't people use float for layout anymore? What replaced it?

### Build It: Responsive Dashboard Layout

Create a complete page layout using different techniques:

**Requirements:**

1. **Box Model Practice**

   - Create boxes/cards with content
   - Add padding inside boxes
   - Add margin between boxes
   - Add borders around boxes
   - Use `box-sizing: border-box` on all elements

2. **Header (Fixed Position)**

   - Create a header that sticks to the top when scrolling
   - Use `position: fixed`
   - Make sure content doesn't hide behind it
   - Add logo on left, navigation on right

3. **Navigation Bar (Flexbox)**

   - Create a horizontal navigation menu
   - Use Flexbox to space items evenly
   - Items should distribute across available space
   - Add hover effects

4. **Content Layout (Grid)**

   - Create a grid layout with main content and sidebar
   - Use CSS Grid with columns: 70% main, 30% sidebar
   - Add gap between grid items
   - Make sure grid is responsive

5. **Card Grid (Flexbox)**

   - Create a grid of cards (like products or blog posts)
   - Use Flexbox to arrange cards
   - Cards should wrap to new rows
   - Cards should have equal heights

6. **Footer**

   - Create a footer at the bottom
   - Use Flexbox for internal layout
   - Make it full width

7. **Positioning Challenges**
   - Add a "back to top" button (fixed position)
   - Position a badge/notification icon on a button (absolute)
   - Make an element overlap another (z-index)

**Layout Requirements:**

- Header: 60px height, fixed at top
- Sidebar: 250px width
- Main content: fills remaining space
- Cards: 3 per row on desktop, wrap responsively
- Footer: spans full width at bottom

**Experiment:**

- Try removing `box-sizing: border-box` - what breaks?
- Change flex-direction from row to column
- Add more grid items than fit - what happens?
- Make a positioned element but forget parent position: relative
- Try different z-index values - what controls stacking?

### Reflection

After building:

- When should you use Flexbox versus Grid?
- What problems does `box-sizing: border-box` solve?
- How does positioning create layers (z-index)?
- Why is understanding the box model crucial for all CSS layout?

---

## 🔵 Advanced: Responsive Design & Performance

### The Problem

Your beautiful desktop design breaks on mobile phones. Images are huge, text is tiny, layouts stack awkwardly, buttons are too small to tap. Over 50% of web traffic is mobile. Your site must work perfectly on any screen size. You also need to optimize CSS for fast loading and smooth animations.

### Understanding Responsive Design

- What does "responsive" mean in web design?
- What would happen if you built a website that only looked good on your laptop?
- Why do some websites make you pinch-zoom on mobile while others adapt perfectly?
- What is "mobile-first" design? Why do people recommend it?

### Viewport and Meta Tag

- What is the viewport?
- You open your site on a phone and it looks like a tiny desktop version. What's missing?
- What does `<meta name="viewport" content="width=device-width, initial-scale=1.0">` do?
- What happens if you forget this meta tag?

### Media Queries

- What is a media query?
- How do you apply different styles for different screen sizes?
- What's the difference between `min-width` and `max-width`?
- You want styles for "tablets only" (not mobile, not desktop). How do you target that?
- What is a "breakpoint"? How do you choose where to place breakpoints?
- What's the difference between `screen`, `print`, and `all` media types?

### Responsive Units

- What's the difference between `px`, `%`, `em`, `rem`, `vw`, and `vh`?
- When should you use pixels versus relative units?
- You set font-size: 2em. What is it relative to?
- What's the difference between `em` and `rem`?
- What are viewport units (`vw`, `vh`)? When are they useful?
- What does `calc()` do? When would you use it?

### Responsive Images

- Your image is 4000px wide but displays at 400px. Is the user downloading the whole thing?
- What is the `srcset` attribute? How does it help with responsive images?
- What are `sizes` attributes? How do they work with `srcset`?
- What is the `<picture>` element? When should you use it instead of `<img>`?
- What is "art direction" for images?
- What is lazy loading? How do you implement it?

### Flexible Layouts

- How do you make a grid that shows 3 columns on desktop, 2 on tablet, 1 on mobile?
- Your design uses fixed widths (300px). How do you make it flexible?
- What does `max-width` do? How is it different from `width`?
- How do you make a container fluid but never wider than a certain size?

### CSS Performance

- Which CSS properties trigger reflow (layout recalculation)?
- Which properties can be animated smoothly (GPU-accelerated)?
- What's the difference between animating `width` versus `transform`?
- Why do some animations feel "janky" or slow?
- What does `will-change` do?
- What is "render-blocking CSS"? How do you fix it?

### Build It: Fully Responsive Portfolio Website

Transform your portfolio into a professional responsive site:

**Requirements:**

1. **Mobile-First Development**

   - Start with mobile styles (320px)
   - Add media queries for larger screens
   - Breakpoints: 768px (tablet), 1024px (desktop)
   - Test at every size

2. **Responsive Grid**

   - Cards: 1 column on mobile, 2 on tablet, 3 on desktop
   - Use CSS Grid with `auto-fit` or `auto-fill`
   - Or use Flexbox with `flex-wrap`

3. **Responsive Typography**

   - Base font-size: 16px mobile, 18px desktop
   - Headings scale proportionally
   - Use `rem` for consistent sizing
   - Consider using `clamp()` for fluid typography

4. **Responsive Navigation**

   - Mobile: Hamburger menu (vertical)
   - Desktop: Horizontal menu
   - Smooth transition between layouts
   - Touch-friendly tap targets (44px minimum)

5. **Responsive Images**

   - Use `srcset` for different resolutions
   - Use `<picture>` for art direction (different crops)
   - Lazy load images below the fold
   - Ensure images never overflow

6. **Flexible Layouts**

   - Use `%` or `fr` units for widths
   - Use `max-width` to prevent super-wide layouts
   - Use `min-height` for flexible boxes
   - Avoid fixed heights

7. **Performance Optimization**
   - Animate `transform` and `opacity` only
   - Use `will-change` for frequently animated elements
   - Minimize CSS file size
   - Inline critical CSS (above-the-fold styles)

**Media Query Breakpoints:**

```css
/* Mobile first: base styles */
/* Tablet: 768px and up */
/* Desktop: 1024px and up */
```

**Testing Requirements:**

- Test on real devices (phone, tablet)
- Use Chrome DevTools device emulation
- Test at random sizes between breakpoints
- Ensure no horizontal scroll at any size
- Test with slow network (DevTools throttling)

**Experiment:**

- Remove viewport meta tag - what happens on mobile?
- Try animating `width` versus `transform` - feel the difference
- Use only fixed widths - watch it break
- Remove media queries - how does mobile look?
- Add hundreds of complex selectors - test performance

### Reflection

After building:

- Why is mobile-first development often better than desktop-first?
- Which CSS properties can you safely animate without performance issues?
- How do you balance responsive design with performance?
- When should you use `em` versus `rem` versus `px`?

---

## 🔴 Expert: CSS Architecture & Scale

### The Problem

Your project has grown. You have 10,000 lines of CSS. Multiple developers are editing the same stylesheet. Class names conflict. Specificity wars are constant. Old styles are accumulating because you're afraid to delete anything. You need a methodology to organize, maintain, and scale CSS.

### Understanding CSS Architecture

- Why does CSS need "architecture"? Can't you just write styles?
- What problems appear when CSS grows large?
- What is a naming convention? Why would you need one?
- What is specificity hell? How do projects get there?
- How do you organize CSS in large projects?

### CSS Methodologies

- What is BEM (Block Element Modifier)?
- What do these mean: `.card`, `.card__title`, `.card--featured`?
- Why would you write long class names like `.site-header__navigation-item--active`?
- What is OOCSS (Object-Oriented CSS)?
- What is SMACSS? How does it organize styles?
- What is utility-first CSS (like Tailwind)?
- What are the pros and cons of each methodology?

### CSS Variables (Custom Properties)

- What are CSS custom properties? How are they different from Sass variables?
- How do you define a CSS variable? How do you use it?
- Your site has 20 shades of blue scattered throughout the CSS. How do CSS variables help?
- Can you change CSS variables with JavaScript?
- What's the difference between `:root` and `:host` for variables?
- How do CSS variables enable theming?

### Cascade Layers

- What are CSS cascade layers (`@layer`)?
- How do layers help control specificity?
- You have reset styles, base styles, component styles, and utility styles. How do layers help organize them?
- What's the cascade order with layers?
- Why would you want to explicitly control cascade order?

### CSS Organization

- How do you split CSS into multiple files?
- What's the difference between one huge CSS file versus many small ones?
- How do you organize CSS by component? By page? By type?
- What is a CSS reset? What is normalization?
- How do you structure your CSS folder/file system?

### Preprocessors and PostCSS

- What is a CSS preprocessor (Sass, Less)?
- What features do preprocessors add that CSS doesn't have natively?
- What is PostCSS? How is it different from Sass?
- What is autoprefixer? What problem does it solve?
- Do you still need preprocessors now that CSS has variables?

### CSS-in-JS

- What is CSS-in-JS?
- How is it different from external stylesheets?
- What are the pros and cons of CSS-in-JS?
- When would you choose CSS-in-JS over traditional CSS?
- What is component-scoped CSS?

### Build It: Design System with Architecture

Create a scalable design system:

**Requirements:**

1. **Choose and Implement Methodology**

   - Pick BEM, utility-first, or hybrid approach
   - Document your naming conventions
   - Create a style guide explaining the system

2. **Design Tokens with CSS Variables**

   - Define color palette (primary, secondary, neutrals)
   - Define typography scale (font sizes, weights, line heights)
   - Define spacing scale (4px, 8px, 16px, 24px, 32px, etc.)
   - Define breakpoints
   - Define shadows, border radii, etc.
   - Store all tokens as CSS variables

3. **CSS Organization**

   - Split into multiple files:
     - `reset.css` - CSS reset/normalize
     - `variables.css` - Design tokens
     - `base.css` - Base element styles
     - `layout.css` - Layout utilities
     - `components.css` - Reusable components
     - `utilities.css` - Utility classes
   - Use `@import` or build tool to combine

4. **Cascade Layers**

   - Implement `@layer` for organization:
     - `@layer reset` - Reset styles
     - `@layer base` - Base element styles
     - `@layer components` - Component styles
     - `@layer utilities` - Utility overrides

5. **Component Library**

   - Create reusable components:
     - Buttons (primary, secondary, outlined, sizes)
     - Cards (default, elevated, with image)
     - Form inputs (text, email, select, etc.)
     - Navigation (header, footer, sidebar)
     - Alerts/notifications
   - All components themeable with CSS variables

6. **Theme System**

   - Create light theme (default)
   - Create dark theme
   - Use CSS variables for theme switching
   - Support prefers-color-scheme media query
   - Implement theme toggle with JavaScript

7. **Documentation**
   - Document all components with examples
   - Show all color tokens
   - Show all spacing values
   - Explain naming conventions
   - Provide usage guidelines

**Build Three Versions for Comparison:**

**Version 1: BEM Methodology**

```css
.card {
}
.card__header {
}
.card__title {
}
.card--featured {
}
```

**Version 2: Utility-First**

```html
<div class="bg-white p-4 rounded shadow"></div>
```

**Version 3: Hybrid Approach**

```css
/* Component classes for structure */
.card {
}
/* Utility classes for variations */
.mt-4 {
}
```

**Experiment:**

- Try scaling to 50+ components
- Have multiple developers work simultaneously
- Refactor from one methodology to another
- Measure CSS file size of each approach
- Compare developer experience

### Reflection

After building:

- What are the trade-offs between BEM and utility-first approaches?
- How do CSS variables make theming easier than Sass variables?
- When does CSS architecture become necessary versus over-engineering?
- How do cascade layers solve specificity problems?

---

# JavaScript

---

## Section 1: What is JavaScript? Your First Program

### Understanding JavaScript

- What is JavaScript, and what problem does it solve?
- What's the difference between HTML, CSS, and JavaScript? What does each one do?
- Why do we need JavaScript? What can you do with JavaScript that you can't do with HTML/CSS?
- Where does JavaScript run? (In the browser? On the server?)
- What does "scripting language" mean?
- Is JavaScript related to Java? (Spoiler: No, but why the similar name?)

### Your First JavaScript

- How do you add JavaScript to an HTML page?
- What's the difference between inline JavaScript (`<script>` in HTML) and external JavaScript (`.js` file)?
- You add `<script>` at the top of `<head>`. Your code doesn't work. You move it to the bottom of `<body>`. Now it works. Why?
- What does `console.log()` do? Where does the output appear?
- How do you open the browser console to see JavaScript output?

### JavaScript Basics

- What is a statement in JavaScript?
- What does the semicolon (`;`) do? What happens if you forget it?
- How do you write comments in JavaScript?
- What is an error? What does "SyntaxError" mean?
- You write `consol.log("Hello")` and get an error. How do you read error messages?

### Making Things Happen

- You want to show a popup message to the user. What does `alert()` do?
- You want to ask the user a question and get their response. What does `prompt()` do?
- You want the user to confirm something (OK or Cancel). What does `confirm()` do?
- Why do people say not to use `alert()` in real websites?

### Build It: "Hello World" Interactive Page

Create your first interactive JavaScript program:

**Requirements:**

1. **Set Up JavaScript**

   - Create an HTML file
   - Add a `<script>` tag at the bottom of `<body>`
   - Write `console.log("Hello World")`
   - Open the page and check the browser console

2. **Console Output**

   - Log different types of messages
   - Log numbers, text, calculations
   - Try logging multiple things at once
   - Understand where output appears

3. **User Interactions**

   - Use `alert()` to show a greeting message
   - Use `prompt()` to ask the user their name
   - Use `confirm()` to ask a yes/no question
   - Log the responses to console

4. **Your First Program**
   - Ask user for their name (prompt)
   - Ask user for their age (prompt)
   - Show a personalized greeting (alert)
   - Log everything to console

**Experiment:**

- Forget the semicolon - what happens?
- Make a typo in `console.log` - read the error message
- Put `<script>` in `<head>` before `<body>` - what breaks?
- Try logging math: `console.log(5 + 3)`
- Try logging text + text: `console.log("Hello" + "World")`

### Reflection

After building:

- Why do we need JavaScript when HTML and CSS already make websites?
- Where does JavaScript code run?
- How do you debug JavaScript when something doesn't work?
- Why is the console your best friend as a developer?

---

## Section 2: Variables & Data Types

### Understanding Variables

- What is a variable? Why do we need them?
- What does "variable" mean? (Hint: it comes from "varies" - can change)
- How do you create a variable in JavaScript?
- What's the difference between `var`, `let`, and `const`?
- When should you use `let` versus `const`?
- What happens if you try to change a `const` variable?

### Declaring Variables

- You write `let name;` What does this do?
- You write `let name = "Alice";` What does the `=` mean?
- Can you create a variable without giving it a value?
- What does "declare" mean? What does "initialize" mean?
- Can you declare multiple variables at once?

### Variable Naming

- What are the rules for naming variables?
- Can variable names have spaces?
- Can they start with numbers?
- What is camelCase? Why do JavaScript developers use it?
- Which is better: `x` or `userName`? Why?

### Understanding Data Types

- What is a data type?
- What are the main data types in JavaScript?
- What's the difference between a string and a number?
- What is a boolean? What values can it have?
- What is `null`? What is `undefined`? What's the difference?

### Working with Strings

- What is a string?
- How do you create a string? (Single quotes? Double quotes?)
- Can you add strings together? What does `"Hello" + "World"` give you?
- How do you put quotes inside a string?
- What are template literals? What do backticks do?
- How do you put variables inside strings?

### Working with Numbers

- How do you create a number?
- Can you do math in JavaScript?
- What happens when you add, subtract, multiply, divide?
- What is `%` (modulo)? What does it do?
- What happens when you divide by zero?
- What is `NaN`? When do you see it?

### Type Checking

- How do you check what type a variable is?
- What does `typeof` do?
- You type `typeof "hello"` - what do you get?
- You type `typeof 42` - what do you get?
- What's weird about `typeof null`?

### Type Coercion

- What is type coercion?
- You type `"5" + 3` - what do you get? Why?
- You type `"5" - 3` - what do you get? Why?
- Why does `+` behave differently than `-`?
- What's the difference between `==` and `===`?
- Why do people say to always use `===`?

### Build It: Personal Information Form

Create a program that works with variables and data types:

**Requirements:**

1. **Variables Practice**

   - Create variables with `let` for things that change
   - Create variables with `const` for things that don't change
   - Try to change a `const` - see what error you get

2. **Different Data Types**

   - Create string variables (name, city, favorite food)
   - Create number variables (age, year born, lucky number)
   - Create boolean variables (isStudent, likesJavaScript)
   - Create a variable with `null`
   - Create a variable without a value (undefined)

3. **Working with Strings**

   - Combine strings with `+`
   - Use template literals with backticks
   - Put variables inside template literals
   - Create a full sentence using multiple variables

4. **Working with Numbers**

   - Do math with numbers (add, subtract, multiply, divide)
   - Calculate age from birth year
   - Use modulo to check if numbers are even or odd
   - Calculate percentages

5. **Type Checking**

   - Use `typeof` on all your variables
   - Log the type of each variable to console
   - Try doing math with strings - what happens?
   - Try adding string + number - what happens?

6. **Interactive Program**
   - Ask user for their name (prompt)
   - Ask for their age (prompt)
   - Ask if they like JavaScript (confirm)
   - Calculate their birth year
   - Show a message with all their info

**Experiment:**

- Try changing a `const` variable - what error do you get?
- Add a string and a number - what happens?
- Subtract a string and a number - what happens?
- Compare `"5" == 5` versus `"5" === 5`
- Try doing math with `null`, `undefined`, `true`

### Reflection

After building:

- Why do variables make programming powerful?
- When should you use `const` versus `let`?
- Why do we need different data types?
- What problems does type coercion cause?

---

## Section 3: Making Decisions with Control Flow

### Understanding Control Flow

- What does "control flow" mean?
- Your program runs from top to bottom. How do you make it do different things based on conditions?
- What is a condition? What is true/false logic?

### If Statements

- What does an `if` statement do?
- You write `if (age > 18)` - what does this check?
- What goes inside the curly braces `{}`?
- What happens if the condition is false?
- Can you have code that runs only when the condition is false?

### Else and Else If

- What does `else` do?
- How do you check multiple conditions with `else if`?
- You're checking grades: A, B, C, D, F. How many `else if` do you need?
- What's the difference between multiple separate `if`s and `else if`?

### Comparison Operators

- How do you check if two things are equal?
- What's the difference between `=`, `==`, and `===`?
- How do you check if something is NOT equal?
- How do you check if a number is greater than, less than?
- What does `>=` and `<=` mean?

### Logical Operators

- What does `&&` mean? (AND)
- What does `||` mean? (OR)
- What does `!` mean? (NOT)
- You want to check if age is between 18 and 65. How do you write this?
- You want to check if username OR password is wrong. How?

### Truthy and Falsy

- What values are "falsy" in JavaScript?
- What does `if (name)` check? Is it checking if name exists?
- Why does `if (0)` not run but `if (1)` does?
- What's the difference between `undefined`, `null`, `""`, and `0`?

### Switch Statements

- What is a switch statement? When do you use it?
- How is switch different from multiple if/else if?
- What does `break` do in a switch?
- What happens if you forget `break`?
- What is the `default` case?

### Ternary Operator

- What is the ternary operator (`? :`)?
- How do you write an if/else in one line?
- You write `age > 18 ? "Adult" : "Minor"` - what does this mean?
- When is ternary more readable than if/else?

### Build It: Interactive Quiz Game

Create a quiz that makes decisions based on user answers:

**Requirements:**

1. **Basic If/Else**

   - Ask user a question (prompt)
   - Check if answer is correct (if statement)
   - Show "Correct!" or "Wrong!" message
   - Log result to console

2. **Grade Calculator**

   - Ask user for a score (0-100)
   - Use if/else if to assign letter grade:
     - 90-100: A
     - 80-89: B
     - 70-79: C
     - 60-69: D
     - Below 60: F
   - Show the grade to user

3. **Login System**

   - Ask for username
   - Ask for password
   - Check if BOTH are correct (&&)
   - Show success or error message
   - Count login attempts

4. **Age Checker**

   - Ask for age
   - Check if age is valid (>= 0 AND <= 120)
   - Check if person is child (<13), teen (13-17), adult (18-64), or senior (65+)
   - Use nested if statements or else if

5. **Menu System with Switch**

   - Show menu options: 1. Start Game, 2. Instructions, 3. Quit
   - Use switch statement
   - Handle each case differently
   - Show message for invalid choice (default)

6. **Ternary Practice**
   - Use ternary to set a variable based on condition
   - Check if user is logged in: `const message = isLoggedIn ? "Welcome back!" : "Please log in"`
   - Use ternary in template literal

**Experiment:**

- Use `=` instead of `===` in a condition - what happens?
- Forget the `break` in a switch case - see fall-through
- Use `&&` vs using nested if statements
- Chain multiple ternary operators - is it readable?
- Check equality of different types: `"5" == 5` vs `"5" === 5`

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

### Build It: Calculator and Utility Functions

Create a collection of reusable functions:

**Requirements:**

1. **Basic Functions**

   - Create a function that adds two numbers
   - Create a function that subtracts two numbers
   - Create a function that multiplies two numbers
   - Create a function that divides two numbers
   - Call each function and log results

2. **Functions with Parameters**

   - Create `greet(name)` - takes name, returns greeting
   - Create `calculateAge(birthYear)` - returns current age
   - Create `isEven(number)` - returns true if even
   - Create `max(a, b)` - returns the larger number

3. **Functions that Return Values**

   - Create `calculateTax(amount, rate)` - returns tax amount
   - Create `calculateTotal(price, quantity)` - returns total
   - Create `getGrade(score)` - returns letter grade
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

**Experiment:**

- Call a function before declaring it - what happens?
- Return multiple times in one function
- Access a local variable from outside the function
- Create a function without return - what does it return?
- Arrow function with multiple statements - need curly braces?

### Reflection

After building:

- How do functions make code easier to maintain?
- Why is it important to return values rather than just console.log?
- When should you use arrow functions versus regular functions?
- How does scope protect variables?

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

### Build It: Student Management System

Create a program that manages student data:

**Requirements:**

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
   - Find a student by name (loop through array)

4. **Nested Data**

   - Each student has an array of grades
   - Access specific grades
   - Add a new grade to a student
   - Calculate average grade for a student

5. **Interactive Features**
   - Ask user for student name
   - Search array for that student
   - Display student information
   - Allow user to add new students

**Experiment:**

- Try accessing `students[100]` - what happens?
- Try accessing `student.nonexistent` - what happens?
- Put functions inside objects (methods)
- Create objects inside arrays inside objects (deep nesting)
- Use bracket notation with variables: `student[propertyName]`

### Reflection

After building:

- Why are objects better than separate variables for related data?
- Why are arrays better than numbered variables (user1, user2, user3)?
- When do you use objects versus arrays?
- How do you organize complex data structures?

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
✅ Functions and code organization  
✅ Objects and arrays for data storage  
✅ Asynchronous programming  
✅ DOM manipulation and interactivity  
✅ Modern ES6+ features

### You're Ready For

After this workbook, you can:

- ✅ Build complete, interactive websites from scratch
- ✅ Debug HTML, CSS, and JavaScript issues
- ✅ Understand how the web works
- ✅ Read and understand others' code
- ✅ Learn frameworks (React, Vue, etc.)
- ✅ Build real projects for real users

### What's Next?

#### Option 1: Advanced JavaScript

Continue to **"Advanced JavaScript Self-Mastery Workbook"** to master:

- Closures and advanced scope
- Prototypes and inheritance
- Advanced async patterns
- Memory management
- Design patterns

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
