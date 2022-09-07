# node-js-CICD-pipeline-jenkins
test-manual

sudo apt-get install git
Clone our node app repo:

git clone https://github.com/<username>/node-app.git
Navigate into the project folder and install app dependencies:

cd node-app
npm install — production
Before we can access our app on the browser we need to complete an additional step. As you recall we are running our app on port 3000 by default. DigitalOcean firewall blocks clients accessing any port but 80. Thankfully Ubuntu includes UFW firewall configuration tool that adds firewall rule to unblock specific ports.

Let’s unblock port 3000 and run our app:
  
sudo ufw allow 3000
node index.js
Now you can access your node app by appending the PORT to your IP address:

http://NODE.SERVER.IP:3000
  
  
# Let’s install PM2 and start our node instance:

sudo npm install pm2@latest -g
pm2 start index.js
Now our node server is configured and running.
  
Make our new script file executable:

chmod +x script/deploy
  
  
# Commit and push:

git add .
git commit -m ‘add deployment script’
git push origin master
  
  
# After you push you should see Jenkins Job starts. 
When complete, you should see your changes on http://NODE.SERVER.IP:3000
  
 
