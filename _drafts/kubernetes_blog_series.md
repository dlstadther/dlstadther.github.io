Kubernetes Blog Series

Macro Goal: Construct a Stateless Jenkins master/slave executor Build server using Kubernetes.

V0: Initial Installation Requirements
V1: Learn basic Kubernetes kubectl (and minikube) commands to deploy a basic Jenkins container
V2: Gain a better understanding of V1 through a code refactor to reduce deployment artifacts
V3: Introduction to Jenkins' Configuration as Code (JCasC) plugin + Basic Jenkins security
V4: Expansion on JCasC and Kubernetes DNS through addition of a Stateless Pipeline build job.
V5: Configure a build server with multiple job, in multiple syntaxes, with the inclusion of system dependencies

V5+: multi job, python job (with tests) (maybe run Luigi tests), persistent volume? (do any jenkins files really need to be persisted? build history, nextBuildNumber, etc.), using Jenkins HELM deployment, Deployment vs ReplicaSet
