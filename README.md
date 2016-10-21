# Microservice Framework - Mesos/Marathon, Docker, Weave and Flocker

https://youtu.be/-AMdZjGXMCo


Instruction :

- Clone the git <br>
git clone https://github.com/reza-rahim/microservice

- Chnge the dir<br>
cd microservice

- Bring Vagrant machine up <br>
vagrant up

- Log in to mgmt vagrant box <br>
vagrant ssh mgmt

- Build the mesos/marathon cluster<br>
./mesos_build_cluster.sh

  mesos ui: http://10.0.15.11:5050/  
  matathon: http://10.0.15.11:8080/

- Deploy the nginx, Node.js and Mongo Db Application <br>
source /etc/bash.bashrc <br>
./mesos_deploy_app.sh

  Application UI: http://10.0.15.11:9080/

- Scale up Node.js app from 2 instance to 3 instance<br>
./mesos_deploy_scaleup_app.sh

- Move the Mongo DB from 10.0.15.12 to 10.0.15.13, the data movement is done by flocker with ZFS file system. <br>
./mesos_move_db.sh

- Start the weave scope <br>
./mesos_weave_scope.sh

  Weave Scope UI: 10.0.15.10:4040 