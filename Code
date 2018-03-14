import RPi.GPIO as GPIO
import time
import datetime
import sys


now = datetime.datetime.now()

#while(True):
#    now = datetime.datetime.now()
#    if(now.minute=="37" or now.minute==37): 
#         print("Curtains should go up")
#         break

PIN = 7

GPIO.setmode(GPIO.BOARD)

GPIO.setup(PIN,GPIO.IN)

stable = 0

#sys.exit(0)

up = False
down = False
count=0
while(True):
    inp = GPIO.input(PIN)==GPIO.LOW
    if(not inp):
        stable+=1
    else:
        stable-=1

    if(stable>10 and not up):
        print("The curtains should go up")
        up = True
        down = False
        stable=0
    elif(stable<-10 and not down):
        print("The curtains should go down")
        down = True
        up = False
        stable=0
    else:
        if(count>30):
            stable = 0

    count+=1
    time.sleep(1)
