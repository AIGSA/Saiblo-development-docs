## 评测机部署

Saiblo 平台支持分布式测评机。测评机需要主动与 Saiblo 网站后端建立 Websocket 连接。当且仅当测评机与后端的 Websocket 连接正常时，平台认为测评机上线，并会给测评机分配对应的编译/评测任务。

具体地，评测机需要连接到平台后端的地址，如 `127.0.0.1:8000`。在初始化时评测机可以选择是否提供房间功能，如果提供，则测评机还需在初始化时给平台后端提供其房间系统服务器地址，连接成功后在前端的服务器列表中便会看到该测评机。

关于网站后端测评机的具体通信协议，请参考[后端与测评端](/dev/backend2judger)。

测评机的具体配置请参考测评组的文档。

