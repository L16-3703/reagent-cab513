# 试剂柜分级安防系统 — Web 端页面

毕业设计《基于ESP32的实验室试剂柜分级安防管控系统》配套静态页面：

| 文件 | 用途 |
|---|---|
| `index.html` | Web 管控中心：实时取用台账、分级告警、设备在线状态（MQTT over WSS 订阅 `reagentcab/#`） |
| `ble-poc.html` | 手机端 Web Bluetooth 测试页：连接试剂柜（`ReagentCab-XXXX`）、挑战-应答认证、监督人授权、试剂选择 |
| `mqtt.min.js` | MQTT.js 浏览器库（本地化，避免 CDN 依赖） |

## 使用说明

- 两个页面均为纯前端，不依赖后端服务
- **必须通过 HTTPS 访问**（Web Bluetooth 与 WSS 的安全上下文要求）；Gitee Pages 默认提供 HTTPS
- 手机使用 `ble-poc.html` 时：需开启定位服务（安卓蓝牙扫描要求）、手机需在设备附近（蓝牙为本地射频）
- 数据主题：`reagentcab/<设备MAC后2字节>/record|status|alert`（原型使用公共测试 broker，产品化需私有 broker + 鉴权）

## 部署

Gitee Pages：仓库 → 服务 → Gitee Pages → 部署，得到 `https://<用户名>.gitee.io/<仓库名>/`。
