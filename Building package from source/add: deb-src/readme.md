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
