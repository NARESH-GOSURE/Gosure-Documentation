
## Module Creation

### Module:
 - A module is a functional unit within a larger system or application.
 -  In the context of a software, a module typically represents a specific set of features, functionalities, or tools that serve a particular purpose. 
 - Modules are often designed to be reusable, flexible, and easy to integrate with other modules or components.

### Example:
- In the context of the Lead module mentioned earlier, it's likely a module that handles lead management, lead tracking, or lead generation-related tasks.


## Modules Compared to Different Versions

### Module Creation: Version 1 vs Version 2



### Version 1: 
    - In Version 1, Modules and Module categories can be created directly through the UI portal. 
        -  This allows for a more intuitive and user-friendly experience.

### Version 2: 
    - In contrast, Version 2 requires the use of Postman, an external tool, to create module types and module categories. 
        - This approach provides more flexibility and control, but may require more technical expertise.

### Creating Modules and Module Categories: 
    - To create a new module menu, an instance of the job type named "module-type" needs to be created. 
        - Once this is done, the corresponding module categories can be defined based on the user's configuration. 
            - This allows for a high degree of customization and flexibility in module creation.
## Our Module Features:
1. The module is utilized to create, modify, access, and delete data within a specific job type.    
2. Instead of granting access to all job types within a tenant, modules and module categories are employed to provide limited access by creating them. This allows for the creation of multiple job types within a particular tenant, while controlling user accessibility to each job type.

3. The menu items visible in the sidebar are categorized under the job type named 'Module-Type'.
 4. Module-Type is a system-defined job type that is visible at the UI level. 

5. Module categories, which are the second level of menu items at the UI level, have predetermined required fields.

6. Modules created at the configuration level should be easily accessible to everyone, ensuring seamless usability."
## Components Of Module Creation (Module Constants):

- When creating a module, there are several essential components to consider. These components help define the module's purpose, behaviour, and appearance within the system.

