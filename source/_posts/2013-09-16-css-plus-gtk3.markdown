---
layout: post
title: "CSS+Gtk3"
date: 2013-09-16 14:00
comments: true
categories: [gtk, python]
---

Remix GTK3 Apps with the magical CSS  <!--more-->

I assumed you know Gtk2 and write Gtk apps in any language, I show you how to  theme your GTK3 apps. Please note CSS support is available for Gtk3 and not for Gtk2.  

First of all create a window which have some widget on it. 
``` Python A Example Window

import gi.repository Gtk

win=Gtk.Window()
lbl=Gtk.Label("Hello")
lbl.set_name('mylabel') #use as CSS selector i.e #mylabel

win.set_size_request(200,100)
win.connect('delete-event',close)
win.add(lbl)

win.show_all()
Gtk.main()


def close(event,data):
	Gtk.main_quit()
```

Okay, so we done with GTk app right? But where is CSS? You have to add CSS using ``GtkStyleContext`` and ``GtkStyleProvider`` these classes allows to import ``css`` file or embed css code in app. So first create a css that apply color to label.

```css Example CSS

#mylabel{
	color: #FF0000;
	background-color: #000000;
}
```
