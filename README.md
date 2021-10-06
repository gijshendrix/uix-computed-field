# GraphCMS Computed Field UI Extension Demo

## Introduction

This demo UI Extension for GraphCMS can be used to compute and store custom fields in your model. It uses the Mustache templating engine to compute the titles.

## How to use

Deploy the code to Vercel, or run locally. Then install this extension on GraphCMS as a UI extension using the URL to your index page as the URL (following [this guide](https://graphcms.com/docs/ui-extensions/getting-started/installing-ui-extensions)). 

For testing purposes, you can also use the Github Pages url for this repository: `https://gijshendrix.github.io/uix-computed-field/`

In the extension settings, specify the Computed field template using Mustache template (see reference below for syntax). Field values are accessed by their apiID (so the value of a field called `years` would be rendered by using the template `{{years}}`'. For reference fields, usually only the title field is accessible. This can be used in the template by using the following syntax: `{{<apiid_of_reference_field>.<name_of_title_field_in_reference>}}` in case the reference is of type "to-one". For "to-many" references, it's possible to use this syntax from Mustache: `{{#<apiid_of_reference_field>.connect}} {{<name_of_title_field_in_reference>}} {{/<apiid_of_reference_field>.connect}}` where `connect` is an internal name that must be used exactly as is.


## References

* [GraphCMS Documentation for UI Extensions](https://graphcms.com/docs/ui-extensions)
* [Mustache.js documentation](https://github.com/janl/mustache.js)
