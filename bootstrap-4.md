# My notes from Bootstrap 4 documentation

## Getting started

### Starter template for quick up & going 

``` html
<!doctype html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-beta.3/css/bootstrap.min.css" integrity="sha384-Zug+QiDoJOrZ5t4lssLdxGhVrurbmBWopoEl+M6BdEfwnCJZtKxi1KgxUyJq13dy" crossorigin="anonymous">

    <title>Hello, world!</title>
  </head>
  <body>
    <h1>Hello, world!</h1>

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.2.1.slim.min.js" integrity="sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js" integrity="sha384-ApNbgh9B+Y1QKtv3Rn7W3mgPxhU9K/ScQsAP7hUibX39j7fakFPskvXusvfa0b4Q" crossorigin="anonymous"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-beta.3/js/bootstrap.min.js" integrity="sha384-a5N7Y/aK3qNeh15eJKGWxsqtnX/wWdSZSKp+81YjTmS15nvnvxKHuzaWwXHDli+4" crossorigin="anonymous"></script>
  </body>
</html>
```

### Box-sizing

Global `box-sizing` value has been changed from `content-box` to `border-box` which means width of element that you set will contain border and padding, too.

## Layout

### Containers

Containers are required when using default grid system. There are two kinds of containers:

* `.container` : fixed-width container, meaning its `max-width` changes at each breakpoint.

* `.container-fluid` : fluid-width, meaning it's spanning the entire width of the viewport all the time.

### Grid system

* Bootstrap's grid system uses a series of containers, rows, and columns to layout and align content.

* Rows are wrappers for columns. Each has horizontal `padding` (called a _gutter_) for controlling the space between them. This padding is counteracted on the rows with negative margins. You can remove the `margin` from rows and `padding` from columns with `.no-gutters` on the `.row`.

* In a grid layout, content must be placed within columns and only columns may be immediate children of rows.

* Grid columns without a specified `width` such as `.col-sm` will automatically layout as equal width columns.

* Column `width`s are sized relative to their parent element.

* Grid breakpoints apply to that one breakpoint and all those above it. For example, `.col-lg-4` applies to large  and extra-large devices, but not the ones smaller than large breakpoint.

* Handy table for breakpoints and grid system:

  | Name | Extra small | Small | Medium | Large | Extra-large |
  | ---- | ----------- | ----- | ------ | ----- | ----------- |
  | Screen size | <576px | >=576px | >=768px | >=992px | >=1200px |
  | Max container width | None(auto) | 540px | 720px | 960px | 1140px |
  | Class prefix | `.col-` | `col-sm` | `.col-md` | `.col-lg` | `.col-xl` |
  | # of columns | 12 | 12 | 12 | 12 | 12|
  | Gutter width | 30px (15px on each side of column) | 30px (15px on each side of column) | 30px (15px on each side of column) | 30px (15px on each side of column) | 30px (15px on each side of column) |

* `.col-{breakpoint}-auto` classes size columns based on the natural width of their content.

* Create equal-width columns that span multiple rows by inserting a `.w-100` class where you want the columns to break to a new line.
  ``` html
  <div class="row">
    <div class="col">col</div>
    <div class="col">col</div>
    <div class="w-100"></div>
    <div class="col">col</div>
    <div class="col">col</div>
  </div>
  ```
* Use flexbox alignment utilities to vertically and horizontally align columns:

  * Vertical alignment 1:
    ![Vertical alignment 1](https://github.com/erolaliyev/programming-notes/blob/master/Images/Bootstrap-4/vertical-alignment%201.png)
    ```html
    <div class="container">
      <div class="row align-items-start">
        <div class="col">
          One of three columns
        </div>
        <div class="col">
          One of three columns
        </div>
        <div class="col">
          One of three columns
        </div>
      </div>
      <div class="row align-items-center">
        <div class="col">
          One of three columns
        </div>
        <div class="col">
          One of three columns
        </div>
        <div class="col">
          One of three columns
        </div>
      </div>
      <div class="row align-items-end">
        <div class="col">
          One of three columns
        </div>
        <div class="col">
          One of three columns
        </div>
        <div class="col">
          One of three columns
        </div>
      </div>
    </div>
    ```
  * Vertical alignment 2:
    ![Vertical alignment 2](https://github.com/erolaliyev/programming-notes/blob/master/Images/Bootstrap-4/vertical-alignment%202.png)
    ```html
    <div class="container">
      <div class="row">
        <div class="col align-self-start">
          One of three columns
        </div>
        <div class="col align-self-center">
          One of three columns
        </div>
        <div class="col align-self-end">
          One of three columns
        </div>
      </div>
    </div>
    ```
  * Horizontal alignment:
    ![Horizontal alignment]
    ()
    ```html
    <div class="container">
      <div class="row justify-content-start">
        <div class="col-4">
          One of two columns
        </div>
        <div class="col-4">
          One of two columns
        </div>
      </div>
      <div class="row justify-content-center">
        <div class="col-4">
          One of two columns
        </div>
        <div class="col-4">
          One of two columns
        </div>
      </div>
      <div class="row justify-content-end">
        <div class="col-4">
          One of two columns
        </div>
        <div class="col-4">
          One of two columns
        </div>
      </div>
      <div class="row justify-content-around">
        <div class="col-4">
          One of two columns
        </div>
        <div class="col-4">
          One of two columns
        </div>
      </div>
      <div class="row justify-content-between">
        <div class="col-4">
          One of two columns
        </div>
        <div class="col-4">
          One of two columns
        </div>
      </div>
    </div>
