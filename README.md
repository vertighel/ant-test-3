This is the same example as in https://github.com/vertighel/ant-test, but uses json and appends some properties of the sender, taken from the configuration file.

# Install node

From:
http://yoember.com/nodejs/the-best-way-to-install-node-js/

On Linux (other OS are treated in the previous link):

```bash
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.2/install.sh | bash	

nvm list
nvm ls-remote
nvm install 7.10.0
nvm use 7.10.0
nvm alias default 7.10.0
node -v
npm install -g npm
npm -v

```

On Mac, add the following line in `.bash_profile`:

```bash
source ~/.nvm/nvm.sh
```

# Clone this repository

```bash
git clone https://github.com/orsa-unige/ant-test-3.git

```
# Install missing modules

```bash
npm -f install

```
# Install `ruby`  order to get `sass`, then install `sass`

On Debian-based distributions:

```bash
sudo apt-get install ruby ruby-dev
sudo su -c "gem install sass"
```
- if you want to modify the sass file to extend the CSS, then `sass --watch style.sass:style.css` in order to dinamically compile the `sass` file into `css` at each saving

# Launch the project

 - Launch the websocket server,
 - launch the webserver,
 - open the html page and send messages;
 - launch all the websocket client you want, they will send random pairs of numbers.
 - open the node console to send messages to the server directy from the console, and to enable/disable page elements:
 ```node
var s=require("./sendtest.js")
s.send({x:1, y:2})
s.disable("button")
s.enable("button")
```

The server will recieve messages from connected peers and it will dispatch these messages back, such as in an IM chat. The messages from the ws clients will appear as list items; the messages from the webpage will appear on the box.
