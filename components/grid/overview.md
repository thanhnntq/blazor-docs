---
title: Overview
page_title: Grid Overview
description: Overview of the Grid for Blazor.
slug: components/grid/overview
tags: telerik,blazor,grid,datagrid,overview
published: True
position: 0
---

# Blazor Grid Component Overview

This article provides a quick introduction so you can get your first <a href="https://www.telerik.com/blazor-ui/grid" target="_blank">Blazor Data Grid component</a> up and running in a few seconds, a video tutorial, and a list of the key features it provides.

The Telerik Blazor Data Grid provides a comprehensive set of ready-to-use features covering everything from paging, sorting, filtering, editing, and grouping to row virtualization, optimized data reading, keyboard navigation and accessibility support.

The Telerik Blazor Grid is built on native Blazor from the ground up, by a company with a long history of making enterprise-ready Grids. This results in a Data Grid that delivers lightning fast performance and is highly customizable.

## Creating Data Grid

1. Use the `TelerikGrid` tag to add the component to a view, for example, `~/Pages/Index.razor`.

1. Set the Grid's `Data` attribute to the variable that holds your data collection.

1. Enable some of the Data Grid features, like paging, sorting, and grouping.
   
1. Under the `GridColumns` tag, set the desired [`GridColumn`]({%slug components/grid/columns/bound%}) instances. Their `Field` property points to the name of the model field that you want to display in the column.

>caption Get started with the Blazor Data Grid by providing it with a data collection and enabling its key features

````CSHTML
General Grid with its most common features

<TelerikGrid Data="@MyData" Height="400px"
             Pageable="true" Sortable="true" Groupable="true"
    <GridColumns>
        <GridColumn Field="@(nameof(SampleData.Id))" Width="120px" />
        <GridColumn Field="@(nameof(SampleData.Name))" Title="Employee Name" Groupable="false" />
        <GridColumn Field="@(nameof(SampleData.Team))" Title="Team" />
        <GridColumn Field="@(nameof(SampleData.HireDate))" Title="Hire Date" />
    </GridColumns>
</TelerikGrid>

@code {
    public IEnumerable<SampleData> MyData = Enumerable.Range(1, 30).Select(x => new SampleData
    {
        Id = x,
        Name = "name " + x,
        Team = "team " + x % 5,
        HireDate = DateTime.Now.AddDays(-x).Date
    });

    public class SampleData
    {
        public int Id { get; set; }
        public string Name { get; set; }
        public string Team { get; set; }
        public DateTime HireDate { get; set; }
    }
}
````

To see the result from the code snippet above, select the **PREVIEW** tab in the code snippet toolbar.

### Blazor Data Grid Video Tutorial

If you prefer video instructions, watch the Blazor Data Grid video tutorial. It covers to following main topics:

* What is the Blazor Data Grid by Telerik UI.

* How to add:

   * The Telerik UI root component.
   * The Blazor Data Grid to a view.
   * Data Grid columns.

* How to enable additional features.

>caption Video tutorial - Get started with Telerik Data Grid for Blazor

<iframe width="560" height="315" src="https://www.youtube.com/embed/NW2hHtmM2Gk" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Data Binding

