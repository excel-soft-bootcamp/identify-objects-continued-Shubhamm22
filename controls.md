ASP.NET provides the following validation controls:

- RequiredFieldValidator
- RangeValidator
- CompareValidator
- RegularExpressionValidator
- CustomValidator
- ValidationSummary



##### RequiredFieldValidator Control

The RequiredFieldValidator control ensures that the required field is not empty. It is generally tied to a text box to force input into the text box.

```
  <asp:RequiredFieldValidator ID="RequiredFieldValidator1" runat="server" ErrorMessage="Please Enter the Field"></asp:RequiredFieldValidator>
```

## RangeValidator Control

The RangeValidator control verifies that the input value falls within a predetermined range.

```
            <asp:RangeValidator ID="RangeValidator1" runat="server" ErrorMessage="Enter Your Age(15-45)" MaximumValue="45" MinimumValue="15"></asp:RangeValidator>

```

## CompareValidator Control

The CompareValidator control compares a value in one control with a fixed value or a value in another control.

```
            <asp:CompareValidator ID="CompareValidator1" runat="server" ControlToCompare="TextBox2" ControlToValidate="TextBox3" ErrorMessage="Password do not match"></asp:CompareValidator>

```

## RegularExpressionValidator

The RegularExpressionValidator allows validating the input text by matching against a pattern of a regular expression. The regular expression is set in the ValidationExpression property.

```
            <asp:RegularExpressionValidator ID="RegularExpressionValidator1" runat="server" ControlToValidate="TextBox4" ErrorMessage="Enter Valid E-mail" ValidationExpression="\w+([-+.']\w+)*@\w+([-.]\w+)*\.\w+([-.]\w+)*"></asp:RegularExpressionValidator>

```

## CustomValidator

The CustomValidator control allows writing application specific custom validation routines for both the client side and the server side validation.

  Client Side:   

```
        <script>
        function validateLength(sender, args) {
            if (args.Value.length < 5)
                return args.IsValid = false;
            else
                return args.IsValid = true;
        }
    </script>
       <asp:CustomValidator ID="CustomValidator1" runat="server" ClientValidationFunction="validatelength" ControlToValidate="TextBox3" ErrorMessage="password must be greather than 4"></asp:CustomValidator>
  

```

Server Side:

```
            <asp:CustomValidator ID="CustomValidator2" runat="server" OnServerValidate="CustomValidator1_ServerValidate" ControlToValidate="TextBox3" ErrorMessage="Password must be less than 8"></asp:CustomValidator>
            
 protected void CustomValidator1_ServerValidate(object source, ServerValidateEventArgs args)
        {
            if (args.Value.Length >8)
            {
                args.IsValid = false;
            }
            else
            {
                args.IsValid = true;
            }
```

## User Controls

User controls behaves like miniature ASP.NET pages or web forms, which could be used by many other pages. These are derived from the System.Web.UI.UserControl class. These controls have the following characteristics:

- They have an .ascx extension.

- They may not contain any <html>, <body>, or <form> tags.

- They have a Control directive instead of a Page directive.

  ```
  UserControl1.ascx
  <table>
  	<tr>
  	  <td>Good Morning</td>
  	</tr>
  	
  	<tr>
  	  <td>Have a wonderfull day</td>
  	</tr>
  </table>
  WebForm1.aspx
  <%@ Register Src="~/UserControl1.ascx" TagName="WebControl" TagPrefix="TWebControl"%>
     <TWebControl:WebControl ID="WebControl1" runat="server" />
  ```

  