 **1.) PreInit** :- PreInit is the first stage of asp.net page event life cycle.In this stage following events can be fired on asp.net page.

- Check the IsPostBack Property to determine whether This page is processing first time.

- Create & Recreate Dynamic controls

- Set A Master page in the code dynamically

- Set the theme & Skin property on the page.

  **2.) Init** :- 

  - This event fires after each control has been initialized.
  - This is used to read the property of each initialized control .
  - Set Unique Id  and skin properties of the controls.
  - We can't get the Text Box value due to view state property is false after click  the  Submit Button.
  - In this event, we can't able to get the post back values of the controls. 

**3.) InitComplete** :- 

- Initialization process will be complete in this section..
- It is raised by the page object.
- This is used for event processing task.

**4.) PreLoad** :- 

- In This Event ,From where View state functionality starts retrieving the page controls data (value).
- In this event,View State Data are loaded  to the controls.
- In this event ,Post Back data are also handled by the Page contols
- This Event (PreLoad) always Fired after the InitComplete Event.

**5.) Load** :-

- It use the On Load event method to set the properties of the controls and establish database connection.
- The page calls the On Load event method on the page then recursively does the same for each child controls until the  control load and page load . 
- We can check IsValid Property on the page Load event method.
- We can Create Dynamic  controls also in this event method.
- All the page values restored in this method. 

**6.) LoadComplete** :-

- It raised at the end of the event handling stage.
- It use this event for tasks that require that all other controls on the page be loaded.
- All the event processing has been done in this event method.

**7.) PreRender** :-

- PreRender event method is called when page has  created all the controls and displayed in browser.
- PreRender method is last place where you can change any things on the page.
- Any change will be stored on the page.
- The PreRender event occurs for each controls on the page.

**8.) SaveStateComplete** :-

- Before this events occurs,View State has been saved for the page and for all controls.
- This event is fired after the complete the PreRenderComplete event.
- In this event method , if you change the server control then state will not be available in next Post Backs.
- In this Event Method ,You can do the changes in server control also. 

**9.) Render**  :-

- This method (Render ) display the  HTML,DHTML and Scripts codes in control on the  Browser (client side).
- A user code (.ascx file) automatically incorporates rendering so you will not need to explicitly render the control in the code.

**10.) Unload** :-

- This is the last event that fired on the page.
- This is the page cleaning process such as Instances cleaning or objects,closing the database connections ,closing the opened file.
- In this phase you can't do any manipulation.
- Suppose if you call a method such as Response.write method then page will throw an exception.