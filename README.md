# OpenShift-KnowledgeBase
OpenShift learning

# OpenShift Container Platform 3.6- Installation
0. OpenShift Architecture and Components
Architecture

Infrastructure components:
  Kubernetes Infra:
    Kubernetes manages containerised application across a set of container or hosts and provide mechanisms for deployment, maintenance and application scaling. The Docker service packages: instantiates and runs containerisd application.
    Kubernetes Cluster contains one or more masters and set of nodes.
    OCP 3.6 uses Kubernetes 1.6 & docker 1.12
    
    Componets:
      Master : Consists of API server, Repication Conttoller,scheduler, Datastore
      AppNode: Pods
      InfraNode: Router/Registry, Metrics/EFK
      
      Master: It contains master componets, including API server, Controller manager server & ETCD. Master manages nodes in                 its kubernetes cluster and schedules pods to run on nodes.
        Master Components:
          *API Server : It validates & configues the data for pods,services and replication controllers. Assigns pods to nodes            & synchronizes pod information with service configuration. It can be run as standalone process
          *ETCD: It stores the persistent master state. While othe components watch ETCD for changes to bring themselves into            desired state.
                 ETCD is an Opensource distributed key-value store that provides shared configuration and service discovery              for container linux clusters.
                 It comes by default with all master nodes. It can be run standalone(Optionally).
          *Controller Manager Server: The Controller Manager Server watches ETCD for changes to replication controller objects            and then uses the API to enforce the desired state.
                 It can also be run as a standalone process. Several such process create a cluster with one active leader at a            time.
          *HA Proxy: Optional, used when configuring highly-available masters with the native method to balance load between              API master endpoints.
          
Core Concepts
Networking
