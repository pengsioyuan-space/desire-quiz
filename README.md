# 欲望测试

一个独立、纯前端的中文趣味测试网站。包含 20 道题、六维欲望雷达图和多种结果报告。

- 无后端、无数据库、无登录
- 答案只在浏览器内计算，不上传
- 可直接部署到 GitHub Pages、CloudBase 或任意静态托管
- 手机端优先，桌面端自适应

## 本地预览

直接打开 `index.html`，或运行 `python -m http.server 8000` 后访问 `http://localhost:8000/`。

## GitHub Pages

仓库 Settings → Pages → Build and deployment，选择 `Deploy from a branch`，分支选 `main`，目录选 `/ (root)`。

> 本测试仅供娱乐，不构成心理评估或专业建议。

## HTTP 网关自定义域名
迁移原因：使用自定义域名入口访问，避免继续依赖云开发默认访问地址；平台提示是否消失需部署后实际核验。
- 地址：https://sioyuan.site/desire-quiz/
- 域名：sioyuan.site；触发路径：/desire-quiz；资源类型：静态托管；选择现有实例 desire-quiz；路径透传关闭。
- 先部署静态文件，再添加独立路由；保留现有根路由及其他站点。
- 仅在匹配网关路径时设置资源基路径，兼容末尾没有斜杠的 URL；保留根路径与本地预览。
- 题目、选项、计分、结果和浏览器存储未修改；没有新增后端接口或修改实际网关配置。
- 部署后验收带/不带末尾斜杠的路径，检查脚本、样式、答题和结果；代码不能绕过平台限制。
- 回滚：撤销本提交并重新部署，网关配置恢复原值。
官方说明：https://docs.cloudbase.net/service/access-static-hosting
