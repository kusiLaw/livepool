FROM python:3.12-slim  
# container is a empty computer, install linux, install python 3.12

# create the working directory to /app in the container
WORKDIR /app 

# Install deps first (Docker layer caching — only re-runs if requirements.txt changes)
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 8000

CMD ["daphne", "-b", "0.0.0.0", "-p", "8000", "config.asgi:application"]