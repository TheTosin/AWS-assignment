#!/bin/bash
 apt update -y
 apt install nginx -y
 systemctl start nginx
 systemctl restart nginx

 export META_INST_PRIVATE_IP=`curl http://169.254.169.254/latest/meta-data/local-ipv4`


 cd /var/www/html
 echo "<!DOCTYPE html>" >> index.html
 echo "<html lang="en">" >> index.html
 echo "<head>" >> index.html
 echo "    <meta charset="UTF-8">" >> index.html
 echo "    <meta name="viewport" content="width=device-width, initial-scale=1.0">" >> index.html

 echo "    <title>-app</title>" >> index.html
 echo "</head>" >> index.html
 echo "<body>" >> index.html
 echo "    <div class="wrapper">" >> index.html
 echo "        <div>" >> index.html
 echo "            <div>" >> index.html

 echo "                <div>" >> index.html

 echo "                    <div>" >> index.html
 echo "                        <div>Instance Type</div>" >> index.html
 echo "                        <div>" $META_INST_TYPE "</div>" >> index.html
 echo "                    </div>" >> index.html

 echo "                    <div>" >> index.html
 echo "                        <div>Private IP</div>" >> index.html
 echo "                        <div>" $META_INST_PRIVATE_IP "</div>" >> index.html
 echo "                    </div>" >> index.html


 echo "                    <div>" >> index.html
 echo "                        <div>Availability zone</div>" >> index.html
 echo "                        <div>" $META_INST_AZ "</div>" >> index.html
 echo "                    </div>" >> index.html

 echo "                </div>" >> index.html
 echo "            </div>" >> index.html
 echo "        </div>" >> index.html
 echo "</body>" >> index.html
 echo "</html>" >> index.html
 systemctl restart nginx
