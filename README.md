<<<<<<< HEAD
<<<<<<< HEAD
# Astro Starter Kit: Basics

```sh
npm create astro@latest -- --template basics
```

[![Open in StackBlitz](https://developer.stackblitz.com/img/open_in_stackblitz.svg)](https://stackblitz.com/github/withastro/astro/tree/latest/examples/basics)
[![Open with CodeSandbox](https://assets.codesandbox.io/github/button-edit-lime.svg)](https://codesandbox.io/p/sandbox/github/withastro/astro/tree/latest/examples/basics)
[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/withastro/astro?devcontainer_path=.devcontainer/basics/devcontainer.json)

> 🧑‍🚀 **Seasoned astronaut?** Delete this file. Have fun!

![just-the-basics](https://github.com/withastro/astro/assets/2244813/a0a5533c-a856-4198-8470-2d67b1d7c554)

## 🚀 Project Structure

Inside of your Astro project, you'll see the following folders and files:

```text
/
├── public/
│   └── favicon.svg
├── src/
│   ├── layouts/
│   │   └── Layout.astro
│   └── pages/
│       └── index.astro
└── package.json
```

To learn more about the folder structure of an Astro project, refer to [our guide on project structure](https://docs.astro.build/en/basics/project-structure/).

## 🧞 Commands

All commands are run from the root of the project, from a terminal:

| Command                   | Action                                           |
| :------------------------ | :----------------------------------------------- |
| `npm install`             | Installs dependencies                            |
| `npm run dev`             | Starts local dev server at `localhost:4321`      |
| `npm run build`           | Build your production site to `./dist/`          |
| `npm run preview`         | Preview your build locally, before deploying     |
| `npm run astro ...`       | Run CLI commands like `astro add`, `astro check` |
| `npm run astro -- --help` | Get help using the Astro CLI                     |

## 👀 Want to learn more?

Feel free to check [our documentation](https://docs.astro.build) or jump into our [Discord server](https://astro.build/chat).
=======
# accessibility-interactive-tutorial
meant to teach accessibility to beginner web developers
>>>>>>> 0c3c7e4 (Initial commit)
=======
### 1. **Why Learn Accessibility?**

Understanding and implementing web accessibility is essential for creating inclusive digital experiences. Here are some key reasons to prioritize accessibility in web development:

- **Inclusivity**: Accessibility ensures that your application is usable by people with disabilities, including those with visual, auditory, motor, or cognitive impairments.
- **Legal Compliance**: Many countries have laws requiring digital accessibility (e.g., ADA in the US, EN 301 549 in Europe, or WCAG compliance worldwide). Non-compliance can lead to lawsuits.
- **Wider Audience**: Making your app accessible increases its potential audience, improving user retention and satisfaction.
- **Improved UX for All**: Accessibility features often enhance usability for everyone. For example, captions help users in noisy environments, and good keyboard navigation benefits power users.
- **Ethical Responsibility**: Accessibility reflects a commitment to social responsibility and equality.

---

### 2. **Keyboard Support**

#### **The Role of Keyboard Accessibility**
Keyboard support is critical for users who cannot use a mouse or touch gestures. These users rely on the keyboard (or assistive devices like switch systems) to navigate and interact with web content. Your app must provide logical, predictable navigation and interactions for all components.

#### **Native Elements That Support Keyboard Navigation**
HTML provides several built-in elements that are keyboard-accessible by default. These elements come with pre-defined focus, event handling, and roles, requiring little to no additional work:
- **`<button>`**: Can be activated with `Space` or `Enter`.
- **`<a href="">`**: Navigable with `Tab` and activated with `Enter`.
- **Form controls**: `<input>`, `<textarea>`, `<select>`, and `<option>` support `Tab`, arrow keys, and other interactions.
- **`<details>`**: Supports keyboard interaction to expand and collapse.
- **`<label>`**: Links a text label with form controls, improving focus and usability.

#### **Adding `tabindex` to Custom Elements**
Custom elements like `<div>` or `<span>` are not focusable or keyboard-accessible by default. To make them interactive:
1. Add `tabindex="0"` to make the element part of the tab order and focusable.
2. Use JavaScript to handle `keydown` events for interactions.
3. Assign appropriate ARIA roles (`role="button"`, `role="menuitem"`, etc.) to convey the element's purpose.

Example: Making a custom button:
```html
<div class="custom-button" role="button" tabindex="0">Click Me</div>
```

```javascript
document.querySelector('.custom-button').addEventListener('keydown', (e) => {
    if (e.key === 'Enter' || e.key === ' ') {
        // Perform button action
    }
});
```

---

### 3. **Screen Reader Support**

#### **The Role of Screen Readers**
Screen readers assist users with visual impairments by reading aloud the content and structure of a webpage. They rely on semantic HTML and ARIA (Accessible Rich Internet Applications) attributes to interpret and convey the interface effectively.

#### **Native Elements That Support Screen Readers**
Some elements are inherently screen reader-friendly because they have semantic meaning:
- **Text Content**: `<p>`, `<h1>`-`<h6>`, `<ul>`/`<ol>`, `<li>`, `<blockquote>`, etc., are announced with their semantic meaning.
- **Interactive Elements**: `<button>`, `<a>`, `<input>`, `<textarea>`, `<select>` provide implicit roles and states.
- **Landmarks**: `<header>`, `<nav>`, `<main>`, `<footer>`, `<aside>`, `<section>` act as navigation aids for screen readers.

#### **Enhancing Custom Elements for Screen Readers**
For custom UI components, you may need to use ARIA attributes to ensure screen readers interpret them correctly:
- **Roles**: Define the purpose of an element (e.g., `role="button"`, `role="alert"`, `role="dialog"`).
- **States**: Indicate dynamic states like `aria-expanded`, `aria-checked`, or `aria-disabled`.
- **Labels**: Provide text alternatives using `aria-label` or `aria-labelledby`.

Example: Custom Toggle for Screen Readers:
```html
<div class="custom-toggle" role="switch" aria-checked="false" tabindex="0">
    Toggle
</div>
```

```javascript
document.querySelector('.custom-toggle').addEventListener('click', function () {
    const isChecked = this.getAttribute('aria-checked') === 'true';
    this.setAttribute('aria-checked', !isChecked);
});
```

#### **ARIA Best Practices**
- Use ARIA only when necessary (e.g., for custom components). Native HTML is always preferred because it’s more reliable.
- Ensure ARIA roles and attributes don’t conflict with native behavior (e.g., don’t add `role="button"` to an actual `<button>`).

---

>>>>>>> b324fb1 (Update README.md)
