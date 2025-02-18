---
title: Visio Services in SharePoint
description: Visio Services in Microsoft SharePoint enables you to load, display, and interact programmatically with Visio .vsdx, .vsdm files and Visio Web Drawings (.vdw) on Microsoft SharePoint and Microsoft SharePoint Online.
ms.date: 12/14/2020
ms.prod: sharepoint
ms.assetid: ed8c5d12-e17d-4ceb-b195-601c26824370
ms.localizationpriority: medium
---
# Visio Services in SharePoint

Visio Services in Microsoft SharePoint enables you to load, display, and interact programmatically with Visio .vsdx, .vsdm files and Visio Web Drawings (.vdw) on Microsoft SharePoint and Microsoft SharePoint Online.

## What's new in Visio Services in SharePoint

Visio Services in Microsoft SharePoint and in Microsoft SharePoint Online includes several new features, including support for the new Microsoft Visio 2013 file format, support for Microsoft Business Connectivity Services (BCS) data sources, and programmatic access to comments.

### New file format

**Applies to**: Visio Services in SharePoint Server & SharePoint Online.

Visio 2013 introduces a new file format (.vsdx), based on the Open Packaging Conventions (OPC) standard (ISO 29500, Part 2) and the XML elements from the previous Visio XML file format (.vdx). It is a zipped, XML-based file format similar to the file formats used in other applications.

With the new file format, you can save a Visio 2013 drawing directly to a SharePoint Server or SharePoint Online library, without having to publish the file as a Visio Web Drawing (.vdw). Even so, Visio Services can still read and display Visio Web Drawing files.

Visio Services retains the ability to display the Visio Web Drawing (.vdw) format in the browser. It now also renders the new Visio drawing (.vsdx) and Visio macro-enabled drawing (.vsdm) formats.

The Visio ServicesECMAScript (JavaScript, JScript) object model contains a new API to support the new file format: the  [Vwa.VwaControl.getDiagramFileType Method](https://msdn.microsoft.com/library/fd8ca95f-a3be-4000-bce8-3aaf1f48148c%28Office.15%29.aspx). The methods returns a value from the  [Vwa.DiagramFileType Enumeration](https://msdn.microsoft.com/library/dd2f8a5d-a54b-44bd-a458-02efdcba0201%28Office.15%29.aspx) that indicates whether the file displayed in the Visio Web Access web part is a Visio drawing (.vsdx) or a Visio Web Drawing (.vdw).

For more information about the new file format in Visio 2013, see  [Introduction to the Visio file format (.vsdx)](https://msdn.microsoft.com/library/69736f40-8f67-46c2-abf6-82dffecb2274%28Office.15%29.aspx).

**Note**: The new Visio files (.vsdx and .vsdm) are only displayed in raster format on Visio Services. Visio Web Drawings (.vdw) can still be displayed using Silverlight.

### Support for Business Connectivity Services (BCS) data

**Applies to**: Visio Services in SharePoint Server & SharePoint Online.

Visio 2013 diagrams can now be connected to external lists created using Microsoft Business Connectivity Services (BCS) on SharePoint servers and in SharePoint Online. Visio Services supports the ability to refresh the Visio diagrams as the data updates.

**Note**: Visio Services does not support SQL, SQL Azure, OLEDC, ODBC, and custom data providers as data sources in SharePoint Online.           |

### Commenting

**Applies to**: Visio Services in SharePoint Server & SharePoint Online.

Visio 2013 includes a new commenting framework. Comments can now be associated with a particular shape or page. Visio Services includes JavaScript APIs to retrieve the comments from a diagram.

For more information about the commenting APIs in the Visio ServicesJavaScript object model, see the topics  [VwaPage.getPageComments Method](https://msdn.microsoft.com/library/d1e7740c-e0fa-4823-b2b6-14551bb84c36%28Office.15%29.aspx) and [VwaShape.getComments Method](https://msdn.microsoft.com/library/fcdec9c2-a503-4315-b048-033cd5ac09dd%28Office.15%29.aspx).

### Expanded recalculation

**Applies to**: Visio Services in SharePoint Server & SharePoint Online.

Visio Services can now recalculate formulas in the ShapeSheet. In addition to refreshing Data Graphics, Visio Services can refresh all shapes with data and visuals that depend upon data. Most ShapeSheet functions are supported for recalculation.

### Improved error handling

**Applies to**: Visio Services in SharePoint Server & SharePoint Online.

When a data refresh error occurs in a Visio drawing displayed in Visio Services, the display now falls back to a static image of the diagram. Visio Services also provides more actionable information in error messages.

### Secure Store Authentication

**Applies to**: Visio Services in SharePoint Server & SharePoint Online.

Previously, Authentication Settings for external data sources (a SQL database, for example) could only be configured through a utility in Microsoft Excel. With Visio 2013, users can now configure their data connected diagrams directly from the Visio client, which allows data sources to be refreshed in Visio Services.

## Visio Services JavaScript Object Model

**Applies to**: Visio Services in SharePoint Server & SharePoint Online.

The [Vwa namespace](https://msdn.microsoft.com/library/b67939fa-d3db-41ff-8864-eabd318ba7c4%28Office.15%29.aspx) in the JavaScript object model in Visio Services gives you programmatic access to Visio drawings displayed in the Visio Web Access web part. Using the JavaScript object model, you can access data about diagrams, pages, and shapes; shape hyperlinks; and shape bounding box properties. With this access, you can create mashups that highlight shapes, place overlays on the diagram, respond to diagram and mouse events, and change the panning and zooming properties of the viewport.

For information about adding a Visio Web Access web part to a SharePoint page and programming that page by using the JavaScript APIs in Visio 2013, see [Customizing Visio Web Drawings in the Visio Web Access web part](https://msdn.microsoft.com/library/ff394649.aspx).

## Visio Services Class Library

**Applies to**: Visio Services in SharePoint Server.

You can use the Visio Services class library, in the  [Microsoft.Office.Visio.Server](https://msdn.microsoft.com/library/Microsoft.Office.Visio.Server.aspx) namespace, to build custom Visio Services data providers. These data providers permit you to programmatically refresh data derived from custom data sources in Visio 2013 diagrams hosted on a SharePoint site.

For more information about creating a custom data provider and to work through a complete end-to-end solution, see  [Creating a Custom Data Provider with Visio Services](https://msdn.microsoft.com/library/ff394595.aspx).

## See also

- [Microsoft.Office.Visio.Server](https://msdn.microsoft.com/library/Microsoft.Office.Visio.Server.aspx)
- [Vwa namespace](https://msdn.microsoft.com/library/b67939fa-d3db-41ff-8864-eabd318ba7c4%28Office.15%29.aspx)
- [Creating a Custom Data Provider with Visio Services](https://msdn.microsoft.com/library/ff394595.aspx)
- [Customizing Visio Web Drawings in the Visio Web Access web part](https://msdn.microsoft.com/library/ff394649.aspx)
- [New in Visio for developers](https://msdn.microsoft.com/library/7e3fb858-0ab8-bd2e-217c-c85b10d79785%28Office.15%29.aspx)
- For a list of new features in vis15short for end users, see [What's new in Visio](https://office.com/redir/HA102749364.aspx).
