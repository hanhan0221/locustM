Make docker images:
docker build -t springsoft/locusts -f dockerfile_locust .
docker build -t springsoft/locusts:master -f dockerfile_master .
docker build -t springsoft/locusts:slave -f dockerfile_slave .


Run docker images:
Master: docker run  -p 8000:8000 -p 6666:6666 -p 6667:6667 -p 5557:5557 -p 5558:5558 -p 8089:8089 -it --rm springsoft/locusts:master

Slave: docker run -e HOST={MASTER_IP} -it --rm springsoft/locusts:slave
