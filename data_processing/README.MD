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
    User 1: malithjkd@192.168.3.30
    User 2: rnd_server@192.168.3.30

    In Ubuntu 

    ```consol
    ssh rnd_server@192.168.3.30
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
    jupyter notebook password
    
    ```
    enter password 2 times


## Start jupyter notebook in Server end

Go to file location 

```consol
cd /...
```

Start jupyter notbook server without browser and specific port

```console
jupyter notebook --no-browser --port=9996
```


## Local pc setup for Jupyter notebook setup

### connect local pc localhost to server localhost

In wondows : use CMD
In Ubutntu : use termilal

```console
ssh -N -f -L localhost:9006:localhost:9996 rnd_server@192.168.3.30
```
If no feedback after password

Then start browser to give url [localhost:9006](http://localhost:9006/)

```consol
localhost:9006
```

jupyter notebook should work now !!!


#### To copy files from local pc to server
Windows : Use [FileZilla client](https://filezilla-project.org/download.php?platform=win64) 

Ubuntu : use scp  

```console
cd /home/...

scp *.png malithjkd@192.168.3.30:home/
```


