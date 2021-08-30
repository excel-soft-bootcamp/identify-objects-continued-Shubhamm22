
| Response.Redirect  |  Server.Transfer|
|:------------- |:---|
| Syntax:  Response.Redirect(url,boolean); |Syntax: Server.Transfer(url);|
|  Example 1: protected void Button1_Click(object sender, EventArgs e)| protected void Button1_Click(object sender, EventArgs e)|
{Session["BeforeMsg"] = "Code Executed Before Redirecting";|{|
Response.Redirect("WebForm2.aspx",true);|Server.Transfer("WebForm2.aspx");|
Session["AfterMsg"] = "Code Executed After Redirecting";}|}|
}|Output: page will be directed|
| Output: Code Executed Before Redirecting|
|Example 2:   protected void Button1_Click(object sender, EventArgs e)| 
{Session["BeforeMsg"] = "Code Executed Before Redirecting";| 
Response.Redirect("WebForm2.aspx?name=",false);
Session["AfterMsg"] = "Code Executed After Redirecting";
}|
|Output: Code Executed Before Redirecting Code Executed After Redirecting||
      
| Server.Execute  |CrossPagePostback|
|:------------- |:---|        
|Server.Execute is used to transfer control from one page to another page. Control execute code on another page and return back to previous page|Cross Page Posting (CrossPagePostBack) is a way to submit one page to another page and it also allows to access controls of Previous Page using the PreviousPage property|
|In this case URL doesn’t change in the browser.|To use cross-page posting, you have to use the ‘postBackUrl’ attribute to specify the page we want to post|
|it can not navigate to outside pages of the application|
|Syntax : Server.Execute(“URL of another page”);|
|It Can access previous page control on new page.|
|PreviousPage.FindControl() is available on new page.|
|It conserves server resources by avoiding that extra round-trip.|


     
