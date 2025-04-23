---
title: 默认 vGPU 作业
translated: true
---

## Job 描述

vGPU 可以通过在 resources.limits 中设置 "volcano.sh/vgpu-number"、"volcano.sh/vgpu-cores" 和 "volcano.sh/vgpu-memory" 来请求。

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: test1
spec:
  restartPolicy: OnFailure
  schedulerName: volcano
  containers:
  - image: ubuntu:20.04
    name: pod1-ctr
    command: ["sleep"]
    args: ["100000"]
    resources:
      limits:
        volcano.sh/vgpu-memory: 1024
        volcano.sh/vgpu-number: 1
```
