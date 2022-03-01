# Default CSS Setup

### HTML file

- create html file
- create following html elements:
- h1 and paragraph with lorem20
- h2 and paragraph with lorem20
- h1 - h5 with random text
- a (anchor tag)
- ul with 3 list items and random text in them

### Main Style File

- create style.css file
- link style sheet with index.html

```sh
<link rel="stylesheet" href="./style.css" />
```

### Normalize.css

- create normalize.css file
- go to [normalize.css](https://necolas.github.io/normalize.css/)
- hit download and copy/paste into normalize.css
- link style sheet with index.html

```sh
<link rel="stylesheet" href="./normalize.css" />
```

### Fonts

- pick a font for headings and one for paragraphs from one of the many font related sites
- examples:

  - [pagecloud](https://www.pagecloud.com/blog/best-google-fonts-pairings)
  - [fontpair](https://www.fontpair.co/)

- then go to [typescale](https://type-scale.com/)
- set the headings and paragraphs to your liking
- grab css at bottom of page
- paste into style.css
- set fonts as css variables (--headingFont, --paragraphFont, --smallFont)
- set paragraph

```css
p {
  margin-bottom: 1.5rem;
  max-width: 45em;
}
```

-- set headings

```css
h1,
h2,
h3,
h4,
h5 {
  margin: 0;
  margin-bottom: 1.38rem;
  font-family: var(--headingFont);
  font-weight: 400;
  line-height: 1.3;
  text-transform: capitalize;
}
```

- probably change .small_text to .small-text (my preference)
- to prevent paddings to change the width of elements, add

```css
*,
::after,
::before {
  box-sizing: border-box;
}
```

- remove underline from links

```css
a {
  text-decoration: none;
}
```

- remove list item markers and padding from unordered list

```css
ul {
  list-style-type: none;
  padding: 0;
}
```

### Color Palette

- visit one of the following sites and pick a primary color:
  - [happyhues](https://www.happyhues.co/)
  - [coolors](https://coolors.co/)
  - [fontpair](https://www.fontpair.co/)
- set --primary-500 variable as your chosen color
- or go to one of these sites and pick a primary color and 8 shades right away
  - [bootstrap](https://getbootstrap.com/docs/5.0/customize/color/#color-sass-maps)
  - [tailwind](https://tailwindcss.com/docs/customizing-colors#color-palette-reference)
- if you have only picked 1 primary color, go to any color shade generator, e.g. [shadowlord](https://noeldelgado.github.io/shadowlord/#b144ab)
- enter chosen color, set % to 20 to get 5 lighter and 5 darker shades of chosen color
- set color variables like following

```css
:root {
  --primary-100: #f2e5db;
  --primary-200: #e5cbb8;
  --primary-300: #d8b094;
  --primary-400: #cb9671;
  --primary-500: #be7c4d;
  --primary-600: #98633e;
  --primary-700: #724a2e;
  --primary-800: #4c321f;
  --primary-900: #26190f;
}
```

- get greyscale by going to [tailwind](https://tailwindcss.com/docs/customizing-colors#color-palette-reference)
- set grey scale color variables like following

```css
:root {
  --grey-50: #fafafa;
  --grey-100: #f4f4f5;
  --grey-200: #e4e4e7;
  --grey-300: #d4d4d8;
  --grey-400: #a1a1aa;
  --grey-500: #71717a;
  --grey-600: #52525b;
  --grey-700: #3f3f46;
  --grey-800: #27272a;
  --grey-900: #18181b;
}
```

- set other variables like following

```css
--backgroundColor: var(--grey-100);
--textColor: var(--grey-800);
--borderRadius: 0.25rem;
--letterSpacing: 1px;
--transition: 0.3s ease-in-out all;
--max-width: 1120px;
--fixed-width: 600px;
```

- use --backgroundColor and --textColors as a variables in body {}
- set global border radius, letter spacing, transition, max width of all elements and a fixed width for smaller elements (like forms)

### Box Shadows

- go to [tailwind](https://tailwindcss.com/docs/box-shadow)
- copy/paste from Box Shadow menu into variables

```css
--shadow-1: 0 1px 3px 0 rgb(0 0 0 / 0.1), 0 1px 2px -1px rgb(0 0 0 / 0.1);
--shadow-2: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
--shadow-3: 0 10px 15px -3px rgb(0 0 0 / 0.1), 0 4px 6px -4px rgb(0 0 0 / 0.1);
--shadow-4: 0 20px 25px -5px rgb(0 0 0 / 0.1), 0 8px 10px -6px rgb(0 0 0 / 0.1);
```

### Handle Image

- find a source image on the internet and copy the link, or get it locally
- right after ul, set up the img tag

```css
   <img
      src="https://upload.wikimedia.org/wikipedia/commons/a/a3/ThinkCentre_S50.jpg"
      alt="computer"
    />
```

- create img class and set the img tag to the class

```css
.img {
  width: 100%;
  height: 100%;
  display: block;
  object-fit: cover;
}
```

- since images will be used best wrappen in containers, create a div.container here
- wrap it around the img tag created before
- create .container class and add some styling

```css
.container {
  width: 50vw;
  border: 5px solid var(--primary-600);
  border-radius: var(--borderRadius);
  max-width: var(--max-width);
}
```

- to explain, in .img, we use:
  - width: 100% to fill out the container with the image exactly
  - height: 100%, in case the container height is set, this need to be set too
  - display: block because otherwise the image leaves a weird empty bar next to it
  - object-fit: cover to preserve the aspect ratio (otherwise the image gets distorted)

### Buttons

- add 2 button elements below the img one

```css
    <button class="btn" type="button">default button</button>
    <button class="btn btn-special" type="button">special button</button>
```

- set their css classes like following

```css
.btn {
  cursor: pointer;
  color: var(--white);
  background-color: var(--primary-500);
  border: none;
  border-radius: var(--borderRadius);
  letter-spacing: var(--letterSpacing);
  padding: 0.375rem 0.75rem;
  box-shadow: var(--shadow-1);
  transition: var(--transition);
  text-transform: capitalize;
  display: inline-block;
}

.btn:hover {
  background-color: var(--primary-700);
  box-shadow: var(--shadow-3);
}

.btn-special {
  color: var(--primary-500);
  background-color: var(--primary-200);
}

.btn-special:hover {
  color: var(--primary-200);
  background-color: var(--primary-700);
  box-shadow: var(--shadow-3);
}
```

- sometimes you would want the buttons to span the whole parent width
- so you add the .btn-block class accordingly

```css
.btn-block {
  width: 100%;
}
```

### Alerts

- set up 2 div elements below the buttons from before, with the following classes

```css
  <div class="alert alert-danger">hello</div>
  <div class="alert alert-success">danger</div>
```

- by default they span the whole width of their parent
- set their classes like this

```css
.alert {
  padding: 0.375rem 0.75rem;
  margin-bottom: 1rem;
  border-radius: var(--borderRadius);
}

.alert-danger {
  color: var(--red-dark);
  background-color: var(--red-light);
}

.alert-success {
  color: var(--green-dark);
  background-color: var(--green-light);
}
```

### Form

- add form element like this

```css
    <form class="form">
      <h4>contact form</h4>
      <div class="form-row">
        <label for="name" class="form-label">Name</label>
        <input
          type="text"
          class="form-input"
          id="name"
          placeholder="Your Name Here"
        />
      </div>
      <div class="form-row">
        <label for="number" class="form-label">Number</label>
        <input
          type="number"
          class="form-input"
          id="number"
          placeholder="Your Name Here"
        />
      </div>
      <div class="form-row">
        <label for="email" class="form-label">Email</label>
        <input
          type="text"
          class="form-input"
          id="email"
          placeholder="Your Email Here"
        />
      </div>
      <div class="form-row">
        <label for="textarea" class="form-label"> Textarea </label>
        <textarea class="form-textarea">
          Default text...
        </textarea>
      </div>
      <button type="submit" class="btn btn-block">Submit</button>
    </form>
```

### Form Alert Text

- add a small tag inside one of the .form-row elements like this

```css
  <small class="form-alert">Please provide value</small>

```

- we added earlier the css for small tags, but now add this

```css
.form-alert {
  color: var(--red-dark);
  letter-spacing: var(--letterSpacing);
  text-transform: capitalize;
}
```

### Loading animation

- add a div.loading

```css
    <div class="loading"></div>

```

- add the following css to loading class

```css
.loading {
  width: 6rem;
  height: 6rem;
  border: 10px solid var(--grey-300);
  border-radius: 50%;
  border-bottom-color: var(--grey-300);
  border-left-color: var(--grey-200);
  border-top-color: var(--grey-100);
  animation: spinner 0.6s linear infinite;
  /* put the loading circle in a container to center */
  /* this line only for this example */
  margin: 0 auto;
}
```

This concludes our default css setup for projects.
