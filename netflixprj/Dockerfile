From python:3.10
ENV PYTHONBUFFERED 1
RUN mkdir /src
WORKDIR /src
COPY . /src
RUN pip install --trusted-host pypy.org --trusted-host files.pythonhosted.org -r requirements.txt

CMD python manage.py collectstatic --no-input && python manage.py makemigrations && python manage.py migrate --run-syncdb && gunicorn --workers 3 --bind :8000 netflixprj.wsgi:application 
