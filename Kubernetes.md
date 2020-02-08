# Kubernetes

## Notes

## Daemon Set

* All or some notes run a copy of the pod.
* Great for log collectors, cluster storage (glusterd)
* Node monitoring tools
* Never created in a pending state (can be somewhat confusing)
* They can communicate a few ways with other pods:
  * ex: DNS, NodeIP and Known Port, and push for when the DaemonSets just send data out.
