gunicorn main:app --workers 1 --worker-class uvicorn.workers.UvicornWorker --bind 0.0.0.0:8000


granian --interface asgi --host 0.0.0.0 --port 8000 --workers 1 --threads 1 main:app


daphne -b 0.0.0.0 -p 8000 main:app


hypercorn --bind 0.0.0.0:8000 --worker-class uvloop main:app
