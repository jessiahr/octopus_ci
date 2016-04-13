sudo cp /etc/letsencrypt/live/registry.URL_HERE/fullchain.pem /etc/letsencrypt/live/registry.octop.us/privkey.pem ~/jarvis/data_nginx/registry_ssl_keys/
sudo cp /etc/letsencrypt/live/ci.URL_HERE/fullchain.pem /etc/letsencrypt/live/ci.octop.us/privkey.pem ~/jarvis/data_nginx/jenkins_ssl_keys/

sudo chown $USER:$USER ~/octo_ci/data_nginx/registry_ssl_keys/*
sudo chown $USER:$USER ~/octo_ci/data_nginx/jenkins_ssl_keys/*

htpasswd -c registry.password USERNAME
htpasswd -c jenkins.password USERNAME

