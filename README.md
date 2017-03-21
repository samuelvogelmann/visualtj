# VisualTJ
<img src="/images/visualtj.png" width="100%">

> Make your robot see and recognize the world

## How it works
-
-
-
-

## Hardware Requirements and Setup

- [Raspberry Pi 3](https://www.amazon.com/dp/B01C6Q2GSY/ref=wl_it_dp_o_pC_nS_ttl?_encoding=UTF8&colid=1BLM6IHU3K1MA&coliid=I1WPZOVL411972)
- [Raspberry Pi camera module](https://www.amazon.com/Raspberry-Pi-Camera-Module-Megapixel/dp/B01ER2SKFS/ref=sr_1_1?ie=UTF8&qid=1486759306&sr=8-1&keywords=raspberry+pi+v2+camera)
- [Speaker with 3.5mm audio jack](https://www.amazon.com/gp/product/B014SOKX1E/ref=oh_aui_detailpage_o00_s00?ie=UTF8&psc=1)
- [IBM TJBot](http://ibm.biz/mytjbot): You can 3D print or laser cut the robot

Follow the step-by-step instructions on [instructables](http://www.instructables.com/id/) to assemble and prepare your RaspberryPi/TJBot to run the code.

## Build the Application

### Install Node-RED
At first check if Node-RED is already installed on your Pi. Since November 2015 release of Raspbian Jessie NodeREDcomes preinstalled on the os image. If not, open a terminal application on the Pi and execute the following commands to install the latest version of NodeRED and npm (Node Package Manager):

	sudo aptget update
	sudo aptget distupgrade
	curl sL https://deb.nodesource.com/setup_6.x | sudo -E -bash 
	sudo aptget install -y nodejs
	sudo npm install -g node-red

You can troubleshoot [here](http://nodered.org/docs/getting-started/installation).

### Install IBM Watson Services Nodes
Execute the following commands from a terminal to install the collection of Node-RED nodes for IBM Watson Services:
	
	cd ~/.nodered
	npm install noderednodewatson
	
You will then need to restart Node-RED.

### Start and access Node-RED
You have installed Node-RED as a global npm package, so you can execute the following commands from a terminal to start Node-RED:

	nodered

After Node-RED has started, you can access the browser-based flow editor at http://localhost:1880 with a browser on your Pi.

### Download and Import the Sample Flow
Clone or download the repository to get the sample flow.

	git clone git@github.com:samuelvogelmann/visualtj.git
	cd visualtj

Copy the content of the 'flow.json' file to clipboard. Go to http://localhost:1880 and import the flow using the import function. In the upper right corner click on the menu bar, then 'Import Form' > 'Clipboard' to import the flow.

<img src="/images/flow-import.png" width="100%">

Paste the sample flow into the "Paste nodes here" field and click 'Import'.

### Update your Bluemix Credentials
In this step, you get API access to the Watson services used in this recipe.

You need to update the Visual Recognition node within your flow with your Visual Recognition credentials.


## Run the Application

Finally click the red 'Deploy' button in the upper right corner to deploy your flow. Now you can access the application at
http://localhost:1880/tjvisual


## Whats Next?

There are a few things you can do .. and ways to take your robot forward!
- Train the Visual Recognition service to improve its classification capabilites. This tutorial and the documentation will help you creating you own custom classifier.


## Contributing and Issues

To contribute, please feel free to fork the repo and send in a pull request.
Also, if you find any issues (bugs, etc) or have questions, please feel free to open up a [github issue](https://github.com/victordibia/tjwave/issues/new).


## Dependencies List

- Watson Developer Cloud: [Watson visual Recognition](https://www.ibm.com/watson/developercloud/visual-recognition.html) and [Watson Text to Speech](https://www.ibm.com/watson/developercloud/text-to-speech.html)
- [Node-RED](http://nodered.org/)
- [Node-Red nodes for Watson services](https://flows.nodered.org/node/node-red-node-watson)


## License

MIT License
