# minimart-product-service

MiniMart 的商品进程（Category / SPU / SKU / Stock）。领域用语与 v1 契约在编排仓 [`minimart-infra`](../minimart-infra)。

- Spring 名：`product-service`
- 端口：8082
- 库：`minimart_product`（由 infra 的 `docker/mysql/init.sql` 建；本进程尚未连库）
- 不发起 Feign 调用。order-service 通过 `minimart-product-api` 预占/确认/释放 Stock。

本机运行：

```bash
./gradlew bootRun
```

编排：与其它仓并列 clone 后，在 `minimart-infra` 执行 `docker compose up`（无 Nacos；Docker DNS 与 K8s Service 名一致）。
