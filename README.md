# Install Jekyll Docker
[manual here](https://dev.to/stankukucka/install-jekyll-on-your-mac-with-docker-compose-file-everything-you-need-to-get-going-2alf)

```bash
mkdir jekyll-website
cd jekyll-website
touch docker-compose.yml
```

copy code below in your `docker-compose.yml` file

```yml
version: "3"

services:
  jekyll:
    image: jekyll/jekyll:latest
    command: jekyll serve --watch --force_polling
    ports:
      - 4000:4000
    volumes:
      - .:/srv/jekyll
```

```bash
docker-compose run jekyll /bin/bash

jekyll new . --force
```

config your Jekyll files, then

```yml
bundle update

exit

docker-compose up
```