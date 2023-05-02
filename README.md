# Plexamp Headless 4 for Raspberry PI using Docker.
Based on <https://forums.plex.tv/t/suggestions-for-the-future-headless-rpi-support/218187/161>.

Update from https://github.com/malfario/plexamp-rpi-docker 

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

After setting up, run player:
```
docker-compose exec plexamp bash
node ~/plexamp/js/index.js
```

You should be able to access web player here : http://YOUR_SERVER_IP:32500.

You can now `stop/start` server by using `docker-composer down` or `docker-compose up -d`.

