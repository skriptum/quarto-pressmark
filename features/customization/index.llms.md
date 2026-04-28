# Customization

Making Pressmark work for you (e.g with a Dark Mode)

![](colorpicker.jpg)

Swiss Design Color Picker

Maybe you’d like to tweak the theme’s default colors or switch to a different font. Since everything is defined in a single SCSS file, making these changes is straightforward.

If you want to go beyond basic customization, take a look at the [Quarto documentation](https://quarto.org/docs/output-formats/html-themes.html) or this excellent [blog post](https://silviacanelon.com/blog/2023-09-29-hello-quarto/) by Silvia Canelón.

## Changing background colors

Open the SCSS file and you’ll find the following variables:

``` css
$primary-color: #faf9f6;  // page background
$primary-color-shade: #f0eee7; // code blocks, etc.
$highlight-color: #990f3d; // accent color
$highlight-color-shade: #d0b6b6; // button hover color
$dark : #000000;  // mostly used for borders
$font-color: #1b1b1b; // text color

// DARK MODE COLORS
// $primary-color: rgb(20, 20, 20);  // page background
// $primary-color-shade: rgb(30, 30, 30); // code blocks, etc.
// $highlight-color: rgb(210, 156, 174); // accent color
// $highlight-color-shade: rgb(211, 60, 111); // button hover color
// $dark : rgb(156, 156, 156);  // mostly used for borders
// $font-color: rgb(218, 218, 218); // text color
```

To enable dark mode, simply comment out the first six lines and uncomment the dark mode values below. The defaults are designed to work well out of the box.

If you have a specific color palette in mind, feel free to adjust these variables to match your style.

## Changing the font

To change the font, the easiest approach is to pick one from Google Fonts. For example, a clean sans-serif option for body text is Josefin Sans.

Import the font in pressmark.scss and update the Bootstrap body font variable:

``` css
@import url('https://fonts.googleapis.com/css2?family=Josefin+Sans:ital,wght@0,100..700;1,100..700&display=swap'); // sans-serif
...
$font-family-text: 'Josefin Sans', 'Georgia', 'Times New Roman', serif;
```

Your site should now use the new font.

**Note**: It’s recommended to keep the default fonts for headings and small caps. They’re carefully chosen to match the theme, and the CSS sizing is optimized for them.
