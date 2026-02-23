Based on the given assignment which is to design and deploy a scalable multi-client application environment using DevOps.

It should :  Run multiple applications (Node.js & Python)
            Support containerized deployment
            Enable automated CI/CD
            Provide monitoring and logging
            Run on AWS cloud infrastructure

This project simulates a real production DevOps environment.

-----------------  Application Architecture Overview

Two backend services were provided:   1.  Node.js Application (NestJS) 

                                      2. Python Application (FastAPI)

Both applications were containerized using Docker and deployed together.

----------------------Containerization Using Docker

Each application includes:      Dockerfile
                                Application source code
                                Runtime dependencies
                                Docker images were built using: docker build

------------------------Docker Swarm Orchestration

Docker Swarm was used as the orchestration platform.

The swarm cluster was initialized on AWS EC2:  docker swarm init

Services were deployed using a stack file:  docker stack deploy

Each application runs with multiple replicas for scalability.

---------------------------Reverse Proxy Using NGINX

NGINX acts as a single entry point for users.

Routing configuration:  URL	Service
                        /node	NodeJS App
                        /python	FastAPI App

------------------------------AWS EC2 Deployment

Infrastructure setup:   Ubuntu EC2 instance (Swarm manager & Swarm worker)

                        Docker installed

                        Security group allowing: Port( 80 (Application) , 3001 (Grafana) , 9090 (Prometheus) )
          
          
          
          !(https://github.com/PratikshaWankhede/devops-assignment-/blob/main/Screenshot-1.png)

The entire system runs inside this EC2 instance.

 -------------------------------CI/CD Pipeline Using GitHub Actions

Deploy updated services using Docker Swarm

-------------------------------Monitoring through Prometheus & Grafana

Monitoring stack includes:    Prometheus

                              Grafana

Health status is measured using:  probe_success

Values:  1 → Service running

        0 → Service down

------------------------Centralized Logging

Logging stack:   Promtail → Loki → Grafana

------------------------Health Checks & Observability

System health is continuously verified using:  HTTP endpoint monitoring

                                               Container status tracking

                                               Metrics visualization
                        
                                               Log aggregation

This provides complete observability of the application environment.

--------------------------Final Outcome

The final environment provides:    Multi-service deployment

                                   Automated CI/CD pipeline

                                   Health monitoring dashboards

                                   Centralized logging system

                                   Cloud-hosted scalable setup

The solution closely resembles a real-world DevOps production architecture.

✔ CI/CD implementation
✔ Monitoring explanation
✔ Interview-ready project
