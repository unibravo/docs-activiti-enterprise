---
Title: Modeling user interfaces
---

# Modeling user interfaces
The user interfaces (UI) section of the Modeling Application allows for user interfaces to be configured and deployed with an application. The user interfaces available are: 

* [Alfresco Process Workspace](../workspace/README.md) to start and action processes and tasks. 
* [Alfresco Digital Workspace](https://docs.alfresco.com/adw/concepts/welcome-adw.html) to view content associated to processes and tasks. 

## Naming  
UI names must be in lowercase and between 1 and 26 characters in length. Alphanumeric characters and hyphens are allowed, however the name must begin with a letter and end alphanumerically. 

The following are examples of valid UI names: 

```
process-ui-1
content
process-ui-alpha
```

## Using user interfaces
Use the following steps to create a user interface definition: 

**In the UI section of the Modeling Application**: 

1. Create a new UI and give it a name and optional description. 

	**Note**: The `name` given to a UI will form part of the URL to access it. 
	
2. Select `process` or `content` for the UI template. 

	**Note**: `process` refers to the Process Workspace and `content` refers to the Digital Workspace. 

3. Save your UI definition. 

## Accessing user interfaces
User interfaces are accessed as part of an application, so the application name forms part of the URL. The `name` that is given to the user interface definition then forms the final part of the URL as in the following example format: `{my-domain}/{application-name}/ui/{ui-name}`



