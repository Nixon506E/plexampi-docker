# Plexamp Headless 4 for Raspberry PI using Docker.
Based on <https://forums.plex.tv/t/suggestions-for-the-future-headless-rpi-support/218187/161>.

Update from https://github.com/malfario/plexamp-rpi-docker 

## Install

```
git clone <repo> plexamp
cd plexamp
docker-compose build
docker-compose up -d
```

First run, set token :
```
docker-compose exec plexamp bash
node ~/plexamp/js/index.js
```

1. Get a token here: https://www.plex.tv/claim/
2. And fill prompt.
3. Set speaker name

## Test run
After setting up, run player:
```
docker-compose exec plexamp bash
node ~/plexamp/js/index.js
```

You should be able to access web player here : http://YOUR_SERVER_IP:32500.

## run with docker
You can now `stop/start` server by using `docker-composer down` or `docker-compose up -d`.

## Start service on boot

Update `WorkingDirectory` path in `docker-plexamp.service` :
```
chmod +x </path/to/repo/>docker-plexamp.service
sudo ln -s </path/to/repo/>docker-plexamp.service /etc/systemd/system/docker-plexamp.service
sudo systemctl enable docker-plexamp
sudo service docker-plexamp.service start 
sudo systemctl daemon-reload
```