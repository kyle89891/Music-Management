*code of python for music player

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
os.chdir(r'C:\Users\RAWAT\Desktop\akash')  // please set a directory path of songs here from your local computr
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

