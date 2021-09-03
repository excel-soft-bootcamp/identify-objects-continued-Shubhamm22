# AJAX

- AJAX stands for **A**synchronous **Ja**vaScript and **X**ML.
- AJAX is a new technique for creating better, faster, and more interactive web applications with the help of XML, HTML, CSS, and Java Script.
- AJAX allows web pages to be updated asynchronously by exchanging small amounts of data with the server behind the scenes. This means that it is possible to update parts of a web page, without reloading the entire page.
- A user can continue to use the application while the client program requests information from the server in the background.

## AJAX Server Controls

- ScriptManager
- UpDatePanel
- Timer
- UpdateProgress
- ScriptManagerProxy
- Pointer



### Script Manager:

- The ScriptManager control is the most important control and must be present on the page for other controls to work.

- There can be only one script manager within a web page and it should be first control.

  ```
  <asp:ScriptManager ID="ScriptManager1" runat="server">
          </asp:ScriptManager>
  ```

  

### UpDatePanel:

- ##### It  is responsible for updating the particular requested content of the page instead of the entire page which is not requested. The ASP.Net controls are put under the update panel to make the benefit of this control. The ASP.Net controls which are kept under the update panel will be updated when the user clicks on a particular ASP.Net Control which are used in an application.

  ```
   <asp:ScriptManager ID="ScriptManager1" runat="server">
          </asp:ScriptManager>
          <br />
          <asp:UpdatePanel ID="UpdatePanel1" runat="server">
              <ContentTemplate>
                  <asp:Button ID="Button1" runat="server" Text="Click" OnClick="Button1_Click" />
                  &nbsp;&nbsp;&nbsp;
                  <asp:Label ID="Label1" runat="server"></asp:Label>
              </ContentTemplate>
          </asp:UpdatePanel>
          
           protected void Button1_Click(object sender, EventArgs e)
          {
              Label1.Text = DateTime.Now.ToShortTimeString();
          }
  ```

  