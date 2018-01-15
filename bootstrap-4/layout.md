# Containers

Containers are required when using default grid system. There are two kinds of containers:

* `.container` : fixed-width container, meaning its `max-width` changes at each breakpoint.

* `.container-fluid` : fluid-width, meaning it's spanning the entire width of the viewport all the time.

# Grid system

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
    ![Vertical alignment 1](https://github.com/erolaliyev/programming-notes/blob/master/bootstrap-4/Images/vertical-alignment-1.png)
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
    ![Vertical alignment 2](https://github.com/erolaliyev/programming-notes/blob/master/bootstrap-4/Images/vertical-alignment-2.png)
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
    ![Horizontal alignment](https://github.com/erolaliyev/programming-notes/blob/master/bootstrap-4/Images/horizontal-alignment.png)
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
* Add `.w-100` wherever you want to wrap ypur columns to a new line in the same row.
* Use `.order-` for controlling **visual order** of your content:
  * These classes are responsive, you can set the order by breakpoint such as `.order-1 .order-md-2`.
  * Includes support for 1 through 12.
  * `.order-first` changes the order of one element by applying _order: -1_ which makes that column first in order.
  * Unordered column comes before all `.order-`s but after `.order-first` if there is.
* `offset-{breakpoint}-*` moves columns to the right. They increase the left margin of a column by `*` columns.
* `offset-{breakpoint}-0` resets the previously set offsets.
* To nest content add a new `.row` and set of `.col-{breakpoint}-*` columns within an existing `.col-{breakpoint}-*` column.
