create:
	kind create cluster --config kind-example-config.yaml

delete:
	kind delete cluster

metrics-server:
	kubectl apply -f components.yaml
	kubectl patch deployment metrics-server -n kube-system -p '{"spec":{"template":{"spec":{"containers":[{"name":"metrics-server","args":["--cert-dir=/tmp", "--secure-port=4443", "--kubelet-insecure-tls","--kubelet-preferred-address-types=InternalIP"]}]}}}}'

