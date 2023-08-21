### Hi-level description and definitions: 

We are working on simple helpdesk system for own education purposes. 

#### Roles:
 **Administrator** is a superuser in our system, able to do anything. Also Administrator is an Agent and a User
**Agent** is a person/account, who intend to solve problems and document it. Also Agent is a User
 **User** is a person who create a ticket because they a problem
 
 **Ticket** is an item of work, it has: 
 * Unique ID (number)
 * Subject (text field, limited) 
 * Description (text field, unlimited) 
 * Created by (link to user account)
 * Recieved via (one of list, may be extended later)
	 * web
	 * e-mail
	 * Telegram bot 
* Assigned to (link to one or more Agents)
 * Status (one of the list, may be extended later)
	 * New
	 * In progress
	 * Pending
	 * Waiting for user's response 
	 * Resolved
	 * Closed
* Comments (array of messages) 
	* Message contains: 
		* Ticket ID
		* Sender (User or system)
		* Subject 
		* Text (html?) 
		* Attachments (files, images)  
* Archived (binary flag) 



### Project links: 
[ Documentation](https://github.com/VikingEngineers/supHubDocs)
[ Tasks](https://tree.taiga.io/project/lazyseal-suphubpro/kanban) 
