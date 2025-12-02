# SeceoKnight_with_N8N

# Step 1: Deploy your Ubuntu machine on Virtual or AWS.

# Step 2: Install N8N using following steps for your convenience.

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


# step 3: after complete installation you have to access n8n by using provided url by n8n after compplete installation.

# step 4: then Simply you have create your own workflow or simply impport my provided workflows. 
ex. SeceoKnight Alert - IP Reputation check.json

# Wazuh/SeceoKnight Server side Configuration to receive alert in our workflow.

1. add the script custom-n8n in path - /var/ossec/integrations/

       nano /var/ossec/integrations/custom-n8n

2. Permission and ownership of script :

       chmod 750 custom-n8n
       chown root:wazuh custom-n8n

3. add the integration block inside /var/ossec/etc/ossec.conf

        <integration>
          <name>custom-n8n</name>
          <hook_url>https://9eight9.seceokniight.online/webhook-test/e645d98e-f80c-47e5-b96e-762c96f3db76</hook_url> <!-- Replace with your n8n hook URL -->
          <!-- <level>4</level> -->
          <rule_id>81606</rule_id> <!-- Replace rule id's which you want to send to our workflow -->
          <alert_format>json</alert_format>
        </integration>

4. Restart the server.

       sudo systemctl restart wazuh-manager


REsult for - ✅SeceoKnight Alert - IP Reputation Check



