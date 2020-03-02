# Kubernetes

## Notes

* Top can be used on nodes or pods to see the runtime metrics
  * example: `k top pods|nodes`
* JSON path can be used to scope specific fields from responses of get/describe/ex.
  * example: `k get somePod -o jsonpath --template{.status.podIp}`

## Labels/Annotations

* General way to tag objects.
* Require the --overwrite flag when changing

## Ingress



## Daemon Set

* All or some notes run a copy of the pod.
* Great for log collectors, cluster storage (glusterd)
* Node monitoring tools
* Never created in a pending state (can be somewhat confusing)
* They can communicate a few ways with other pods:
  * example: DNS, NodeIP and Known Port, and push for when the DaemonSets just send data out.
