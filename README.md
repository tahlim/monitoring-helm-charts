# monitoring-helm-charts


kubectl get secret --namespace prometheus-operator prometheus-operator-grafana -o jsonpath="{.data.admin-password}" | base64 --decode ; echo
kubectl get secret --namespace monitoring grafana -o jsonpath="{.data.admin-password}" | base64 --decode ; echo

--------------------------------------------------------------------------------------------------------------------------------------------
kubectl create namespace monitoring

node selector = (service=true)

1. install influxdb(time series DB, jitne bhi metrices prometheus report kr rha hi usse vo store krta hi, like ek week and ek month ka data dekhne k liye)

helm install influxdb -n monitoring .

Note: user - admin , passowrd - admin123  (and promethes me influxdb ka pod ip daal dena hi with ports)

2. install kube-state-metrics

helm install kube-state-metrics -n monitoring .

3. install prometheus

helm install prometheus -n monitoring .

4. install grafana

helm install grafana -n monitoring .

Password: lYTjpvAGpiDJf83N0Kq4o8JYPFZxA2TLloKgrSaq
