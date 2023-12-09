---
title: "[HOWTO] Display daily/weekly/monthly Internet Traffic totals on the Desktop using Conky"
date: "2010-11-09"
categories: 
  - "ubuntu-linux"
tags: 
  - "conky"
  - "linux"
  - "vnstat"
---

To be able to display weekly/monthly traffic totals, you will need to [install and configure vnstat](http://www.khattam.info/solved-vnstat-zero-database-found-exiting-2010-11-09.html) first. After that, you will be able to monitor traffic totals from command line using the following command in the terminal:

vnstat

To view daily traffic totals, you can use the command:

vnstat -d

To view weekly traffic totals, use the command:

vnstat -w

Similarly, to view monthly totals, use the command:

vnstat -m

If you have an interface other than eth0, you will need to specify it via command line option "-i", so if your interface is called ppp0, the above commands will respectively be as follows:

vnstat -d -i ppp0
vnstat -w -i ppp0
vnstat -m -i ppp0

If you already use conky, you can add the following lines to your ~/.conkyrc file:

${color slate grey}Internet 
${color slate grey}Up:${color}${upspeed eth0}k/s
${upspeedgraph eth0 20,140 000000 ffffff}
${color slate grey}Today: ${color} ${exec vnstat -d|grep \`date +%m/%d/%y\`|awk '{print $5 $6}'}
${color slate grey}Week:  ${color} ${exec vnstat -w|grep 'current week'|awk '{print $6 $7}'}
${color slate grey}Month: ${color} ${exec vnstat -m -i eth0|grep \`date | cut -d' ' -f2\`|awk '{print $6 $7}'}

${color slate grey}Down:${color}${downspeed eth0}k/s${color slate grey} 
${downspeedgraph eth0 20,140 000000 ffffff}
${color slate grey}Today: ${color} ${exec vnstat -d|grep \`date +%m/%d/%y\`|awk '{print $2 $3}'}
${color slate grey}Week:  ${color} ${exec vnstat -w|grep 'current week'|awk '{print $3 $4}'}
${color slate grey}Month: ${color} ${exec vnstat -m -i eth0|grep \`date | cut -d' ' -f2\`|awk '{print $3 $4}'}

You should change the colors and position to match with the rest of the conky configuration.

If you are interested in my .conkyrc, here it is:

\# Conkyrc X.v0.5.3 
# exudus @ http://www.localh0st.net
#
# A comprehensive conky script, configured for use on
# Ubuntu / Debian Gnome
# 
# Modified by \_khAttAm\_ @ http://www.khattam.info
# Uses an external applications : sensors, vnstat. So make sure they are installed 
# and configured
# Assumes the internet connection is on eth0, change it to match your system
# 

# Create own window instead of using desktop (required in nautilus)
own\_window yes
own\_window\_hints undecorated,below,sticky,skip\_taskbar,skip\_pager
background no

# Use double buffering (reduces flicker, may not work for everyone)
double\_buffer yes

# fiddle with window
use\_spacer right
use\_xft yes

# Update interval in seconds
update\_interval 2.0

# Minimum size of text area
minimum\_size 150 5
maximum\_width 300

# Draw shades?
draw\_shades yes

# Text stuff
draw\_outline no # amplifies text if yes
draw\_borders no
draw\_graph\_borders yes

uppercase no # set to yes if you want all text to be in uppercase

# Stippled borders?
stippled\_borders 1

# border margins
# border\_margin 1

# border width
border\_width 1

# Default colors and also border colors, grey90 == #e5e5e5
default\_color 4D4D4D
default\_shade\_color black
default\_outline\_color grey90

own\_window\_colour brown
own\_window\_transparent yes

# Text alignment, other possible values are commented
#alignment top\_left
#alignment top\_right
#alignment bottom\_left
alignment bottom\_right

# Gap between borders of screen and text
gap\_x 10
gap\_y 50

# stuff after 'TEXT' will be formatted on screen

override\_utf8\_locale yes
xftfont Ubuntu:size=8
xftalpha 0.8

TEXT
${color slate grey}${alignc}$sysname $kernel$color
${color slate grey}UpTime: ${color}${alignr}$uptime

${color slate grey}CPU1${color}${alignr}${exec sensors | grep -i Core\\ 0|cut -d' ' -f8}   ${cpu cpu0}%
${color light grey}${cpubar 4 cpu0}
${color slate grey}CPU2${color}${alignr}${exec sensors | grep -i Core\\ 1|cut -d' ' -f8}   ${cpu cpu1}%
${color light grey}${cpubar 4 cpu1}
${color slate grey}FAN${color}${alignr}${exec sensors | grep -i fan1|cut -d' ' -f8} RPM

${color slate grey}Load: ${color}$loadavg
${color slate grey}Processes: ${color}$processes  
${color slate grey}Running: ${color}$running\_processes

${color}${font}${color slate grey}Highest CPU:
${color #ddaa00} ${top name 1}${alignr}${top cpu 1}
${color lightgrey} ${top name 2}${alignr}${top cpu 2}
${color lightgrey} ${top name 3}${alignr}${top cpu 3}
${color lightgrey} ${top name 4}${alignr}${top cpu 4}

${color}${font}${color slate grey}Highest MEM:
${color #ddaa00} ${top\_mem name 1}${alignr}${top\_mem mem 1}
${color lightgrey} ${top\_mem name 2}${alignr}${top\_mem mem 2}
${color lightgrey} ${top\_mem name 3}${alignr}${top\_mem mem 3}
${color lightgrey} ${top\_mem name 4}${alignr}${top\_mem mem 4}

${color slate grey}I/O disque :${color lightgrey} $diskio $color
${diskiograph 20,140 000000 ffffff}

${color slate grey}HOME ${color }
${fs\_free /home}/${fs\_size /home}
${fs\_bar 3,140 /home}

${color slate grey}MEM:
${color } $memperc% $mem/$memmax
${membar 3,140}
${color slate grey}SWAP:
${color } $swapperc% $swap/$swapmax
${swapbar 3,140}
${color slate grey}Internet 
${color slate grey}Up:${color}${upspeed eth0}k/s
${upspeedgraph eth0 20,140 000000 ffffff}
${color slate grey}Today: ${color} ${exec vnstat -d|grep \`date +%m/%d/%y\`|awk '{print $5 $6}'}
${color slate grey}Week:  ${color} ${exec vnstat -w|grep 'current week'|awk '{print $6 $7}'}
${color slate grey}Month: ${color} ${exec vnstat -m -i eth0|grep \`date | cut -d' ' -f2\`|awk '{print $6 $7}'}

${color slate grey}Down:${color}${downspeed eth0}k/s${color slate grey} 
${downspeedgraph eth0 20,140 000000 ffffff}
${color slate grey}Today: ${color} ${exec vnstat -d|grep \`date +%m/%d/%y\`|awk '{print $2 $3}'}
${color slate grey}Week:  ${color} ${exec vnstat -w|grep 'current week'|awk '{print $3 $4}'}
${color slate grey}Month: ${color} ${exec vnstat -m -i eth0|grep \`date | cut -d' ' -f2\`|awk '{print $3 $4}'}
 
${color slate grey}IP (eth0):${color} ${addr eth0}
