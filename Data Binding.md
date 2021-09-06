## Data Binding

User can bind the data with the controls of the forms. This process is known as data binding. There are two types of data binding in ASP.NET known as simple data binding and declarative data binding.

#### Single value data binding

In simple data binding, the control is bounded to a data set. The properties of the control are used for binding with the value. Depending on the control to be bounded, the binding’s property is set.

```
<asp:Label ID="Label1" runat="server">
            UserID: <%# UserID %><br />
            UserName: <%# UserName %><br />
            City: <%# City %>
        </asp:Label>
        
        public int UserID;
        public string UserName;
        public string City;

        protected void Page_Load(object sender, EventArgs e)
        {
            UserID = 1;
            UserName = "Shubham";
            City = "Mysore";

            this.DataBind();
        }
```



#### **Repeatated value data binding**

The process of binding a component like listbox, DataGrid, record list with the dataset is known as declarative binding. When there is more than one element in the database, the declarative binding is used.

