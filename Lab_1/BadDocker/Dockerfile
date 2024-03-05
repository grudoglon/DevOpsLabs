FROM python:latest AS alakasam

EXPOSE 8000

RUN pip3 install click==8.0.3
RUN pip3 install colorama==0.4.4
RUN pip3 install Flask==2.0.2
RUN pip3 install gunicorn==20.1.0
RUN pip3 install itsdangerous==2.0.1
RUN pip3 install Jinja2==3.0.3
RUN pip3 install MarkupSafe==2.0.1
RUN pip3 install Werkzeug==2.0.2

COPY . .

CMD ["gunicorn", "--bind", "0.0.0.0:8000", "app:app"]
