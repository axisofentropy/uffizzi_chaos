FROM nginx

# If it has been less than six minutes since build, exit.
# If now is more than ten minutes since build, listen TCP port 80.
CMD cat date.tmp && date --utc +'%s' && if [ $((`date --utc +'%s'` - `cat date.tmp` )) -lt 360 ]; then exit 100; else nginx -g 'daemon off;'; fi

# stamp build time within image.
RUN date --utc +'%s' | tee date.tmp

