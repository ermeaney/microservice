# Microservice Framework - Mesos/Marathon, Docker, Weave and Flocker

**Youtube Video: https://youtu.be/-AMdZjGXMCo**

**Use Vagrant 1.8.6 or up**

##Instruction:
1. **Clone the git**

   `git clone https://github.com/reza-rahim/microservice`

2. **Change the dir**

   `cd microservice`

3. **Bring Vagrant machines up**

   `vagrant up`

4. **Log in to mgmt vagrant box**

   `vagrant ssh mgmt`

5. **Build the mesos/marathon cluster**

   `./mesos_build_cluster.sh`

  1. mesos ui: http://10.0.15.11:5050/  
  2. matathon: http://10.0.15.11:8080/

6. **Deploy the nginx, Node.js and Mongo Db Application**

   ```
   source /etc/bash.bashrc

   ./mesos_deploy_app.sh
    ```
  1. Application UI: http://10.0.15.11:9080/

 **At this point, you can move to `Overview of the Framework`. After understanding the system, you can comeback and perform the next three steps**
 
7. **Scale up Node.js app from 2 instance to 3 instance**
 
   `./mesos_deploy_scaleup_app.sh`
   

8. **Move the Mongo DB from 10.0.15.12 to 10.0.15.13, the data movement is done by flocker with ZFS file system.**

   `./mesos_move_db.sh`

9. **Start the weave scope**

   `./mesos_weave_scope.sh`

  1. Weave Scope UI: http://10.0.15.10:4040 
