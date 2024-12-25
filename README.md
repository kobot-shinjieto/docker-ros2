# DOCKER-ROS2
Docker上でROS2環境を作成した．

# 目次

- [DOCKER-ROS2](#docker-ros2)
- [1. システム構成](#1-システム構成)
  - [1.1 システム](#11-システム)
  - [1.2 フォルダ構成](#12-フォルダ構成)
- [2. Docker操作](#2-docker操作)
  - [2.1 基本操作](#21-基本操作)
  - [2.2 VSCode上での操作](#22-vscode上での操作)
    - [2.2.1 WSLに接続](#221-wslに接続)
    - [2.2.2 Dockerコンテナをアタッチ](#222-dockerコンテナをアタッチ)
    - [2.2.3 プロジェクトを開く](#223-プロジェクトを開く)

# 1. システム構成

## 1.1 システム
| 環境 | バージョン |
| -- | -- |
| ホストOS | Windows 11 Home |
| WSL2 | Ubuntu20.04 LTE |
| Docker | v26.0.0 |
| Docker Compose | v2.25.0 |
| ROS | ROS2 Humble |

## 1.2 フォルダ構成
```shell
.
└── docker-ros2
    ├── assets/
    ├── doc/
    ├── docker/
    │   ├── Dockerfile
    │   └── docker-compose.yaml
    ├── src/
    ├── .gitignore
    └── README.md
```

# 2. Docker操作

## 2.1 基本操作
1. Dockerイメージのビルド

```shell
$ cd docker
$ docker build -t docker-ros2 .
```

2. Dockerコンテナの起動

```shell
$ docker compose up -d
```

3. Dockerコンテナの終了

```shell
$ docker compose down
```

## 2.2 VSCode上での操作

### 2.2.1 WSLに接続
- ①画面左下のアイコンをクリック
- ②`Connect to WSL`を選択し，リモートウィンドウを開く

![img](./doc/img/VSCODEでWSLを選択.jpg)

### 2.2.2 Dockerコンテナをアタッチ

1. コンテナを起動
- ①Docker拡張機能を選択
- ②起動したいコンテナを右クリックし`Start`を選択

![img](./doc/img/Dockerコンテナを起動.png)


1. コンテナをVScodeにアタッチ
- ①コンテナのマークが緑になり起動状態であることを確認
- ②`Attach Visual Studio Code`を選択しコンテナをアタッチ

![img](./doc/img/DockerコンテナをVScodeにアタッチ.jpg)

### 2.2.3 プロジェクトを開く

- ①開いたウィンドウの`File`を選択
- ②`Open Folder...`を選択し，プロジェクトを格納している作業フォルダを開く

![img](./doc/img/作業フォルダを開く.jpg)
