FROM python

 WORKDIR /usr/src/app

 COPY requirements.txt ./requirements.txt

 RUN pip install -r requirements.txt

 COPY . .

 EXPOSE 80

 CMD ["gunicorn", "app:app", "-b", "0.0.0.0:80", "--log-file", "-", "--access-logfile ", "-", "--workers", "4","--keep-alive", "0"]