# IntelliTrail

This module is known as Intelligent Fleet Tracking system. Intellitrail is a web-based application that allow you to locate, monitor and manage your machine fleet. This is a kind of IOT device, which is configured to send different events of signal to MQTT. From MQTT data is flowing to MySQL and Cassandra through live data handler so that we can keep track of historical data. We expose required data using Flask API's integrated through AWS API gateway and is consumed by front-end who uses the data to populate tables or plot various graphs etc., to get various insights like machine usage, geo location of the device, machine shifts, low usage, High usage etc.

## Getting Started

1.Clone the project from gitlab
```
git clone https://gitlab.diversey.com/digital/intellitrail/ioc-portal-data-intellitrail.git
```

2.go to ioc-portal-data-intellitrail\Flask

3.Run app.py
```
python app.py
```

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

1.Install Mysql Community edition

2.Install Dev Centre for cassandra from the link:
```
https://downloads.datastax.com/datastax-ddc
(datastax-ddc-64bit-3.9.0.msi)
```
3.Create tables in given link:
```
https://docs.google.com/document/d/1o39jGIScUl8yLUvTX9hO1RnxbLxkwAoInnlFei4Oyic
```
4.Install python 2.7.13 from the link :
```
https://www.python.org/downloads/release/python-2713/
```
5.Install all the libraries in given [file](https://gitlab.diversey.com/digital/intellitrail/ioc-portal-data-intellitrail/blob/master/Flask/requirements.txt)
```
pip install -r requirements.txt
```
            OR
```
python -m pip install -r requirements.txt
```
6.Run the cql server in path
```
C:\Program Files\DataStax-DDC\apache-cassandra\bin
```
run command in cmd:
```
cassandra
```
7.Create tables in cassandra from given link:
```
https://docs.google.com/document/d/1A7zsQu_f7yjZ6yxGyst_ofNv1rmxzlOpYg5aza7Uuds
```

### Installing

Run app.py in ioc-portal-data-intellitrail\Flask
```
python app.py
```
If it is not giving any error then your development environment is running
In the result you will get
```
* Serving Flask app "app" (lazy loading)

* Debug mode: off/on
```
It means your all dependencies and software has been installed.

### And coding style tests

Strictly following the pep8 coding style

```
pylint <python_filename>.py
```

To check Cyclomatic Complexity

```
radon cc -s <python_filename>.py
```

## Deployment

1. open workspase
2. Download latest code from git
3. open the winscp and connect to
```
 10.244.144.62
```
4. transfer the code to server through winscp
5. run the command
```
 lsof -i:8000
```
6. kill all the processes by running the command 
```
kill -9 <process id of our python execution>
```
7. Go to directory where app.py is present
```
ioc-portal-data-intellitrail\Flask
```
8. At last run the command 
```
sudo gunicorn -b 0.0.0.0:8000 app:app &
```
9. Now your API is exposed at
``` 
http://34.253.12.236:8000
```

## Built With

* [Flask_Restful](https://flask-restful.readthedocs.io/en/latest/) - The rest framework used
* [Python](https://docs.python.org/2/index.html) - Python dependicies
* [gunicorn](http://docs.gunicorn.org/en/19.7.1/news.html) - Used to expose API's
* [flask_sqlalchemy](http://flask-sqlalchemy.readthedocs.io/en/stable/) - ORM used
* [Cassandra_driver](https://datastax.github.io/python-driver/) -  Cassandra used

## Authors

* **Diversey**

the list of contributors - need to be added

## License

The list of the license for given libraries and software is given in 
```
ioc-portal-data-intellitrail\Flask\license\license.txt
```
This project is licensed under the (Need to be added)

## Acknowledgments

* To run this application ,First Setup AWS API gateway and create all the tables with all the dependencies and software.
