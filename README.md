# EymenArm
In this project, a remote controlled servo based robot arm is coded and designed.


import time 
import serial 
import RPi.GPIO as GPIO

GPIO.setmode(GPIO.BCM)
GPIO.setup(17, GPIO.OUT)
GPIO.setup(18, GPIO.OUT)
GPIO.setup(27, GPIO.OUT)
GPIO.setup(22, GPIO.OUT)
GPIO.setup(23, GPIO.OUT)
GPIO.setup(24, GPIO.OUT)
s1 = GPIO.PWM(17, 50) # GPIO 17 for PWM with 50Hz
s2 = GPIO.PWM(18, 50)
s3 = GPIO.PWM(27, 50)
s4 = GPIO.PWM(22, 50)
s5 = GPIO.PWM(23, 50)
s6 = GPIO.PWM(24, 50)
s1.start(2.5) # Initialization
s2.start(5) # Initialization
s3.start(5) # Initialization
s4.start(5) # Initialization
s5.start(5) # Initialization
s6.start(5) # Initialization


ser = serial.Serial(
port='/dev/rfcomm0', 
baudrate = 9600, 
parity=serial.PARITY_NONE, 
stopbits=serial.STOPBITS_ONE, 
bytesize=serial.EIGHTBITS, 
timeout=1 
    )

###################
counter=0

while 1:
    ser.readline()
    print x
    





angle = 2.5
speed = 0.1
s1.ChangeDutyCycle(angle)
"""servo_01"""

while 1:
    s1.ChangeDutyCycle(2.5)
    x=ser.readline()
    x = x.decode("utf-8")
    if not x == "":
        print ("gelen veri:", x)
        liste1 = x.split("x")#yeni apk ile x.split("x") yap
        if liste1[0] == "s1":#yeni apk ile bunu yapıştır if liste1[0] == "s1":
            aci = int(liste1[1].split(".")[0])
            angle = (aci/180*10) + 2.5
            if angle < 2.5:
                angle = 2.5
            elif angle > 12.5:
                angle = 12.5
            s1.ChangeDutyCycle(angle)
        else:
            print(liste1[0])
    
        """servo_02"""
        
        liste1 = x.split("x")#yeni apk ile x.split("x") yap
        if liste1[0] == "s2":#yeni apk ile bunu yapıştır if liste1[0] == "s1":
            aci = int(liste1[1].split(".")[0])
            angle = (aci/180*10) + 2.5
            if angle < 2.5:
                angle = 2.5
            elif angle > 12.5:
                angle = 12.5
            s2.ChangeDutyCycle(angle)
            
        """servo_03"""
        
        liste1 = x.split("x")#yeni apk ile x.split("x") yap
        if liste1[0] == "s3":#yeni apk ile bunu yapıştır if liste1[0] == "s1":
            aci = int(liste1[1].split(".")[0])
            angle = (aci/180*10) + 2.5
            if angle < 2.5:
                angle = 2.5
            elif angle > 12.5:
                angle = 12.5
            s3.ChangeDutyCycle(angle)

        """servo_04"""

        liste1 = x.split("x")#yeni apk ile x.split("x") yap
        if liste1[0] == "s4":#yeni apk ile bunu yapıştır if liste1[0] == "s1":
            aci = int(liste1[1].split(".")[0])
            angle = (aci/180*10) + 2.5
            if angle < 2.5:
                angle = 2.5
            elif angle > 12.5:
                angle = 12.5
            s4.ChangeDutyCycle(angle)

        """servo_05"""

        liste1 = x.split("x")#yeni apk ile x.split("x") yap
        if liste1[0] == "s5":#yeni apk ile bunu yapıştır if liste1[0] == "s1":
            aci = int(liste1[1].split(".")[0])
            angle = (aci/180*10) + 2.5
            if angle < 2.5:
                angle = 2.5
            elif angle > 12.5:
                angle = 12.5
            s5.ChangeDutyCycle(angle)
            
        """servo_06"""

        liste1 = x.split("x")#yeni apk ile x.split("x") yap
        if liste1[0] == "s6":#yeni apk ile bunu yapıştır if liste1[0] == "s1":
            aci = int(liste1[1].split(".")[0])
            angle = (aci/180*10) + 2.5
            if angle < 2.5:
                angle = 2.5
            elif angle > 12.5:
                angle = 12.5
            s6.ChangeDutyCycle(angle)

        print("donusturulmus aci:", angle)
        print("gelen aci degeri:", aci)
        print("/"*50)
        
