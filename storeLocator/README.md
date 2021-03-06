Store Locator plugin
====================

Version History
--------------------------------------

### 1.1 ###
- api_uri is now customizable
- Changed a variable from 'language' to 'lang' which was the reason why IE crashed 
- Changed the alert to window.console for logging purpose
- Added a a link around the span of the pos title

### 1.2 ###
Added a compatible JS file for jQuery < 1.5 versions

Plugin setup
--------------------------------------

To use the store Locator plugin you'll need ( _these lines are already provided in index.html in the package_ ): 

1. jQuery >= 1.7.1 ( http://code.jquery.com/jquery-1.7.2.min.js )
2. Include Google Map V3 API ( http://maps.google.com/maps/api/js?sensor=false )
3. Include Store Locator plugin ( http://widgets.leadformance.com/storeLocator/v1/lf_storelocator.min.js )
4. Call the plugin ( _default values_ ):

				<script type="text/javascript">  
					$(function(){  
						$('.lf_storeLocatorWidget').lf_storelocator({  
							api_key: "myapikey", 
							api_uri: "myapiURL",
							fo_uri: "myfoURL",
							allow_geolocation: true,
							lang: "fr"
						});  
					});  
				</script>


Plugin options
--------------------------------------

You can customize your plugin with the following options : 

### api_key ###
**Mandatory.**
Type : String  
Leadformance API Key

### max_results ###
Type : Integer  
Default : 3  

### fo_uri ###
Type : String  
Your Front office URL. If missing, some fonctionnality will be disabled.  

### allow_geolocation ###
Type : boolean  
Default : true  
Allow your visitor to use geolocation fonctionnality (only available for compatible browsers : IE9+, FF3.5+, Chrome 5+, Safari 5+, Opera 10.60+)  

### pos_infos ###
Type : String  
Default : ["name","address","address2","postal_code","city","phone","fax"]  
Point of sale information you want to be displayed.

**Available options :**

* name
* address
* address2
* postal_code
* city
* phone
* fax
* company

### lang ###
Type : String  
Default : "en"
Available : "fr", "de", "nl"
If the language asked isn't found, it'll display english texts.  

### lang_override ###
Type : Object  
Override the default language and the "lang" parameter.   

**Available parameter :**

* formLabelFind
* formPlaceHolder
* formLabelGeoloc
* errorNoData
* errorNoResult
* errorGeoLoc
* errorTryAgain
* errorXHR
* textVisitUs
		
**Example :**

				$(function(){  
					$('.lf_storeLocatorWidget_submit').lf_storelocator({  
						lang: "fr",  
						lang_override:  
						{  
							'formLabelFind': 'Find a store near Paris',  
							'textVisitUs': 'Klicken Sie auf Besuch'  
						}  
					});  
				});`  

CSS customization
--------------------------------------

You can fully customize the HTML with the CSS joined to your package. Take care not to delete the class needed by the plugin : 

* **lf_storeLocatorWidget** for your main container
* **lf_storeLocatorWidget_find** for your search field
* **lf_storeLocatorWidget_submit** for the search button

