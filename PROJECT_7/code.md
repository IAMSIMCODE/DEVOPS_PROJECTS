

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

<h2>IMPLEMENTING LOAD BALANCER WITH NGINX</h2>

<button type="button" style="background-color: #008CBA; border: none;  color: white; padding: 10px 24px;  text-align: center; text-decoration: none; display: inline-block; font-size: 16px; border-radius: 8px;">Copy Below Code</button>




<p style="background-color: black; padding: 5px 10px;color: #f44336; font-size: 14px;">sudo apt update -y && sudo apt install apache2 -y</p>


<p style="background-color: black; padding: 5px 10px;color: #f44336; font-size: 12px;">sudo systemctl status apache2</p>

<p style="background-color: black; padding: 5px 10px;color: #f44336; font-size: 12px;">sudo vi /etc/apache2/ports.conf</p>

<p style="background-color: black; padding: 5px 10px;color: #f44336; font-size: 12px;">sudo vi /etc/apache2/sites-available/000-default.conf</p>

<p style="background-color: black; padding: 5px 10px;color: #f44336; font-size: 12px;">:wq!</p>

<p style="background-color: black; padding: 5px 10px;color: #f44336; font-size: 12px;">sudo systemctl restart apache2</p>


<p style="background-color: black; padding: 5px 10px;color: #f44336; font-size: 12px;">sudo vi index.html</p>

<p style="background-color: black; padding: 5px 10px;color: #f44336; font-size: 12px;">sudo chown www-data:www-data ./index.html</p>


<p style="background-color: black; padding: 5px 10px;color: #f44336; font-size: 12px;">sudo cp -f ./index.html /var/www/html/index.html</p>


<p style="background-color: black; padding: 5px 10px;color: #f44336; font-size: 12px;">sudo systemctl restart apache2</p>


<p style="background-color: black; padding: 5px 10px;color: #f44336; font-size: 12px;">sudo apt update -y && sudo apt install nginx</p>

<p style="background-color: black; padding: 5px 10px;color: #f44336; font-size: 12px;">sudo systemctl status nginx</p>


<p style="background-color: black; padding: 5px 10px;color: #f44336; font-size: 12px;">sudo vi /etc/nginx/conf.d/loadbalancer.conf</p>

<p style="background-color: black; padding: 5px 10px;color: #f44336; font-size: 12px;">sudo nginx -t</p>


<p style="background-color: black; padding: 5px 10px;color: #f44336; font-size: 12px;">sudo systemctl restart nginx</p>


<h2>AUTOMATING LOADBALANCER CONFIGURATION WITH SHELL SCRIPTING</h2>


<button type="button" style="background-color: blue; border: none;  color: white; padding: 5px 10px;  text-align: center; text-decoration: none; display: inline-block; font-size: 15px; border-radius: 8px;">Copy Below Code</button>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo apt update -y && sudo apt install apache2 -y</p>


<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo vi install_configure_apache.sh</p>


<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo chmod +x install_configure_apache.sh</p>


<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">./install_configure_apache.sh Public_IP</p>


<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo vi nginx.sh</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">type esc then shift + :wq!</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">sudo chmod +x nginx.sh</p>

<p style="background-color: white; padding: 5px 5px;color: #f44336; font-size: 14px;">./nginx.sh PUBLIC_IP WEBSERVER1 WEBSERVER2</p>




