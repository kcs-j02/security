# CSIRT / Incident Response Security Lab

CSIRT・インシデントレスポンスを実践的に学習するための
ホームセキュリティラボです。

VMware Workstation上に Kali Linux、Ubuntu Server、Windows 11 を構築し、
隔離した仮想ネットワーク内で実験を行っています。

## 目的

セキュリティツールの使い方を覚えるだけではなく、

「ある操作を行うと、ネットワークやサーバーでは何が起きるのか」

「その痕跡を防御側からどのように発見・調査できるのか」

を実際のパケットやログから理解することを目的としています。

最終的には、

Detection
↓
Triage
↓
Investigation
↓
Containment
↓
Recovery
↓
Lessons Learned

まで、一連のインシデントレスポンスを自分のラボ内で再現することを目指します。


## Lab Environment

| Machine | Role | CPU | RAM | Storage |
|---|---|---:|---:|---:|
| Kali Linux | 攻撃・診断・調査 | TBD | TBD | TBD |
| Ubuntu Server | Linux Server / 調査対象 | 2 vCPU | 6 GB | 40 GB |
| Windows 11 | Client / 調査対象 | TBD | TBD | TBD |

Virtualization: VMware Workstation


## Network

実験時はVMware Host-only Networkを使用します。

    Kali Linux              Ubuntu Server
    192.168.159.131         192.168.159.129
         |                       |
         +------ Host-only ------+
              192.168.159.0/24
                     |
                 Windows 11

VM同士は通信できますが、検証時は外部ネットワークから分離します。

パッケージのインストールなど、インターネット接続が必要な場合のみ
NATを使用します。


## Learning Cycle

このラボでは、

目的
↓
仮説
↓
実験
↓
観測
↓
結果
↓
考察
↓
次の仮説

というサイクルで検証を進めます。


## Lab Notes

日々の構築・実験内容は `logs/` に記録します。

- 2026-09-22 - ラボ構築 / Nmap / tcpdump / TCP SYN Scan