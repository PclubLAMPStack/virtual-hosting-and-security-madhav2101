1.)Create two directories in root directory (/var/www/html) named as Website 1 and Website 2 using command mkdir website1 and mkdir website2
2.)Create index.html
using vi /var/www/html/website1 and entering simple html code
 <!DOCTYPE html>
<html>
<head>
    <title>Web Gawd can stop you anywhere</title>
</head>
<body>
    <h1>Forbidden</h1>
    <p>You should be an authenticated user contact web gawd</p>
</body>
</html>
3.)Editing Hosts File and entering ip's with respect to website name (vi /etc/hosts)
![Screenshot (43)](https://github.com/PclubLAMPStack/virtual-hosting-and-security-madhav2101/assets/130836620/df1e3832-ff5d-4edf-8cfc-b6fffadcff47)
4.) Editing ifcfg-ens33 file (vi /etc/sysconfig/ifcfg-ens33)
![Screenshot (40)](https://github.com/PclubLAMPStack/virtual-hosting-and-security-madhav2101/assets/130836620/6293d774-24b8-4fe8-b685-4be8da553fee)
5.)Editing httpd.conf file (vi /etc/httpd/conf/httpd.conf)![Screenshot (37)](https://github.com/PclubLAMPStack/virtual-hosting-and-security-madhav2101/assets/130836620/7f975091-9f0a-4ab7-ba4f-e59714b19e7b)
6.)Adding forbidden.html to noindex directory in /usr/share/httpd/noindex(vi /usr/share/httpd/noindex/forbidden.html)![Screenshot (41)](https://github.com/PclubLAMPStack/virtual-hosting-and-security-madhav2101/assets/130836620/e384bbe7-bb91-4ae9-8a79-0fa0de3ba202)
7.)Editing welcome.conf file in /etc/httpd/conf.d (vi /etc/httpd/conf.d/welcome.conf) to get desrired output when error  of authorization is executed.![Screenshot (37)]![Screenshot (42)](https://github.com/PclubLAMPStack/virtual-hosting-and-security-madhav2101/assets/130836620/b7291b65-447f-4287-8a22-89aeda4e6ae7)
8.)Creating users-
   htpasswd -c -w /etc/httpd/webpass user1
   htpasswd  -w /etc/httpd/webpass user2
   htpasswd  -w /etc/httpd/webpass user3
   htpasswd  -w /etc/httpd/webpass user4
9.)Accessing websites from c10 & c20
website1:![Screenshot (39) 1](https://github.com/PclubLAMPStack/virtual-hosting-and-security-madhav2101/assets/130836620/899bf9e9-78f2-46e5-ae5a-bbf379c30102)
website2:<img width="692" alt="Screenshot 2023-06-11 223337" src="https://github.com/PclubLAMPStack/virtual-hosting-and-security-madhav2101/assets/130836620/0b5c4d27-b80b-4159-91d0-6c0a31f236b2">
