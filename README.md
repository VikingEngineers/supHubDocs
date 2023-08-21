
## Hi-level description and definitions: 

### Mission
We are working on simple helpdesk system for own education purposes.

The product must be: 
* Easy to use
* Simple in the architecture and code
* Well documented and easy to read (included codestyle and comments)

### Site structure 

**Login page** Require to enter something (let's start from e-mail and password) and has a link to *submit a ticket without authorization* page

**Registration page**
If we do not have e-mail in DB - we just create a new user with new ID 
If we have such user registered automatically - we create a new one, move all tickets created before to new account, block the old accound (make it inactive)
If we have manually registered user - display this fact and propose to use *forgot password*

**Main page** for authorized user contains: 
* List of submitted tickets 
* List of assigned tickets (for Agents) 
* List of tickets in Responsibility Area (for Agents) 

**Ticket page** for authorized user contains: 
* All the fields of ticket in human-readable format 
* Comment/message form 
* For whom can change something - control elements 

**User page** for Agents contains another user info - name, bio, all created tickets (with filters) 

**Admin page** - dashboards, banhammer, etc. 

**Submit ticket page** provides a form to send a ticket with or withour authorization. Contains fields: 
* Contact type (for unauthorized users)  (dropdown list) - starting from e-mail, later will be able to add telegram 
* Contact info  (for unauthorized users)  (e-mail) 
	* If contact exists in database - we create a new ticket for this user 
	* If contact does not exists - we create a new account with no password, send an access link to provided contact and keep it alive  
 

### Roles:
 **Administrator** is a superuser in our system, able to do anything. Also Administrator is an Agent and a User
**Agent** is a person/account, who intend to solve problems and document it. Also Agent is a User
 **User** is a general term to describe any account. User can be created manually or automatically. By default user has a lowest access level
 
 **Ticket** is an item of work, it has: 
 * Unique ID (number)
 * Area (from the custom list, has default value) 
 * Subject (text field, limited) 
 * Description (text field, unlimited) 
 * Priority (0 - 5, number, 0 is critical, 5 is backlog)
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

 **User** is an account, it has: 
 * Unique ID 
 * Creation type (registration or auto)
 * Active? (binary) 
 * Visible name 
 * Bio (description)? including custom information like occupation, department, etc. 
 * Roles (user, agent, admin) 
 * Responsibility area (none or any of Area values in the Ticket)
 * Assigned tickets (none for users, any number of tickets ids for agents) 
 * Password 
 * Access tokens for automatically generated users 
 
 



### Project links: 
[ Documentation](https://github.com/VikingEngineers/supHubDocs)
[ Tasks](https://tree.taiga.io/project/lazyseal-suphubpro/kanban) 
