# 网站前端-游戏系统

[TOC]

## games.vue

| 参数 | 值                     |
| ---- | ---------------------- |
| 地址 | `/games`               |
| 用途 | 查看所有已经部署的游戏 |
| 权限 | 登录用户               |
| 预览 | ![](imgs\games.PNG)    |

| 属性  | 解释                                                         |
| ----- | ------------------------------------------------------------ |
| games | 所有游戏，使用asyncData获取                                  |
| modal | 之前设计时点击游戏详情会弹出弹窗，数据来自于modal，但是这个功能被屏蔽了 |

| 函数       | 参数 | 返回值 | 解释                                                         |
| ---------- | ---- | ------ | ------------------------------------------------------------ |
| readDetail | game | null   | 之前设计时点击游戏详情会弹出弹窗，调用这个函数用来控制弹窗，该功能被屏蔽了 |

## game/_id.vue

| 参数 | 值                                |
| ---- | --------------------------------- |
| 地址 | `/game/<game id>`                 |
| 用途 | 查看编号为game id的游戏的详细信息 |
| 权限 | 登录用户                          |
| 预览 | ![](imgs\game_id.PNG)             |

| 属性 | 解释                                                |
| ---- | --------------------------------------------------- |
| id   | 当前选项卡的编号                                    |
| game | 该游戏详情页面对应的游戏的数据，使用asyncData获取值 |

| 函数             | 参数 | 返回值 | 解释                                                         |
| ---------------- | ---- | ------ | ------------------------------------------------------------ |
| isActive/select  | id   | null   | 用于维护当前的选项卡是哪个选项卡                             |
| download_file    | url  | null   | 点击下载游戏包按钮时调用该函数，向服务器请求游戏包文件       |
| isManager        | null | null   | 当前用户是否为当前游戏的管理员，具有修改权限                 |
| introductionHTML | null | null   | 将markdown格式的introduction转化为html格式，在网页上进行富文本显示 |

| 依赖部件   | 传入部件参数           |
| ---------- | ---------------------- |
| match-list | 游戏编号               |
| ai-list    | 游戏编号，允许远程算力 |

## game/_slug/edit.vue

| 参数 | 值                                |
| ---- | --------------------------------- |
| 地址 | `/game/<game id>/edit`            |
| 用途 | 修改编号为game id的游戏的详细信息 |
| 权限 | 超级管理员                        |
| 预览 | ![](imgs\game_id_edit.PNG)        |

| 属性      | 解释                                          |
| --------- | --------------------------------------------- |
| form      | 修改游戏详情提交的表单，使用asyncData获取初值 |
| isLoading | 正在提交表单到服务器                          |
| isOK      | 服务器返回提交表单成功信息                    |
| err_code  | 提交表单失败时，设置为响应的status code       |
| game      | 当前选中游戏的详细信息，使用asyncData获取值   |

| 函数        | 参数 | 返回值 | 解释                                 |
| ----------- | ---- | ------ | ------------------------------------ |
| saveInfo    | null | null   | 将修改后的游戏详情表单提交到服务器上 |
| upload_game | null | null   | 选中游戏包并将游戏包上传到服务器上   |

## game/_slug/ranklist.vue

| 参数 | 值                                |
| ---- | --------------------------------- |
| 地址 | `/game/<game id>/ranklist`        |
| 用途 | 查看编号为game id游戏绑定的排行榜 |
| 权限 | 登录用户                          |
| 预览 | ![](imgs\game_id_ranklist.PNG)    |

| 属性    | 解释                                                       |
| ------- | ---------------------------------------------------------- |
| game    | 当前排行榜对应游戏的信息，使用asyncData获取                |
| players | 排行榜中每个玩家的信息，包括得分，username，AI分支和版本号 |

| 函数           | 参数             | 返回值             | 解释                                                         |
| -------------- | ---------------- | ------------------ | ------------------------------------------------------------ |
| | |  |  |

## match/_id.vue

| 参数 | 值                                                       |
| ---- | -------------------------------------------------------- |
| 地址 | `/match/<match id>`                                      |
| 用途 | 查看对局编号为match id的对局详情，如果有HTML播放器则回放 |
| 权限 | 登录用户                                                 |
| 预览 | ![](imgs\match_id.PNG)                                   |

yyt说他写