To show data in a Grid, define [GridColumn]({%slug components/grid/columns/bound%}) instances or allow the Grid to [generate columns automatically]({%slug grid-columns-automatically-generated%}). Declared columns take a model `Field` and expose settings for [templates]({%slug components/grid/features/templates%}), [grouping](#grouping) and [reordering]({%slug components/grid/columns/reorder%}). To [edit](#editing) data or invoke custom logic, define a [CommandColumn]({%slug components/grid/columns/command%}). [Read more about the Blazor Grid Data Binding...]({%slug grid-data-binding%})

## Loading Animation

The Blazor Data Grid provides a [loading animation]({%slug components/grid/loading-animation%}) that improves the user experience by indicating an ongoing data operation, for example, paging, grouping and others.

## Editing

The Blazor Data Grid can perform CRUD operations on its current data collection and exposes events that let you control the operations and transfer changes to the actual data source. Depending on your requirements, you can choose between the [`Incell`]({%slug components/grid/editing/incell%}), [`Inline`]({%slug components/grid/editing/inline%}), and [`Popup`]({%slug components/grid/editing/popup%}) edit modes. [Read more about the Blazor Data Grid CRUD operations...]({%slug components/grid/editing/overview%})

## Paging

The Blazor Data Grid supports paging of the data out-of-the box. This allows you to split the content into pages for better user experience. [Read more about the Blazor Data Grid paging...]({%slug components/grid/features/paging%})

An alternative to standard paging is to configure [virtual scrolling]({%slug components/grid/virtual-scrolling%}) and eliminate the pager when displaying large volumes of data. 

## Sorting, Filtering, and Grouping

To help the user in finding the needed information, the Data Grid can automatically perform data operations like sorting, filtering, and Grouping. Read more about: [Blazor Data Grid sorting]({%slug components/grid/features/sorting%}), [Blazor Data Grid filtering]({%slug components/grid/filtering%}), and [Blazor Data Grid grouping]({%slug components/grid/features/grouping%}).

## Scrolling

You can choose between the two scroll modes that the Blazor Data Grid offers:

* `Scrollable` (the default setting)&mdash;The scrollbars are controlled by the grid's `Width` and `Height` parameters and the data shown in it. If the rendered rows are taller than the height, there will be a vertical scrollbar. If the sum of the column widths is larger than the width, there will be a horizontal scrollbar. [Read more about the Blazor Data Grid scrollable mode]({%slug grid-columns-width%}).

* `Virtual`&mdash;Virtual scrolling is an alternative to paging. [Read more about the Blazor Data Grid virtual scrolling]({%slug components/grid/virtual-scrolling%}).

The Grid offers also a Virtual horizontal scrolling. You can read more about this feature in the [Column Virtualization]({%slug grid-columns-virtual%}) article.

## Column Features

The columns of the Grid are one of its main building blocks and offer a wide range of built-in functionalities.

* [Autogenerated Columns]({%slug grid-columns-automatically-generated%})&mdash;You can autogenerate Data Grid columns for each public property in its model.

* [Frozen Columns]({%slug grid-columns-frozen%})&mdash;The Data Grid lets you lock one or more columns.

* [Column Menu]({%slug grid-column-menu%})&mdash;The Data Grid allows you to setup a menu for it's columns. It enables you to perform high-level customization like [sorting]({%slug components/grid/features/sorting%}), [filtering]({%slug components/grid/filtering%}), [showing or hiding]({%slug grid-columns-visible%}) columns and [freezing or unfreezing]({%slug grid-columns-frozen%}) them.

* [Display Format]({%slug grid-columns-displayformat%})&mdash;The Data Grid columns can render their values by applying styles that depend on the current culture. This enables you to create applications that can be used all over the world.

* [Column Resizing]({%slug components/grid/columns/resize%}) and [Reordering]({%slug components/grid/columns/reorder%})&mdash;To easily focus on the important data, the end users can re-arrange the columns in the table by dragging the column headers. They can also resize the columns by taking advantage of the two resizing mechanisms provided by the Blazor Data Grid.

* [UI Virtualization]({%slug grid-columns-virtual%})&mdash;The Blazor Data Grid supports virtual scrolling for the columns and allows you to render the content only for the currently visible viewport.

* [Column Visibility]({%slug grid-columns-visible%})&mdash;To programmatically hide some of the Data Grid columns when certain conditions occur, you can use the `Visible` parameter.

* [Multi-Column Headers]({%slug grid-columns-multiple-column-headers%})&mdash;The multi-column headers allow you to group several related columns under a common column header.

* [Events]({%slug grid-column-events%})&mdash;The Blazor Data Grid columns generate a variety of events that you can handle and further customize the behavior of the Data Grid.

## More Blazor Data Grid Features

* [Selection]({%slug components/grid/selection/overview%})&mdash;The Data Grid offers single or multiple selection modes.

* [State]({%slug grid-state%})&mdash;The Data Grid provides its current state (such as filtering, sorting, grouping, selection, and so on) through methods and events so you can store the Grid layout for your end users&mdash;this lets them continue where they left off.

* [Toolbar]({%slug components/grid/features/toolbar%})&mdash;You can define user actions in a dedicated toolbar.

* [Hierarchy]({%slug components/grid/features/hierarchy%})&mdash;You can visualize the parent-child relations between data records.

* [Row Drag and Drop]({%slug grid-drag-drop-overview%})&mdash;You can move a single row or multiple rows between different parents in the same Data Grid or between different Data Grid instances.

## Styling the Blazor Data Grid

The Blazor Data Grid allows you to style it by using the built-in [Data Grid Templates functionality]({%slug components/grid/features/templates%}) and customize almost every aspect of the table, for example, the columns, rows, column headers and footers, and many more. You can also use the `Class` property to configure complex CSS rules, [apply conditional formatting]({%slug components/grid/styling%}#conditional-formatting), and [take advantage of the elastic design]({%slug components/grid/styling%}#elastic-design).

## Storing a Blazor Data Grid Reference

The Data Grid is a generic component, and to store a reference, you must use the model type that you pass to its `Data` when declaring the variable.

>caption Store a reference to a Telerik Grid

````CSHTML
@using Telerik.Blazor.Components

<TelerikGrid Data="@MyData" @ref="theGridReference">
	<GridColumns>
		<GridColumn Field="@(nameof(SampleData.ID))">
		</GridColumn>
		<GridColumn Field="@(nameof(SampleData.Name))" Title="Employee Name">
		</GridColumn>
	</GridColumns>
</TelerikGrid>

@code {
	Telerik.Blazor.Components.TelerikGrid<SampleData> theGridReference;

	public IEnumerable<SampleData> MyData = Enumerable.Range(1, 50).Select(x => new SampleData
	{
		ID = x,
		Name = "name " + x
	});

	//in a real case, keep the models in dedicated locations, this is just an easy to copy and see example
	public class SampleData
	{
		public int ID { get; set; }
		public string Name { get; set; }
	}
}
````

## Next Steps

* [Showing data in the Blazor Data Grid]({%slug components/grid/columns/bound%})

* [Implementing CRUD operations in the Blazor Data Grid]({%slug components/grid/editing/overview%}#notes)

## See Also

  * [Live Demos: Grid](https://demos.telerik.com/blazor-ui/grid/index)
  * [API Reference](https://docs.telerik.com/blazor-ui/api/Telerik.Blazor.Components.TelerikGrid-1)
