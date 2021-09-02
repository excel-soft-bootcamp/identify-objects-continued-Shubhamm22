Cache Option:

- Page Output Caching
- Partial Page Caching
- DataSource Caching
- Data Caching  
  

## Page Output Caching

Page Output Caching caches an entire page. It provides you to cache the entire rendered contents of a page in memory. The next time that any user requests the same page, the page is retrieved from the cache.

```
  <%@ OutputCache Duration="20" VaryByParam="none" %>
   protected void Page_Load(object sender, EventArgs e)
        {
            Label1.Text = DateTime.Now.ToString();
        }
```

## Using Partial Page Caching

 For example, you might want to cache a set of database records displayed in a page, but not cache a random advertisement displayed in the same page. By the use of User Control you can perform Partial Page Caching.

```
WebUserControl1.ascx
<%@ Register Src="~/WebUserControl1.ascx" TagPrefix="uc1" TagName="WebUserControl1" %>

<uc1:WebUserControl1 runat="server" id="WebUserControl1" />
<%@ Control Language="C#" AutoEventWireup="true" CodeFile="WebUserControl1.ascx.cs" Inherits="WebUserControl" %>
<%@ OutputCache Duration="20" VaryByParam="none" %>

<asp:Label ID="Label1" runat="server" Text="User control Time"></asp:Label>
WebForm1.aspx:
protected void Page_Load(object sender, EventArgs e)
        {
            Label1.Text = DateTime.Now.ToString();
        }
```



## Data Caching

The main aspect of data caching is caching the data source controls.

```
<asp:Label ID="lbltime" runat="server"></asp:Label>
protected void Page_Load(object sender, EventArgs e)
{
   lbltime.Text = String.Format("Page posted at: {0}", DateTime.Now.ToLongTimeString());
}
```

## Object Caching

Object caching provides more flexibility than other cache techniques. You can use object caching to place any object in the cache. The object can be of any type - a data type, a web control, a class, a dataset object, etc. The item is added to the cache simply by assigning a new key name.

```
Cache.Insert("my_item", obj, null, DateTime.MaxValue, TimeSpan.FromMinutes(10));
```

