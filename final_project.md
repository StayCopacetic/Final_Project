# Final Project - Blog Site w/ Multiple Links

## Course HTML:

```html
<!-- Below are various portions of the html that I want to examine further, aka the syntax, naming conventions and when classes were utilized over relying on inheritence -->

<section class="call-to-action">
  <div class="container">
    <header>
      <h2 class="section-title">Inbox</h2>
      <p class="section-subtitle">Knowledge letters</p>
    </header>
    <img
      src=""
      alt=""
    />

    <form
      action=""
      method="post"
      class="newsletter"
    >
      <div>
        <label for="">Name</label>
        <input type="text" />
      </div>
      <div>
        <label for="">Email</label>
        <input
          type="email"
          name=""
          id=""
        />
      </div>
      <button type="submit">Subscribe</button>
    </form>
  </div>
</section>

<footer class="primary-footer">
  <div class="primary-footer__inner">
    <a
      href="index.html"
      aria-label="acme home page"
      ><img
        src="logo.svg"
        alt=""
        class="logo"
    /></a>

    <dl>
      <dt class="text-serif">Map</dt>
      <dd><a href="#">Blog</a></dd>
      <dd><a href="#">Privacy</a></dd>
    </dl>

    <dl>
      <dt class="text-serif">Resources</dt>
      <dd><a href="#">Courses</a></dd>
      <dd><a href="#">Hacks</a></dd>
      <dd><a href="#">Free stuff</a></dd>
    </dl>
  </div>
  <div class="split text-serif">
    <p class="copywrite">© 2020 acme. All rights reserved</p>
    <ul class="footer-social">
      <li><a href="#">Yt</a></li>
      <li><a href="#">Tw</a></li>
      <li><a href="#">Fb</a></li>
      <li><a href="#">Li</a></li>
    </ul>
  </div>
</footer>
```

---

## Course CSS:

