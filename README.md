# Syntaxt highlighting for LDraw™ files in Sublime Text 3

<img src="./ldraw-syntax-for-sublime-text-screenshot.png?raw=true" height="400" alt="Screenshot">

## What does it do?
The syntax file annotates the code and provides scopes to the text in your source code. These scopes can then be used by Sublime Text to highlight your code according to a color scheme. And other plugins can also use these scopes for other functionality, such as autocomplete suggestions, hinting, etc.

I included a color scheme for the specific scopes used in the syntax file. You can use it as-is, or copy the content to your current color scheme (see below) and adjust it.

## Features
* Color highlighting:
  * Header statements (see Notes)
  * Meta commands (see Notes)
  * Comments
  * Line commands
  * Deprecated, invalid and/or unpreferred code
* Impove readability:
  * Coloring `x`, `y` and `z` coordinates in RGB
  * Marking every odd vertex' background to differentiate them
* Faster and better review and optimization of your code

## Installation
Download the two source files from this Github.

### Adding the syntax file
1) Copy `LDraw.sublime-syntax` into you Sublime Text 3 `Packages\User` folder and restart your application.
   > If you can't find it, click `Preferences` -> `Browse Packages` inside Sublime Text 3. This should open the right folder where you'll find the `User` folder.

   > For Windows, it's under: `C:\Users\[your username]\AppData\Roaming\Sublime Text 3\Packages\User`
2) Open a `.LDR`, `.DAT` or `.MPD` file and it should highlight straight away!
   > If not, click `View` -> `Syntax` -> `LDraw` or click on `Plain text` in the bottom right corner and select `LDraw`
   > If you start a new file with `0 `, it will auto-detect that you're starting a LDraw file and switch to the right syntax

### (Optional) Adding the color scheme
Although most highlighting should probably work fine in your current theme and color scheme, for full functionality you need to set up the colors for some specific text scopes.
1) Open `Material-Theme.sublime-color-scheme` in Sublime Text 3.
2) Click `Tools` -> `Packages` -> `Package Development` -> `Edit Current Color Scheme`
   > Note: You might need Sublime's [PackageDev](https://github.com/SublimeText/PackageDev) package installed for this.
3) Copy and paste/merge the `variables` and `rules` from the source file to the now opened current color scheme file.
4) (Optional) Adjust colors and styles as you wish.
5) Save the current color scheme file in your `Packages\User` folder.

## Notes
* This is just a start and does not contain _all_ official file specification restrictions, etc.
* Only some of the header statements and meta commands are supported at the moment.
* **Feel free to send suggestions, open issues, improve the code and send in pull requests!**

## More info
* [LDraw File Format Specification](https://www.ldraw.org/article/218.html)
* [Sublime Text Syntax Definitions](https://www.sublimetext.com/docs/syntax.html)
* [Sublime Color Schemes](https://www.sublimetext.com/docs/color_schemes.html)

## Credits
* The color scheme is based on **Mattia Astorino's [Material Theme](https://github.com/equinusocio/material-theme)**.
* The rest is made by Philip van Heemstra

## License
This work is licensed under a [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-nc-sa/4.0/).

[LDraw](https://www.ldraw.org)™ is a trademark owned and licensed by the Estate of James Jessiman
