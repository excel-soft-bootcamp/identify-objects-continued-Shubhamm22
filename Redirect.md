
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
      
           


     
