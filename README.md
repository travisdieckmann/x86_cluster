# X86 Cluster
MicroK8s on Ubuntu running on X86 Hardware/VMs

## Summary
Everything foundational with the home X86 MicroK8s cluster

### IP Address Space
Nodes: 172.16.0.30-172.16.0.39
MetalLB: 172.16.0.200-172.16.0.250

## Upgrade
```bash
microk8s kubectl drain <node> --ignore-daemonsets
apt update && apt upgrade -y
snap refresh microk8s --channel=1.28 && reboot
microk8s kubectl uncordon <node>
```

## MetalLB
https://microk8s.io/docs/addon-metallb
```bash
microk8s enable metallb:172.16.0.200-172.16.0.250
```

## Prometheus
https://www.server-world.info/en/note?os=Ubuntu_20.04&p=microk8s&f=8

