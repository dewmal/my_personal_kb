###

I wasted a lot of time on this. I wish I had found this first: https://docs.cloud.oracle.com/en-us/iaas/developer-tutorials/tutorials/apache-on-ubuntu/01oci-ubuntu-apache-summary.htm

    configure ingress route for port 80

    install ubuntu.

    install apache/nginx

    curl localhost should bring back webpage in text format, however fails over internet.

    forget ufw firewall - this may cause issues with the Oracle firewall

    use

$ sudo iptables -I INPUT 6 -m state --state NEW -p tcp --dport 80 -j ACCEPT
$ sudo netfilter-persistent save

g) test your web page over internet
