


# Lead Module Overview
- The Lead module is equipped with a series of dropdown menus, which are designed to gather essential information about the lead, including their relevant details.

#### List of Drop-down Menus:
```bash
1.	Lead Information
2.	Address Information
3.	Description Information
4.	Lead Value
5.	Actions
```

### Lead Summary Information
![](https://github.com/NARESH-GOSURE/Gosure-Documentation/blob/main/lead%20summary.png)
## Features of Lead Module

#### Expand All: 
- This feature allows you to expand all dropdown menus on a single page, providing a comprehensive view of all the information related to the lead.
#### Collapse All: 
- Conversely, the Collapse All feature gathers all the retrieved information and consolidates it into a single, organized unit, making it easier to review and analyse.

![](https://github.com/NARESH-GOSURE/Gosure-Documentation/blob/main/lead%20expand%20and%20collapse.png)


### Creating a New Fields: 
- By utilizing the radio slider button, we have the ability to create new fields based on our specific requirements, complete with all the necessary options we need.

#### Field Creation Radio Button
![](https://github.com/NARESH-GOSURE/Gosure-Documentation/blob/main/field%20radio%20button.png)

### Lead Parameter Controls:
- Lead parameters can be configured with a list of options for field type characteristics, allowing you to assign specific attributes to each field as needed.


![](https://github.com/NARESH-GOSURE/Gosure-Documentation/blob/main/lead%20parameter%20controls.png)

### Field Data Type's
![](https://github.com/NARESH-GOSURE/Gosure-Documentation/blob/main/fielddatatype-1.png)
![](https://github.com/NARESH-GOSURE/Gosure-Documentation/blob/main/fielddatatype-2.png)

### Lead Module Inputs:

![](https://github.com/NARESH-GOSURE/Gosure-Documentation/blob/main/leadinfo.png)
![](https://github.com/NARESH-GOSURE/Gosure-Documentation/blob/main/leadaddressinfo.png)
![](https://github.com/NARESH-GOSURE/Gosure-Documentation/blob/main/lead%20description%20info.png)
![](https://github.com/NARESH-GOSURE/Gosure-Documentation/blob/main/leadvalue%20info.png)

## Field Properties
#### 1.	Unique Field ID:
    - The Unique Field ID is used to maintain a unique identifier for the job type's field name.
    - You can use any unique name that represents the uniqueness of the job type's field name.



#### 2.	Display Order:
    - This parameter determines the order in which the field will be displayed within the field group.

#### 3.	Field Name:
    - The Field Name represents the specific fields that should be added under a particular job type.

#### 4.	Display Name:
    - The Display Name is used to display the field name in the job type at the front-end UI level.

#### 5.	Template Name:
    - The Template refers to the predetermined field details that can be downloaded. 
    - The Template Name refers to the name that will be printed in the template form.

#### 6. OCR Name:
    - Optical Character Recognition (OCR) is a technology used to scan documents and extract relevant details. 
    - This technology retrieves data from scanned documents and places it within the OCR field tab.
    - However, OCR has limitations in accurately identifying and replacing data, which can affect its efficiency. 
    - As a result, its performance needs to be rechecked and optimized for reliable results.


#### 7. Dependent Fields:
    - A Dependent Field is a field that relies on the value of another field. In other words, one field is dependent on the value of another field. You can add multiple dependent fields for a single field. 
    - The key feature of dependent fields is that when the value of the primary field changes, the corresponding dependent field values also change dynamically. 
    - This allows for automatic updates and ensures that related fields are always in sync.

#### 8. Field Group:
    - A Field Group is a way to categorize and organize fields under different attributes at the front-end UI level.
    - It defines which field names are grouped together under specific categories or sections, making it easier to manage and display related fields in a user-friendly manner.


#### 9. Column Layout:
    - The Column Layout value determines the number of columns required to display field values in the UI design. 
    - By default, a 2-column layout is used, which means that field values are arranged in two columns to provide a clean and organized visual representation.


#### 10. Field type:
    - The Field Type represents the data type of the field value that needs to be entered. We have a comprehensive list of field types collected from various domains, providing a wide range of options for selection. 
    - The chosen field type determines the validation process and the necessary values that need to be filled in. 
    - For example, if the field type is "Email", the validation process will check for a valid email address format, and the user will be required to enter a valid email address. 
    - Similarly, if the field type is "Date", the validation process will check for a valid date format, and the user will be required to enter a date in the correct format.


#### 11. Subjoblimit:
    - The Subjob Limit value enables you to restrict the number of subjobs that can be added.
    - By default, the subjob limit is set to 0, which means there is no subjobs to that particular field. 
    - If the subjob limit is set to -1, which means there is no limit to the number of subjobs that can be added.
    - The Subjob Limit condition is only applicable when the field type is specifically set to "Subjobs Type". For fields with other types, the subjob limit condition will not be applied.
    - However, by specifying a positive integer value, you can limit the number of subjobs and disable the "Add New" button once the specified limit is reached. 
    - This feature helps to prevent excessive addition of subjobs and maintain a organized workflow.

#### 12. Mandatory:
    - By designating a field as mandatory, you ensure that users must specify a corresponding value for that field. 
    - This is a crucial requirement, as the system cannot proceed with necessary operations without these mandatory field values.

#### 13. isPublicAttachment:
    - This feature is exclusively applicable to fields with the "Attachment" field type. 
    - When enabled, the attachment field will be linked to a public database that can be accessed at any time without requiring any login credentials.
    - This means that the attached files will be stored in a publicly accessible database, allowing users to access them without needing to authenticate or provide any credentials.


#### 14. IS NOT Duplicate:
    - By enabling the duplicate check options, you can verify whether your field values are duplicated or not. 
    - Additionally, you can specify external checks by defining combinations of fields to be checked for duplicates. 
    - This feature allows you to customize the duplicate detection process, ensuring that your data remains accurate and consistent.

#### 15. Default value or Allowed Value:
    - This feature enables you to apply default values or allowed values to a field. 
    - You can also utilize queries to fetch values from a table (for selection data types) or leverage reports that generate arithmetic values (for numeric data types) configured within the system.
    - Furthermore, you can employ AJAX calls to dynamically populate field values based on a single input data entry. This allows for real-time data fetching and updating, enhancing the overall user experience.
    - If we have only two values for selection data types, we can define two values using the pipe symbol (|), where one of the values can be an output value.


#### 16. Pattern input:
    - The Pattern Input feature is used when you expect field values to conform to a specific pattern or format.
    - By defining an overall pattern, you can convert input values to the desired format, ensuring consistency and accuracy.
    - This feature is particularly useful in scenarios where automatic ID field generation is required. 
    - Instead of relying on the system to generate IDs, you can define a pattern to create unique and meaningful IDs that meet your specific requirements.

#### 17. Add New Type:
    - Currently, unused.
#### 18. Enable Incremental Search:
    - Enabling Incremental Search allows users to dynamically search a field by incrementing characters.
    - As the user types, the query is updated in real-time, and the results are fetched based on the updated query.


#### 19. Enable Add More:
    - Enabling the "Add More" option allows users to provide additional information for a particular field.
    - This feature is useful when a single field requires multiple values or when users need to provide supplementary details.

#### 20. Multi Selection:
    - The multi-selection option enables users to select multiple values from a drop-down menu simultaneously.
    - This feature provides a convenient way to choose multiple options from a list, saving time and effort.
#### 21. isSearchable:
    - The isSearchable option is a powerful feature that allows you to add a specific field to the special filter tab. 
    - By enabling this option, you can include the field in the advanced filtering capabilities, providing users with a more precise way to search and filter data based on their requirements.

#### 22. ShowInListView:
    - The ShowInListView option is a convenient feature that allows you to display field data values in the Management Information System (MIS) view.
    - By enabling this option, the field values are automatically included in the MIS view, providing a quick and easy way to access and review key information.
#### 23. Propagate this field to entered subForm Fields:
    - The Propagate option allows you to automatically copy the value of a field to its corresponding subform fields.
    - By enabling this option, you can ensure that the value is consistently applied across all related subforms, eliminating the need for manual data entry and reducing errors.
#### 24. Propagate the other form field to this field:
    - The Propagate from Another Form Field option allows you to copy the value of another form field into the current field.
    - This feature enables you to automatically populate the current field with data from a related field, streamlining your workflow and reducing manual data entry.


#### 25. Report Default Value:
    - Until now, there have been no default report values.
    - Instead, the values will change dynamically based on the user's input.

#### 26. isReportParam:
    - This isReportParam feature enables the direct addition of field values to the filter in the MIS view, allowing for data filtration based on specific criteria.

#### 27. isPivotParam:
    - The isPivotParam feature enables the inclusion of field values in the pivot table within the Report tab, thereby facilitating further filtering and analysis based on these fields.

#### 28. isPivotRowParam:
    - The isPivotRowParam feature allows us to automatically add field values to the row level of the pivot table, making filtration more easily accessible.

#### 29. isPivotColumnParam:
    - The isPivotColumnParam feature allows us to automatically add field values to the column level of the pivot table, making filtration more easily accessible.
#### 30. isAggragate:
    - By utilizing the isAggregate feature, you can aggregate specific numerical field values and have them automatically added to the Aggregate values tab of the pivot table in the Reports tab.

#### 31. isHidden:
    - By selecting this option, you can configure fields to be accessible only for backend operations, effectively hiding them from the frontend and development environments. 
    - This enables you to utilize these fields for calculations and processing without making them visible to users or developers.

#### 32. Rule:
    - In this Rule tab, you can define and store custom rules set by the client based on their specific requirements. 
    - These rules are applied to a particular field, governing its behaviour and validation according to the client's needs.
#### 33. Hidden Dependent Field:
    - Hidden Dependent Field feature allows you to hide fields that are dependent on other fields, making them invisible to users while still maintaining their functionality in the background. 
    - These hidden dependent fields can be used for calculations, processing, or other backend operations without cluttering the user interface.

#### 34. Trackable Fields:
    - Enable this option to maintain a complete and tamper-proof record of all changes made to the field value, with every modification tracked and logged in the activity history for transparency and accountability. 


#### 35. Risk Calculation Fields:
    - Risk Calculation Fields allow you to define and calculate risk scores based on specific criteria, enabling you to identify and prioritize potential risks and opportunities.

#### 36. Chatbot Enabled Fields:
    - Chatbot Enabled Fields allow you to integrate chatbot functionality into our forms, surveys, or applications, enabling users to interact with your system using natural language processing (NLP) and artificial intelligence (AI).

#### 37. Limited Fields:
    - The Limited Fields option enables the field value to be listed in the short forms, allowing users to provide input to the limited field, which in turn triggers a specific process or action.
#### 38. Show Review
    - Currently,Undesigned.
#### 39. Show Appointment
    - Currently,Undesigned.
#### 40. Chatbot Question:
    - Chatbot questions help to clarify the user's intent, ensuring the chatbot provides relevant and accurate responses.
#### 41. Chatbot Hindi Question:
    - Chatbot Hindi question options can help users to clarify their intent in the Hindi language.
#### 42. Default Value:
    - A default value is a pre-defined value that is automatically entered into a field or register form if the user doesn't provide a value. 
    - Default values can help reduce errors by providing a valid value that can be used if the user doesn't enter anything.
#### 43. Tags:
    - Tags/Tag names can be used to categorize and search for content related to generating reports and documents in PDF format, and creating visualizations such as tables, charts, and images.
#### 44. isHParam:
    - In this context, isHParam allows you to add a field value as a hierarchical filter, which is dependent on another field. 
    - This enables hierarchical filtering, where the filter values are organized in a tree-like structure, and the selection of one filter value affects the available options for the next filter.
#### 45. enableSimilar To:
    - When “enableSimilar To” is turned on, the system checks all the fields that have been marked as "similar" and pulls them up as a group of similar fields. 
    - This allows users to easily identify and analyse fields that share similar characteristics.
#### 46. label:
    - The label feature is used to display a custom name for a field in a genUI (generated user interface), making it easier for users to understand and work with the field.
#### 47. similarToConfig:
    - The similarToConfig field helps to enter rules for the enableSimilarTo field, which can categorize similar fields based on the set of rules that have been entered into the similarToConfig tab.
### 48. hOrder Question:
    - The 'hOrder Question' assists in ordering the fields in the hierarchical filter section by specifying the hierarchical order.
