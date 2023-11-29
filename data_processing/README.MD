# Date pre-processing and ML model traning. 


### Content 

1. Crating list of all the data collected and get summary of data on hand. 

2. Preparing dataset for ANN traning 



---
### Remote Server Setup 

1. Install ubuntu desktop 
   (In future needs to run ROS)

2. Install net tools
   ```consol
   sudo apt install net-tools
   ``` 

3. Install ubuntu server
   ```consol
   sudo apt install ubuntu-server
   ```
4. Open ssh server  [ref](https://www.cyberciti.biz/faq/how-to-install-ssh-on-ubuntu-linux-using-apt-get/)
    Install
    ```consol
    sudo apt-get install openssh-server
    ```

    Enable ssh server
    ```consol
    sudo systemctl enable ssh
    ```

    Start/ stop/ restart ssh
    ```consol
    sudo systemctl start ssh
    sudo systemctl stop ssh
    sudo systemctl restart ssh
    ```

    Status ssh server

    ```consol
    sudo systemctl status ssh
    ```

    Allow firewall
    ```consol
    sudo ufw allow ssh
    ```

5. Remove desktop GUI [ref](https://www.cyberciti.biz/faq/switch-boot-target-to-text-gui-in-systemd-linux/)
    ```consol
    systemctl get-default
    sudo systemctl set-default multi-user.target 
    sudo systemctl reboot
    ```
7. Activate desktop GUI 
    ```consol
    systemctl get-default
    sudo systemctl set-default graphical.target
    sudo reboot
    ```

### Connect to Remote Server

1. In wondows: Install "Putty"

    In ubuntu: install open ssh client in desktop or laptop

    ```consol
    sudo apt-get update
    sudo apt-get upgrade
    sudo apt-get install openssh-client
    ```

2. Connect to the remote server 
    In Windows: 
    User 1: malithjkd@<server_IP> port 80
    User 2: rnd_server@<server_IP> port 80

    In Ubuntu 

    ```consol
    ssh malithjkd@192.168.3.30
    ```

### First time jupyter setup work (user setup)

1. Install conda and required packages using termail

2. activate conda enviroment

    ```console
    conda activate base
    ```
    to see the evriroment list

    ```console
    conda env list
    ```

    to see which python is running

    ```console
    which python
    ```


2. Check jupyter folder is avelable at "/home/malithjkd"
    ```consol
    ls -all
    ``` 
    
    If not create folder for jupyter

    ```console
    mkdir .jupyter
    ```

3. Create password for jupyter notebook

    ```console
    jupyter lab password
    
    ```
    enter password 2 times

4. Start jupyter notbook server without browser and specific port

    ```console
    jupyter lab --no-browser --port=9996
    ```


## Local pc setup for Jupyter notebook setup

### connect local pc localhost to server localhost

In wondows : use CMD
In Ubutntu : use termilal

```console
ssh -N -f -L localhost:9006:localhost:9996 malithjkd@192.168.3.30
```

Then start browser to give url

```console
localhost:9006
```

jupyter notebook should work now !!!


#### To copy files from local pc to server
go to the file location 

```console
cd

scp *.png malithjkd@192.168.1.53:home/
```


