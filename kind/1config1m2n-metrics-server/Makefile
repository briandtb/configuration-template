all: create metrics-server ingress-contour

create:
	kind create cluster --config kind-example-config.yaml

delete:
	kind delete cluster

metrics-server:
	kubectl apply -f components.yaml
	kubectl patch deployment metrics-server -n kube-system -p '{"spec":{"template":{"spec":{"containers":[{"name":"metrics-server","args":["--cert-dir=/tmp", "--secure-port=4443", "--kubelet-insecure-tls","--kubelet-preferred-address-types=InternalIP"]}]}}}}'

ingress-contour:
	kubectl apply -f https://projectcontour.io/quickstart/contour.yaml
	kubectl patch daemonsets -n projectcontour envoy -p '{"spec":{"template":{"spec":{"nodeSelector":{"ingress-ready":"true"},"tolerations":[{"key":"node-role.kubernetes.io/master","operator":"Equal","effect":"NoSchedule"}]}}}}'
