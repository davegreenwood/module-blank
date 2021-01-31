# Module Blank

## Docker

Using the image at:
https://github.com/envygeeks/jekyll-docker

Guide:
https://dev.to/michael/compile-a-jekyll-project-without-installing-jekyll-or-ruby-by-using-docker-4184


### Build

docker run --rm -it \
    --volume="$PWD:/srv/jekyll" \
    --volume="$PWD/_vendor/bundle:/usr/local/bundle" \
    --env JEKYLL_ENV=production \
    jekyll/jekyll:3.8 \
    jekyll build


### Serve

docker run --rm \
    --volume="$PWD:/srv/jekyll" \
    --volume="$PWD/_vendor/bundle:/usr/local/bundle" \
    --env JEKYLL_ENV=development \
    -p 4000:4000 jekyll/jekyll:3.8 \
    jekyll serve

Using Docker volume:

docker run --rm \
    --volume="${PWD}":/srv/jekyll \
    --volume="${HOME}/tmp/jekyll/bundle":/usr/local/bundle \
    --volume="${HOME}/tmp/jekyll/site":/site \
    --env JEKYLL_ENV=development \
    -p 4000:4000 \
    jekyll/jekyll:3.8 \
    jekyll serve --trace --destination /site


## Requirements

git submodule add https://github.com/hakimel/reveal.js.git
cd reveal.js
git checkout tags/4.1.0
cd ..
git commit -m "reveal 4.1.0"

