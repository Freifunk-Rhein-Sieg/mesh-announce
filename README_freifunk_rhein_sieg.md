patched to deliver fixed nodeinfo, hostname, domain and hardware-model of host.

when running multiple instances on same host, provide unique directory for each service:

root@fgw03 ~ # systemctl | grep respondd
respondd_bat04.service                                                                      loaded active running   Respondd_bat04
respondd_bat05.service                                                                      loaded active running   Respondd_bat05
respondd_bat11.service                                                                      loaded active running   Respondd_bat11
respondd_bat14.service                                                                      loaded active running   Respondd_bat14


root@fgw03 ~ # ps ax | grep respondd
11951 ?        Ssl    0:10 python3 /opt/mesh-announce_bat04/respondd.py --data-provider-directory /opt/mesh-announce_bat04 -i bat04 -b bat04 -s su-sa -n 66811882820e
11967 ?        Ssl    0:13 python3 /opt/mesh-announce_bat11/respondd.py --data-provider-directory /opt/mesh-announce_bat11 -i bat11 -b bat11 -s su-ak -n b63caea149d6
11983 ?        Ssl    0:14 python3 /opt/mesh-announce_bat14/respondd.py --data-provider-directory /opt/mesh-announce_bat14 -i bat14 -b bat14 -s su-rhb -n dab834f6dcdd
12757 ?        Ssl    0:10 python3 /opt/mesh-announce_bat05/respondd.py --data-provider-directory /opt/mesh-announce_bat05 -i bat05 -b bat05 -s su-snw -n 6aecf4821417

root@fgw03 /opt # ls mesh*
mesh-announce_bat04:
announce.py  domain.fixed  hostname.fixed  neighbours.d  nodeinfo.d   README.md               respondd.py     statistics.d
announce.sh  gather.py     model.fixed     nodeid.fixed  __pycache__  respondd_bat04.service  sitecode.fixed

mesh-announce_bat05:
announce.py  domain.fixed  hostname.fixed  neighbours.d  nodeinfo.d   README.md               respondd.py     statistics.d
announce.sh  gather.py     model.fixed     nodeid.fixed  __pycache__  respondd_bat05.service  sitecode.fixed

mesh-announce_bat11:
announce.py  domain.fixed  hostname.fixed  neighbours.d  nodeinfo.d   README.md               respondd.py     statistics.d
announce.sh  gather.py     model.fixed     nodeid.fixed  __pycache__  respondd_bat11.service  sitecode.fixed

mesh-announce_bat14:
announce.py  domain.fixed  hostname.fixed  neighbours.d  nodeinfo.d   README.md               respondd.py     statistics.d
announce.sh  gather.py     model.fixed     nodeid.fixed  __pycache__  respondd_bat14.service  sitecode.fixed
