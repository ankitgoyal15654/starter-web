# Intellitrail

This module is known as Intelligent Fleet Tracking system. Intellitrail is a web-based application that allow you to locate, monitor and manage your machine fleet. This is a kind of IOT device, which were configured to send different types of signals to Aws IOT. From AWS IOT data are flowing to MySQL and then from MySQL we are sending data to Cassandra so that we can keep track of historical data also. . We expose these data using API gateway and Flask API integration and send it to our front-end team who plot various graphs to get various insights like machine usage, geo location of the device, machine shifts, low usage, High usage etc.

## Getting Started

1.clone the project
```
git clone https://gitlab.diversey.com/digital/intellitrail/ioc-portal-data-intellitrail.git
```
2. go to ioc-portal-data-intellitrail\Flask
3. Run app.py
```
python app.py
```

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

1. Install Mysql
2. Install dev centre for cassandra from the link:
```
https://downloads.datastax.com/datastax-ddc/
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
pip -r requirements.txt
```
            OR
```
python -m pip -r requirements.txt
```
6. Run the cql server in path
```
C:\Program Files\DataStax-DDC\apache-cassandra\bin
```
run command
```
cassandra
```
7. Create tables in cassandra from given link:
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
Mean you all dependicies of software has installed

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

the list of contributors - need to added

## License

The list of the license for given libraries and software is given in 
```
ioc-portal-data-intellitrail\Flask\license\license.txt
```
This project is licensed under the (Need to added)

## Acknowledgments

* To run this application ,First Setup API gateway and create all the tables with all the dependencies and software .
