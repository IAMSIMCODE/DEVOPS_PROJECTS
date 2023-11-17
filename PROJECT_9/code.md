.button {
  background-color: #4CAF50; /* Green */
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
}

<h2>Implementing Wordpress Website With LVM Storage Management</h2>


<button type="button" style="background-color: blue; border: none;  color: white; padding: 5px 10px;  text-align: center; text-decoration: none; display: inline-block; font-size: 15px; border-radius: 8px;">Copy Below Code</button>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">ls /dev/</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">xvdf, xvdh, xvdg</p>


<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo gdisk /dev/xvdf</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo yum install lvm2</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo lvmdiskscan</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo pvcreate /dev/xvdf</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo pvcreate /dev/xvdg</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo pvcreate /dev/xvdh</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo pvs</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo vgcreate webdata-vg /dev/xvdf /dev/xvdg /dev/xvdh</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo vgs</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo lvcreate -n apps-lv -L 14G webdata-vg</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo lvcreate -n logs-lv -L 14G webdata-vg</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo lvs</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo lsblk</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo mkfs -t ext4 /dev/webdata-vg/apps-lv</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo mkfs -t ext4 /dev/webdata-vg/logs-lv</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo mkdir -p /var/www/html</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo mkdir -p /home/recovery/logs</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo mount /dev/webdata-vg/apps-lv /var/www/html/</p>


<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo rsync -av /var/log/. /home/recovery/logs/</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo mount /dev/webdata-vg/logs-lv /var/log/</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo rsync -av /home/recovery/logs/log/. /var/log</p>


<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo blkid</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo vi /etc/fstab</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo mount -a</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo systemctl daemon-reload</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">dh -h</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo yum update -y</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo yum install wget httpd php php-mysqld php-fpm php-json</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo systemctl enable httpd</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo systemctl start httpd</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo yum install https://dl.fedoraproject.org/pub/epel/epel-release-latest-9.noarch.rpm</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo yum install yum-utils</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo yum module list php</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo yum module reset php</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo yum module enable php:remi-7.4</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo yum install php php-opchache php-gd php-curl php-mysqlnd</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo systemctl start php-fpm</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo systemctl enable php-fpm</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">setsebool -p http_execmen 1</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo systemctl restart httpd</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">mkdir wordpress</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">cd wordpress</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo wget http://wordpress.org/latest.tar.gz</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo tar xzvf latest.tar.gz</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">cp wordpress/wp-config-sample.php wordpress/wp-config.php</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">cp -R wordpress /var/www/html</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo rm -rf latest.tar.gz</p>


<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo chown -R apache:apache /var/www/html/wordpress</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo chcon -t httpd_sys_rw_content_t /var/www/html/wordpress -R</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo setsebool -p http_can_network_connect=1</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo yum install mysql-server</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo systemctl restart mysqld</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo systemctl enable mysqld</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo mysql</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">CREATE DATABASE wordpress;</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">CREATE USER 'myuser'@'< Web-server-Ip-Address>' IDENTIFIED BY 'mypass';</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">GRANT ALL ON wordpress.* TO 'myuser'@'< Web-server-Ip-Address>';</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">FLUSH PRIVILEGES;</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">SHOW DATABASES;</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">exit</p>