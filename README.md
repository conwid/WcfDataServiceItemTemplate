# WCF Data Services Template for Visual Studio 2017

**This repository contains the source code for my WCF Data Services Template Visual Studio 2017 extension. You can download the extension from the [marketplace](https://marketplace.visualstudio.com/items?itemName=CONWID.WcfDataServiceTemplateExtension).**

**Also to check out [my blog post](https://dotnetfalcon.com/visual-studio-item-template-for-wcf-data-services/) on the making of the template!**

With Visual Studio 2015, you could create something called a WCF Data Service. This is basically an OData capable endpoint that is wrapped around and Entity Framework context and you can use the OData endpoint to access the context, which in turn accesses the database.

Unfortunately, VS 2017 does not support creating WCF Data Services from a template. Even if it did, the old template from VS2015 scaffolds code that is not compatible with the new Entity Framework versions. The code itself is pretty similar, but you have to use a different base class from a different Nuget package. This extension is here to help you if you want to create a WCF Data Services using VS2017.

## Accessing the template
After you install the extension, you'll see another item template in Visual Studio. Just create a WCF project, and then try to add a new item to the project. Type 'WCF' into the searchbox, and you'll have the new option right there:

![](https://dotnetfalconcontent.blob.core.windows.net/wcf-data-services-marketplace-content/wcf%20data%20service.png)

The item template is available for both web app and web site based templates, both for C# and VB.NET.

## Using the template
The template itself is pretty self-explanatory: just follow the comments and substitute the right classnames.

## Changes to the original template
This is basically a port of the original WCF Data Services template from Visual studio 2015. I did have to make a few changes in order to make this work:
- It uses the new (and still-in-beta-after-years) version of the Entity Framework Data Services Provider ([see here](https://www.nuget.org/packages/Microsoft.OData.EntityFrameworkProvider/))
- All the Nuget packages are embedded in the VSIX itself (the original template specified a registry key, which specified a folder on your hard drive that contained the packages).
- Changed the base class that the context is derived from; this was necessary to make it work with EF 6 and above.

## Licensing and terms
Check out the license notes here or at the marketplace. Use it at your own risk :) Also note that most of the heavy lifting was actually done by MS with the VS2015 version, all credits and the respective rights belong to them.

## Contribution
If you have any ideas, questions or problems, feel free to create an issue. PRs are always welcome :)

**Don't forget to check out [my blog post](https://dotnetfalcon.com/visual-studio-item-template-for-wcf-data-services/) on the making of the template!**
