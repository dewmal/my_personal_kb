
https://github.com/dewmal/my_personal_kb/blob/master/Screenshot_2019-12-03%20How%20To%20Set%20Up%20a%20Node%20js%20Application%20for%20Production%20on%20CentOS%207%20DigitalOcean.png

Use this

sudo  setsebool -P httpd_can_network_connect 1

for avoid *1 connect() to 0.0.0.0:0000 failed (13: Permission denied) while connecting to upstream, client: 116.206.244.203, server: ceylonfx.com, request: "GET / HTTP/1.1", upstream: "http://0.0.0.0:0000/", host: "ceylonfx.com"
