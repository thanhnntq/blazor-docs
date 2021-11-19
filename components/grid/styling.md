---
title: Styling
page_title: Grid Styling
description: The Blazor Data Grid by Telerik UI allows you to style it by using templates, conditional formatting, complex CSS rules, and more.
slug: components/grid/styling
tags: telerik,blazor,grid,styling
published: True
position: 59
---

# Blazor Data Grid Styling

The Blazor Data Grid enables you to style it by using various approaches, for example, you can:

* Define your own content for column cells or even the entire row through [Templates]({%slug components/grid/features/templates%}).

* Set the [`Height` of the grid]({%slug common-features/dimensions%}),

* Use the `Class` to provide more complex CSS rules (like ones that will be inherited in a template).

Below, you can see examples on how to [format the cells and the rows of the Grid based on certain conditions](#conditional-formatting) and how to take advantage of the [elastic design](#elastic-design).

## Conditional Formatting

You can format the cells and rows of the Grid based on certain condition in the logic of the application. 

To do so, use the [OnCellRender]({%slug grid-column-events%}#oncellrender) and [OnRowRender]({%slug grid-events%}#onrowrender) events and set the desired CSS class through the event handlers arguments.

>caption Use the OnCellRender and OnRowRender events to customize the formatting of the Grid rows and cells based on conditions.

@[template](/_contentTemplates/grid/common-link.md#conditional-style-row-and-cell-render)

>caption The result from the code snippet above

![conditional formatting of the grid](images/grid-styling-conditional-formatting-example.png)

## Elastic Design

You can benefit from the elastic design the components expose to change their font size so they change dimensions.

>caption Change font size and dimensions of a grid

````CSHTML
The grid offers elastic design capabilities

<style>
    div.smallerFont,
    div.smallerFont .k-filtercell * {
        font-size: 10px;
    }

        div.smallerFont .k-dropdown.k-header.k-dropdown-operator {
            width: calc(8px + 2em) !important;
        }

        /* One example for altering content inside the cells - the inputs in InCell editing mode here 
        You can create similar rules as needed by inspecting the rendered HTML. This blog can help you do that
        https://www.telerik.com/blogs/improve-your-debugging-skills-with-chrome-devtools
        */
        div.smallerFont .k-grid-edit-cell input{
            font-size: 10px;
        }
</style>

<TelerikGrid Data="@MyData" Class="smallerFont"
             Pageable="true" FilterMode="Telerik.Blazor.GridFilterMode.FilterRow"
             Sortable="true" Height="200px">
    <GridColumns>
        <GridColumn Field="@(nameof(SampleData.ID))">
        </GridColumn>
        <GridColumn Field="@(nameof(SampleData.Name))" Title="Employee Name">
        </GridColumn>
        <GridColumn Field="@(nameof(SampleData.HireDate))" Title="Hire Date">
        </GridColumn>
    </GridColumns>
</TelerikGrid>

original:

<TelerikGrid Data="@MyData"
             Pageable="true" FilterMode="Telerik.Blazor.GridFilterMode.FilterRow"
             Sortable="true" Height="200px">
    <GridColumns>
        <GridColumn Field="@(nameof(SampleData.ID))">
        </GridColumn>
        <GridColumn Field="@(nameof(SampleData.Name))" Title="Employee Name">
        </GridColumn>
        <GridColumn Field="@(nameof(SampleData.HireDate))" Title="Hire Date">
        </GridColumn>
    </GridColumns>
</TelerikGrid>

@code {
    //in a real case, keep the models in dedicated locations, this is just an easy to copy and see example
    public class SampleData
    {
        public int ID { get; set; }
        public string Name { get; set; }
        public DateTime HireDate { get; set; }
    }

    public IEnumerable<SampleData> MyData = Enumerable.Range(1, 50).Select(x => new SampleData
    {
        ID = x,
        Name = "name " + x,
        HireDate = DateTime.Now.AddDays(-x)
    });
}
````

>caption The result from the reduced font size is a reduction in the overall size of the grid elements

![Blazor Grid Component Reduced Font Size Example](images/grid-reduced-font-size.png)

## See Also

* [Grid Templates]({%slug components/grid/features/templates%})
* [Grid Toolbar]({%slug components/grid/features/toolbar%})