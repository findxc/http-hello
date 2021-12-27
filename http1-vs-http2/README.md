# http1-vs-http2

参考 https://http2.akamai.com/demo 来测试 HTTP/1.1 和 HTTP/2 的速度差异。

## 怎么运行

需要先在 `nginx` 路径下手动添加 `ssl-key.pem` 和 `ssl-cert.pem` 证书。可以安装 [mkcert](https://github.com/FiloSottile/mkcert) 然后执行 `mkcert -key-file ssl-key.pem -cert-file ssl-cert.pem 127.0.0.1` 来生成证书。

然后通过 `docker compose up -d` 启动后，访问 `https://127.0.0.1:441` 和 `https://127.0.0.1:442` 就分别是 HTTP/1.1 和 HTTP/2 的效果了。

在 Chrome 开发者工具的 Network 中可以模拟不同的网络环境来进行对比，比如设置网络延时、带宽等。

详见 https://github.com/findxc/blog/issues/63 。