##Displaying a TOCControl context menu

###Purpose  
This sample shows how context menus appear when you right-click a TOCControl that has a MapControl as its "buddy." The sample contains a map context menu and a layer context menu that host control commands and custom commands defined within the application.  


###Usage
1. Load a map document into the MapControl.    
1. Right-click a map or layer on the TOCControl to display a context menu.   





####Additional information  
<div xmlns="http://www.w3.org/1999/xhtml" xmlns:my="http://schemas.microsoft.com/office/infopath/2003/myXSD/2006-02-10T23:25:53">The map context menu contains feature selection and layer visibility commands and appears on the TOCControl when a map item is clicked. The layer context menu contains selection and scale threshold commands and appears when a layer item on the TOCControl is right-clicked.</div>  
<div xmlns="http://www.w3.org/1999/xhtml" xmlns:my="http://schemas.microsoft.com/office/infopath/2003/myXSD/2006-02-10T23:25:53"> </div>  
<div xmlns="http://www.w3.org/1999/xhtml" xmlns:my="http://schemas.microsoft.com/office/infopath/2003/myXSD/2006-02-10T23:25:53">Each context menu is implemented using the ToolbarMenu coclass. In Form_Load, the AddItem method is used to add custom commands defined within the application to a map ToolbarMenu and a layer ToolbarMenu with their style set. A predefined SelectionMenu is added to the map ToolbarMenu with the AddSubMenu method. The Hook property of each ToolbarMenu is set to the MapControl. The ITOCControl.HitTest method is used in the ITOCControlEvents.OnMouseDown event when right-clicked to determine whether a map or a layer has been clicked. The ITOCControl.SelectItem method is used to select the item that is clicked. The MapControl CustomProperty is set to the resulting layer and is used by the custom commands. The PopupMenu method displays the map's ToolbarMenu or the layer's ToolbarMenu.</div>  
<div xmlns="http://www.w3.org/1999/xhtml" xmlns:my="http://schemas.microsoft.com/office/infopath/2003/myXSD/2006-02-10T23:25:53"> </div>  
<div xmlns="http://www.w3.org/1999/xhtml" xmlns:my="http://schemas.microsoft.com/office/infopath/2003/myXSD/2006-02-10T23:25:53">Several of the custom command classes, such as the LayerVisibility class, define multiple related command objects by implementing the ICommandSubType interface. For custom commands that are added to the layer's ToolbarMenu to determine which layer to work with, the IMapControl3.CustomProperty property is used. </div>  


####See Also  
[TOCControl class](http://desktop.arcgis.com/search/?q=TOCControl%20class&p=0&language=en&product=arcobjects-sdk-dotnet&version=&n=15&collection=help)  
[ITOCControl interface](http://desktop.arcgis.com/search/?q=ITOCControl%20interface&p=0&language=en&product=arcobjects-sdk-dotnet&version=&n=15&collection=help)  
[ToolbarMenu class](http://desktop.arcgis.com/search/?q=ToolbarMenu%20class&p=0&language=en&product=arcobjects-sdk-dotnet&version=&n=15&collection=help)  
[IToolbarMenu interface](http://desktop.arcgis.com/search/?q=IToolbarMenu%20interface&p=0&language=en&product=arcobjects-sdk-dotnet&version=&n=15&collection=help)  


---------------------------------

####Licensing  
| Development licensing | Deployment licensing | 
| :------------- | :------------- | 
| Engine Developer Kit | Engine |  
|  | ArcGIS for Desktop Basic |  
|  | ArcGIS for Desktop Standard |  
|  | ArcGIS for Desktop Advanced |  


