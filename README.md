##ASP.NET PDF Viewer by GroupDocs

This C# sample demonstrates key features and capabilities of an ASP.NET PDF viewer built based on the [GroupDocs.Viewer for .NET library](https://groupdocs.com/dot-net/document-viewer-library).
___

###System Requirements

* NET Framework 4.0+
* Web-server: IIS, IIS Express or ASP.NET Development Server (Cassini)
* ASP.NET Web Forms or ASP.NET MVC v. 3+
* Internet Explorer 8+, Mozilla Firefox, Chrome, Opera, Safari 5+ and other similar web-browsers on the client side.

___

###Quick Start Guide

1. Download the sample project.

2. Open it in Microsoft Visual Studio 2012 or higher. The GroupDocs.Viewer for .NET library itself is located in the `GroupDocsViewerWebFormsSample\libs` folder.

3. Compile and run the project. You will see a start page - `Default.aspx` - with a sample PDF documents in your browser.     The project has a kind of repository (the `FileRepository` class). It browses an `App_Data` folder and returns a list of files located in the folder. The list is then displayed on the main page (`Default.aspx`). We’ve added a sample PDF document to the `App_Data` folder, but you can add your own files there - they will appear on the main page after refreshing it. Along with PDF files, the viewer supports over [50 other document formats](https://groupdocs.com/dot-net/document-viewer-library/features#supportForAllCommonDocumentFormats).

4. In the list of available documents (on the `Default.aspx`  page), there are options to view a document either in the image-based or in the HTML-based mode.     In the image-based mode, the viewer extracts texts form source documents, rasterizes backgrounds and then renders extracted texts over the rasterized backgrounds in a web-browser. In the HTML-based mode, the viewer converts source documents to a combination of pure HTML markup, CSS and SVG/PNG images, and then streams these to client web-browsers.

5. When clicking the `Open` link, a new page is opened with the viewer’s GUI and the document inside. 

***

###In-depth Details

GroupDocs.Viewer sends asynchronous requests to stream documents from the server. In the `web.config` file you'll find all the necessary HTTP-handlers. When using ASP.NET MVC, there is no need to specify all these HTTP-handlers. Instead you can simply invoke the `Groupdocs.Web.UI.Viewer.InitRoutes()` method.

A root storage path is specified in the Application_Start method within the `Global.asax` file. This is absolutely necessary for GroupDocs.Viewer to work properly. Here you can also set a log file path and specify a license file if you have one. Without the license GroupDocs.Viewer operates in an evaluation mode. To get a free 30-day license, please contact GroupDocs support.

The `Default.aspx` page, as described before, displays a list of all documents available in the `App_Data` folder. 

The `Viewer.aspx` page contains the GUI (GroupDocs.Viewer widget) on the code-front. In the `HEAD` block, you will find all the necessary JavaScript/CSS libraries and scripts. The GroupDocs.Viewer widget (`<%= Viewer.ClientCode().TargetElementSelector("#viewer")…`) is located in the `BODY` block. When the web-page is rendered, this widget is transformed to a JavaScript code, which invokes GroupDocs.Viewer, creates a viewport and fills it with the document’s content.

At the end of the `Viewer.aspx` page there is also a JS code responsible for the dynamic resizing of the GroupDocs.Viewer viewport.

***

###Useful Links

GroupDocs.Viewer for .NET – Homepage:      
[https://groupdocs.com/dot-net/document-viewer-library](https://groupdocs.com/dot-net/document-viewer-library)

Documentation:      
[https://groupdocs.com/docs/display/viewernet/Home](https://groupdocs.com/docs/display/viewernet/Home)

Support Forum:      
[http://groupdocs.com/Community/Forums/Default.aspx](http://groupdocs.com/Community/Forums/Default.aspx)
