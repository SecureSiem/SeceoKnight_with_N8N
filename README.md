# SeceoKnight_with_N8N

Step 1: Deploy your Ubuntu machine on Virtual or AWS.

Step 2: Install N8N using following steps for your convenience.

# Download this script on your ubuntu machine.

    wget https://raw.githubusercontent.com/SecureSiem/SeceoKnight_with_N8N/refs/heads/main/install-n8n.sh

# ⚙️ Run the Installer

Use the following command to run the script with your own domain and email address:

    sudo -E DOMAIN="<your-domain-or-subdomain>" EMAIL="<your-email-id>" bash install-n8n.sh

Example: 

    sudo -E DOMAIN="n8n.gobotify.com" EMAIL="admin@gobotify.com" bash install-n8n.sh

# NOTE:
# Setting up your domain for the N8N server

1. Go to Hostinger and purchase a domain.

2. After that, navigate to the Domains Overview section.

3. Click on Manage DNS Records and add a new record for your N8N server:

Type: A

Name: 9eight9

Points to: (Public static IP of your Ubuntu server)

4. Save the record.

After this, your N8N access URL will be: example - 9eight9.yourdomain.com. ( as we add in above command for installation time).



