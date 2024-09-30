# client-postgres



## configuration, using kustomize, to deploy a postgres instance into kubernetes

### notes

1. the _config.properties_ defines the database name, and a user/password to access it. no, not even remotely secure [should be fixed]
2. _overlays/dev_ defines a _HostPort_ persistent volume and ties both the **pv** and **pods** to that node. definitely a sandbox solution where you have multiple nodes and no good pv sources that span nodes (solution was found in [this thread](https://stackoverflow.com/questions/60247100/hostpath-assign-persistentvolume-to-the-specific-work-node-in-cluster))
