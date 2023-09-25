### Flush DNS cache on MacOS

    sudo dscacheutil -flushcache; sudo killall -HUP mDNSResponder

### Swap tilde key on Mac keyboard

    https://gist.github.com/thomasstxyz/1a64875ce2c57e9e3c649b6f70fc9066

### Get application which listens on specific port

    sudo lsof -i -P | grep LISTEN | grep :$PORT

### 3rd party software tools for MacOS

https://github.com/ther0n/UnnaturalScrollWheels 

https://mousefix.org

https://iterm2.com/index.html

### Install Npm & Yarn

Download & Install Node.js from the website:

https://nodejs.org/en/download

Allow user to install packages globally:

    sudo chown -R $(whoami) $(npm config get prefix)/{lib/node_modules,bin,share}

Install Yarn:

    npm install --global yarn
