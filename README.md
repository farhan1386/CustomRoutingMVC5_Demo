# What is Routing in MVC? 

Routing is a matching mechanism of incoming requests to the URL patterns which are registered in route table. UrlRoutingModule class is used for the same process.

Type of Routing 

1. Convention-Based Routing 
2. Attribute Routing 

# What is Attribute Routing in MVC?

Attribute routing is introduced in MVC5. Attributes are being used to define the routes. This type of routing gives more control over classic URI Routing. Attribute Routing can be defined at controller level or at Action level. ASP.NET Web API supports attribute routing.

# How to enabling Attribute Routing?

To enable attribute routing, call MapMvcAttributeRoutes during configuration.

public class RouteConfig
{
    public static void RegisterRoutes(RouteCollection routes)
    {
        routes.IgnoreRoute(“{resource}.axd/{*pathInfo}”);
 
        routes.MapMvcAttributeRoutes();
    }
}

# You can also combine attribute routing with convention-based routing.

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



