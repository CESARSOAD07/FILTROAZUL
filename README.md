# FILTROAZUL

import cv2
import numpy as np

cap = cv2.VideoCapture('http://192.168.1.67:4747/video')

lower_blue = np.array([80,60,20])
upper_blue = np.array([130,255,255])

while True:
        ret, frame = cap.read()
        hsv = cv2.cvtColor(frame, cv2.COLOR_BGR2HSV)
        blueMask = cv2.inRange(hsv, lower_blue, upper_blue)
        res = cv2.bitwise_and(frame,frame, mask=blueMask)
        
        cv2.imshow('frame'frame)
        cv2.imshow('mask', blur)
        cv2.imshow('filtrado', res)
        
        if cv2.waitKey(1) & 0xff == ('q')
              break
cap.release()
cv2.destroyAllWindows()
