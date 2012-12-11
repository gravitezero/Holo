Holo theme for gnome shell & gtk *3.6.1*

Based on the excellent work from Tiheum : [Holo theme on DeviantArt](http://tiheum.deviantart.com/art/Holo-280076980)     
Since there seems to have been big changes from 3.6 to 3.6.1 in gnome-shell, some parts of this themes need to be redesigned.

Thanks a lot to Tiheum for his icons and themes (I am a great fan of both)

Disclaimer :
This repository bring 2 changes from Tiheum works :
> Some compatibility with gnome-shell & gtk 3.6.1 
> Some changes based on my personal preferences (for example, I am not a great fan of the green used for selection)

And also, I made some changes that might appears quite odd if not used if Faenza or Faience icon theme.

Usability & work progression
================

* **Gnome-shell**: partly usable, reviews welcome    
* **Gtk-3**: not usable, working on it    
* **Gtk-2**: partly usable, I am not gonna fix this    
* **Metacity**: usable    


Installation
============

To install it directly using command line :

    # Install git (if not already)
    yaourt -S git
    # Checkout git repo
    git clone git@github.com:gravitezero/Holo.git
    # move it to the right place
    sudo mv Holo /usr/share/theme

---

This is from the r3gis3r [repo](http://github.com/r3gis3r/Holo-Gnome3-Theme) I used until now.

Extra configuration
===================
## Firefox
If you are a Firefox user, you may also appreciate [~illusionmist Holo Stylish script for Firefox](http://illusionmist.deviantart.com/art/Holo-Theme-for-Firefox-294051732)

## Thunderbird
And the thunderbird script [r3gis3r Holo Stylish script for Thunderbird](http://userstyles.org/styles/64593/holo-theme-for-thunderbird-linux-thunderbir-11?r=1335276031)

## Fonts
You may also want to install Roboto fonts

To do so use following command lines :

    # Get roboto fonts
    wget http://www.fontsquirrel.com/fonts/download/roboto -O roboto.zip
    # Create .fonts theme (if not already)
    mkdir ~/.fonts
    # Unzip fonts in folder
    unzip roboto.zip -d ~/.fonts

If you plan to use _Roboto Light_ instead of _Roboto_, you'll notice weird behavior from apps such as Thunderbird and Pidgin.     
It's because they try to use _Roboto_ in weight normal which resolves to Medium style and it will appear bold for you.    
So, you have to force the resolution of _Roboto_ into _Roboto Light_ for _normal_ weight.
So edit your ```~/.fonts.conf``` and fill with :

```xml
<?xml version="1.0"?>
<!DOCTYPE fontconfig SYSTEM "fonts.dtd">
<fontconfig>
    <match target="pattern">
        <test name="family" qual="any">
            <string>Roboto</string>
        </test>
        <test name="weight" compare="less_eq">
            <const>normal</const>
        </test>
        <edit mode="assign" name="weight">
            <const>light</const>
        </edit>
    </match>
</fontconfig>

```

Finally, you can then use gnome-tweak-tool to setup everything.


----

Remember that the Holo theme is released under GPLv3 license.
And don't hesitate to share if you modify for your own needs ;).