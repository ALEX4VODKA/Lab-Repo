# Lab

面向 SRE / 云原生运维 / DevOps / AI Infra 求职方向的长期实战学习仓库。

这个仓库的目标不是构建一个“大而全”的云原生平台，也不是追求掌握尽可能多的技术栈。

核心目标是：

> 通过真实的三节点 Linux / Kubernetes Lab，将简历中的技术能力、筛选后的面试问题和真实工作场景转化为可重复实践、故障排查和面试验收能力。

---

## 1. 学习原则

本项目采用 **Ticket 模式**，不采用 Day 1 / Day 2 等时间绑定式计划。

时间可以弹性，但验收标准不能降低。

Ticket 状态统一为：

- `TODO`：尚未系统学习或实践
- `LEARNING`：已经学习/实践，但还不能独立完成
- `PASSED`：达到明确验收标准

一个 Ticket 即使跨多天完成也没有问题。

只有达到 Acceptance Criteria 后才能标记为 `PASSED`。

---

## 2. 核心目标

重点建立以下能力：

### Linux / Shell

- 进程与服务
- CPU / Memory / Load
- Disk / Filesystem
- Permissions
- Logs
- I/O
- systemd
- grep / awk / sed / find
- Pipe / Redirect
- 基础 Shell 自动化

Shell 不作为独立课程学习，而是融合进日常 Linux、Docker 和 Kubernetes 操作。

### Network

重点掌握：

- IP
- Subnet
- Gateway
- ARP 基础
- TCP
- Port
- DNS
- HTTP
- HTTPS / TLS

以及常用排障工具：

- `ip`
- `ping`
- `ss`
- `nc`
- `curl`
- `dig`
- `nslookup`
- `traceroute`
- `tcpdump`

### Container / Docker

重点掌握：

- Image
- Container
- Dockerfile
- ENTRYPOINT / CMD
- Volume / Bind Mount
- Port Mapping
- Container Network
- Namespace
- Cgroup
- containerd
- CRI

### Kubernetes

这是本仓库最重要的主线之一。

重点包括：

- Control Plane 组件
- API Server
- etcd
- Scheduler
- Controller Manager
- kubelet
- containerd / CRI
- CNI

以及：

- Pod
- Deployment
- ReplicaSet
- StatefulSet 基础
- DaemonSet 基础
- Job / CronJob 基础
- Service
- ClusterIP / NodePort
- EndpointSlice
- ConfigMap / Secret
- requests / limits
- Probe
- PVC / PV
- Namespace
- Node
- taint / toleration 基础
- affinity 基础

重点训练真实故障排查，而不是只学习正常部署。

---

## 3. SRE / 工程工具

### Git

Git 应贯穿整个 Lab。

重点形成：

- Working Tree
- Staging Area
- Commit
- Branch
- Remote
- origin
- push / pull
- merge
- conflict

的实际使用习惯。

### Ansible

Ansible 的明确目标：

> 能够熟练使用 Ansible 初始化自己的三节点 Kubernetes Lab。

包括：

- Inventory
- SSH Key
- Ad-hoc
- Playbook
- Role
- Variables
- register
- when
- handler
- 幂等性

最终应能够从基础 Ubuntu 环境完成节点标准化和 Kubernetes 集群初始化。

### SQL / MySQL

重点：

- 基础 SQL
- JOIN
- GROUP BY
- Index
- EXPLAIN
- Transaction / ACID 基础
- 慢查询基本排查

不以 DBA 深度为目标。

### Prometheus / Grafana

重点：

- Metrics
- Scrape
- Target
- TSDB
- PromQL 基础
- node-exporter
- kube-state-metrics
- 容器指标
- Alertmanager 基础
- Grafana 可视化

需要在本 Lab 中实际观察 Node / Pod / Container 的指标。

### Nginx

重点：

- Reverse Proxy
- Load Balancing 基础
- HTTP / HTTPS
- TLS Certificate 基础
- access.log / error.log
- 404 / 502 / 504 排障

### Helm

仅要求基础使用：

- Chart
- Release
- values.yaml
- templates

以及常用：

- install
- upgrade
- rollback
- uninstall
- template
- show values

