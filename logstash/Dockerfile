FROM logstash

COPY logstash.conf ~/
# RUN logstash-plugin install logstash-output-sumologic

CMD ["-f", "~/logstash.conf"]