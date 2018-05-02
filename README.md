# wind_wave_shadow script

Simple python script that displays the geometric wave shadow cast by the NE Freeport ship channel jetty after the user supplies the wind and wave directions. 

## What's it for?

To help decide if it's worth the 1hr+ drive from Houston to Surfside beach to do some surfing or surf kiting.

Surfside beach gets more ridable swell than you would otherwise guess, but it's almost exclusively short-period wind-swell generated by local weather systems. Because the swell is generated locally, it is usually accompanied by the same wind that helped generate it; this wind can lead to undesirably choppy conditions if it's directed onshore. Luckily the approximately 3/4 mile long jetty can act as a chop blocker for certain wind directions, which is what this script is designed to help us visualize.

Generally we want the jetty to block the surface level wind and its associated chop, but we don't want it to block the incoming wind swell. Ideally the wind would be blocked by the jetty or shore while the swell is minimally blocked by the jetty. In that particular case it's possible to have relatively clean surf near the jetty—even with relatively strong side to side-onshore wind.

## How to use:

1. you need python 3.5+ installed on your computer along with the _Pillow_ and _tkinter_ modules

2. clone (download) script to your local drive

3. open terminal window, change your working directory to the cloned directory, and then the script executable `chmod +x shadow\ overlay.py` It's necessary for your working directory to be the same as the script directory in order for the link to the `surfside.png` file to resolve.

4. get the wind and swell directions from magicseaweed.com or some other source

5. run the script: `/your path/shadow\ overlay.py wind_direction swell_direction`
> example: `~/dev/shadow\ overlay.py 160 190`

6. hopefully a picture of the jetty opens with some triangles displayed. If so, here's what they mean:
    * blocked wind and chop is good—it's represented by a green triangle
    * blocked swell is not necessarily good—it's represented by a red triangle
    * overlap between blocked swell and blocked wind _might_ be good if the swell is big enough and refracts around the jetty, although it will be smaller than unobstructed swell—it's represented by a kind of yellow-ish color
    * swell shadow that is inside of wind shadow may be ok if you want to ride smaller waves—it is also represented by a yellow-ish color
7. key bindings:
    * `q` closes the map window and terminates the script
    * `p` saves a png image file to the `~/downloads` directory on a mac.
    * `right-click` clears the screen and resets the calibration
    * `left-click` captures calibration points, which is essentially for testing. So if you were to right click reset the screen, you would:
        a. `left-click` the point where the jetty and shore meet
        b. `left-click` the point where the jetty ends
        c. `left-click` a point on the shore
        d. hit `Return` after you see the black triangle and it will project the shadows again.

## what you're seeing

Note that this code doesn't take swell refraction into consideration. In reality, this swell refraction will cause it to bend around the jetty and fill in the swell shadow that this script has calculated. The idea here is that the biggest swell will be found _outside_ the shadow and it will get smaller as you move inside the shadow. This can be a good thing if you want smaller waves to paddle out through or ride.
