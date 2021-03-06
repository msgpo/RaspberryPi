## updating
- Due to the Raspbian GNU/Linux 9.9 (stretch) is not compatible with our Multli Adapter board V2.1, we have updated our board to    support     new firmware.
### for the version 9.9 above firmware,you can use our new board.
![Alt text](https://github.com/ArduCAM/RaspberryPi/blob/master/data/Multi_Cam_Adapter_Board_v2.1.1.jpg)


## Quickly start
  - Run the below command to install the PyQt5 module
  ```Bash
  sudo apt-get install python-pyqt5
  ```
  - Run the below command to install the cv2 module
  ```Bash
  sudo apt-get install python-opencv
  ```

## Configuration
- Enable the camera 
- Configure the i2c1 

![Alt text](https://github.com/ArduCAM/RaspberryPi/blob/master/data/cfg_i2c1_1.png)

![Alt text](https://github.com/ArduCAM/RaspberryPi/blob/master/data/cfg_i2c1_2.png)
- Download the RaspberryPi library 
```bash
git clone https://github.com/ArduCAM/RaspberryPi.git
```
- Go to RaspberryPi/Multi_Camera_Adapter/Multi_Adapter_Board_4Channel/Multi_Camera_Adapter_V2.2 folder
```Bash
cd RaspberryPi/Multi_Camera_Adapter/Multi_Adapter_Board_4Channel/Multi_Camera_Adapter_V2.2
```
- Run the below command to init and check the camera
```Bash
sudo ./init_camera.sh
```
-If anything is normal, you will see below message
![Alt text](https://github.com/ArduCAM/RaspberryPi/blob/master/data/check_msg.png)
## Add support for Pi4 B
- Just a quick post to let you know that you’ll need a new wiringPi for the Raspberry Pi 4B.
- To upgrade:
```bash
cd /tmp
```
```bash
wget https://project-downloads.drogon.net/wiringpi-latest.deb
```
```bash
sudo dpkg -i wiringpi-latest.deb
```

- Run the below command to start the demo
- opencv2.0
```Bash
sudo python 4cam_cv2.py
```
- opencv3.0
```Bash
sudo python 4cam_cv3.py
```
![Alt text](https://github.com/ArduCAM/RaspberryPi/blob/master/data/Multi_Camera_Adapter_Board_openCV3.0.png)
- Operation video demo link
```bash
 https://youtu.be/DRIeM5uMy0I
```

## Troubleshoot
- Can't find video0 
	- check if the i2c bus is normal
		- add dtparam=i2c_vc=on to /boot/config.txt,then reboot 
		- run i2cdetect -y 0 to check the devive's address.
		- if it does not detect the device's address, please check the ribbon cable connection to ensure it is not reversed.
		

