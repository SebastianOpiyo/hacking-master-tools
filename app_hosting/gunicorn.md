# GUNICORN
Is used to server the application

# Running the application
--------------------------
**This command exposes the application to anyone in the network**:
```bash
gunicorn --bind 0.0.0.0:<app_port> <app_name>.wsgi
```

**Thic command checks the gunicorn running processes**
```bash 
ps aux | grep gunicorn
```

**Restart gunicorn after making changes**
```bash
sudo systemctl restart gunicorn
```

**You can use supervisor to manage gunicorn**
```bash
supervisorctl restart gunicorn
```

**Gracefully restart using HUP signal**
```bash
pkill -HUP gunicorn```

**Accessing gunicorn service and fixing config**
----------------------------
```bash
sudo nano /etc/systemd/system/gunicorn.service
```

**Viewing gunicorn logs starting with the latest**
----------------------------
```bash
journalctl -u gunicorn -r
```

**Picking the 50 latest logs**
```bash
journalctl -u gunicorn -r -n 50 
```

**Reloading and checking gunicorn status**
```bash 
sudo systemctl daemon-reload```

**Check Status**
```bash 
sudo systemctl status gunicorn
```



**Sites-available**
---------------------
The sites-available directory is used in Nginx to store configuration files for individual websites or applications. It is part of a common convention in Nginx to organize and manage multiple site configurations on a single server.

---

### **Purpose of sites-available**
1. **Configuration Storage**:
   - This directory contains the configuration files for all the websites or applications that can potentially be served by Nginx.
   - Each file in this directory typically corresponds to a single website or application.

2. **Separation of Active and Inactive Sites**:
   - The files in sites-available are not automatically active. They are just stored here for organizational purposes.
   - To activate a site, you create a symbolic link to the configuration file in sites-enabled.

3. **Easier Management**:
   - By separating available sites (`sites-available`) from active sites (`sites-enabled`), you can easily enable or disable specific sites without deleting their configuration files.

---

### **How It Works**
1. **Create a Configuration File**:
   - You create a configuration file for your site in sites-available. For example:
     ```bash
     sudo nano /etc/nginx/sites-available/mywebsite
     ```

2. **Enable the Site**:
   - To enable the site, create a symbolic link from sites-available to sites-enabled:
     ```bash
     sudo ln -s /etc/nginx/sites-available/mywebsite /etc/nginx/sites-enabled/
     ```

3. **Reload Nginx**:
   - After enabling the site, reload Nginx to apply the changes:
     ```bash
     sudo systemctl reload nginx
     ```

4. **Disable the Site**:
   - To disable the site, remove the symbolic link from sites-enabled:
     ```bash
     sudo rm /etc/nginx/sites-enabled/mywebsite
     ```
   - Then reload Nginx:
     ```bash
     sudo systemctl reload nginx
     ```

---

### **Why Use This Convention?**
- **Organization**: Keeps all site configurations in one place (`sites-available`), even if they are not currently active.
- **Flexibility**: Allows you to quickly enable or disable sites without deleting their configuration files.
- **Best Practice**: This is a widely used convention in Nginx, making it easier for administrators to manage multiple sites.

---

### **Important Notes**
- The sites-available and sites-enabled directories are not mandatory. They are a convention, not a requirement. You can define all your site configurations directly in the main Nginx configuration file (`/etc/nginx/nginx.conf`), but this is not recommended for managing multiple sites.
- Always test your Nginx configuration after making changes:
  ```bash
  sudo nginx -t
  ```