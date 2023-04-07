## Introduction & Declaration
This repository is a record of my previous work done for Computer Networking course. It's not a music player for daily use.       

Skills & Knowledges I learned through this programming experience:
* TCP sockets programming in Python
* mutli-threading
    * how to create threads in Python
    * how to make container thread-safe
* understanding of protocol
* some other knowledges about computer networking

## Main Function
What can users do in the client-end:
* upload a song to the server
<img src = "/images/init.jpg"> <img src = "/images/addsong.jpg">

* create a playlist and store it to the server
   <img src = "/images/createlist.jpg">

* view the contents of playlists stored on the server
   <img src = "/images/openlist.jpg">

* delete a song stored on the server
   <img src = "/images/delesong.jpg">

* add/remove a song to/from a playlist stored on the server
<img src = "/images/addsongtolist.jpg"><img src = "/images/delefromlist.jpg"><img src = "/images/message.jpg"><img src = "/images/listafterdele.jpg">

* play songs
* download songs stored on the server (automatically download when the "play" button is clicked)


*code of python

import pygame
from pygame import mixer
from tkinter import *
import os
def playsong():
 currentsong=playlist.get(ACTIVE)
 print(currentsong)
 mixer.music.load(currentsong)
 songstatus.set("Playing")
 mixer.music.play()
def pausesong():
 songstatus.set("Paused")
 mixer.music.pause()
def stopsong():
 songstatus.set("Stopped")
 mixer.music.stop()
def resumesong():
 songstatus.set("Resuming")
 mixer.music.unpause() 
root=Tk()
root.title('Musik Player')
mixer.init()
songstatus=StringVar()
songstatus.set("choosing")
#playlist---------------
playlist=Listbox(root,selectmode=SINGLE,bg="pink",fg="white",font=('arial',15)
,width=40,height=10)
playlist.grid(columnspan=7)
os.chdir(r'C:\Users\RAWAT\Desktop\akash')
songs=os.listdir()
for s in songs:
 playlist.insert(END,s)
 playbtn=Button(root,text="Play",command=playsong)
 playbtn.config(font=('arial',20),bg="DodgerBlue2",fg="white",padx=7,pady=7)
 playbtn.grid(row=1,column=0)
pausebtn=Button(root,text="Pause",command=pausesong)
pausebtn.config(font=('arial',20),bg="DodgerBlue2",fg="white",padx=7,pady=7)
pausebtn.grid(row=1,column=1)
stopbtn=Button(root,text="Stop",command=stopsong)
stopbtn.config(font=('arial',20),bg="DodgerBlue2",fg="white",padx=7,pady=7)
stopbtn.grid(row=1,column=2)
Resumebtn=Button(root,text="Resume",command=resumesong)
Resumebtn.config(font=('arial',20),bg="DodgerBlue2",fg="white",padx=7,pady=7)
Resumebtn.grid(row=1,column=3)
mainloop()