```css
/* Adding the css because I am going to study the structure of the cascade and how various properties are created. */

:root {
  --ff-sans: 'IBM Plex Sans', sans-serif;
  --ff-serif: 'IBM Plex Serif', serif;

  /* small screen font-sizes */
  --fs-200: 0.75rem;
  --fs-300: 1rem;
  --fs-400: 1.25rem;
  --fs-500: 1.375rem;
  --fs-600: 1.75rem;
  --fs-900: 2.125rem;

  --fw-200: 200;
  --fw-300: 300;
  --fw-400: 400;
  --fw-700: 700;

  --clr-neutral-100: #fff;
  --clr-neutral-200: #eef1f6;
  --clr-neutral-300: #a9afbc;
  --clr-neutral-400: #737b8c;
  --clr-neutral-500: #434956;
  --clr-neutral-900: #020203;

  --clr-primary-300: #f3f7ff;
  --clr-primary-400: #8ea8da;

  --br: 1rem;
}

@media (min-width: 40em) {
  :root {
    --fs-500: 1.75rem;
    --fs-600: 2.125rem;
    --fs-900: 4.25rem;
  }
}

/* reset */

*,
*::before,
*::after {
  box-sizing: border-box;
}

h1,
.h1,
h2,
.h2,
h3,
.h3,
h4,
.h4 {
  line-height: 1;
}

body,
h1,
h2,
h3,
p,
dl,
dd,
figure {
  margin: 0;
}

ul[class],
ol[class] {
  list-style: none;
  padding: 0;
}

input,
button,
textarea,
select {
  font: inherit;
}

img {
  max-width: 100%;
  height: auto;
  display: block;
  border-radius: var(--br);
}

body {
  line-height: 1.3;
  font-family: var(--ff-sans);
  font-size: var(--fs-400);
  font-weight: 300;
  padding: 1.5rem;
}

.bg-primary-300 {
  /* used bg-color instead og background, so that it doesn't override another property that's included in your stylesheet. Be careful with how you're setting up your padding because it can interfere with padding applied to elements in the container block. */
  background-color: var(--clr-primary-300);
  border-radius: 1rem;
  padding-left: 1rem;
  padding-right: 1rem;
}

/* typography */

h1,
h2,
h3,
.section-subtitle,
.text-serif {
  font-family: var(--ff-serif);
  font-weight: var(--fw-200);
}

a {
  font-weight: var(--fw-700);
  font-size: var(--fs-300);
  color: var(--clr-neutral-900);
}

a:hover,
a:focus {
  color: var(--clr-primary-400);
}

.text-500 {
  font-size: var(--fs-500);
}

.page-title {
  font-size: var(--fs-900);
}

.page-intro {
  font-size: var(--fs-600);
}

.section-title {
  font-size: var(--fs-600);
  color: var(--clr-neutral-400);
}

.section-subtitle {
  font-size: var(--fs-600);
}

.btn {
  display: inline-block;
  cursor: pointer;
  border: 0;
  background: none;
  font-weight: var(--fw-700);
  font-size: var(--fs-300);
  font-family: var(--ff-sans);
  text-decoration: none;
  color: var(--clr-neutral-900);
}

.btn::after {
  content: '\203A';
  margin-left: 1em;
  font-weight: var(--fw-300);
}

.btn:hover,
.btn:focus {
  color: var(--clr-primary-400);
}

/* general layout */

section {
  padding: 2.5rem 0;
}

@media (min-width: 40em) {
  section {
    padding: 3.5rem;
  }
}

.container {
  max-width: 50rem;
  margin: 0 auto;
}

.flow-content > * + * {
  margin-top: var(--flow-spacer, 1em);
}

.split {
  display: flex;
  flex-direction: column;
}

.split > * + * {
  margin: 4rem 0 0 0;
}

.split > * {
  flex-basis: 100%;
}

@media (min-width: 40em) {
  .split {
    flex-direction: row;
  }

  .split > * + * {
    margin: 0 0 0 2.5rem;
  }
}

.xl-space {
  margin-top: 5rem;
}

/* components */

.primary-header {
  border-radius: var(--br);
  padding: 2rem;
  background-color: var(--clr-primary-400);
  min-height: 50vh;
}

.primary-nav {
  position: fixed;
  bottom: 0.5em;
  left: 0.5em;
  right: 0.5em;
  border-radius: var(--br);
  background: var(--clr-neutral-900);
  font-family: var(--ff-serif);
}

.primary-nav ul {
  display: flex;
  justify-content: space-around;
  margin: 0;
  padding: 0.8em 0;
}

.primary-nav li {
  line-height: 0;
}

.primary-nav a {
  color: var(--clr-neutral-200);
  text-decoration: none;
}

@media (min-width: 40em) {
  .primary-nav {
    position: static;
    background: transparent;
  }

  .primary-nav a {
    color: inherit;
    text-decoration: none;
  }

  .primary-header__inner {
    display: flex;
    justify-content: space-between;
  }

  .primary-nav ul {
    padding: 0;
  }

  .primary-nav li {
    margin-left: 2em;
  }
}

.article-preview h3 {
  font-size: var(--fs-500);
}

.article-preview img {
  object-fit: cover;
  height: 12.5rem;
  width: 100%;
}

.article-preview .info {
  display: flex;
  font-weight: var(--fw-400);
  font-size: var(--fs-200);
  color: var(--clr-neutral-400);
}

.article-preview .info > *:first-child {
  margin-right: 2rem;
}

.call-to-action form {
  margin-top: 3rem;
  display: flex;
  flex-direction: column;
  gap: 3rem;
}

.call-to-action form > div {
  flex-basis: 100%;
  flex-shrink: 1;
  flex-grow: 1;
}

.call-to-action input {
  width: 100%;
  border: 0;
  border-bottom: 2px solid var(--clr-neutral-300);
}

.call-to-action input:focus {
  border-color: var(--clr-primary-400);
  border-width: 4px;
}

.call-to-action input::placeholder {
  color: var(--clr-neutral-300);
  opacity: 1;
}

.call-to-action label {
  display: block;
  margin-bottom: 0.5em;
  font-size: var(--fs-300);
  font-weight: var(--fw-400);
}

.call-to-action button {
  align-self: flex-start;
}

@media (min-width: 40em) {
  .call-to-action form {
    flex-direction: row;
  }

  .call-to-action button {
    align-self: center;
  }
}

.primary-footer__inner {
  --border: 2px solid var(--clr-neutral-200);
  border-top: var(--border);
  border-bottom: var(--border);
  padding: 3em 0;
  margin: 2em 0;
}

footer {
  padding-bottom: 1em;
}

.footer-nav {
  display: flex;
}

.footer-nav > *:first-child {
  margin-right: 4em;
}

.footer-social {
  display: flex;
  gap: 2em;
}

.footer-social a {
  font-weight: var(--fw-200);
}

/* homepage styles */

.intro {
  --flow-spacer: 2em;
}
```
