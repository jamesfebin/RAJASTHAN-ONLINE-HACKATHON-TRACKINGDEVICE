# RAJASTHAN-ONLINE-HACKATHON-TRACKINGDEVICE
In today’s trend, we are continuously worried about the security of our child, daughter, wife, and mother and of course complete family. 
If they go somewhere we are continuously thinking about them and we don’t know if any problem suddenly comes up with them so in that case, we are unable to do any kind of action on it.safety is the major issue facing by the woman all around the world.

we have developed a system (prototype) comprises of software and hardware that can help user to send alert message to nearby police station and the emergency contact number.
 
we have made two separate project -:
1. hardware that send coordinates to the server 
2. android application(complementary project)


# hardware that send coordinates to the server

we are using ESP32 in our project having inbuilt Bluetooth and wifi module.
![bazaar549177_1](https://user-images.githubusercontent.com/19189211/42413423-3ced7df4-823d-11e8-90f8-30e8c851253b.jpg)
ESP32 is a series of low cost, low power system on a chip microcontroller with integrated Wi-Fi and dual-mode Bluetooth. The ESP32 series employs a Tensilica Xtensa LX6 microprocessor in both dual-core and single-core variations and includes inbuilt antenna switches, RF balun, power amplifier, low-noise receive amplifier, filters, and power management modules. 

function of ESP32 in  project is to connect to available Bluetooth device(mobile) of the user or available wifi of the environment and send geolocation data to the server. if the user pressed the reset button in an emergency.  server sends an alert message to the emergency number provided by the user and find nearby police station for reporting.

#### things required for the project
1. ESP32 module
2. arduino ide with esp32 board and library installed

ESP32 can post geolocation data to any server by using user mobile network access.we have used two services to see the power of ESP32 
1. ESP32 posting coordinates to FIREBASE
2. ESP32 sending an alert message with coordinates through IFTTT service


#### ESP32 posting coordinates to firebase
we have uploaded ESP_GEO_LOCATION_ON_FIREBASE.ino just copy the code in arduino ide to see it in action.
1. get the google apis keys -: https://console.developers.google.com/apis/dashboard?project=namanpractice&duration=PT1H
2. make the database in firebase console and note the name of server -:
![image1](https://user-images.githubusercontent.com/19189211/42413654-398a3fb2-8242-11e8-9293-dd956ed37bab.png)
3. get the database secret setting->projectsetting->service account
![image2](https://user-images.githubusercontent.com/19189211/42413676-8f07a4c0-8242-11e8-9714-54af5f54648c.png)

now you have a google apis key,servername and database secret you can replace them in code.
just upload ESP_GEO_LOCATION_ON_FIREBASE.ino uploaded above and happy code.

#### ESP32 sending an alert message with coordinates through IFTTT service
we are sending message with coordinates to all the people that we want.
IFTTT is the free way to get all your apps and devices talking to each other.
IFTTT -: https://ifttt.com/

Step 1: Visit www.IFTTT.com and sign up for new ID if you don’t have one already. After registering you will be sent a mail to your E-mail ID verify it and you will be logged into IFTTTT.

Step 2: Search for SMS Applet or visit this link-:https://ifttt.com/sms 
Now Register your Mobile number with that Applet here I have used the number “00919612365489” as an example number. Always include the leading “00” followed by your country code and then your mobile number. Here I am from India hence my country code is “91” and my mobile number is “96123456789”. Once the number is entered click on “Send Pin” and verify your mobile number.

![one](https://user-images.githubusercontent.com/19189211/42413741-55697d36-8244-11e8-8f7d-3ea2fd04f871.png)

Step 3: Now we have configured one Applet, we will another Applet called Maker Webhooks, so search for it or use this link -: https://ifttt.com/maker_webhooks
click on connect than you will prompt to this screen

![two](https://user-images.githubusercontent.com/19189211/42413771-c33690a6-8244-11e8-9bf6-7b691d946c1c.png)

Step 4: Now it is time to create our own Applet that could sync both the above applets. To do this navigate to My Applets -> New Applet, or follow this link -: https://ifttt.com/create?aea=true



 
 
