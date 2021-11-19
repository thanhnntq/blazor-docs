---
title: Loading Animation
page_title: Grid Loading Animation
description: The Blazor Data Grid by Telerik UI provides a built-in loading animation that appears automatically when the grid detects a long data operation.
slug: components/grid/loading-animation
tags: telerik,blazor,grid,loading-animation,loading,indicator
published: True
position: 15
---

# Loading Animation

The loading animation indicates that the user has initiated a data operation that requires more than 600ms to complete. The indicator appears as a loading sign over the Blazor Data Grid. The loading animation improves the user experience by providing a visual hint that the requested action is still executing and this prevents repeated actions.

The data operations that trigger the loading animation include:

* [Paging]({%slug components/grid/features/paging%})
* [Filtering]({%slug components/grid/filtering%})
* [Sorting]({%slug components/grid/features/sorting%})
* [Grouping]({%slug components/grid/features/grouping%}) 
* [Expanding groups with load-on-demand]({%slug grid-group-lod%})
* [Editing]({%slug components/grid/editing/overview%})
* [Inserting]({%slug components/grid/editing/overview%})
* [Deleting records]({%slug components/grid/editing/overview%})

The grid will not, however, display a loading animation during its initial rendering. It cannot know when or even if data will be provided to it, and having an automatic loading sign appear can either make it show up indefinitely, or it could prevent the user from altering any saved grid state (such as changing filters). If you want a loading animation on the initial load, you can add a [LoaderContainer component]({%slug loadercontainer-overview%}#basic-loadercontainer) with the desired `Visible` logic.

When using the [`OnRead` event]({%slug components/grid/manual-operations%}), the loading sign will display every time its event handler is called, which will include the initial load of data - the grid will raise that request every time.

You can see both scenarios in action in the [Live Demo: Grid Loading Animation](https://demos.telerik.com/blazor-ui/grid/loading-animation).

## See Also

* [Grid Data Binding]({%slug grid-data-binding%})
* [Live Demo: Grid Loading Animation](https://demos.telerik.com/blazor-ui/grid/loading-animation).
