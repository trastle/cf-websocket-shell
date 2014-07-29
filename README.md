
http://www.iamjambay.com/2013/12/send-interactive-commands-to-cloud.html


cf push websocket-demo -c '/app/websocketd --port=$PORT --dir=/app/ --devconsole'


## Rebuilding this from scratch

To build this directory from scratch you need to do the following:

    $ # Make a directory for your work
    $ mkdir websocketd-demo
    $ cd websocketd-demo

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
    
    