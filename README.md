# resume-verification-blockchain
# Resume Information Verification

This folder contains a demonstration of basic resume information verification using blockchain. The agents provide a web browser interface to show establishing relationships between agents, issuing verifiable credentials, and proving claims from verifiable credentials. We wrote the entire project using HyperLedger Indy.

## Prerequisites

The only prequisite (other than a browser) is an account with [Docker Hub](https://hub.docker.com). Docker Hub is the "Play Store" for the [Docker](https://docker.com) ecosystem.

## Installing the Demonstration

Go to the [Play with Docker](https://labs.play-with-docker.com/) and (if necessary) login. This site is operated by Docker to support developers learning about Docker.


Click the "Start" button to start a Docker sandbox you can use to run the demo, and then click the `+Add an Instance` link to start a terminal in your browser. Within the terminal that is visible in your browser, run the following commands:


cd resume-verification-blockchain/src/indy-material/nodejs


## Starting the Demonstration

The steps for running the demonstration are:

- Run the command `./manage build` to build the components of the software
- Run the command `./manage up` to run the components

It takes a while for the demo to start&mdash;lots of things are happening. The logs for all of the containers will display in the terminal window. Logs show the output of both the Blockchain Ledger nodes communicating and the Indy agents starting up and communicating with the ledger.

Things to watch for as the demo starts up:

- You should periodically see things like "Listening on port 3001," which indicates an Agent is up and running.
- You should **not** see a stack trace error in the code&mdash;that would indicate a problem.
- You should **not** see any "Container exiting" messages, indicating containers not starting up properly.
- There should be 10 docker containers running. You can hit `ctrl-c` to exit the log viewer and run the command `docker ps` to see all of the containers running.
  - To get back to seeing the scrolling logs, run `./manage logs`.
- Once the output slows significantly and you only see messages from the nodes (the containers running the ledger), everything should be working.

### Accessing the ledger and agents in a web browser:

As the project starts up, a series of four digit numbers will appear above the terminal. Those are the exposed ports of the running containers and the numbers are links to start a browser tab accessing that port.

To go through the demonstration, click the following numbers from the list:

- **3000** for Student
- **3002** for IIIT Hyderabad	
- **3003** for Google INDIA

If you click the links before the agent is active, you might get a `Connection reset by peer` error messages. Monitor the logs and wait longer and then try again.



## Stopping the Demo

To stop the demo, go to the browser tab where you ran `docker-compose up`, click the red `Close Session` button on the left and close the browser tab. Note that if you don't close the session or the tab, the terminal session will expire 4 hours after you started it.



