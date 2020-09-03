# What is Routing in MVC? 

Routing is a matching mechanism of incoming requests to the URL patterns which are registered in route table. UrlRoutingModule class is used for the same process.

Type of Routing 

1. Convention-Based Routing 
2. Attribute Routing 

# What is Attribute Routing in MVC?

Attribute routing is introduced in MVC5. Attributes are being used to define the routes. This type of routing gives more control over classic URI Routing. Attribute Routing can be defined at controller level or at Action level. ASP.NET Web API supports attribute routing.

# How to enabling Attribute Routing?

To enable attribute routing, call MapMvcAttributeRoutes during configuration.

```
public class RouteConfig
{
    public static void RegisterRoutes(RouteCollection routes)
    {
        routes.IgnoreRoute(“{resource}.axd/{*pathInfo}”);
 
        routes.MapMvcAttributeRoutes();
    }
}
```

# You can also combine attribute routing with convention-based routing.

```
public static void RegisterRoutes(RouteCollection routes)
{
    routes.IgnoreRoute(“{resource}.axd/{*pathInfo}”);
 
    routes.MapMvcAttributeRoutes();
 
    routes.MapRoute(
        name: “Default”,
        url: “{controller}/{action}/{id}”,
        defaults: new { controller = “Home”, action = “Index”, id = UrlParameter.Optional }
    );
}
```

# The following table lists the constraints that are supported.

| #Constraint	| #Description	 | #Example |
| :---:   | :-: | :-: |
| alpha	| Matches uppercase or lowercase Latin alphabet characters (a-z, A-Z)| {x:alpha}|	
|bool|	Matches a Boolean value.|{x:bool}|
|datetime|Matches a DateTime value.|{x:datetime}|
|decimal|Matches a decimal value.|{x:decimal}|
|double|Matches a 64-bit floating-point value.|{x:double}|
|float|Matches a 32-bit floating-point value.|{x:float}|
|guid|Matches a GUID value.|{x:guid}|
|int|Matches a 32-bit integer value.|{x:int}|
|length|Matches a string with the specified length or within a specified range of lengths.|{x:length(6)} {x:length(1,20)}|
|long|Matches a 64-bit integer value.|{x:long}|
|max|Matches an integer with a maximum value.|{x:max(10)}|
|maxlength|Matches a string with a maximum length|{x:maxlength(10)}|
|min|Matches an integer with a minimum value.|{x:min(10)}|
|minlength|Matches a string with a minimum length.|{x:minlength(10)}|
|range|Matches an integer within a range of values.|{x:range(10,50)}|
|regex|	Matches a regular expression.|{x:regex(^\d{3}-\d{3}-\d{4}$)}|

# What is Route Prefix?

Route prefix are associated with routes by design in attribute routing.It is used to set a common prefix for an entire controller.
