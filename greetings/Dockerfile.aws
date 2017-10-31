FROM ubuntu:14.04
RUN apt-get update -y \ 
    && apt-get install -y python-setuptools python-pip
ADD requirements.txt /src/requirements.txt
RUN cd /src; pip install -r requirements.txt
ADD . /src
EXPOSE 5000
ENV  PASSWORD $CLOUDARK_RDS_MasterUserPassword
ENV  DB $CLOUDARK_RDS_DBName
ENV  HOST $CLOUDARK_RDS_Address
ENV  USER $CLOUDARK_RDS_MasterUsername
CMD ["python", "/src/application.py"]
