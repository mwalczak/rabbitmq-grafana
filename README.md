# rabbitmq-grafana

Monitor rabbitmq instance with Grafana and Prometheus

Start with:
```
docker-compose up -d
```

Enable prometheus metrics in your rabbitmq servers (3.8.0+):
```
rabbitmq-plugins enable rabbitmq_prometheus
```
and remember to expose port 

Login to Grafana:

http://localhost:3000

with: ```admin / secret``` (you can change password in docker-compose.yml)

Go to:

http://localhost:3000/dashboard/import

and import dashboard from file:
```
dashboard.json
```

Note:

Add more rabbitmq servers in 
```
- job_name: 'rabbitmq-server'
    static_configs:
      - targets:
          - 'rabbitmq:15692'
```