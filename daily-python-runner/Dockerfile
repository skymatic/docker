FROM python:3.6-alpine

COPY run-python /etc/periodic/daily/run-python
RUN chmod 0755 /etc/periodic/daily/run-python
RUN touch /var/log/cron

ENV CRONJOB="python --version"

CMD printenv | sed -e 's/^\([^=]*\)=\(.*\)$/export \1="\2"/g' > /root/envvars.sh && crond && tail -f /var/log/cron
