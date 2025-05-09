# Ansible Roles

An Ansible role is a reusable, self-contained unit of automation that is used to 
organize and manage tasks, variables, files, templates, and handlers in a structured way. 

Roles help to encapsulate and modularize the logic and configuration needed to manage 
a particular system or application component. 

This modular approach promotes reusability, maintainability, and consistency across different 
playbooks and environments.

**Command to create ansible role is****

ansible-galaxy role init <role_name>


## Key Components of an Ansible Role

### Tasks
The main list of actions that the role performs.

### Handlers
Tasks that are triggered by changes in other tasks, typically used for actions like restarting services.

### Files
Static files that need to be transferred to managed hosts.

### Templates
Where we will have dynamic files, which we want to change.
Jinja2 templates that can be rendered and transferred to managed hosts.

### Vars
Variables that are used within the role.

### Defaults
Default variables for the role, which can be overridden.

### Meta
Metadata about the role, including dependencies on other roles.

### Library
Custom modules or plugins used within the role.

### Module_defaults
Default module parameters for the role.

### Lookup_plugins
Custom lookup plugins for the role.

## Directory Structure of an Ansible Role

An Ansible role follows a specific directory structure:

```
<role_name>/
  ├── defaults/
  │   └── main.yml
  ├── files/
  ├── handlers/
  │   └── main.yml
  ├── meta/
  │   └── main.yml
  ├── tasks/
  │   └── main.yml
  ├── templates/
  ├── vars/
      └── main.yml
```

## Why Use Ansible Roles?

### Modularity
Roles allow you to break down complex playbooks into smaller, reusable components. 
Each role handles a specific part of the configuration or setup.

### Reusability
Once created, roles can be reused across different playbooks and projects. This saves time 
and effort in writing redundant code.

### Maintainability
By organizing related tasks into roles, it becomes easier to manage and maintain the code. 
Changes can be made in one place and applied consistently wherever the role is used.

### Readability
Roles make playbooks cleaner and easier to read by abstracting away the details into logically
named roles.

### Collaboration
Roles facilitate collaboration among team members by allowing them to work on different parts
of the infrastructure independently.

### Consistency
Using roles ensures that the same setup and configuration procedures are applied uniformly across
multiple environments, reducing the risk of configuration drift.

Here’s a more polished and structured version of your notes:  

---  

### How to Use Roles in a Playbook**  

#### **Step 1: Create a New Ansible Role**  
To generate a new role structure, use:  
```bash
ansible-galaxy role init <role_name>  
```  
**Example:**  
```bash
ansible-galaxy role init test1  
```  
This creates a directory with the standard Ansible role structure (e.g., `tasks/`, `vars/`, `handlers/`).  

#### **Step 2: Configure the Role**  
Add necessary files inside the role directory, such as:  
- **Tasks** (`tasks/main.yml`) – Define playbook steps.  
- **Variables** (`vars/main.yml` or `defaults/main.yml`) – Set role variables.  
- **Handlers** (`handlers/main.yml`) – Manage service restarts/reloads.  

#### **Step 3: Call the Role in a Playbook**  
To use the role in a playbook, reference it under `roles:`:  
```yaml
---
- hosts: all  
  become: true  
  roles:  
    - test1  
```  

---


Above is the syntax to call roles in the playbook