不深入复杂 Helm Template 开发。

### ArgoCD

只要求基础 GitOps：

- Git as Source of Truth
- Application
- Sync
- Auto Sync
- Synced / OutOfSync
- Self Heal
- Prune
- 基本 Rollback

不学习高级 ArgoCD 平台能力。

---

## 4. 实验 Workload

计划逐渐引入：

- Ollama
- Nginx
- MySQL
- Redis

其中 Ollama 作为较真实的容器化 Workload，用于串联：

Docker → Kubernetes → Service → PVC → Helm → ArgoCD

Redis只要求熟悉并能够部署和简单使用。

---

## 5. 本轮不作为主线的内容

当前冲刺阶段不主动深入：

- Go
- eBPF
- Service Mesh
- Istio 深入
- Kubernetes 源码
- Cilium 深入
- Redis 源码
- MySQL 内核
- 高级 Helm
- 高级 ArgoCD
- 复杂 PromQL
- Kafka / Hadoop 等其他大规模技术栈

如未来明确岗位需要，再单独增加专项。

---

## 6. Repository Inputs

`inputs/` 保存本项目进行规划时使用的事实材料。

这些目录原则上视为只读。

### `inputs/resume/`

当前求职使用的简历。

### `inputs/interviews/`

人工筛选后的面试记录。

仍按公司/面试记录保存为 TXT，并保留：

- 面试官原始措辞
- 场景题
- 追问关系

已尽量删除答案和无关信息。

这些文件用于：

- 发现高频问题
- 设计 Ticket
- 设计 Lab
- 设计 Incident

不应自动改写原文件。

### `inputs/work-cases/`

包含：

`WORK_CASES.md`

来源于真实工作截图和聊天记录的结构化事实场景。

只代表实际材料中可以确认的内容。

Lab 后续模拟出的故障不得反写成真实工作经历。

### `inputs/projects/`

当前简历相关项目源码和说明。

### `inputs/internship-code/`

实习期间实际代码。

当前主要作为后置的实习经历和 Python 代码防守材料。

---

## 7. Lab Environment

环境状态记录在：

`environment/LAB_ENV.md`

当前计划使用：

- `lab-master`
- `lab-worker1`
- `lab-worker2`

三台 Ubuntu VMware 虚拟机。

当前环境尚未初始化 Kubernetes。

第一阶段首先解决：

- VMware NAT
- IP
- Gateway
- DNS
- 节点互通
- Internet Access
- SSH
- Static IP

网络基础本身也是本项目的学习内容，不应绕过。

---

## 8. Incident-driven Learning

故障训练是本项目核心。

计划逐渐覆盖：

- Pod Pending
- FailedScheduling
- CrashLoopBackOff
- ImagePullBackOff
- OOMKilled
- Exit Code 137
- Init Failure
- command / args / ENTRYPOINT
- Service unreachable
- selector / targetPort
- DNS
- Probe Failure
- PVC Pending
- Mount Failure
- read-only filesystem
- Permission
- Node resource issue
- HTTP / HTTPS
- Nginx 502 / 504

并鼓励跨层故障：

Application → Kubernetes → Container → Linux → Network

---

## 9. Codex / ChatGPT / User 分工

### Codex

负责：

- Repo Audit
- MASTER_PLAN
- Ticket体系
- 依赖设计
- Lab工程建设
- Incident设计与故障注入
- 状态维护
- Handoff生成

### ChatGPT

主要负责：

- 知识答疑
- 理解检查
- 连续追问
- 模拟面试
- Ticket最终验收
- 规划审核与范围收敛

### User

必须亲自完成关键学习动作：

- Linux操作
- Shell命令
- 网络排障
- kubectl
- Docker
- Ansible执行
- Git操作
- SQL
- Helm
- ArgoCD观察与操作
- 故障定位与修复

AI不应替代用户完成核心排障过程。

---

## 10. Source of Truth

后续由 Codex 创建并维护：

- `MASTER_PLAN.md`
- `STATUS.md`

其中：

`STATUS.md`

将成为当前学习进度的唯一事实来源。

不要使用多个互相独立的学习进度系统。