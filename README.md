# To run application within laravel directory
    - Go inside laravel directory after that go inside laravel-app or laravel-app follow the README.md steps

# To run application within vuejs directory
    - Go inside vuejs directory after that go inside vue-app or vuejs-dist follow the README.md steps

# To deploy laravel and vuejs applications on top of kubernetes.
    - First deploy application in docker
    - Convert the application in docker image and use that image in kubernetes or push it to self hosted registry like harbor
    - Expose the required ports

# An architecture diagram to set up Laravel Dockerized applications on Kubernetes:

                    +---------------------------+
                    |         Kubernetes        |
                    +---------------------------+
                                  |
                 +----------------------------------+
                 |              Ingress             |
                 +----------------+-----------------+
                                  |
                                  v
                     +------------+-------------+
                     |         Nginx            |
                     +------+-----------+-------+
                            |           |
                            v           v
               +------------+--+    +---+------------+
               |   Laravel Pod  |   | MySQL Pod      |
               +------+---------+    +--------+------+
                      |                       |
                      v                       v
        +-------------+--------+   +----------+------------+
        |   Laravel Container  |   | MySQL Container       |
        +----------------------+   +-----------------------+

# An architecture diagram for deploying Vue.js application on Kubernetes:

              +------------------------+
              |                        |
              |   Kubernetes Cluster   |
              |                        |
              +------------+-----------+
                           |
          +----------------+---------------+
          |                                |
          |          Ingress Controller    |
          |          (e.g., Nginx)         |
          +------------+-------------------+
                         |
            +------------v---------------+
            |                            |
            |       Service (NodePort)   |
            |                            |
            +------------+---------------+
                         |
            +------------v----------------+
            |                             |
            |    Deployment               |
            |    (Vue.js Application)     |
            |                             |
            +------------+----------------+
                         |
            +------------v----------------+
            |                             |
            |      Docker Containers      |
            |      (Vue.js Application)   |
            |                             |
            +------------+----------------+
