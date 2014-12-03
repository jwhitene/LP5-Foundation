LP5-Foundation
==============

Luminis Platform 5 Foundation Theme - Working menu and column collapse.  

Notes:  This theme is not styled.  Its purpose is just to show how to work Foundation into the Ellucian Portal. 

Build Software:

Eclipse Java EE IDE for Web Developers. Version: Kepler Service Release 2
Luminis LP-5.2.1.0 Patch Build 103
Liferay Plugins SDK 6.1.1

Pre-Reqs
    Install the Liferay IDE in Eclipse - http://www.liferay.com/community/wiki/-/wiki/Main/Liferay+IDE+Installation+Guide
    Setup the plugins SDK - http://www.liferay.com/community/wiki/-/wiki/Main/Liferay+IDE+Getting+Started+Tutorial
    
Creating a Theme
In eclipse, New–> Liferay Project, Select the Theme radio button.  
Name your theme, choose your liferay-plugin-ins SDK and the java/tomcat runtime you want to test in.
On the next screen, use velocity templates if you want to use what Ellucian uses.  

You'll have this directory structure to begin with:
Theme-Name
build.xml
docroot
---_diffs
---css
---images
---javascript
---js  
---META-INF  
---templates  
---WEB-INF

The _diffs directory in Eclipse is where you make all your changes.  
I copied the css, images, javascript, js, and templates folders from the base Ellucian theme into my _diffs folder. 
Make sure you replicate full paths to the files you'll be editing.

$ ls docroot/_diffs/
css  images  javascript  js  templates

templates/portal_normal.vm is where you can call your custom js or css.   I put mine in the _diffs/js folder.  
If your javascript is in the _diffs/js directory, you can reference it in the templates like this:
<script src="$javascript_folder/modernizr.js"></script>  There are many template variables you can use.  $css_folder is another.

When you are ready to deploy your Theme to the server, right click on the project, select Liferay ---> war (very bottom).
Copy the theme from your plugins-sdk-6xx/dist directory to 
$CP_ROOT/products/tomcat/tomcat-admin/deploy and tomcat-portal/deploy.


