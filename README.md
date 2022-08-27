# webhook2websocket

Forward webhook content to websocket clients.

## Workflow

Client

1. connect to ws and register client
2. get webhook URL
3. forward webhook URL to any service with your request
4. wait for response on websocket

Service

1. get task with webhook for response
2. do your job
3. notify client via webhook


## Dependencies

* redis server

## Usage

```bash
export WEBOOK_URL="https://wh2ws.example.com/webhook"
export WEBSOCKET_URL="https://wh2ws.example.com/ws"
export REDIS_URL="redis://redis.example.com:6379/0"
export LISTEN_IP="0.0.0.0"
export LISTEN_PORT=8080
./wh2ws
```

or

```
./xh2ws --redis-url redis://redis.example.com:6379/0 \
  --webhook-url https://wh2ws.example.com/webhook \
  --websocker-url https://wh2ws.example.com/ws \
  --listen-ip 0.0.0.0 \
  --listen-port 8080
```
