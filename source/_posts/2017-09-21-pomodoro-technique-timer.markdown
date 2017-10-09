---
layout: post
title: "Pomodoro Technique Timer"
date: 2017-09-21 23:43:14 -0700
comments: true
categories:
---

Pomodoro technique is a useful time management technique. There have been
written a lot about pomodoro technique ever since it was published by
Francesco Cirillo in the late 1980-s.

The technique recommends using a mechanical timer for measuring time. There are
several reasons for using a mechanical timer: ticking timer reminds about
pomodoro in progress and presumably boosts focus.

Conventional kitchen timers are very nice, but they are not particularly
convenient for office environment. They are ticking, and their ringing is too
loud and very difficult to adjust. There are many apps for pomodoro technique
timer, but I've always wanted something that satisfies my requirements and has
a physical button rather than a virtual one. I tried retrofitting existing
timers and toys. It turned out to be easier to build an electronic timer. It
also looks very techy.

You can find the eagle project files
[here](https://github.com/VictorDenisov/pomodoro-timer-pcb). I used oshpark
community order for PCBs. You can order this PCB
[here](https://oshpark.com/shared_projects/IVhyku4U) The firmware is available
[here](https://github.com/VictorDenisov/arduino-pomodoro) I used sparkfun
[USBtiny ISP](https://www.sparkfun.com/products/9825) to program it.

The timer has five binary positions for displaying remaining minutes. It also
has LEDs for busy and available mode. You can tell your colleagues that if the
light is red then you are busy. The timer goes off with an audible beep. The
whole system is designed the way that you can use arduino IDE to compile the
firmware and program the device.

A general view of the timer.
{% img images/pomodoro/timer_view.jpg %}
