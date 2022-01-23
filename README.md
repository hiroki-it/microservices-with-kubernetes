# microservices-with-kubernetes

## マイクロサービスアーキテクチャの構成

### アプリケーション

| マイクロサービス名                                          | 言語   | フレームワーク | プロキシコンテナ     | 境界付けられたコンテキストの説明                             |
| ------------------------------------------------------------ | ------ | -------------- | -------------------- | -------------------------------------- |
| [order-service](https://github.com/hiroki-it/microservices-with-kubernetes/tree/main/src/order-service) | PHP    | Lumen          | Nginx，Envoy                | 受注業務を実現します．                 |
| [payment-service](https://github.com/hiroki-it/microservices-with-kubernetes/tree/main/src/payment-service) | Go     | Gin            | Envoy | 会計業務を実現します．             |
| ***-service（comming soon...）                                      | Python | Flask          | Envoy |                  -                      |                             |

### インフラ

| 役割                         | ツール               | 導入の状況      |
| ---------------------------- | -------------------- | --------------- |
| 仮想化              | Docker             | ◯               |
| コンテナオーケストレーション              | Kubernetes             | ◯               |
| サービスメッシュミドルウェア | Istio，IstioOperator | ◯               |
| 開発環境のCI/CD              | Skaffold             | ◯               |
| テンプレート管理             | Helm                 | comming soon... |
| API Gateway                  | AWS API Gateway      | comming soon... |
| CD                           | ArgoCD               | comming soon... |


<br>

## 環境構築

### minikubeの起動

```bash
$ make minikube-start

$ eval $(minikube -p minikube docker-env)
```

### デプロイ

#### ・Kubernetesの場合

```bash
$ make deploy-kubernetes
```

#### ・Istioの場合

```bash
$ make deploy-istio
```
