Alfresco Share Custom Footer
============================

#Introduction

This extension aims to disable the default footer by overriding the theme css.

The logic is simple and this is achieved by:

- Create a new theme called: `Custom Theme`
- Copy the `Light Theme` files and rename it to `Custom Theme`
- Rename all selectors from `ligthTheme` to `customTheme`
- Find the `.sticky-footer` selector and add: `display: none!important;`
- Done

#Slingshot.properties
  
This extension also removes the:

`page.title=Alfresco &raquo; {0}`

from every page, so now instead of heaving the page title showing in your browser tab:

		<html>
			<head>
				<title>Alfresco >> Search </title>
				...
			</head>
			...
		</html>

it'll show:

		<html>
			<head>
				<title> Search </title>
				...
			</head>
			...
		</html>

#Aikau override

In the current Aikau version: 

`aikau-1.0.8.1.jar`

the page title is being hardcoded in the `Title.js` found here:

`/META-INF/js/aikau/1.0.8.1/alfresco/header/`

so a small change was made to get rid of the:

`Alfresco >>` 

prefix in the `page-title`. This change affects only Aikau rendered pages (URLs behind `share/page/dp/ws/`).

Every other page can be customized through `slingshot.properties` l18n files, as already done here in this extension.

#Usage

Simply download the `.amp` from the target folder, and apply it as usualy to your share instance by:

- copying the amp into `alfresco/amps_share`
- running `alfresco/bin/apply_amps.sh` (Linux) or `alfresco/bin/apply_amps.bat` (Windows)
 
