## CockroachDB クラスタを構築するための docker-compose

- クラスタ数は 1、ノードは 3 で構築する。

  ```
  - node1(roach1)
  - node2(roach2)
  - node3(roach3)
  ```

1. docker-compose 起動

   ```bash
   docker-compose up -d
   ```

2. クラスタの初期化

   ```bash
   docker exec -it roach1 ./cockroach --host=roach1:26357 init --insecure
   ```

3. SQL クライアントへ接続

   ```bash
   docker exec -it roach1 ./cockroach sql --host=roach2:26258 --insecure
   ```

### 参考

- [Deploy a Local Cluster in Docker (Insecure)](https://www.cockroachlabs.com/docs/v24.2/start-a-local-cluster-in-docker-windows)
