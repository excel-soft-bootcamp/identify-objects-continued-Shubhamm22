## ASP.NET MVC Routing

- In MVC, routing is a process of mapping the browser request to the controller action and return response back. Each MVC application has default routing for the default **HomeController**.

- The **RouteConfig.cs** file is used to set routing for the application

```
 public static void RegisterRoutes(RouteCollection routes)
        {
            routes.IgnoreRoute("{resource}.axd/{*pathInfo}");

            routes.MapRoute(
                name: "Default",
                url: "{controller}/{action}",
                defaults: new { controller = "Home", action = "Echo", id = UrlParameter.Optional }
            );
        }
        HomeController.cs
        public class HomeController : Controller
    {
        public string Echo()
        {
            return "Good Morning";
        }  
    }
```

## Route Defaults

The default route table contains a single route (named Default). The Default route maps the first segment of a URL to a controller name, the second segment of a URL to a controller action, and the third segment to a parameter named **id**.

Imagine that you enter the following URL into your web browser's address bar:

/Home/Echo

The Default route maps this URL to the following parameters:

- controller = Home
- action = Echo
- id = UrlParameter.Optional

## Route Constraints

The Route Constraint in ASP.NET MVC Routing allows us to apply a regular expression to a URL segment to restrict whether the route will match the request.

```
 routes.MapRoute(
                name: "Default",
                url: "{controller}/{action}",
                defaults: new { controller = "Home", action = "Echo", id = UrlParameter.Optional },
            constraints :new { id = @"\d+" });
            Url: Home/Echo/10
```

### View Bag   V/s View Data



|                           View Bag                           |                          View Data                           |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|          Used to pass data from Controller to View.          |          Used to pass data from Controller to View.          |
| It uses the dynamic feature that was introduced in to  c#  4 and allows an object to have properties dynamically added to it and it stored as name/value pairs . | ViewData is derived from the ViewDataDictionary class and is basically a Dictionary object i.e. Keys and Values where Keys are String while Values will be objects. |
|             Does not provide compile time Error              |             Does not provide compile time Error              |
|                     ViewBag.msg="hello";                     |                   ViewData["msg"]="hello";                   |
|                                                              |                                                              |

###### View Bag:

```
 public ViewResult Index()
        {
            ViewBag.Cities = new List<string>()
            {
                "Mysore","Kodagu","Mandya"
            };
           return View();
        }
        Index.cshtml:
        <ul>
    @foreach(string strcities in ViewBag.Cities )
            {
                <li>@strcities</li>
            }
</ul>
```

View Data:

```
 public ViewResult Index()
        {
            ViewData["Cities"] = new List<string>()
            {
                "Mysore","Kodagu","Mandya"
            };
            return View();
        }
        Index.cshtml:
        <ul>
        @foreach (string strcities in (List<string>)ViewData["cities"])
        {
            <li>@strcities</li>
        }
</ul>
```

## <u>Action Results</u>

###### View Result

- View result is a basic view result. It returns basic results to view page. View result can return data to view page through which class is defined in the model. View page is a simple HTML page. Here view page has “.cshtml” extension. 

###### Partial View Result 

- Partial View Result is returning the result to Partial view page. Partial view is one of the views that we can call inside Normal view page.

```
public class HomeController : Controller
    {

        //PartialViewResult
        public PartialViewResult Index()
        {
            return PartialView("PartialView");
        }
        PartialView.cshtml:
        <h3>Its a Partial View</h3>
```

###### Redirect Result

- Redirect result is returning the result to specific URL.

  ```
  public ActionResult Echo(string message)
          {
  
              return Redirect("/Home/Display");
          }
          public string Display()
          {
              return "Good Evening";
          }
  ```

  - ##### **RedirectToRoute Result**

The RedirectToRouteResult is used whenever we need to go from one action method to another action method within the same or different controller.

```
public class HomeController : Controller
{
    public RedirectToRouteResult Index()
    {
        return RedirectToRoute(new { controller = "Home", action = "Display" });
    }
}
```

- ##### **RedirectToAction Result** 

The RedirectToAction Result in ASP.NET MVC is returning the result to a specified controller and action method. Controller name is optional in RedirectToAction method. If not mentioned, the Controller name redirects to a mentioned action method in the current Controller. 

```
 public ActionResult Index()
            {
                return RedirectToAction("Message", "Login");
            }
        
```

###### JSON Result:

- Json result is a significant Action Result in MVC. It will return simple text file format and key value pairs. If we call action method, using Ajax, it should return Json result.

```
public JsonResult Index()
        {
            return Json(new { Name = "John Smith", ID = 4, DateOfBirth = new DateTime(1999, 12, 31) },
                JsonRequestBehavior.AllowGet);
        }
```

###### File Result:

- File Result returns different file format view page when we implement file download concept in MVC using file result.

```
public ActionResult Index()
        {
            return File("Web.Config", "text");
        }
```

###### Content Result:

- Content result returns different content's format to view. MVC returns different format using content return like HTML format, Java Script format and any other format.

```
 public ActionResult Index()
        {
            return Content("<script>alert('Good Morning');</script>");
        }
```

