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

Configure Munin to look for templates and static files at the new location:

```
cat > /etc/munin/munin-conf.d/munstrap-dark.conf <<EOF
tmpldir   /etc/munin/munstrap-dark/templates
staticdir /etc/munin/munstrap-dark/static
EOF
```

Edit /usr/share/perl5/munin/master/GraphOld.pm (Path may vary) according to colors.patch (because I'm lazy)


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

Revert to stock
---------------

```
rm -rf /etc/munin/munin-conf.d/munstrap-dark.conf /etc/munin/munstrap-dark
```