### Module in Version1:
![](https://github.com/NARESH-GOSURE/Gosure-Documentation/blob/main/module%20inputs.png)


### 1.	Module Name: 
    - The module name is a descriptive title that suggests the module's purpose, such as managing or tracking clients, customers, or a company's clientele.
        - It is a unique and concise name that identifies the module within the system.
### 2.	Module Label: 
    - The module label is a human-readable name or title for the module, providing a clear and concise description of its function.

### 3.	Module Entry Job ID: 
    - The module entry job ID specifies the job type name under which this module is accessed at the module level.

### 4.	Module Value:
    - The module value is a crucial component that determines the module's functionality and behaviour.

### 5.	 Module Priority :
    - The module priority determines the order in which the module category should appear in the portal.

### 6.	 MODULE_ENTRY_TYPE:
    - The MODULE_ENTRY_TYPE defines the job type, whether it is a single entry or multi-entry job type.
        - In a multi-entry job type, multiple job types can be accessed by configuring them in the UI.

### 7.	 ModuleUID: 
    - The ModuleUID is a unique field assigned at the module level, displaying a unique record that can be easily accessed. 
        - This UID is a unique string or code that identifies the module within the system.
### 8.	 Hide Currency Symbol:
    - The hide currency symbol feature hides the currency symbol and displays only the numbers.
### 9.	 MODULE_TYPE:
    - The MODULE_TYPE specifies the module category under which the module type should appear.
### 10.	Module Chatbot Label:
    - The module chatbot label is used for chatbox applications at the module level, identifying the chatbot module within the system.

### 11.	  Module Hindi Chatbot Label:
    - The Module Hindi chatbot label is similar to the previous one, but it is specifically for the Hindi version of the chatbot module.

### 12.	Menu Hindi Chatbot Label: 
    - The menu Hindi chatbot label is used to display the name of the Hindi chatbot module within a menu, often being a shorter version of the module name designed to fit within a menu item.
### 13.	Module Icon: 
    - Each module category is represented by a module icon, which is displayed before the module category. 
        - This icon provides a visual representation of the module category, making it easier to identify and navigate within the system.

##  Functionalities of the Module:


![](https://github.com/NARESH-GOSURE/Gosure-Documentation/blob/main/module-features%202.png)

### 1.	Guage Meter: 
    - The Gauge Meter feature allows users to determine whether to enable or disable the gauge meter for a specific module. 
        - This decision is made by the user configuring the module, providing them with the flexibility to customize the module's settings according to their needs.

### 2.	Is Widgets:
    - "Is Widgets" refers to a module that contains a collection of widgets, which are small, self-contained blocks of content or functionality that can be easily added to a dashboard.
        - These widgets provide a quick and easy way to access key information, perform tasks, or visualize data.
            - In our Dashboard, we are visualising the secondary status and module information as a widget for the easy understand of visualization.


### 3.	Similar To Active: 
    - The 'Similar To Active' feature is designed to identify data that is similar to the currently active data.
        - This feature enables the module to recognize and extract relevant information from existing active data, making it easier to work with related data sets.

#### Use cases: 
##### 1. Identifying Similar kinds of data:
    - It helps to recognize patterns and relationships between different data points, enabling the identification of similar kinds of data.
##### 2. Generating Underwriting Reports in MIS: 
    - In the Management Information System (MIS), this feature automatically fetches similar records, which can be used to generate underwriting reports.

### 5. bulkActionsActive:
    - BulkActionsActive is likely a boolean value that indicates whether bulk actions are currently active or enabled. 
        - In our applications, bulk actions allow users to perform a single action on multiple items or records at once. 
## Components of Menu Creations (Menu Constants):
### 1.	Menu_key:
    - This property allows you to create multiple menus within a particular module category. 
        - For example, you can have menus such as "Dashboard", "Insights", and "Reports" within a single module category.
### 2.	Menu_icon: 
    - This features represents the icon that corresponds to each menu option within the module category.
### 3.	Menu_route_link:   
    - Each menu item within the module category has a unique route link associated with it, providing a distinct URL that directs to a different page view, which was designed earlier.
### 4.	Menu entry job id: 
    - The Menu entry job id feature allows you to specify the job type name that is associated with a particular set of menu actions. 
        - This means that each job type has its own unique set of menus that are specific to that job type, and the menu actions will only be performed for that specific job type.
### 5.	Menu_Priority : 
    - Menu_Priority is a feature that allows you to set the priority or order of menu items within a module category. 
        - This means that you can control the sequence in which menu items are displayed with higher-priority items appearing at first.
### 6.	Menu_chatbot_label:  
    - Menu_chatbot_label is a feature that allows you to assign a specific label or identifier to a menu item that can be used by a chatbot or other automated system to interact with the menu.
### 7.	Menu_Type: 
    - Menu_Type refers to the hierarchical structure of a menu, allowing it to have either a single level or multiple levels of access.

## Other Compoments of Module Creation:

### 1.	Loading msg: 
    - This feature allows you to display a custom message to the user when an API call is being made and no response is received. 
        - This is often referred to as a "loading" or "waiting" message.
### 2.	No_records_msg: 
    - This feature allows you to display a custom message to the user when a search query returns no results. 
        - This is often referred to as a "no results found" or "no data available" message.

### 3.	isRegister: 
    - Is Register is a feature that determines whether a user needs to register before accessing a particular feature or functionality.

### 4.	Default_Expand_All :
    - Default_Expand_All is a feature that allows you to expand all the information in a particular module by default. 
        - When this feature is enabled, all the content within the module is automatically expanded. 
            - We provide value to be 1, which means that when the module is loaded, all the information is expanded by default.

### 5.	Roles_config: 
    - Roles_config is a feature that restricts access to a particular module based on the user's role. 
        - This means that you can configure the module to only be accessible to specific roles or groups of users, while denying access to others.
