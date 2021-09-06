## Data Bound Controls

The standard ASP.NET data presentation controls are:

- DataList
- DetailsView
- FormView
- GridView
- ListView
- Repeater

## Repeater Control

The Repeater control supports the following features:

- List format
- No default output
- More control and complexity
- Item as row
- Paging, Sorting and Grouping requires custom code writing
- only Web control that allows you to split markup tags across the templates
- no built-in selection capabilities
- no built-in support for edit, insert and delete capabilities
- no built-in support for paging, sorting and grouping capabilities
- no built-in layout or styles, need to declare all layout, formatting and style tags explicitly within the control's templates
- Strictly emits the markup specified in its templates, nothing more and nothing less.

## DataList Control

The DataList control supports the following features:



- Support for binding data source controls such as SqlDataSource, LinqDataSource and ObjectDataSource
- Directional rendering
- Good for columns
- Item as cell
- Updatable
- Control over Alternate item
- Paging function needs handwriting.

## GridView Control

The GridView control supports the following features:

- Improved data source binding capabilities
- Tabular rendering – displays data as a table
- Item as row
- Built-in sorting capability
- Built-in select, edit and delete capabilities
- Built-in paging capability
- Built-in row selection capability
- Multiple key fields
- Programmatic access to the GridView object model to dynamically set properties, handle events and so on
- Richer design-time capabilities
- Control over Alternate item, Header, Footer, Colors, font, borders, and so on.
- Slow performance as compared to Repeater and DataList control

## ListView Control

The ListView control supports the following features:



- Binding to data source controls Customizable appearance through user-defined templates and styles.
- Built-in sorting and grouping capabilities
- Built-in insert, edit and delete capabilities
- Support for paging capabilities using a DataPager control.
- Built-in item selection capabilities
- Multiple key fields
- Programmatic access to the ListView object model to dynamically set properties, handle events and so on
- Fast performance as compared to GridView

## DetailsView control

The DetailsView control supports the following features:



- Tabular rendering
- Supports column layout, by default two columns at a time
- Optional support for paging and navigation.
- Built-in support for data grouping
- Built-in support for edit, insert and delete capabilities

## FormView control

The FormView control supports the following features:

- Template driven
- Supports column layout
- Built-in support for paging and grouping
- Built-in support for insert, edit and delete capabilities

