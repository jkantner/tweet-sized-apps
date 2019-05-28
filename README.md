# tweet-sized-apps

To sharpen my skill at JavaScript minification, I occasionally write apps whose entire source fits in a tweet. The best approach for most of these is to adopt the style of Atari 2600 games but a lot more like Pong—using black and white.

To try these yourself, just fire up a new [CodePen demo](https://codepen.io/pen) and paste in the HTML pane. Just so you know, these are never done; I’m always in search of ways to cut off more bytes and even open room for more features!

## Clock Widget
Bytes: **279**

A minimalistic UTC clock consisting of a circle and lines for the hands

### Code
```
<body onload=c=c.getContext('2d');setInterval("d=Date.now();c.clearRect(0,0,w=150,w);c.beginPath();c.arc(w/=2,w,w,0,6.3);c.moveTo(w+Math.sin(h=d/36e5%24*.524)*40,w-Math.cos(h)*40);c.lineTo(w,w);c.lineTo(w+Math.sin(m=d/6e4%60*.105)*60,w-Math.cos(m)*60);c.stroke()",8)><canvas id=c
```

## Doodle Jump
Bytes: **275**

So far, we have room for controlling the character and his ability to jump off platforms. Exiting at one side of the screen to end up on the opposite also works. There’s currently no scoring or progression, and passing the top of the screen results in ending up at the bottom.

🕹 J - left, K -  right

### Code
```
<body onkeyup=x+=event.which%2?9:-9 onload="c=C.getContext('2d');a=0;P=[x=63,9,y=99,x];setInterval(`a+=.01;y+=y<0?108:a;c.fillRect(0,0,W=144,W);for(p in P)l=p*36,d=P[p],a=y>l&&y<l+4&&x+8>d&&x<d+20?-1:a,c.clearRect(d,l,20,4);c.clearRect(x=x?x>W?9:x:W,y,8,-8)`,7)"><canvas id=C
```

## Flappy Bird
Bytes: **277**

The core game functionalty is mostly there, but few limits remain: one pipe at a time and same vertical pipe positions.

🕹 Click/tap - flap

### Code
```
<body id=B onload="c=C.getContext('2d');o=[90,-92,98];y=0;x=225;s=0;setInterval('c.fillRect(0,0,W=150,W);for(i in o)c.clearRect(+i?x:37,o[i],+i?14:9,+i?W:9);b=o[0];b<W-9&&(x<23||x>46||58<b&&b<89)?(y+=.04,x<-13?(x=W,++s):--x,o[0]+=y):B.innerHTML=s',9)"><canvas id=C onclick=y=-1
```
