# Open Source Alternatives to AWS Services *gptGenerated*

This document maps AWS services (covered in the AWS Solutions Architect Associate/Professional exams) to their
open-source counterparts.

---

## 🧠 Compute

| AWS Service       | Open Source Alternative                           | Notes                            |
|-------------------|---------------------------------------------------|----------------------------------|
| EC2               | KVM, VirtualBox, Proxmox, OpenStack Nova          | Virtual machines and hypervisors |
| Lambda            | OpenFaaS, Knative, Apache OpenWhisk               | Serverless function execution    |
| Auto Scaling      | Kubernetes HPA, Terraform + Cron + Custom Metrics | Scaling workloads automatically  |
| Elastic Beanstalk | Dokku, CapRover, Fly.io (FOSS-friendly)           | PaaS-like abstraction for apps   |

---

## 🗂️ Storage

| AWS Service | Open Source Alternative          | Notes                       |
|-------------|----------------------------------|-----------------------------|
| S3          | MinIO, Ceph Object Gateway (RGW) | Object storage              |
| EBS         | OpenStack Cinder, Longhorn, Rook | Block storage               |
| EFS         | NFS, GlusterFS, CephFS           | Network/shared file systems |

---

## 🛠️ Infrastructure as Code & Orchestration

| AWS Service    | Open Source Alternative    | Notes                      |
|----------------|----------------------------|----------------------------|
| CloudFormation | Terraform, Pulumi, Ansible | Declarative infrastructure |
| OpsWorks       | Chef, Puppet, Ansible      | Configuration management   |

---

## 🧮 Databases

| AWS Service | Open Source Alternative                  | Notes                              |
|-------------|------------------------------------------|------------------------------------|
| RDS         | PostgreSQL, MySQL, MariaDB               | Native open-source RDBMS           |
| Aurora      | Vitess, CockroachDB, TiDB                | Cloud-native/distributed SQL       |
| DynamoDB    | Apache Cassandra, ScyllaDB, FoundationDB | NoSQL key-value/wide-column stores |
| ElastiCache | Redis, Memcached                         | In-memory caching                  |
| Neptune     | Neo4j (Community), JanusGraph, ArangoDB  | Graph databases                    |

---

## 📡 Networking & Content Delivery

| AWS Service   | Open Source Alternative           | Notes                            |
|---------------|-----------------------------------|----------------------------------|
| VPC           | OpenStack Neutron, Calico, Cilium | Virtual networking               |
| Route 53      | CoreDNS, PowerDNS, Unbound        | DNS service                      |
| API Gateway   | Kong, Tyk, Traefik, Envoy         | API management                   |
| CloudFront    | NGINX + GeoIP, Varnish, Squid     | CDN-like caching/reverse proxy   |
| Load Balancer | HAProxy, NGINX, Traefik, Envoy    | Load balancing and reverse proxy |

---

## 🔐 Identity & Access Management

| AWS Service | Open Source Alternative      | Notes                      |
|-------------|------------------------------|----------------------------|
| IAM         | Keycloak, Authelia, Dex, OPA | Auth, RBAC, SSO            |
| Cognito     | Keycloak, ORY Kratos/Hydra   | User identity & federation |

---

## 📈 Monitoring & Logging

| AWS Service | Open Source Alternative               | Notes                  |
|-------------|---------------------------------------|------------------------|
| CloudWatch  | Prometheus + Grafana, Zabbix, Netdata | Metrics and monitoring |
| CloudTrail  | Auditd, OSQuery, ELK Stack            | Audit logging          |
| X-Ray       | Jaeger, OpenTelemetry, Zipkin         | Distributed tracing    |

---

## 📬 Messaging & Streaming

| AWS Service | Open Source Alternative                   | Notes          |
|-------------|-------------------------------------------|----------------|
| SNS         | NATS, RabbitMQ (PubSub), Apache Kafka     | Pub/Sub        |
| SQS         | RabbitMQ, ActiveMQ, Kafka, Celery + Redis | Queuing        |
| Kinesis     | Apache Kafka, Redpanda, Pulsar, Fluvio    | Streaming data |

---

## 🔒 Security & Compliance

| AWS Service     | Open Source Alternative                        | Notes               |
|-----------------|------------------------------------------------|---------------------|
| KMS             | HashiCorp Vault, Keycloak                      | Key management      |
| Secrets Manager | Vault, Bitwarden (self-hosted), Sealed Secrets | Secrets management  |
| GuardDuty       | Wazuh, OSSEC, Falco                            | Intrusion detection |

---

## 📦 DevOps & CI/CD

| AWS Service  | Open Source Alternative                    | Notes           |
|--------------|--------------------------------------------|-----------------|
| CodePipeline | Jenkins, GitLab CI, Argo Workflows, Tekton | CI/CD pipelines |
| CodeBuild    | Jenkins, Buildkite (open agent)            | Build systems   |
| CodeDeploy   | Ansible, Jenkins + SSH, Spinnaker, FluxCD  | App deployment  |

---

## 🧭 Other Tools

| AWS Concept   | Open Source Tool                   | Notes                   |
|---------------|------------------------------------|-------------------------|
| Service Mesh  | Istio, Linkerd, Consul Connect     | Microservice networking |
| Cost Tracking | OpenCost, Kubecost                 | Cost visibility         |
| ECS/EKS       | Docker + Kubernetes, Podman, Nomad | Container orchestration |

---

## 📊 Big Data & Analytics

| AWS Service             | Open Source Alternative                         | Notes                                      |
|-------------------------|-------------------------------------------------|--------------------------------------------|
| EMR (Elastic MapReduce) | Apache Hadoop, Apache Spark, Flink, Dask        | Big data processing frameworks             |
| Glue (ETL)              | Apache NiFi, Apache Airflow, Talend Open Studio | ETL orchestration and data pipelines       |
| Athena                  | Presto, Trino, Apache Drill                     | Query engines for data lakes               |
| Redshift                | ClickHouse, Apache Druid, Greenplum, DuckDB     | Data warehouses and OLAP databases         |
| QuickSight              | Apache Superset, Metabase, Redash               | Business intelligence & data visualization |

---

## 🤖 Machine Learning & AI

| AWS Service    | Open Source Alternative                | Notes                                       |
|----------------|----------------------------------------|---------------------------------------------|
| SageMaker      | Kubeflow, MLflow, H2O.ai, JupyterHub   | ML model training, tracking, and deployment |
| Comprehend     | spaCy, NLTK, Hugging Face Transformers | NLP libraries and frameworks                |
| Rekognition    | OpenCV, Dlib, YOLOv5, DeepFace         | Image and facial recognition                |
| Lex (Chatbots) | Rasa, Botpress                         | Conversational AI and chatbot frameworks    |
| Translate      | OpenNMT, Fairseq                       | Machine translation                         |
| Forecast       | Prophet (by Facebook), Darts           | Time series forecasting                     |
| Personalize    | LensKit, Surprise, LightFM             | Recommendation systems                      |
