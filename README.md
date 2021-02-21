# SCSS Partial for equal size grid system

This SCSS Partial creates a grid system with equal sized columns that can be used for layouts such as image galleries or for layouting other content pieces. [demo](http://mariodammann.de/projects/mtg-token-generator/).

## Demo
1. [Image grid](http://mariodammann.de/projects/css-grid/fixed.html)
2. [Nested content grid](http://mariodammann.de/projects/css-grid/content.html)

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes

### Prerequisites

1. [Sass](https://sass-lang.com/install) (only if you want to change the default styling)


### Installation

1. Clone the repo
   ```sh
   git clone https://github.com/webdamn/css-grid
   ```
2. Import the sass partial into your existing project
    ```scss
   @import "grid";
   ```
3. Compile to css

## How to use

This grid allows you to define how many columns (equal sized) are used for the chosen breakpoints. Out of the box this grid system allows the display of up to 12 columns. This limitation may be changed via the **$grid-columns** sass variable.

### Grid types
There are two ways to define your grid columns that may also be mixed.
1. Fixed amount of columns
2. As many as possible

#### Fixed amount of columns ([Demo](http://mariodammann.de/projects/css-grid/fixed.html))
This creates a grid of images with 6 columns on extra large screens (>=1200px), 3 columns on medium sized screens (>= 992px) and 2 columns on extra small screens (>= 480px). The grid automaticly falls back to 1 column, unless you explitly define a fallback e.g. "grid--2" to always use atleast 2 columns.
  ```html
   <div class="grid grid--xl--6 grid--md--3 grid--xs--2">
      <img src="...">
      <img src="...">
      <img src="...">
      ...
    </div>
   ```
#### As many columns as possible ([Demo](http://mariodammann.de/projects/css-grid/auto-fit.html))
This creates a grid of images with as many columns as possible while maintaining a minimum column width of 240px.
  ```html
   <div class="grid grid--auto-fit">
      <img src="...">
      <img src="...">
      <img src="...">
      ...
    </div>
   ```
   
#### Mixed ([Demo](http://mariodammann.de/projects/css-grid/mixed.html))
This creates a grid of images with 6 columns on extra large screens (>=1200px). Below this resolutions the grid creates as many columns as possible while maintaining a minimum column width of 240px.
  ```html
   <div class="grid grid--xl--6 grid--xs--auto-fit">
      <img src="...">
      <img src="...">
      <img src="...">
      ...
    </div>
   ```   
   
### Breakpoints

The default grid includes the following breakpoints. You may change (rename, remove, add) breakpoints by editing the **$grid-breakpoints** sass map.
| Breakpoint         | min-width                                                                                          |
|------------------|-----------------------------------------------------------------------------------------------------|
| XS | >= 480px                  |
| SM | >= 768px                  |
| MD | >= 992px             |
| LG | >= 1200px            |
| XL | >= 1400px        |

### Other settings

#### Grid class
The default grid class/prefix is "**grid**". You may change this via the **$grid-class** sass variable.

#### Grid gap
The default grid gap between rows/columns is 24px. You may change this via the **$grid-gap-row** or **$grid-gap-column** sass variables.

#### Minimum width for columns in auto-fit grids
The default grid uses a minimum width of 240px for columns in the auto-fit grid. You may change this via the **$grid-auto-fit-min-width** sass variable.
