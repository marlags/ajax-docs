---
title: Getting Started
page_title: Getting Started | UI for ASP.NET AJAX Documentation
description: Getting Started
slug: captcha/getting-started
tags: getting,started
published: True
position: 2
---

# Getting Started



## Getting Started

The following tutorial demonstrates using __RadCaptcha__ to validate page submission. The walk-through will also show how to display the Error Message in a ValidationSummary.

1. In the default page of a new ASP.NET AJAX-enabled Web Application add a __RadCaptcha__ control, a Button control that causes post back on a click and a ValidationSummary control.
>caption 

![Rad Captcha](images/RadCaptcha.PNG)

1. Open the __RadCaptcha__ Smart Tag and select the Enable __RadCaptcha__ httpHandler link. Click OK to close the confirmation dialog for the RadCaptcha handler.
>caption 

![radcaptcha-smart-tag](images/radcaptcha-smart-tag.png)The httpHandler can be also enabled by placing the following lines in the web.config file:

````XML
	    <configuration>
		    <system.web>
	            <httpHandlers>
	                <add path="Telerik.Web.UI.WebResource.axd" type="Telerik.Web.UI.WebResource, Telerik.Web.UI" verb="*" validate="false" /> 
	            </httpHandlers>
		    </system.web>
		    <system.webServer>
	            <handlers>
	                <add name="Telerik_Web_UI_WebResource_axd" verb="*" preCondition="integratedMode" path="Telerik.Web.UI.WebResource.axd" type="Telerik.Web.UI.WebResource, Telerik.Web.UI" /> 
	            </handlers>
		    </system.webServer>
	    </configuration>
````



>note By default the image is stored in the Cache. However, if more than one server is used to host the page (web-farm environment) the Session should be used, because if the Cache is used the image is stored locally on the server. When Session is used, the HttpHandler definition (in the .config file) of the __RadCaptcha__ should be modified manually by setting the type of the HttpHandler has to be set to __type="Telerik.Web.UI.WebResourceSession"__ .
>


````XML
	    <configuration>
		    <system.web>
			    <httpHandlers>
				    <add path="Telerik.Web.UI.WebResource.axd" type="Telerik.Web.UI.WebResourceSession, Telerik.Web.UI" verb="*" validate="false" />
			    </httpHandlers>
		    </system.web>
		    <system.webServer>
			    <handlers>
				    <add name="Telerik_Web_UI_WebResource_axd" verb="*" preCondition="integratedMode" path="Telerik.Web.UI.WebResource.axd" type="Telerik.Web.UI.WebResourceSession, Telerik.Web.UI" />
			    </handlers>
		    </system.webServer>
	    </configuration>
````



1. In the Properties Window for the __RadCaptcha__ control set the following properties:

1. ErrorMessage = You have entered an invalid code.

1. ValidationGroup = SubmitGroup

1. In the Properties Window for the ValidationSummary control set the ValidationGroup property to the same value as in RadCaptcha (ValidationGroup = SubmitGroup). Do the same for the Button control.

1. Press F5 to run the Application. __RadCaptcha__ validates the input on a post back.
>caption 

![Rad Captcha In Browser](images/RadCaptchaInBrowser.PNG)

