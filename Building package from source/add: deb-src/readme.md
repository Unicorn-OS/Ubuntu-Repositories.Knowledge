sch: https://www.google.com/search?q=deb-src+%2Fetc%2Fapt%2Fsources.list.d%2F

# Solution:
https://askubuntu.com/questions/1512042/ubuntu-24-04-getting-error-you-must-put-some-deb-src-uris-in-your-sources-list

>There is a new config file location with a new file format layout for 24.04 unlike previous Ubuntu releases
>
>Add the below snippet to the new config file /etc/apt/sources.list.d/ubuntu.sources
>```
>Types: deb-src
>URIs: http://us.archive.ubuntu.com/ubuntu/
>Suites: noble noble-updates noble-backports noble-proposed
>Components: main restricted universe multiverse
>Signed-By: /usr/share/keyrings/ubuntu-archive-keyring.gpg
>```
>
>If you want to do this using a one line command:
>
>`sed -i 's/^Types: deb$/Types: deb deb-src/' /etc/apt/sources.list.d/ubuntu.sources`
...
>NOTE if the machine is under control of cloud-init (ignore this for those viewers at home this pertains to some remote cloud Ubuntu VM not your home laptop) instead make a similar addition of deb-src to the template file as per
>
>$ cat /etc/apt/sources.list.d/ubuntu.sources
>```
>## Note, this file is written by cloud-init on first boot of an instance
>## modifications made here will not survive a re-bundle.
>##
>## If you wish to make changes you can:
>## a.) add 'apt_preserve_sources_list: true' to /etc/cloud/cloud.cfg
>##     or do the same in user-data
>## b.) add supplemental sources in /etc/apt/sources.list.d
>## c.) make changes to template file
>##      /etc/cloud/templates/sources.list.ubuntu.deb822.tmpl
>##
>```
