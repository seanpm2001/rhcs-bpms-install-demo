App Dev Cloud with JBoss BPM Suite Install Demo 
===============================================
This demo is to install JBoss BPM Suite in the Cloud based on leveraging any Red Hat OpenShift container based platform such as:

 - [Red Hat Container Platform (OCP)](https://github.com/redhatdemocentral/ocp-install-demo)
  
It delivers a fully functioning JBoss BPM Suite containerized on OSE.


Install JBoss BPM Suite OpenShift
---------------------------------
1. First ensure you have an OpenShift container based installation, such as one of the followling installed first:

  - [OCP Install Demo](https://github.com/redhatdemocentral/ocp-install-demo)

  - or your own OpenShift installation.

2. [Download and unzip this demo.](https://github.com/redhatdemocentral/rhcs-bpms-install-demo/archive/master.zip)

3. Download JBoss EAP & JBoss BPM Suite, add to installs directory (see installs/README).

4. Run 'init.sh' or 'init.bat' file. 'init.bat' must be run with Administrative privileges:
```
   # The installation needs to be pointed to a running version
   # of OpenShift, so pass an IP address such as:
   #
   $ ./init.sh 192.168.99.100  # example for OCP.
```

Now log in to JBoss BPM Suite to start developing containerized BPM projects (the address will be generated by OCP):

  - Find the exposed serivce (login to JBoss BPM Suite Business Central) by selecting the Project - Applications - Routes - Hostanme
    URL.

  - OCP example: [http://rhcs-bpms-install-demo-appdev-in-cloud.192.168.99.100.nip.io/business-central](http://rhcs-bpms-install-demo-appdev-in-cloud.198.168.99.100.nip.io/business-central)  ( u:erics / p:bpmsuite1! )

5. Not sure how to get started with JBoss BPM Suite? Try one of these <a href="https://bpmworkshop.github.io/#/5"
	 target="_blank">online workshops</a> to build a first project from scratch.

Notes
-----
This project can be installed on any OpenShift platform, such as OpenShift Container Platform.
It's possible to install it on any available installation by pointing this installer to an OpenShift IP address:
```
  $ ./init.sh IP
```

If for any reason the installation breaks or you want a new JBoss BRMS installation, just remove the project rhcs-bpms-install-demo
entry in the OpenShift console and re-run the installation.

To clone a repository in the running container, the following actions would need to occur from a developer's machine.

1. Execute port forwarding through the OpenShift CLI. This will open a tunnel between the developer's machine and the pod through the OpenShift API pod proxy. The command window will block while the session is open:

   ```
   # Read-write access to repo on port 8001.
   #
   $ oc port-forward $(oc get pod -l=deploymentconfig=rhcs-bpms-install-demo --template='{{ range .items }} {{ .metadata.name }} {{ end }}') 8001:8001
   ```

2. Clone the repository. In another window, clone the remote repository after logging in to Business Central, creating a repository and identifying the repository URL in the Admin Perspective (this example is a BackOffice repository):

   ```
   # Read-write access to repo on port 8001.
   #
   $ git clone git://localhost:8001/BackOffice
   ```


Supporting Articles
-------------------
- [Holiday Homework - Red Hat Cloud demo updates](http://www.schabell.org/2016/12/holiday-homework-redhat-cloud-demo-updates.html)

- [App Dev in the Cloud: How To Run JBoss BPM Suite in a Container](http://www.schabell.org/2016/11/appdev-cloud-howto-run-jboss-bpmsuite-in-container.html)

- [Rocking App Dev in the Cloud with JBoss BPM Suite Install Demo](http://www.schabell.org/2016/03/rocking-appdev-in-cloud-jboss-bpmsuite-install-demo.html)


Released versions
-----------------
See the tagged releases for the following versions of the product:

- v1.7 - JBoss BPM Suite 6.4.0 and JBoss EAP 7.0.0 with OpenShift genereated routes and service URLs.

- v1.6 - JBoss BPM Suite 6.4.0 and JBoss EAP 7.0.0 running on any given OpenShift installation and loading mulitple projects.

- v1.5 - JBoss BPM Suite 6.4.0 and JBoss EAP 7.0.0 running on any given OpenShift installation and port forwarding for git repo access configured.

- v1.4 - JBoss BPM Suite 6.4.0 and JBoss EAP 7.0.0 running on any given OpenShift installation.

- v1.3 - JBoss BPM Suite 6.3.0 and JBoss EAP 6.4.7 running on any given OpenShift installation.

- v1.2 - JBoss BPM Suite 6.3.0 and JBoss EAP 6.4.7 running on Red Hat CDK.

- v1.1 - JBoss BPM Suite 6.2.0.GA-redhat-1-bz-1334704 and JBoss EAP 6.4.4 running on Red Hat CDK.

- v1.0 - JBoss BPM Suite 6.2.0-BZ-1299002, JBoss EAP 6.4.4 and running on Red Hat CDK using OpenShift Enterprise image. 

![OCP console](https://github.com/redhatdemocentral/rhcs-bpms-install-demo/blob/master/docs/demo-images/rhcs-bpms-ocp-console.png?raw=true)

![OCP build](https://github.com/redhatdemocentral/rhcs-bpms-install-demo/blob/master/docs/demo-images/rhcs-bpms-build-ocp.png?raw=true)

![OCP pod](https://github.com/redhatdemocentral/rhcs-bpms-install-demo/blob/master/docs/demo-images/rhcs-bpms-pod-ocp.png?raw=true)

![JBoss BPM Suite OCP console](https://github.com/redhatdemocentral/rhcs-bpms-install-demo/blob/master/docs/demo-images/jboss-bpms-ocp-console.png?raw=true)

![JBoss BPM Suite OCP](https://github.com/redhatdemocentral/rhcs-bpms-install-demo/blob/master/docs/demo-images/jboss-bpms-ocp.png?raw=true)

![Cloud Suite](https://github.com/redhatdemocentral/rhcs-bpms-install-demo/blob/master/docs/demo-images/rhcs-arch.png?raw=true)


