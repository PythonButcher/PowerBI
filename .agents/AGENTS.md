# Power BI Project Rules

This document outlines constraints and behavioral guidelines for working on the Power BI Court Analytics project.

## Verification Constraints
- **UI Path Verification**: Never assume visual styling paths or grid behaviors from general applications (such as Excel or Web) apply to Power BI Desktop.
- **Web Lookup Requirement**: Before recommending click-paths for formatting, sorting, or styling visuals, always perform a web search to verify the options exist in modern Power BI Desktop (specifically from recent releases, 2025/2026).
- **No Spreadsheet Defaults**: Do not assume spreadsheet behaviors like "double-clicking column headers to auto-fit" exist in Power BI. Column sizing must be handled through the Visualizations/Format pane settings (e.g., `Column headers > Options > Auto-size width`) or manual dragging.
- **Conditional Formatting**: Remember that conditional formatting (data bars, background colors, etc.) is configured in the **Format visual** pane under the **Cell elements** card in the modern Power BI UI, not via the fields list/pane dropdown.

## Future Advanced Power BI Roadmap
The user intends to implement advanced Power BI features once the basic layout is settled. Keep these in mind for future design iterations:
- **Visual Toggle/Bookmarks**: Use bookmarks and selection panels to toggle between different visual representations (e.g. switching between a chart and a detailed table view).
- **Advanced Grouping/Slicing**: Implement group bins, hierarchical groupings, or custom grouping columns.
- **Decomposition Trees & Key Influencers**: Utilize AI visuals to dive deep into case timelines, delays, and collections.
- **Advanced Navigation & Slicer Panels**: Build collapsible slicer menus using bookmarks and button visuals for a clean dashboard space.

