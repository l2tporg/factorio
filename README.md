# run
- udpポート34197をあけてください(必須)
- tcpポート27015をあけてください(オプショナル)
- volumesを/tmp/factorioをどこか別の場所に移動しないと消える可能性あり！
- crashした場合に自動でrestartします

```
docker run -d -p 34197:34197/udp -p 27015:27015/tcp \
  -v /tmp/factorio:/factorio \
  --name factorio \
  --restart=always  \
  dtandersen/factorio
```


# upgrading 
- 必ず/tmp/factorioのバックアップをとりましょう
```
docker stop factorio
docker rm factorio
docker pull dtandersen/factorio
```