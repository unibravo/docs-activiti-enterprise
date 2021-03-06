---
Title: Alfresco Modeling Application
---

# Alfresco Modeling Application

The Alfresco Modeling Application is used to create and update the components that make up an Alfresco Activiti Enterprise project. These include: 

* [Projects](../modeling/projects.md) are the top level component of a business application. The other components all sit within a project definition:

![Modeling project view](../images/modeling-elements.png)

* [Processes](../modeling/processes/README.md) use BPMN elements to model a business process. They incorporate the other components created in the Modeling Application.

* [Forms](../modeling/forms/README.md) are used to collect data from end-users and are attached to a start event or user task within a process.

* [Connectors](../modeling/connectors/README.md) are used to execute logic outside of processes. Values are sent from a process to a connector to be used as part of the logic and the results sent back to the process instance afterwards.

* [Decision tables](../modeling/decisions.md) are used to make business decisions as part of a process. 

* [User interfaces](../modeling/interfaces.md) are for associating user interfaces with an applications. 

* [Files](../modeling/files.md) can be uploaded and used within a project. 

* [Scripts](../modeling/scripts.md) can be created and implemented in a process definition to execute at runtime. 

* [Triggers](../modeling/triggers.md) are used to listen for an event and then execute an action when the event criteria are met.

## Modeling
All components of an application can be designed using a Graphical User Interface (GUI) or an XML or JSON editor. Users require the `ACTIVITI_MODELER` role in order to create projects within the Modeling Application. 

The [files that comprise an application](../modeling/projects.md#files) are stored in an instance of Alfresco Content Services (ACS). Process instances and tasks that are running can also be stored in a separate repository as nodes, including any content uploaded to them.

The URL of the Modeling Application will be in the format: `gateway.{domain-name}/modeling`.

## About
The about page can be accessed via the UI or at the URL: `gateway.{domain-name}/modeling/about` and shows the packages and package versions used in the application. 

## Settings
You can view the application configuration of the Modeling Application by visiting the URL: `gateway.{domain-name}/modeling/app.config.json`.