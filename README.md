# prometheus-for-k8s

该仓库基于[kube-prometheus-stack helm chart](https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack/templates) 生成各个监控组件的yaml文件。

kube-prometheus-stack的部署文档可以参考：[kube-prometheus-stack的使用](https://blog.huweihuang.com/kubernetes-notes/monitor/kube-promethus-stack/)

包含的组件有：

- grafana
- kube-state-metrics
- prometheus
- alertmanager
- node-exporter
- 
