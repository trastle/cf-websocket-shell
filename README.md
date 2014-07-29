# cf-websocket-shell

This is a convenience repo to create a websockets "shell" into a Cloud Foundry Warden Container. The work is taken from @jambay and I've put it here for personal ease of use.

To Read the original source of this work you'll need to look elsewhere

* [iamjambay.com - Send Interactive Commands to a Cloud Foundry App with websocketd](http://www.iamjambay.com/2013/12/send-interactive-commands-to-cloud.html)
* [YouTube - Websocketd and cloud foundry apps](http://www.youtube.com/watch?v=aRq38DEa-gE)

# Usage 

Using the app in this repo:


1. Clone this repo:

       $ git clone 

2. Push the application to your Cloud Foundry install:

       $ cf push websocket-demo -c '/app/websocketd --port=$PORT --dir=/app/ --devconsole'

3. Open your app in the browser with a URL similar to the following:<br>
   ```https://websocket-demo.your-cf.com/bash.sh```

4. Open the connection by entering the secure websocket URL in the colsole and hitting the tick:<br>
   ```wss://websocket-demo.your-cf.com/bash.sh```
       
5. Type the commands you want to evaluate at the send prompt

    ![image](http://i.imgur.com/sOMnMC6.png?1)
       
       
# Rebuilding this from scratch

You can re-create the repository checked in here by running the following:

    $ # Make a directory for your work
    $ mkdir cf-websocket-shell
    $ cd cf-websocket-shell

    $ # Create a default rails App
    $ gem install rails
    $ rails new .
    $ bundle install
    
    $ # Download websocketd
    $ wget https://github.com/joewalnes/websocketd/releases/download/v0.2.9/websocketd-0.2.9-linux_amd64.zip
    $ unzip websocketd-0.2.9-linux_amd64.zip
    $ rm websocketd-0.2.9-linux_amd64.zip
    
    $ # Grab @jambay's bash "shell"
    $ curl https://raw.githubusercontent.com/jbayer/websocketd-cloudfoundry/master/bash.sh > bash.sh
    $ chmod 755 bash.sh
    