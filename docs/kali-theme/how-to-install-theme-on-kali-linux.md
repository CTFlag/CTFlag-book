# How To Install The Destop Theme On Kali Linux

## How To Install Max OS Theme on Kali Linux
1. First Step : install the `gnome-tweak-tool` so execute the following
> apt install gnome-tweak-tool


2. Second Step : install the MaxOS theme : [elementary-x](https://github.com/surajmandalcell/elementary-x)

Open terminal and execute the following
> git clone https://github.com/surajmandalcell/elementary-x.git ~/.themes/elementary-x


Select this theme in tweak tool or execute the following
> gsettings set org.gnome.desktop.interface gtk-theme "elementary-x"


3. Third Step : install the the MacOS icon theme : [la-capitaine-icon-theme](https://github.com/keeferrourke/la-capitaine-icon-theme)

Open terminal and execute the following
> git clone https://github.com/keeferrourke/la-capitaine-icon-theme.git ~/.icons/la-capitaine-icon-theme

Select this theme in tweak tool or execute the following
> gsettings set org.gnome.desktop.interface icon-theme "la-capitaine-icon-theme"


### Reference Video
<iframe width="560" height="315" src="https://www.youtube.com/embed/B_LoOCtefYE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
