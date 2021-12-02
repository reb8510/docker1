# Installing Docker with OpenVAS/Greenbone vulnerability scanner

**Welcome to how to install Docker**
<p>This is how to install Docker on Ubuntu. I also installed OpenVAS/Greenbone vulnerability scanner via Docker. </p>
<p>Go ahead and open up your Ubuntu VM and open terminal.</p>

**Apt Update**
<p>To make sure all the reposititories are updated.</p>
<pre><code> sudo apt-get update</code></pre>

**Apt Upgrade**
<p>To make sure all the reposititories are upgraded.</p>
<pre><code> sudo apt-get upgrade</code></pre>

**Install Docker**
<p>This is when you will actually install docker after you have updated and upgraded all repositiories.</p>
<pre><code> sudo apt-get install docker.io</code></pre>

**Check Status**
<p>To check to see if Docker is running you will run this command.</p>
<pre><code>sudo service docker status</code></pre>

**If inactive, run this**
<p>If by chance your Docker is not running (inactive), you will run this command.</p>
<pre><code> sudo service docker start</code></pre>

**Check Status**
<p>To check to see if Docker is running once again you will run this command. This will then show the Docker is active!</p>
<pre><code>sudo service docker status</code></pre>

**Install Container for OpenVAS**
<p>To run an application you will need to install a container for OpenVAS. This is the Container I used. The Container was not found locally, but it will download from Docker. So it will take a couple minutes.</p>
<pre><code>sudo docker run -d -p 443:443 --name openvas mikesplain/openvas</code></pre>

**Open Local Host**
<p>Since now the container is installed locally, open FireFox and open up the following...</p>
<pre><code>https://localhost/</code></pre>

**Login to OpenVAS**
<p>Login to OpenVAS and then you will instantly be taken to the dashboard to run scans</p>
<pre><code>login: admin password: admin</code></pre>

**Run Vulnerability Scan**
<p>Login to OpenVAS, open dashboard, above the dashboard you will find "Scans" and once you hover over "Scans", you will click "Task," once the Task dashboard loads, you will find the star icon in the left corner, and that is where you will choose to create a Vulnerability Scan.  </p>

**How to create a docker-compose.yml file**
<pre><code>docker run -p 80:80 -v /var/run/docker.sock:/tmp/docker.sock:ro --restart always --log-out max-size=1g nginx</code></pre>
<p>This is the output once the docker-compose.yml is created</p>
<pre><code>version: '3.3'
services:
    nginx:
        ports:
            - '80:80'
        volumes:
            - '/var/run/docker.sock:/tmp/docker.sock:ro'
        restart: always
        image: nginx
        </code></pre>

Attached in the Harvey submission is the output of the OpenVAS dashboard! Thank you :-)
