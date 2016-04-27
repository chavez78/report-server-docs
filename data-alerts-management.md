---
title: Data Alerts Management
page_title: Data Alerts Management
description: Data Alerts Management
slug: alerts-management
tags: scheduling,alerts,management
published: True
position: 710
---

# Data Alerts Management



The **Data Alerts** view is the place from which you can manage data alerts, review the alerts' execution and manage subscribers.

Data Alerts
----------

The **Data Alerts** view allows you to create, modify and delete data alerts.
A Data Alert is a task which runs at a scheduled time and checks whether a specific data conditions are met. If the data conditions are met a report document is generated and sent to the alert's subscribers. A data alert can be run only once or on a recurrent basis, for example: daily, weekly, monthly or yearly. Within the recurrence rule, you set the intervals and range for how often a data alert is to be run.

A data alert has the following settings:

-   **Name** - the name of the data alert. It should be unique among the other data alerts

-   A report definition specified by Category and Name

-   Target document format - can be any single document format provided by the Telerik Reporting engine:

    -   PDF - Renders a report in the Adobe Acrobat Reader. The format is shown as Acrobat (PDF) File in the Export drop-down of the report toolbar.

    -   XLS - Renders a report in Microsoft Excel. The report opens in Microsoft Excel 97 or later.

    -   CSV - Renders a report in comma-delimited format. The report opens in a viewing tool associated with CSV file formats.

    -   RTF - Renders a report in Rich Text Format. The report opens in Microsoft Word 97 or later.

    -   XPS - Renders a report in XML Paper Specification (XPS) format - electronic representation of digital documents based on XML. The report opens in Microsoft XPS Viewer.

    -   DOCX - Renders a report in Microsoft Word 2007 format (also known as OpenXML) - it is a zipped, XML-based file format developed by Microsoft for representing word processing documents.

    -   XLSX - Renders a report in Microsoft Excel 2007 format (also known as OpenXML) - it is a zipped, XML-based file format developed by Microsoft for representing spreadsheets.

    -   PPTX - Renders a report in Microsoft PowerPoint 2007 format (also known as OpenXML) - it is a zipped, XML-based file format developed by Microsoft for presentations.

    -   MHTML - Renders a report in MHTML. The report opens in Internet Explorer. The format is shown as Web Archive in the Export drop-down of the report toolbar.

-   **Enabled** - the data alert can be temporary disabled without the need to delete it

-   **Start** - the actual start date of the data alert

-   **Repeat** - defines the recurrence rule if the data alert should be executed on regular intervals. The repeat pattern can be daily, weekly, monthly and yearly. Currently, hourly repetition is not supported.

-   **Parameters** - the parameters allow you to define the parameter values that will be used for the report when the data alert is executed. 
The parameters area includes all report parameters of the report regardless their visibility (visible or invisible). By default the 
invisible report parameters will use their values specified at design time, i.e. they are not overridden by the parameter values 
specified in the parameters. If you want to override the invisible parameters' values with the task's parameters you have to uncheck the 
"*Use Default Value*" checkbox.
The "*Use Default Value*" checkbox for all parameters determines whether the value of the report parameter specified at design time will be used or whether it will be overridden by the value that you have specified in the task's parameters. When it is checked the design time value of the report parameter will be used and when it is unchecked the stored in the task parameters value will be used.

-   **Mail template** - specifies the mail template which is sent when the data conditions are met and a report is generated. When there 
is an error during the report processing or a general error in the data alert execution then the **Configuration** | **Mail Templates** 
| **Data Alert Error** mail template is used.
    If you haven't explicitly changed this template then the template from **Configuration** | **Mail Templates** | **Data Alert Attachment** will be used**.**
    In the template you can use the following mail variables which will be replaced automatically when the task is executed:

    -   {FirstName} - the first name of the user

    -   {LastName} - the last name of the user

    -   {ReportName} - the name of the report document

    -   {AlertName} - the name of the data alert

    -   {DocumentFormat} - the specified in the task rendering format

    -   {StartTime} - start time of the report document generation

    -   {StartTimeShort} - start time of the report document generation formatted with the **short time pattern** of the operating system

    -   {StartTimeLong} - start time of the report document generation formatted with the **long time pattern** of the operating system

    -   {StartDate} - start date of the report document generation formatted with the **short date pattern** of the operating system

    -   {StartDateLong} - start date of the report document generation formatted with the **long date pattern** of the operating system

    -   {EndTime} - end time of the report document generation

    -   {EndTimeShort} - end time of the report document generation formatted with the **short time pattern** of the operating system

    -   {EndTimeLong} - end time of the report document generation formatted with the **long time pattern** of the operating system

    -   {EndDate} - end date of the report document generation formatted with the **short date pattern** of the operating system.

    -   {EndDateLong} - end date of the report document generation formatted with the **long date pattern** of the operating system

    -   {ExecutionTime} - elapsed time for the report document generation

    -   {ExecutionTimeDays} - elapsed time for the report document generation in **days**

    -   {ExecutionTimeHours} - elapsed time for the report document generation in **hours**

    -   {ExecutionTimeMinutes} - elapsed time for the report document generation in **minutes**

    -   {ExecutionTimeSeconds} - elapsed time for the report document generation in **seconds**

    -   {ExecutionTimeMilliseconds} - elapsed time for the report document generation in **milliseconds**

    -   {@\[ReportParameter.Name\]} - the value of the specified by the \[ReportParameter.Name\] report parameter used when running the scheduling task.
        Note: The \[ReportParameter.Name\] placeholder stands for the actual name of the report parameter. The list of all possible report parameters that can be used in the mail template is available through the *variables* dropdown in the Kendo editor.


-   **Rules** - the data alert rules specify the conditions which the data from the report should meet in order the alert to be triggered. In order to specify a rule a data item from the report should be chosen. 

You can search alerts by their Name, Report, or Document Format. For more information, see [Search]({%slug search%}).

Activity view
-------------

The **Activity** view for a data alert shows the created by the data alert documents. A created document can be downloaded for preview in the target format or deleted. The list items also display whether the alert has successfully created a document or there was an error while generating it.

Subscribers view
----------------

From the **Subscribers** view, you can manage who will receive the created documents as mail attachments. A subscriber can be an existing report server user or an external user which is represented through his email. The external emails should be separated with semicolon (;) or comma (,).