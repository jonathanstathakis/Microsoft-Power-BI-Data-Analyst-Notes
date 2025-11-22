# 04 Design Effective Reports in Power BI

- [URL](https://learn.microsoft.com/en-us/training/paths/power-bi-effective/)

## 01 Scope Report Design Requirements

### 01 Introduction

- design starts with defining clear goals.
- goals should identify:
  - audience
  - type of report
  - UI needs.
  - UX needs.

### 02 Identify the Audience

- 3 types of report consumers:
  - executive
  - analyst
  - information worker.
- executive:
  - responsible for medium or long term plans/decisions.
  - e.g. C-level exec.
- analyst:
  - provide guidance.
  - determine effectiveness of business strategies
  - develop improve processes
  - implement change.
  - e.g. business analyst, data analyst.
- information worker:
  - uses data to make decisions, take action.
  - temporal scope is day-to-day.
  - follow processes.
  - e.g.: inventory manager.

### 03 Determine Report Types

- report design is classified by type.
- 4 report types:
  - dashboard
  - analytical
  - operational
  - educational
- mapping:
  - executives: dashboard reports.
  - analysts: analytical reports.
  - information worker: operational reports
  - general audiences: educational reports.
- dashboard:
  - monitor and interpret key facts ASAP.
  - Visuals:
    - focused
    - self-explanatory
    - clearly labelled.
  - communicates meaning behind the data.
- analytical report:
  - structured space for analysis.
  - help discover answers.
  - include many slicers and filters.
  - contain complex visuals exposing in-depth detail.
  - pages are designed for interactivity.
  - focus on UX.
  - many pathways included:
    - explore
    - share
    - return to start.
  - able to remove layers
  - add context.
  - should allow:
    - drill-down
    - drillthrough
    - tooltips
- operational report:
  - purpose:
    - monitoring of current or real-time data.
    - make decisions from data.
    - acting on those decisions.
  - should include:
    - buttons to navigate report.
    - buttons to perform actions in external systems.
  - serve as hub for actions.
  - should:
    - minimise aanlytical features to stay focused on operation.
- educational report:
  - assumes user unfamiliar with data/context.
  - provide clear narrative detail.
  - used in journalism and by governments.

### 04 Define User Interface Requirements

- form factor: size of the hardware used to view reports and page orientation
- orientation: portrait or landscape.
- large monitors perfect for viewing reports in web browsers.
- form factor influences design.
- mobile devices have smaller form factor.
- phone and tablet display in portrait by default.
- smaller form factor:
  - fewer and less complex visuals
  - larger visuals.
- mobile devices can include augmented or mixed reality.
- methods of adapting a larger form factor for a smaller one include only selecting a subset of visuals.
- input method:
  - computers may have a keyboard and pointing device
  - mobiles interact with content by the following:
    - gestures:
      - tap
      - double tap
      - drag
      - pinch
      - spread
      - press
    - on-screen keyboards
    - voice control
    - barcode
    - QR code reader.
  - augmented or mixed reality relies on hand gestures and body movement.
  - audience input method should influence:
    - number of visuals
    - complexity of visuals
    - spacing
    - use of interactive design elements:
      - tooltips
      - slicers
      - buttons
      - filters
- style and theme:
  - UI design includes style and theme
  - need a consistent and distinctive appearance with a deliberate theme.
  - theme:
    - org. branding: express or complement.
    - should include:
      - brand mark / logo
      - colors:
        - align or complement org. branding.
        - distinct colors to provide strong contrast.
      - text settings:
        - font selection
        - size
        - color
  - centralising resources:
    - images and themes should be stored in a central repo.
    - improves change management.
    - changes made to repository will automatically _cascade_ through reports.
- Accessibility:
  - need to consider accessibility.
  - helps comm. to broadest audience possible.
  - consider:
    - no-to-low vision
    - other physically disabilities.
  - design considerations:
    - form factor
    - input method
    - style
    - theme
  - no to low vision:
    - clear and large sized fonts.
    - well-spaced and large visuals.
    - clear and distinctive contrasting colours.
    - intuitive report navigation parsable by keyboard and screen readers.
  - other:
    - alt-text to visuals
    - set tab order of report elements for keyboard nav.

### 05 Define User Experience Requirements

#### 01 Intro

- UX requirements.
- defining requirements helps report meet need of audience
- focus on UX makes report:
  - easier to use
  - more access.
  - more valuable to dec. making
- should consider:
  - interactive exploration
  - flexible data access
  - support scenario analysis
  - automate delivery
  - encourage collaboration
- interactive exploration:
  - users engage with report
  - discover insights independently.
  - features include:
    - drilling:
      - drill up
      - drill down
      - drill through
    - navigation:
      - within report and to other reports.
    - filtering:
      - fliter and slice
      - visual, page or whole report.
  - makes report more dynamic, access.
  - add drillthrough buttons
  - drillthrough lets people find the level of detail they want.
- flexible data access:
  - empowers users.
  - increases inclusivity and value
  - examples:
    - data export to common formats.
    - natural language questions: Q&A visual.
    - data alerts for key values.
    - link to open webpages.
    - configure actions:
      - open apps.
      - write back data entry values.
      - start workflows.
  - Q&A visual: lets users use natural language to generate content.
- support scenario analysis and customization:
  - allows users to test diff. sits., personalize data view.
  - examples include:
    - what-if-analysis: adjustable parameters.
    - flexible layouts: work across multiple pages, print well.
    - ability to print to a physical printer OR as a PDF.
  - increases adaptability and accessibility
- automate delivery and encourage collab:
  - subscriptions: automatically deliver report on a scheduled basis.
  - in-report conversations:
    - comments
    - feedback
    - user engagement in conv. about report.

### 06 Explore Designs in a Power BI Report

- done.

## 02 Design Power BI Reports

### 02.01 Introduction

### 02.01.01 Introduction

- reports can be built on PBI Desktop or PBI Service.
- mobile platform is only for consumption.

#### 02.01.02 Report Structure

- report object hierarchy:
  - one _semantic model_
  - one or more _pages_.
  - each page has one or more _report object_.
- report objects:
  - visuals
  - elements:
    - text boxes
    - buttons
    - shapes
    - images
- report pages:

#### 03.01.03 Report Pages

- Page operations:
  - add
  - rename
  - reorder
  - hide
  - duplicate
  - delete
- similar in behavior to Excel worksheets.
- sometimes better to generate a single page with filters/slicers than pages for individual datasets.
- Consumers navigate between pages via a _page tab_ (PBI desktop) or _Pages_ pane (Fabric).
- how many pages depends on report requirements.
- report design should follow logical flow both between pages and on a page.
- standard design has high level summations on first page then following pages justify or drill.
- reasons for separating pages into multiple reports:
- different audiences
- need to secure, share, or distribute in diff. ways.
- pages can be hidden
- reasons for hiding page:
- work in progress
- control acess
- page navigation can be provided through buttons or drilling through from a viz.
- pages can be designed as tooltips to be revealed on hover over a viz.
- page-level settings can be configured in _Format_ options.
- page level settings include: page info, page size, page background.

### 02 Design the Analytical Report Layout

- report design should help users comprehend its content to effectively communicate its meaning.
- report design is a blend of science and art.
- Report objects include:
- visuals: results of queries.
- decorations: images, background shapes, text.
- design begins with determining number, sequence and purpose of pages.
- clearly separate topics, subjects and avoid having opposing objectives on same page.
- Design each page layout with report objects relevant to requirement.
- placement:
- report objects should be placed in order.
- most important top left
- move from left to right then top to bottom.
- if audience reads right to left or other, accommodate.
- arrange objects so vertical and horizontal edges align
- have related report objects in logical groupings.
- ordered report layout creates connection, avoids clutter.
- rule of thirds.
- balance:
- stability and structure of design.
- how weight of objects is spread.
- variety of size of objects.
- types:
  - symmetrical:
    - equal weight on both sides of page.
  - asymmetrical:
    - contrast.
    - can use _golden ratio_ to achieve asymm. balance.
- Proximity:
- nearness of report objects.
- groups can be delineated by space.
- Contrast:
- combine two opposing objects:
  - tools of contrast:
    - colors
    - fonts
    - font properties
    - lines
- emphasize important objects.
- Use to direct consumers throughout structure.
- Repetition:
- create association and consistency

### 03 Design Visually Appealing Reports

- report should be visually appealing.
- consumers should be able to quickly find + understand answers.
- should be user friendly
- well-designed report may fit more content
- space:
  - reduce clutter
  - increase readability.
  - includes margins and spacing between report objects.
- margins:
  - the border area around each page.
  - frames the report objects.
  - no method to set pre-defined margin
  - user must place objects to obey an implicit margin.
  - left and right margin should be equal
  - top and bottom margin can differ.
  - space in top or bottom margin can include:
    - branding
    - titles
    - slicers
    - other info separate from visuals.
- object spacing:
  - need sufficient around and within report objects.
  - visual headers may overlap poorly placed objects.
  - sections of related objects can be separated by using different space depth.
  - need a evenly spaced and balanced report.
- size:
  - size describes page size and visual size.
  - page size:
    - can use pre-defined or custom dimensions.
    - if dims larger than consumer screen size need to use scrollbars.
    - larger page take more time to render
    - may not render top-to-bottom.
  - visual size:
    - more important == larger size.
    - visuals of equal importance should be equal sized.
    - responsive:
      - many visuals are size responsive.
      - larger visuals show more detail.
    - consumer can use focus mode can be used to enlarge a visual
- alignment:
  - visuals need to be properly aligned
  - edges of visuals should be aligned
  - spacings between visuals need to be consistent.
  - formatting alignment should be consistent i.e. titles and legends.
  - sections from alignment:
    - implicit:
      - visuals are grouped by proximity.
    - explicit:
      - use colored shapes or overlays.
  - Format/alignment commands help to align visuals.
- Colour:
  - use sparingly, meaninfully.
  - overuse can be distracting
  - use softer colour as base
  - try to align with corporate colours.
  - softer colours ensure focus is on data.
  - Reserve use of bolder colours to highlight exceptions.
  - colour contrast:
    - need well contrasting.
    - imp. for access. i.e. low vision.
- consistency:
  - consistency is important when defining:
    - spacing
    - margin
    - size
    - alignment
    - object formatting, including:
      - font
      - font size
      - font weight
      - colours
  - lack of consistency makes report appear unbalanced.
  - report theme:
    - quickest way to achieve consistency
    - applies format settings to whole report.
    - there are built-in themes in _theme gallery_
    - start with built-in then customize.
    - create a new theme from scratch.
    - themes are overridden if a value is explicitly set (don't).
    - export themes to JSON to apply to other reports.
    - _powerbi.tips_ can be used to gen. a theme.

### 04 Use Report Objects

- common properties of report objects are:
  - location
  - size
  - alt text
  - title
  - effects:
    - background
    - border
    - shadow
- properties are set in _Format_
- visuals:
  - 30 core visuals
  - found under _Visualizations_
  - custom visuals:
    - found in Microsoft AppSource
    - also can upload as PBIVIZ file.
  - steps to adding a viz:
    - select viz type
    - position and size
    - define analytic query:
      - map semantic model fields to visual _wells_
      - add visual-level filters
      - rename field mappings
      - modify summarization behavior
    - modify sort
    - format options
    - use Analytics to overlay supporting data.
- Elements:
  - dont use semantic model data.
  - include:
    - text box
    - buttons
    - shapes
    - image
  - text box:
    - holds rich text
    - can have hyperlinks.
    - embedded dynamic values:
      - can embed text values from semantic model that can change depending on filter.
  - buttons:
    - interact with report
    - actions:
      - return to prev. page
      - specific page
      - drill through to a page
      - select bookmark
      - open Q&A
      - open URL.
  - shapes:
    - decoration or interactive like button.
    - can include text
  - Image:
    - upload
    - formats include:
      - BMP
      - JPEG
      - GIF
      - TIFF
      - PNG
    - can act as button.

### 05 Select Report Visuals

- primary goal of data viz is to comm. to consumers clearly and effectively.
- visual type and layout is important.
- categorical visuals:
  - bar chart
  - column chart
  - dont use color as qualitative dimension if many individuals.
  - sort categorical charts by value.
  - if there is a logical order to the categories, then sort by them.
- Time series visuals:
  - use line or column chart for time series.
  - X-axis tor time
  - sort x-axis from earliest to latest left to right.
  - Analytics can be used to add forecasts.
  - best used when there is a consistent flow of data.
  - missing data:
    - line charts interpolate missing data.
    - if too much, use column chart instead to avoid misinterp.
  - other time series visuals:
    - stacked column
    - area
    - line and stacked column
    - ribbon: shows rank changes as well.
- proportional visuals:
  - show how data is distributed across a dimension.
  - column, bar charts.
  - best used with absolute values.
  - types of visual:
    - 100% stacked column chart
    - funnel chart
    - treemap
    - pie chart
    - doughnut chart.
- Numeric visuals:
  - card visuals.
  - high level callouts
  - powerful in dashboard and analytical reports.
  - possible to use multi-row card visuals.
- Grid visuals:
  - tables and matrices.
  - tables:
    - fixed number of columns
    - columns express grouped or summarized data.
  - matrices:
    - group on columns and rows.
    - best for hierarchical navigation:
      - can drill down on columns or rows.
  - conditional formatting is possible:
    - colors
    - font colours
    - icons
  - Format options allow fine grained control of these visuals.
- Performance visuals:
  - colours or icons display status.
  - KPI visual:
    - need:
      - unit of measurement to track
      - goal for the measurement to display progress
      - time series by which the effort progresses along.
  - performance visuals:
    - Gauge
    - Table with conditional formatting
    - Matrix with conditional formatting
- Geospatial visuals:
  - maps
  - either Map or Filled map visual
  - use depends on how the data displays, interpretation.
  - take a lot of space, use with care.
- Visual layout:
  - choosing the right visual also depends on available space in layout
  - visuals which rely on vertical space to convey info should not be used in landscape layout, vice versa.

### 06 Apply Filters and Slicers to Reports

- intro:
  - many ways to filter a report.
  - levels of filtering:
    - semantic model + row-level security.
    - report
    - page
    - visual
    - measure
  - the structure of the report itself is filtered at the report, page and visual level.
- semantic model:
  - semantic model can enforce row-level security which restricts data access based on user privileges.
  - its not good if row-level security causes users not to see no data i.e. BLANK
- Report Structure:
  - report structure is hierarchical:
    - top level report
    - second level pages
    - third level objects
  - filters pane can apply filters at any level of the hierarchy.
- Measure:
  - `CALCULATE` and `CALCULATETABLE` can add, remove or modify filters and relationships
  - time intelligence functions can override pre-existing filters
  - _report-level measures_ are, as per the name, defined at the report level.
- Apply Filters to the Report Structure:
  - Filters should be applied to the report during design time.
  - Filters pane has 3 level options:
    - all pages:
      - report-level, global filters.
    - this page:
      - page-level. report level cascades to page-level.
    - this visual:
      - visual level filters. all pages and this page filters cascade down.
    - filtering visuals using measures:
      - a visual can be filtered from the value of a measure.
      - measure-based filters are used to eliminate groups.
  - filters apply to a single field
  - filter types:
    - Basic
    - Advanced
    - Top N
    - Relative date / Relative time
  - filters can be locked to stop consumers from modifying them.
  - filters can be hidden.
  - filters should be hidden when the user doesnt need to know about it.
  - can also hide entire Filters pane.
- Apply filters with slicers:
  - Slicers are visuals that filter other visuals.
  - slicers can be modified to moderate how they affect other visuals.
  - sync slicers can filter visuals on other pages.
  - slicers are configured in the following ways:
    - one field
    - multiple fields from the same table
    - hierarchy
  - slicer respects data type.
  - data types include:
    - text
    - numeric
    - date
  - text fields generate a list slicer
  - numeric fields generate numeric range "between" filter
  - date fields produce a data range "between" filter.
  - slicers can be configured as dropdown lists.
  - slicer style can be applied via Format your visual/slicer settings/visual/options/style
  - date field slicers can filter by relative date or time
  - slicers can be restricted to _Single select_ to restrict selection options.

### 07 Understand Filtering Techniques and Considerations

### 08 Case Study - Configure Report Filters Based on Feedback

### 09 Exercise - Design Power BI Reports

## 03 Enhance Power BI Report Designs for the User Experience

### 01 Introduction

### 02 Design reports to show details

### 03 Design reports to highlight values

### 04 Design reports that behave like apps

### 05 Work with bookmarks

### 06 Design reports for navigation

### 07 Work with visual headers

### 08 Design reports with built-in assistance

### 09 Tune report performance

### 10 Optimize reports for mobile use

### 11 Exercise - Enhance Power BI reports

## 04 Perform Analytics in Power BI

### 01 Introduction to analytics

### 02 Explore statistical summary

### 03 Identify outliers with Power BI visuals

### 04 Group and bin data for analysis

### 05 Apply clustering techniques

### 06 Conduct time series analysis

### 07 Use the Analyze feature

### 08 Create what-if parameters

### 09 Use specialized visuals

### 10 Exercise - Perform analytics in Power BI
