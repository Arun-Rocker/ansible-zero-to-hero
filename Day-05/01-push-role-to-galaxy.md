# Push your Ansible roles to Ansible Galaxy

1. Make sure your role is structured correctly. The basic structure should look like this:

```
my_role/
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
├── tests/
│   ├── inventory
│   └── test.yml
└── vars/
    └── main.yml
```

2. Make sure ansible-galaxy CLI exists

```
ansible-galaxy --version
```

3. Push Your Role to GitHub

```
cd <role-name>
git init
git remote add origin <https://github.com/your_github_username/my_role.git>
git add .
git commit -m "Initial commit"
git push -u origin main
```

4. Import the Role to Ansible Galaxy

```
ansible-galaxy role import <your_github_username> <role-name>
```
Here’s a more readable and polished version of your running notes:  

---

### **How to Use Roles from Ansible Galaxy**  

1. **Create an Account on Ansible Galaxy**  
   - Sign up at [Ansible Galaxy](https://galaxy.ansible.com/) to access community roles.  

2. **Install a Role from Ansible Galaxy**  
   - Example: To install a Docker role for setting up Docker on two worker machines, run:  
     On linux server run below command
     ansible-galaxy role install <role_name>
     
   - **Default Installation Path**:  
     ```bash
     ~/.ansible/roles/
     ```  
     (This is where all installed roles are stored.)  

3. **Use the Installed Role in a Playbook**  
   - Once the role is installed, reference it in your playbook:  
     ```yaml
     ---
     - hosts: all  
       become: true  
       roles:  
         - test1  
     ```  



