从 https://github.com/eclipse/paho.mqtt.golang/releases v1.1.1 版本搬运过来,
初始的git hash 为 [36d01c2b4cbeb3d2a12063e4880ce30800af9560](https://github.com/eclipse/paho.mqtt.golang/commit/36d01c2b4cbeb3d2a12063e4880ce30800af9560)

### 解决问题

1. 原始版本在订阅topic超过500个处理比较低效, 原因在于router的匹配过程慢. 现修改为把具体的topic保存到map里, 如果是订阅具体的topic, 则直接到map里查找;若是通配符消息, 则按之前的逻辑走

