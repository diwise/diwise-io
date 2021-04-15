# diwise-io

Web site to be served under diwise.io

# Build and run with Docker

```bash
docker build -f deployment/Dockerfile -t diwise/diwise-io:latest .
docker run --rm -it -p 8080:8080 diwise/diwise-io
```
