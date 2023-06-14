# 0. 概述

该仓库基于[kube-prometheus-stack helm chart](https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack/templates) 生成各个监控组件的yaml文件。由于kube-prometheus-stack是一组打包监控工具，在真实场景中并不一定需要安装全部组件，因此本文旨在提供一种灵活的监控组件安装方案，用户可以根据需求安装所需组件。

kube-prometheus-stack的部署文档可以参考：[kube-prometheus-stack的使用](https://blog.huweihuang.com/kubernetes-notes/monitor/kube-promethus-stack/)

包含的组件有：

- grafana
- kube-state-metrics
- prometheus
- prometheus-node-exporter
- prometheus-operator
- alertmanager

建议安装的组件：

- kube-state-metrics
- prometheus
- grafana

# 1. 搭建k8s监控体系

## 1.1. 部署监控告警系统

- 部署kube-state-metrics
- 部署prometheus
- 部署grafana

## 1.2. 配置监控模板



## 1.3. 配置告警策略



# 2. k8s监控指标

## 2.1. 用户视角

### 2.1.1. Pod级别

筛选标签：namespace/deployment/pod/container

- CPU（使用量，limit，request值）
- 内存指标（使用量，limit，request值）
- 网络发送速率、接收速率

### 2.1.3. 流量数据（Nginx）

- 入流量
- 出流量
- Url延迟

## 2.2. 管理员视角

### 2.2.1. Node级别

- CPU（使用量，limit，request值）
- 内存（使用量，limit，request值）
- 磁盘

- 网络入流量，出流量

### 2.2.2. 集群维度

- 集群维度（集群CPU,内存总量、limit，request值）
- 节点维度（总量，ready, notready）
- pod维度（总量，running, crash，pending）
- deployment维度

### 2.2.3. k8s组件级别

- **Etcd**（核心）
- **Apiserver**（核心）
- Controller-manager
- Scheduler
- Kubelet
- Kube-Proxy

# 3. k8s告警指标

## 3.1. 用户视角

Pod级别

- Pod 状态告警（crash，pending）
- Pod 资源告警（CPU、内存超过limit 80%阈值）

## 3.2. 管理员视角

管理员视角包含用户视角的告警。

### 3.2.1. Node级别

- Node状态（NotReady，宕机）
- Node 资源值（CPU、内存、根分区磁盘 80%阈值）
- Node其他告警

### 3.2.2. k8s组件告警

- k8s 组件状态告警

# 4. k8s监控指标函数

## 4.1. kube-state-metrics函数

## 4.2. cAdvisor函数

参考：
- https://cloud.tencent.com/document/product/1416/56011
- https://mp.weixin.qq.com/s/ffn0ur5ZBTvM9dztgjz5EA