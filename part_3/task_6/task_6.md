## Report 3.6b

The use of Docker has multiple advantages. Firstly by using Docker, one can count on reproducibility as every container will run exactly the same on another computer running Docker. Docker also provides isolation so dependencies or settings of containerized application do not affect your computer or any other running containers. Dividing large applications to multiple containers prevents other containers from being compromised when one container becomes compromised. Docker makes also maintaining multiple environments easy and allows easy continuous integration via CI-tool and Docker Hub. Lastly, but not least, Docker Hub provides multiple pre-configured container images for everyones use.

Docker also has disadvantages. Due to overhead in Docker, applications will not run as fast as on bare-metal server, though overhead is smaller than in virtual machines. Docker also lacks true cross-platform compatibility as application designed to run in a Docker container on Windows can not run on Linux, and vice versa. Docker can also only host applications that run on command line as there is no graphical interface. And although Docker provides security through separation it will also create new security challenges e.g. monitoring in dynamic, large-scale environment. Docker development also progresses rapidly, so you will have to keep your host up-to-date.

Use Docker...
- ...to match your production environment and development environment.
- ...to avoid depencency conflicts when running multiple applications on same server.
- ...to achieve faster software delivery cycle.
- ...to enable application portability.
- ...when you want to use microservice architecture.

Do not use Docker...
- ...when your application is resource hungry and/or performance is critical.
- ...when security is critical.
- ...to substitute for virtual machines.
- ...when your environment is large and you do not have man-power to keep dependencies in containers up-to-date.
