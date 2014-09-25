Munstrap-dark
========

Alternative dark Munin 2.x templates based on Twitter Bootstrap 3

![Sample](sample.jpg)

Installation
------------

Get Munstrap:

```
cd /etc/munin
git clone https://github.com/Hypfer/munstrap-dark.git
```

Replace the Munin stock template by Munstrap (don't worry, there is a backup of the old files):

```
cp -rb munstrap-dark/templates .
cp -rb munstrap-dark/static .
```

Edit /usr/share/perl5/munin/master/GraphOld.pm (Path may vary) according to this patch (because I'm lazy)

127,131c127
-         qw(00CC00 0066B3 FF8000 FFCC00 330099 990099 CCFF00 FF0000 808080
-             008F00 00487D B35A00 B38F00         6B006B 8FB300 B30000 BEBEBE
-             80FF80 80C9FF FFC080 FFE680 AA80FF EE00CC FF8080
-             666600 FFBFFF 00FFCC CC6699 999900
-             )];      # Line variations: Pure, earthy, dark pastel, misc colours
---
+         qw(FF1E00 FF7F00 00B6E1 00EB3E FF280B FF840B 11C6F0 0BF548 D11800 D16800 006981 009C29)];
1668,1673c1664,1669
- 		'--color',  'BACK#F0F0F0',   # Area around the graph
- 		'--color',  'FRAME#F0F0F0',  # Line around legend spot
- 		'--color',  'CANVAS#FFFFFF', # Graph background, max contrast
- 		'--color',  'FONT#666666',   # Some kind of gray
- 		'--color',  'AXIS#CFD6F8',   # And axis like html boxes
- 		'--color',  'ARROW#CFD6F8',  # And arrow, ditto.
---
+ 		'--color',  'BACK#363232',   # Area around the graph
+ 		'--color',  'FRAME#323433',  # Line around legend spot
+ 		'--color',  'CANVAS#1f2020', # Graph background, max contrast
+ 		'--color',  'FONT#999999',   # Some kind of gray
+ 		'--color',  'AXIS#999999',   # And axis like html boxes
+ 		'--color',  'ARROW#999999',  # And arrow, ditto.


Clean the old generated files:

```
rm -rf /var/www/munin/*
```

Take a coffee and wait some minutes for the html generation by Munin.

Upgrades
--------

Get the last changes from Munstrap:

```
cd /etc/munin/munstrap-dark
git pull
```

Replace the old version by the new one:

```
cd /etc/munin
rm -rf templates static
cp -r munstrap/templates .
cp -r munstrap/static .
```

Revert to stock
---------------

```
cd /etc/munin
rm -rf templates static
mv templates~ templates
mv static~ static
```
