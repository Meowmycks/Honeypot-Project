# Creating and Managing a Honeynet

## Objective
> Create a honeynet using MHN-Admin. Present your findings as if you were requested to give a brief report of the current state of Internet security. Assume that your audience is a current employer who is questioning why the company should allocate anymore resources to the IT security team.

### MHN-Admin Deployment (Required)

**Summary:** How did you deploy it? Did you use GCP, AWS, Azure, Vagrant, VirtualBox, etc.?

- [x] I deployed the MHN Admin server with Ubuntu 16.04 Minimal using Google Cloud Services.
- [x] The setup:
  - Create a Google Cloud Services account and project.
  - Using Command Prompt, configure and deploy the server.
  - Allow HTTP traffic and inbound traffic on all ports.
  - Using Command Prompt, SSH into the server using the external IP.
  - in the opened window, install MHN by executing the following commands:
      - sudo apt-get update
      - sudo apt-get install git python-magic -y
      - $ cd /opt/
      - $ sudo git clone https://github.com/pwnlandia/mhn.git
      - $ cd mhn/
      - $ sudo sed -i 's/Flask-SQLAlchemy==2.3.2/Flask-SQLAlchemy==2.5.1/g' server/requirements.txt
      - $ sudo ./install.sh
  - Whenever prompted, answer n or blank

![deploy-mhn-admin](https://user-images.githubusercontent.com/45502375/142711009-354963be-1ea6-465d-a43d-3cf5cc165bd3.gif)


### Dionaea Honeypot Deployment (Required)

**Summary:** Briefly in your own words, what does dionaea do?

Dionaea tries to capture or trap malware that exploit vulnerabilities exposed by services offered over a network, and ultimately obtain a copy of the malware.

The Dionaea honeypot was deployed the same way the MHN Admin server was deployed, using MHN's prewritten scripts instead.

![deploy-dioanaea-honeypot](https://user-images.githubusercontent.com/45502375/142711013-bbd790e2-712f-45b3-bde3-e19e961c381c.gif)


### Database Backup (Required) 

**Summary:** What is the RDBMS that MHN-Admin uses? What information does the exported JSON file record?

MHN-Admin uses the MongoDB RDBMS. This is made evident when using the given command to export the _sessions.json_ file. The JSON file records the protocl attacked, the source and destination IP and port, and the time and date of the attack, among other things.

![get-database-backup](https://user-images.githubusercontent.com/45502375/142714049-78c23eea-b1a4-4ab5-9310-22b4cf48932a.gif)


## Notes

Describe any challenges encountered while doing the assignment.

Attempting to use Google Cloud Services via web browser was ironically more complicated than using it via Command Prompt.
