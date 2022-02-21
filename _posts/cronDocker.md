
https://stackoverflow.com/questions/37015624/how-to-run-a-cron-job-inside-a-docker-container
https://www.thegeekstuff.com/2012/07/crontab-log/#:~:text=2%3E%261%20indicates%20that%20the,%2Fjohn%2Flogs%2Fbackup.


Dockerfile -> entry.sh -> crontab.txt

### Dockerfile
```
FROM alpine

COPY . /source/dir

# Authorize entry.sh
RUN chmod +x entry.sh

# set crontab file to cron.txt
RUN crontab -u root /source/dir/cron.d/cron.txt

# run
ENTRYPOINT ["/entry.sh"]

```

### entry.sh
```

### run crond background
/usr/sbin/crond -b

# run your app
python app.py
```

### crontab.txt
```
* 10 * * * python /source/dir/sciprt.py
```
