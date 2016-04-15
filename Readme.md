```bash
sudo apt-get -y install apache2-utils

cd ~
git clone https://github.com/letsencrypt/letsencrypt
cd letsencrypt
./letsencrypt-auto certonly --standalone -d registry.myproject.com
./letsencrypt-auto certonly --standalone -d ci.myproject.com

sudo cp /etc/letsencrypt/live/registry.URL_HERE/fullchain.pem /etc/letsencrypt/live/registry.URL_HERE/privkey.pem ~/jarvis/data_nginx/registry_ssl_keys/
sudo cp /etc/letsencrypt/live/ci.URL_HERE/fullchain.pem /etc/letsencrypt/live/ci.URL_HERE/privkey.pem ~/jarvis/data_nginx/jenkins_ssl_keys/

sudo cp /etc/letsencrypt/live/git.URL_HERE/fullchain.pem /etc/letsencrypt/live/git.URL_HERE/privkey.pem ~/octopus_ci/data_nginx/gogs_ssl_keys/


sudo chown $USER:$USER ~/octo_ci/data_nginx/registry_ssl_keys/*
sudo chown $USER:$USER ~/octo_ci/data_nginx/jenkins_ssl_keys/*
sudo chown -R 1000 ~/octo_ci/data_jenkins/

htpasswd -c registry.password USERNAME
htpasswd -c jenkins.password USERNAME
```

