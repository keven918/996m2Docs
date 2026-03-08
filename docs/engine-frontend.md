# 996M2 游戏引擎 - 客户端 API 文档

> 本文档由 Lua 注释自动转换生成，来源于 996 官方文档

---

游戏内所有变量几乎都藏在元变量中
SL:GetMetaValue(key, param1, param2, ...) 获取
SL:SetMetaValue(key, param1, param2, ...) 设置
SL:PrintMetaKey() 打印所有元变量Key
SL:PrintAllMetaValue() 打印所有能获取的元变量
SL:CheckCondition(conditionStr) 元变量条件判断， 格式: $(原变量ID) ,需要参数的$(原变量ID,参数…)
示例代码
SL:CheckCondition("$(LEVEL) >= 1 and $(PLATFORM_WINDOWS) == false")
SL:CheckCondition("$(ITEM_COUNT,2) >= 1000 and $(PLATFORM_WINDOWS) == false")


## Set

| 参数名 | 说明 | 例子 |
| --- | --- | --- |
| “MAIL_CURRENT_ID” | 设置当前邮件ID |
| param1: 邮件ID | SL:SetMetaValue("MAIL_CURRENT_ID", param1) |
| “BAG_PAGE_CUR” | 设置当前选中的背包页 |
param1: 页签
| “CHAT_CHANNEL_RECEIVIND” | 切换聊天频道接收状态 |
param1: 聊天频道
param2: boolean 接收状态 [不填默认切换相反状态]
| “CUR_CHAT_CHANNEL” | 当前聊天频道 |
| param1: 聊天频道 | SL:SetMetaValue("CUR_CHAT_CHANNEL", channel) | 支持版本号3.40.3以上 |
| “SETTING_VALUE” | 设置的数据 |
param1：设置ID
param2: 设置值 table
| “SETTING_PICK_VALUE” | 设置捡物品数据 |
param1：设置ID
param2：设置值 table
| “SETTING_PICK_GROUP_VALUE” | 设置捡物品组数据 |
param1：设置ID
param2：设置值 table
| “SETTING_RANK_DATA” | 设置排序相关数据 |
param1：设置ID
param2：设置值 table
| “BOSS_REMIND_TYPE” | 设置boss提示类型 |
param1：设置值
| “BOS_REMIND_VALUE” | 设置boss提示值 |
param1：设置值
| “SUPEREQUIP_SHOW” | 角色面板时装显示开关 |
param1：boolean
| “HERO_SUPEREQUIP_SHOW” | 英雄面板时装显示开关 |
param1：boolean
| “SKILL_KEY” | 设置技能快捷键 |
param1：技能ID
param2：0~16
| “H.SKILL_KEY” | 英雄设置技能快捷键 |
param1：技能ID
param2：0~16
| “HERO_GUARD_ISCLICK” | 是否点击英雄守护按钮 |
param1: boolean值
| “HERO_ACTIVES_STATES” | 英雄激活的状态列表 |
param1: table
| “HERO_SUPEREQUIP_SHOW” | 英雄面板 时装显示开关 |
param1: boolean值
| “COMPOUND_OPEN_ID” | 合成打开的ID |
param1: 合成表id
| “SELECT_TARGET_ID” | 选择目标ID | SL:SetMetaValue("SELECT_TARGET_ID", targetID) |
| “ATTACK_STATE” | PC锁定攻击状态 |
| param1: boolean | SL:SetMetaValue("ATTACK_STATE", true) |
| “FUNCDOCK_PARAM” | 功能菜单参数设置 |
| param1: table 参数数据 | SL:SetMetaValue("FUNCDOCK_PARAM", data) |
| “CLIPBOARD_TEXT” | 设置剪贴板文本 |
| param1: string 文本内容 | SL:SetMetaValue("CLIPBOARD_TEXT", "11") |
| “DROPITEM_FLY_WORLD_POSITION” | 设置 自动拾取-掉落物-飞向的世界坐标, 优先级比txt设置的高 |
需要后端先设置setpickitemtobag后才能修改坐标
param1: x坐标
| param2: y坐标 | SL:SetMetaValue("DROPITEM_FLY_WORLD_POSITION", 200, 200) |
| “QUICK_USE_NUM” | 设置快捷栏个数 |
| param1: int | SL:SetMetaValue("QUICK_USE_NUM", 6) | 支持版本号3.40.2以上 |
| “GUIDE_EVENT_BEGAN” | 特定状况引导事件开始通知 |
param1: 脚本引导父节点ID
| param2: 是否需要刷新位置 | SL:SetMetaValue("GUIDE_EVENT_BEGAN", 110, true) | 支持版本号3.40.2以上 |
| “GUIDE_EVENT_END” | 特定状况引导事件结束通知 |
| param1: 脚本引导父节点ID | SL:SetMetaValue("GUIDE_EVENT_END", 110) | 支持版本号3.40.2以上 |
| “INTERNAL_SKILL_ONOFF” | 设置人物内功技能开关 |
param1: 技能ID
param2: 技能类型
[2 = 人物怒内功技能
4 = 人物静内功技能]
| param3: 开关状态 0 开启 1关闭 | SL:SetMetaValue("INTERNAL_SKILL_ONOFF", 101, 2, 1) | 支持版本号3.40.2以上 |
| “H.INTERNAL_SKILL_ONOFF” | 设置英雄内功技能开关 |
param1: 技能ID
param2: 技能类型
[3 = 英雄怒内功技能
5 = 英雄静内功技能]
| param3: 开关状态 0 开启 1关闭 | SL:SetMetaValue("H.INTERNAL_SKILL_ONOFF", 105, 5, 1) | 支持版本号3.40.2以上 |
| “WIN_DEVICE_SIZE” | 修改PC端屏幕分辨率 |
param1: 宽
| param2: 高 | SL:SetMetaValue("WIN_DEVICE_SIZE", 1024, 768) | 支持版本号3.40.2以上 |
| “STALL_SELECT_ID” | 摆摊设置选中的物品唯一ID |
| param1: 物品唯一ID | SL:SetMetaValue("STALL_SELECT_ID", makeIndex) | 支持版本号3.40.3以上 |
| “PC_CHAT_INPUT_FILL” | 填充PC聊天输入框内容 |
| param1: 文本内容 | SL:SetMetaValue("PC_CHAT_INPUT_FILL", msg) | 支持版本号3.40.3以上 |
| “TEAM_STATUS_PERMIT” | 设置允许组队状态 |
| param1: boolean | SL:SetMetaValue("TEAM_STATUS_PERMIT", true) | 支持版本号3.40.3以上 |
| “ADD_STATUS_PERMIT” | 设置允许添加状态 |
| param1: boolean | SL:SetMetaValue("ADD_STATUS_PERMIT", true) | 支持版本号3.40.3以上 |
| “DEAL_STATUS_PERMIT” | 设置允许交易状态 |
| param1: boolean | SL:SetMetaValue("DEAL_STATUS_PERMIT", true) | 支持版本号3.40.3以上 |
| “SHOW_STATUS_PERMIT” | 设置允许显示状态 |
| param1: boolean | SL:SetMetaValue("SHOW_STATUS_PERMIT", true) | 支持版本号3.40.3以上 |
| “TURN_DIR” | 设置转向方向 |
| param1: int 方向 0 ~ 8 | SL:SetMetaValue("TURN_DIR", 4) | 支持版本号3.40.3以上 |
| “USER_TO_MOVE” | 手动发起移动 |
param1: 目标地图坐标 table
param2: 移动方向 0 ~ 8
param3: 移动步长
param4: 移动类型 int
| 1: 点击地板 2: 摇杆 | SL:SetMetaValue("USER_TO_MOVE", originPos, moveDir, moveStep, 2) | 支持版本号3.40.3以上 |
| “SELECT_SHIFT_ATTACK_ID” | 设置PC持续攻击目标ID |
| param1: actorID | SL:SetMetaValue("SELECT_SHIFT_ATTACK_ID", 100181) | 支持版本号3.40.5以上 |
| “DROP_TYPE_ISRECEIVE” | 设置是否接收该分类掉落信息 |
param1: int 掉落分组id
| param2: boolean 是否接收 | SL:SetMetaValue("DROP_TYPE_ISRECEIVE", 1, false) | 支持版本号3.40.5以上 |
| “AUTOUSE_MAKEINDEX_BY_POS” | 添加自动使用弹窗 物品唯一ID |
| param1: 类型 （1: 人物 2: 英雄） param2: 装备位 param3: makeIndex | SL:SetMetaValue("AUTOUSE_MAKEINDEX_BY_POS", playerType, equipPos, MakeIndex) | 支持版本号3.40.7以上 |

## Get

游戏基础相关

| 参数名 | 返回值类型 | 说明 | 例子 |
| --- | --- | --- | --- |
| “SCREEN_WIDTH” | int | 屏幕宽 | SL:GetMetaValue("SCREEN_WIDTH") |
| “SCREEN_HEIGHT” | int | 屏幕高 | SL:GetMetaValue("SCREEN_HEIGHT") |
| “NOTCH_PHONE_INFO” | boolean, table | 是否刘海屏 |
返回参数:
param1: boolean
| param2: table {x = 刘海屏偏移坐标x, y = y, width = 减去刘海屏幕宽, height = 屏幕高} | SL:GetMetaValue("NOTCH_PHONE_INFO") |
| “PLATFORM_ANDROID” | boolean | 安卓平台 | SL:GetMetaValue("PLATFORM_ANDROID") |
| “PLATFORM_IOS” | boolean | iOS平台 | SL:GetMetaValue("PLATFORM_IOS") |
| “PLATFORM_WINDOWS” | boolean | Windows平台 | SL:GetMetaValue("PLATFORM_WINDOWS") |
| “PLATFORM_MOBILE” | boolean | 手机平台(包含安卓和iOS) | SL:GetMetaValue("PLATFORM_MOBILE") |
| “PLATFORM_OHOS” | boolean | 鸿蒙平台 | SL:GetMetaValue("PLATFORM_OHOS") | 支持版本号3.40.4以上 |
| “WINPLAYMODE” | boolean | PC操作模式 | SL:GetMetaValue("WINPLAYMODE") |
| “IS_PC_PLAY_MODE” | boolean | 是否PC操作模式, 等同WINPLAYMODE | SL:GetMetaValue("IS_PC_PLAY_MODE") | 支持版本号3.40.3以上 |
| “CURRENT_OPERMODE” | int | 操作模式(PC=1, 手机=2) | SL:GetMetaValue("CURRENT_OPERMODE") |
| “GAME_ID” | string | 游戏ID | SL:GetMetaValue("GAME_ID") |
| “CHANNEL_ID” | string | 渠道ID | SL:GetMetaValue("CHANNEL_ID") |
| “PACKAGE_NAME” | string | APK包名 | SL:GetMetaValue("PACKAGE_NAME") |
| “VERSION_NAME” | string | APK版本名 | SL:GetMetaValue("VERSION_NAME") |
| “VERSION_CODE” | string | APK版本号 | SL:GetMetaValue("VERSION_CODE") |
| “LOCAL_RES_VERSION” | string | 原始/本地客户端版本号 | SL:GetMetaValue("LOCAL_RES_VERSION") |
| “REMOTE_RES_VERSION” | string | 热更客户端版本号 | SL:GetMetaValue("REMOTE_RES_VERSION") |
| “REMOTE_GM_RES_VERSION” | string | GM资源版本号 | SL:GetMetaValue("REMOTE_GM_RES_VERSION") | 支持版本号3.40.4以上 |
| “DEVICE_UNIQUE_ID” | string | PC唯一设备ID | SL:GetMetaValue("DEVICE_UNIQUE_ID") | 支持版本号3.40.7以上 |
| “PROMOTE_ID” | string | 推广员ID | SL:GetMetaValue("PROMOTE_ID") |
| “FPS” | int | 游戏帧率 | SL:GetMetaValue("FPS") |
| “NET_TYPE” | int | 网络类型 |
0 : wifi
1 : 蜂窝
| -1: 未识别 | SL:GetMetaValue("NET_TYPE") |
| “BATTERY” | int | 手机电量（0~100） | SL:GetMetaValue("BATTERY") |
| “GAME_DATA” | table | 获取cfg_game_data配置 |
| param: 表中的key值 | SL:GetMetaValue("GAME_DATA", param) |
| “IS_SDK_LOGIN” | boolean | 是否是SDK登录 | SL:GetMetaValue("IS_SDK_LOGIN") |
| “996BOX_LOGIN” | boolean | 是否是996盒子登录 | SL:GetMetaValue("996BOX_LOGIN") |
| “996_CLOUD_DEVICE” | boolean | 是否是996云真机 | SL:GetMetaValue("996_CLOUD_DEVICE") | 支持版本号3.40.2以上 |
| “IS_SHOW_MAUNAL_SERVICE” | boolen | 是否开启996客服服务 | SL:GetMetaValue("IS_SHOW_MAUNAL_SERVICE") |
| “PC_NP_STATUS” | boolen | PC端NP反外挂开启状态 | SL:GetMetaValue("PC_NP_STATUS") |
| “PC_NP_ISOWN” | boolen | PC端检测是否自己的NP param1: NP名字 | SL:GetMetaValue("PC_NP_ISOWN", npName) | 支持版本号3.40.7以上 |
| “SPINE_VERSION” | string | 当前spine动画版本 | SL:GetMetaValue("SPINE_VERSION") |
| “SERVER_OPTION” | boolean | 服务器开关（param） | SL:GetMetaValue("SERVER_OPTION", SW_KEY_AUCTION) |
param = {
SW_KEY_AUCTION                        -- 服务器开关 拍卖
SW_KEY_ALL_FIGHTPAGES                 -- 服务器开关 显示所有战斗页
SW_KEY_MISSTION                       -- 服务器开关 任务
SW_KEY_SNDAITEMBOX                    -- 服务器开关 是否显示首饰盒
SW_KEY_TRADE_DEAL                     -- 服务器开关 面对面交易 true/需要面对面
SW_KEY_AUTO_DRESS                     -- 服务器开关 自动穿戴
SW_KEY_OPEN_F_EQUIP                   -- 服务器开关 时装是否开启首饰
SW_KEY_BIND_GOLD                      -- 服务器开关 开启元宝替换绑元
SW_KEY_NPC_BUTTON                     -- 服务器开关 显示npc按钮
SW_KEY_NPC_NAME                       -- 服务器开关 显示npc名字 1:不显示
SW_KEY_DROP_TIPS                      -- 服务器开关 显示绑定丢弃提示 0:显示
SW_KEY_EXP_IN_CHAT                    -- 服务器开关 经验信息是否显示在聊天框 0：显示在聊天框
SW_KEY_SHOW_STALL_NAME                -- 服务器开关 是否显示默认摊位名字  0：显示
SW_KEY_PLAYER_BLUE_BLOOD              -- 服务器开关  是否显示蓝条HUD_SPRITE_MP   0: 显示
SW_KEY_ITEMTIPS_TOUBAO_SHOW           -- 服务器开关  是否显示itemtips的投保描述   1= 开启 0 = 关闭
SW_KEY_BAN_DOUBLE_FIREHIT             -- 服务器开关  是否禁止双烈火    1：禁止
SW_KEY_ALL_TEAM_EXP                   -- 服务器开关 是否开启全队经验 true/false
SW_KEY_EQUIP_EXTRA_POS                -- 服务器开关，是否有额外的装备位置  1= 开启 0 = 关闭
}

服务器相关

| 参数名 | 返回值类型 | 说明 | 例子 |
| --- | --- | --- | --- |
| “SERVER_ID” | string | 服务器ID | SL:GetMetaValue("SERVER_ID") |
| “SERVER_NAME” | string | 服务器名字 | SL:GetMetaValue("SERVER_NAME") |
| “MAIN_SERVER_ID” | string | 主服务器ID | SL:GetMetaValue("MAIN_SERVER_ID") |
| “RES_VERSION” | string | 资源版本 | SL:GetMetaValue("RES_VERSION") |
| “UID” | string | 账号ID | SL:GetMetaValue("UID") |
| “LOGIN_DATA” | table | 登录角色信息 | SL:GetMetaValue("LOGIN_DATA") |
| “RESTORE_ROLES” | table | 可恢复角色信息 | SL:GetMetaValue("RESTORE_ROLES") |
| “SERVER_VALUE” | string | 服务端下发的变量值 |
param1: 服务端变量名
(可在M2红点中控制下发给客户端的变量)
| 注意:获取标记用"{x}"而非"[x]" | SL:GetMetaValue("SERVER_VALUE", param1) |
| “CURRENT_TALK_NPC_ID” | int | 获取当前对话NPC的ID | SL:GetMetaValue("CURRENT_TALK_NPC_ID") | 支持版本号3.40.2以上 |
| “CURRENT_TALK_NPC_TYPEINDEX” | int | 获取当前对话NPC的Index | SL:GetMetaValue("CURRENT_TALK_NPC_TYPEINDEX") | 支持版本号3.40.2以上 |
| “CURRENT_TALK_NPC_LAYER” | widget | 获取当前打开的NPC面板(txt面板) | SL:GetMetaValue("CURRENT_TALK_NPC_LAYER") | 支持版本号3.40.6以上 |
| “M2_FORBID_SAY” | boolean | M2是否禁止说话 |
| param1: boolean 禁止时是否需要提示 | SL:GetMetaValue("M2_FORBID_SAY", true) | 支持版本号3.40.3以上 |
当前地图

| 参数名 | 返回值类型 | 说明 | 例子 |
| --- | --- | --- | --- |
| “MAP_ID” | string | 地图ID | SL:GetMetaValue("MAP_ID") |
| “MAP_NAME” | string | 地图名字 | SL:GetMetaValue("MAP_NAME") |
| “MAP_DATA_ID” | string | 地图数据ID | SL:GetMetaValue("MAP_DATA_ID") |
| “MINIMAP_ID” | string | 小地图ID | SL:GetMetaValue("MINIMAP_ID") |
| “IN_SAFE_AREA” | boolean | 是否是安全区域 | SL:GetMetaValue("IN_SAFE_AREA") |
| “MAP_FORBID_LEVEL_AND_JOB” | boolean | 是否禁止职业和等级 | SL:GetMetaValue("MAP_FORBID_LEVEL_AND_JOB") |
| “MAP_FORBID_SAY” | boolean | 是否禁止说话 | SL:GetMetaValue("MAP_FORBID_SAY") |
| “MAP_SHOW_HPPER” | boolean | 是否血量显示百分比 | SL:GetMetaValue("MAP_SHOW_HPPER") |
| “MAP_FORBID_LOOK” | boolean | 是否禁止查看 | SL:GetMetaValue("MAP_FORBID_LOOK") |
| “MAP_FORBID_LAUNCH_SKILL” | boolean | 是否禁止释放某技能 | SL:GetMetaValue("MAP_FORBID_LAUNCH_SKILL") |
| “MINIMAP_ABLE” | boolean | 小地图资源是否有效 | SL:GetMetaValue("MINIMAP_ABLE") |
| “MAP_DATA_LOADED” | boolean | 地图map文件是否加载(false表示正在下载中)``` | SL:GetMetaValue("MAP_DATA_LOADED") | 支持版本号3.40.2以上 |
| “MAP_ROWS” | int | 地图横向格子数 | SL:GetMetaValue("MAP_ROWS") |
| “MAP_COLS” | int | 地图纵向格子数 | SL:GetMetaValue("MAP_COLS") |
| “MINIMAP_FILE” | string | 获取小地图文件路径 | SL:GetMetaValue("MINIMAP_FILE") | 支持版本号3.40.2以上 |
| “MAP_SIZE_WIDTH_PIXEL” | int | 地图获取宽度像素 | SL:GetMetaValue("MAP_SIZE_WIDTH_PIXEL") | 支持版本号3.40.2以上 |
| “MAP_SIZE_HEIGHT_PIXEL” | string | 地图获取高度像素 | SL:GetMetaValue("MAP_SIZE_HEIGHT_PIXEL") | 支持版本号3.40.2以上 |
| “MAP_IS_OBSTACLE” | boolean | 获取地图格子是否是阻挡 |
param1: 地图坐标X
| param2: 地图坐标Y | SL:GetMetaValue("MAP_IS_OBSTACLE", mapX, mapY) | 支持版本号3.40.2以上 |
| “MAP_PATH_SIZE” | int | 地图计算起点到终点X或者Y 变化最大的差值 | SL:GetMetaValue("MAP_PATH_SIZE") | 支持版本号3.40.2以上 |
| “MAP_PATH_POINTS” | table | 地图计算路径坐标 | SL:GetMetaValue("MAP_PATH_POINTS") | 支持版本号3.40.2以上 |
| “MAP_CURRENT_PATH_INDEX” | int | 地图获取当前路径坐标index | SL:GetMetaValue("MAP_CURRENT_PATH_INDEX") | 支持版本号3.40.2以上 |
| “MAP_PLAYER_POS” | table | 地图获取人物坐标 | SL:GetMetaValue("MAP_PLAYER_POS") | 支持版本号3.40.2以上 |
| “MAP_GET_MONSTERS” | table | 地图获取怪物列表位置等信息 | SL:GetMetaValue("MAP_GET_MONSTERS") | 支持版本号3.40.2以上 |
| “MAP_GET_PORTALS” | table | 地图获取传送点列表位置等信息 | SL:GetMetaValue("MAP_GET_PORTALS") | 支持版本号3.40.2以上 |
| “FIND_IN_VIEW_PLAYER_LIST” | table | 获取视野内玩家列表 | SL:GetMetaValue("FIND_IN_VIEW_PLAYER_LIST") | 支持版本号3.40.2以上 |
| “FIND_IN_VIEW_MONSTER_LIST” | table | 获取视野内的怪物列表。 |
参数说明：
param1: boolean，是否排除主玩家的怪物；
param2: boolean，是否排除有主人的怪物（包含主玩家的怪）。
| “FIND_IN_VIEW_NPC_LIST” | table | 获取视野内NPC列表 | SL:GetMetaValue("FIND_IN_VIEW_NPC_LIST") | 支持版本号3.40.2以上 |
| “IN_SIEGE_AREA” | boolean | 是否在攻城区域 | SL:GetMetaValue("IN_SIEGE_AREA") | 支持版本号3.40.5以上 |
宠物

| 参数名 | 返回值类型 | 说明 | 例子 |
| --- | --- | --- | --- |
| “PET_ALIVE” | boolean | 是否有存活的宝宝 | SL:GetMetaValue("PET_ALIVE") |
| “PET_LOCK_ID” | string | 宠物锁定的目标ID | SL:GetMetaValue("PET_LOCK_ID") |
英雄

| 参数名 | 返回值类型 | 说明 | 例子 |
| --- | --- | --- | --- |
| “USEHERO” | boolean | 是否开启英雄 | SL:GetMetaValue("USEHERO") |
| “HERO_IS_ALIVE” | boolean | 是否召唤英雄 | SL:GetMetaValue("HERO_IS_ALIVE") |
| “HERO_IS_ACTIVE” | boolean | 是否激活英雄 | SL:GetMetaValue("HERO_IS_ACTIVE") |
| “HERO_ID” | int | 英雄ID | SL:GetMetaValue("HERO_ID") |
| “HERO_STATES_SYS_VALUES” | table | 英雄状态系统能设置的列表 | SL:GetMetaValue("HERO_STATES_SYS_VALUES") |
| “HERO_ACTIVES_STATES” | table | 英雄激活的状态列表 | SL:GetMetaValue("HERO_ACTIVES_STATES") |
| “HERO_STATE” | int | 获取英雄状态 0 攻击 1 跟随 2 休息 | SL:GetMetaValue("HERO_STATE") |
| “HERO_GUARDSTATE” | boolean | 获取英雄守护状态 | SL:GetMetaValue("HERO_GUARDSTATE") |
| “HERO_GUARD_ISCLICK” | boolean | 是否点击守护按钮 | SL:GetMetaValue("HERO_GUARD_ISCLICK") |
道具

| 参数名 | 返回值类型 | 说明 | 例子 |
| --- | --- | --- | --- |
| “MONEY” | string | 获取货币数量 | SL:GetMetaValue("MONEY", ID) |
| “MONEY_ASSOCIATED” | string | 获取货币数量 (包括道具表配置的Reserved 等价替换道具的数量) | SL:GetMetaValue("MONEY_ASSOCIATED", id) | 支持版本号3.40.3以上 |
| “STD_ITEMS” | table | 获取所有道具信息 | SL:GetMetaValue("STD_ITEMS") |
| “ITEM_DATA” | table | 根据道具index获取道具信息 | SL:GetMetaValue("ITEM_DATA", itemIndex) |
| “ITEM_COUNT” | int | 根据道具index或者名字获取道具数量 | SL:GetMetaValue("ITEM_COUNT", itemIndex)或者SL:GetMetaValue("ITEM_COUNT", itemName) |
| “ITEM_NAME” | string | 根据道具index获取道具名字 | SL:GetMetaValue("ITEM_NAME", itemIndex) |
| “ITEM_INDEX_BY_NAME” | int | 根据道具名字获取道具index | SL:GetMetaValue("ITEM_INDEX_BY_NAME", itemName) |
| “ITEM_NAME_COLOR” | string | 获取道具名字颜色 | SL:GetMetaValue("ITEM_NAME_COLOR", itemIndex) |
| “ITEM_NAME_COLOR_VALUE” | string | 道具名字颜色,”#FFFFFF”格式 | SL:GetMetaValue("ITEM_NAME_COLOR_VALUE", itemIndex) |
| “ITEM_NAME_COLORID” | string | 道具名字颜色ID, 颜色表ID | SL:GetMetaValue("ITEM_NAME_COLORID", itemIndex) |
| “ITEM_PROMPT_DATA” | table | 道具表prompt解析后数据 | SL:GetMetaValue("ITEM_PROMPT_DATA") |
| “ITEM_CUSTOM_ATTR” | table | 获取物品变量数据 param1: 物品MakeIndex | SL:GetMetaValue("ITEM_CUSTOM_ATTR", param1) | 支持版本号3.40.8以上 |
| “ITEM_IS_BIND” | boolean | 物品是否绑定 |
| param1: table — 物品数据 | SL:GetMetaValue("ITEM_IS_BIND", itemData) |
| “ITEM_DATA_BY_MAKEINDEX” | table | 根据MakeIndex获取背包数据 |
param1: MakeIndex
| param2: 是否是英雄 | SL:GetMetaValue("ITEM_DATA_BY_MAKEINDEX", param1, param2) |
| “EQUIP_DATA_BY_MAKEINDEX” | table | 根据MakeIndex获取装备数据 |
param1: MakeIndex
| param2: 是否是英雄 | SL:GetMetaValue("EQUIP_DATA_BY_MAKEINDEX", param1, param2) |
| “STORAGE_DATA_BY_MAKEINDEX” | table | 根据MakeIndex获取仓库数据 |
| param1: MakeIndex | SL:GetMetaValue("STORAGE_DATA_BY_MAKEINDEX", param1) |
| “QUICKUSE_DATA_BY_MAKEINDEX” | table | 根据MakeIndex获取快捷栏数据 |
| param1: MakeIndex | SL:GetMetaValue("QUICKUSE_DATA_BY_MAKEINDEX", param1) | 支持版本号3.40.3以上 |
| “LOOKPLAYER_DATA_BY_MAKEINDEX” | table | 根据MakeIndex获取查看他人装备数据 |
| param1: MakeIndex | SL:GetMetaValue("LOOKPLAYER_DATA_BY_MAKEINDEX", param1) | 支持版本号3.40.3以上 |
| “BAG_DATA” | table | 获取背包所有物品数据 | SL:GetMetaValue("BAG_DATA") |
| “H.BAG_DATA” | table | 获取英雄背包所有物品数据 | SL:GetMetaValue("H.BAG_DATA") | 支持版本号3.40.8以上 |
| “QUICKUSE_DATA” | table | 获取快捷使用数据 | SL:GetMetaValue("QUICKUSE_DATA") |
| “CHECK_USE_ITEM_BUFF” | boolean, int | 检查禁止使用物品buff |
param1: itemIndex
| 返回参数：能否使用, buffID | SL:GetMetaValue("CHECK_USE_ITEM_BUFF", itemIndex) | 支持版本号3.40.7以上 |
| “ITEM_CAN_AUTOUSE” | boolean | 物品能否自动使用 |
| param1: itemData table — 物品数据 | SL:GetMetaValue("ITEM_CAN_AUTOUSE", itemData) | 支持版本号3.40.7以上 |
| “SKILLBOOK_CAN_USE” | boolean | 技能书能否使用 |
param1: itemName 技能书名字
| param2：boolean 是否英雄 | SL:GetMetaValue("SKILLBOOK_CAN_USE", itemName, false) | 支持版本号3.40.7以上 |
| “ITEM_BELONG_BY_MAKEINDEX” | int | 根据MakeIndex获取物品归属[可参考GUIDefine.ITEM_BELONG] | SL:GetMetaValue("ITEM_BELONG_BY_MAKEINDEX", makeIndex) | 支持版本号3.40.7以上 |
| “BAG_MAKEINDEX_BY_POS” | int | 获取背包物品唯一ID |
param1: 背包位置
| param2: boolean — 是否英雄 | SL:GetMetaValue("BAG_MAKEINDEX_BY_POS", pos) | 支持版本号3.40.8以上 |
| “ITEM_ARTICLE_ENUM” | table | 物品规则类型枚举 | SL:GetMetaValue("ITEM_ARTICLE_ENUM") | 支持版本号3.40.8以上 |
道具框

| 参数名 | 返回值类型 | 说明 | 例子 |
| --- | --- | --- | --- |
| “ITEM_SCALE” | int | 道具框默认缩放 | SL:GetMetaValue("ITEM_SCALE") |
战斗

| 参数名 | 返回值类型 | 说明 | 例子 |
| --- | --- | --- | --- |
| “BATTLE_IS_AFK” | boolean | 是否自动挂机中 | SL:GetMetaValue("BATTLE_IS_AFK") |
| “BATTLE_AFK_BEGIN” | void | 开始自动挂机 | SL:SetMetaValue("BATTLE_AFK_BEGIN") |
| “BATTLE_AFK_END” | void | 结束自动挂机 | SL:SetMetaValue("BATTLE_AFK_END") |
| “BATTLE_IS_AUTO_MOVE” | boolean | 是否自动寻路中 | SL:GetMetaValue("BATTLE_IS_AUTO_MOVE") |
| “BATTLE_MOVE_BEGIN” | void | 开始自动寻路 |
mapID: 地图ID
mapX: 坐标x
mapY: 坐标y
target:
{
type: 0：怪物    1：NPC
index: 目标类型index
}
type: 寻路类型
| 可参考GUIDefine.AUTO_MOVE_TYPE | SL:SetMetaValue("BATTLE_MOVE_BEGIN", mapID, mapX, mapY, target, type) |
| “BATTLE_MOVE_END” | void | 结束自动寻路 | SL:SetMetaValue("BATTLE_MOVE_END") |
| “BATTLE_IS_AUTO_PICK” | boolean | 是否自动捡物中 | SL:GetMetaValue("BATTLE_IS_AUTO_PICK") |
| “BATTLE_PICK_BEGIN” | void | 开始自动捡物 | SL:SetMetaValue("BATTLE_PICK_BEGIN") |
| “BATTLE_PICK_END” | void | 结束自动捡物 | SL:SetMetaValue("BATTLE_PICK_END") |
Actor
actorID: 玩家、怪物、NPC、人形怪等对象ID(对应服务端唯一ID/UserID)

| 参数名 | 返回值类型 | 说明 | 例子 |
| --- | --- | --- | --- |
| “MAIN_ACTOR_ID” | string | 主玩家actorID | SL:GetMetaValue("MAIN_ACTOR_ID") | 支持版本号3.40.3以上 |
| “ACTOR_IS_PLAYER” | boolean | 是否是玩家 | SL:GetMetaValue("ACTOR_IS_PLAYER", actorID) |
| “ACTOR_IS_NETPLAYER” | boolean | 是否是网络玩家 | SL:GetMetaValue("ACTOR_IS_NETPLAYER", actorID) |
| “ACTOR_IS_MONSTER” | boolean | 是否是怪物 | SL:GetMetaValue("ACTOR_IS_MONSTER", actorID) |
| “ACTOR_IS_NPC” | boolean | 是否是NPC | SL:GetMetaValue("ACTOR_IS_NPC", actorID) |
| “ACTOR_IS_HERO” | boolean | 是否是英雄 | SL:GetMetaValue("ACTOR_IS_HERO", actorID) |
| “ACTOR_IS_HUMAN” | boolean | 是否是人形怪 | SL:GetMetaValue("ACTOR_IS_HUMAN", actorID) |
| “ACTOR_NAME” | string | 获取actor 名字 | SL:GetMetaValue("ACTOR_NAME", actorID) |
| “ACTOR_HP” | int | 获取 actor Hp | SL:GetMetaValue("ACTOR_HP", actorID) |
| “ACTOR_MAXHP” | int | 获取actor Max Hp | SL:GetMetaValue("ACTOR_MAXHP", actorID) |
| “ACTOR_MP” | int | 获取actor Mp | SL:GetMetaValue("ACTOR_MP", actorID) |
| “ACTOR_MAXMP” | int | 获取actor Max Mp | SL:GetMetaValue("ACTOR_MAXMP", actorID) |
| “ACTOR_LEVEL” | int | 获取actor等级 | SL:GetMetaValue("ACTOR_LEVEL", actorID) |
| “ACTOR_JOB_ID” | int | 获取actor职业 | SL:GetMetaValue("ACTOR_JOB_ID", actorID) |
| “ACTOR_SEX” | int | 获取actor性别 | SL:GetMetaValue("ACTOR_SEX", actorID) |
| “ACTOR_IS_DIE” | boolean | actor是否死亡 | SL:GetMetaValue("ACTOR_IS_DIE", actorID) |
| “ACTOR_OWNER_ID” | string | 获取actor归属ID | SL:GetMetaValue("ACTOR_OWNER_ID", actorID) |
| “ACTOR_OWNER_NAME” | string | 获取actor归属名字 | SL:GetMetaValue("ACTOR_OWNER_NAME", actorID) |
| “ACTOR_BIGICON_ID” | int | 获取怪物大图标ID | SL:GetMetaValue("ACTOR_BIGICON_ID", actorID) |
| “SELECT_TARGET_ID” | int | 选中的目标actorID或者怪物归属者 | SL:GetMetaValue("SELECT_TARGET_ID") |
| “TARGET_ATTACK_ENABLE” | boolean | 检查该目标是否可以攻击 |
| param1: 目标actorID | SL:GetMetaValue("TARGET_ATTACK_ENABLE", actorID) | 支持版本号3.40.3以上 |
| “ACTOR_TEAM_STATE” | int | 获取actor组队状态 |
0：未组队
1：组队中

| param1: actorID | SL:GetMetaValue("ACTOR_TEAM_STATE", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_GUILD_ID” | string | 获取actor行会ID | SL:GetMetaValue("ACTOR_GUILD_ID", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_GUILD_NAME” | string | 获取actor行会名字 | SL:GetMetaValue("ACTOR_GUILD_NAME", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_TYPE_INDEX” | int | 获取actor的typeIndex, 对应怪物表/NPC表 ID | SL:GetMetaValue("ACTOR_TYPE_INDEX", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_DIR” | int | 获取actor方向 | SL:GetMetaValue("ACTOR_DIR", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_MAP_X” | int | 获取actor地图坐标X | SL:GetMetaValue("ACTOR_MAP_X", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_MAP_Y” | int | 获取actor地图坐标Y | SL:GetMetaValue("ACTOR_MAP_Y", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_POSITION_X” | int | 获取actor世界坐标X | SL:GetMetaValue("ACTOR_POSITION_X", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_POSITION_Y” | int | 获取actor世界坐标Y | SL:GetMetaValue("ACTOR_POSITION_Y", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_MASTER_ID” | int | 获取actor主人ID | SL:GetMetaValue("ACTOR_MASTER_ID", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_HAVE_MASTER” | boolean | 获取actor是否有主人 | SL:GetMetaValue("ACTOR_HAVE_MASTER", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_FACTION” | int | 获取actor阵营ID, 大于0且相等是同阵营 | SL:GetMetaValue("ACTOR_FACTION", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_IN_SAFE_ZONE” | boolean | 获取actor是否在安全区 | SL:GetMetaValue("ACTOR_IN_SAFE_ZONE", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_APPR_ID” | boolean | 获取actor的外观ID | SL:GetMetaValue("ACTOR_APPR_ID", actorID) | 支持版本号3.40.3以上 |
| “ACTOR_WEAPON_ID” | boolean | 获取actor的武器ID | SL:GetMetaValue("ACTOR_WEAPON_ID", actorID) | 支持版本号3.40.3以上 |
| “ACTOR_LEFT_WEAPON_ID” | boolean | 获取actor的左手武器ID | SL:GetMetaValue("ACTOR_LEFT_WEAPON_ID", actorID) | 支持版本号3.40.3以上 |
| “ACTOR_SHIELD_ID” | boolean | 获取actor的盾牌ID | SL:GetMetaValue("ACTOR_SHIELD_ID", actorID) | 支持版本号3.40.3以上 |
| “ACTOR_WINGS_ID” | boolean | 获取actor的翅膀ID | SL:GetMetaValue("ACTOR_WINGS_ID", actorID) | 支持版本号3.40.3以上 |
| “ACTOR_HAIR_ID” | boolean | 获取actor的发型ID | SL:GetMetaValue("ACTOR_HAIR_ID", actorID) | 支持版本号3.40.3以上 |
| “ACTOR_MOUNT_NODE” | widget | 获取actor挂接点 ( ！即取即用 避免存储使用 | SL:GetMetaValue("ACTOR_MOUNT_NODE", actorID) | 支持版本号3.40.7以上 |
| “ACTOR_CAN_LOCK_BY_HERO” | boolean | 检查英雄选中的目标是否能锁定 | SL:GetMetaValue("ACTOR_CAN_LOCK_BY_HERO", actorID) | 支持版本号3.40.7以上 |
| “ACTOR_PKLV” | int | 获取actor红名灰名 |
| 白=0 咖啡=1 红=2 灰=3 | SL:GetMetaValue("ACTOR_PKLV", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_SERVER_ID” | int | 获取actor区服ID, 跨服时使用 | SL:GetMetaValue("ACTOR_SERVER_ID", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_IS_IN_STALL” | boolean | actor是否在摆摊 | SL:GetMetaValue("ACTOR_IS_IN_STALL", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_STALL_NAME” | string | 获取actor摆摊名 | SL:GetMetaValue("ACTOR_STALL_NAME", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_IS_OFFLINE” | string | 获取actor是否是离线状态玩家 | SL:GetMetaValue("ACTOR_IS_OFFLINE", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_IS_MYSTERY_MAN” | boolean | actor是否是神秘人 | SL:GetMetaValue("ACTOR_IS_MYSTERY_MAN", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_IS_HUSHEN” | boolean | 获取actor是否拥有护身 | SL:GetMetaValue("ACTOR_IS_HUSHEN", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_IS_MAINPLAYER” | boolean | actor是否是主玩家 | SL:GetMetaValue("ACTOR_IS_MAINPLAYER", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_IS_HORSEBACK_RADING” | boolean | actor是否是骑马状态 | SL:GetMetaValue("ACTOR_IS_HORSEBACK_RADING", actorID) | 支持版本号3.40.8以上 |
| “ACTOR_NATION_ID” | int | 获取actor国家ID | SL:GetMetaValue("ACTOR_NATION_ID", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_HORSE_MASTER_ID” | int | 获取actor坐骑的主驾ID | SL:GetMetaValue("ACTOR_HORSE_MASTER_ID", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_HORSE_COPILOT_ID” | int | 获取actor坐骑的副驾ID | SL:GetMetaValue("ACTOR_HORSE_COPILOT_ID", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_IS_HORSE_COPILOT” | boolean | actor是否是坐骑的副驾 | SL:GetMetaValue("ACTOR_IS_HORSE_COPILOT", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_IS_DOUBLE_HORSE” | boolean | actor是否是双人坐骑 | SL:GetMetaValue("ACTOR_IS_DOUBLE_HORSE", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_IS_BODY_HORSE” | boolean | actor是否是连体坐骑 | SL:GetMetaValue("ACTOR_IS_BODY_HORSE", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_MOVE_EFFECT” | int | 获取actor的足迹特效ID | SL:GetMetaValue("ACTOR_MOVE_EFFECT", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_DEAR_ID” | int | 获取actor的夫妻ID | SL:GetMetaValue("ACTOR_DEAR_ID", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_MENTOR_ID” | int | 获取actor的师徒ID | SL:GetMetaValue("ACTOR_MENTOR_ID", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_NEAR_SHOW” | boolean | 获取actor是否在附近显示 | SL:GetMetaValue("ACTOR_NEAR_SHOW", actorID) | 支持版本号3.40.3以上 |
| “ACTOR_IS_MOVE” | boolean | 获取actor是否在移动状态 | SL:GetMetaValue("ACTOR_IS_MOVE", SL:GetMetaValue("USER_ID")) | 支持版本号3.40.3以上 |
| “ACTOR_STOME_MODE” | boolean | 获取actor(怪物)是否石化状态 | SL:GetMetaValue("ACTOR_STOME_MODE", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_RACE_SERVER” | int | 获取actor(怪物) race server | SL:GetMetaValue("ACTOR_RACE_SERVER", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_RACE_IMG” | int | 获取actor(怪物) race img | SL:GetMetaValue("ACTOR_RACE_IMG", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_HIDE_NAME” | boolean | 获取actor(怪物)是否不显示名字 | SL:GetMetaValue("ACTOR_HIDE_NAME", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_HIDE_HP_BAR” | boolean | 获取actor(怪物)是否不显示血条 | SL:GetMetaValue("ACTOR_HIDE_HP_BAR", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_NATION_ENEMY_PK” | boolean | 获取actor(怪物)国家模式是否可被攻击 | SL:GetMetaValue("ACTOR_NATION_ENEMY_PK", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_GM_DATA” | table | 获取actor的GM自定义数据 | SL:GetMetaValue("ACTOR_GM_DATA", actorID) | 支持版本号3.40.3以上 |
| “ACTOR_IS_NETPLAYER” | boolean | actor是否网络玩家 | SL:GetMetaValue("ACTOR_IS_NETPLAYER", actorID) |
| “ACTOR_IS_ESCORT” | boolean | actor是否镖车 | SL:GetMetaValue("ACTOR_IS_ESCORT", actorID) |
| “ACTOR_IS_COLLECTION” | boolean | actor是否采集物 | SL:GetMetaValue("ACTOR_IS_COLLECTION", actorID) |
| “ACTOR_IS_DEFENDER” | boolean | actor是否守卫 | SL:GetMetaValue("ACTOR_IS_DEFENDER", actorID) |
| “ACTOR_IS_PICKUPSPRITE” | boolean | actor是否捡物小精灵 | SL:GetMetaValue("ACTOR_IS_PICKUPSPRITE", actorID) |
| “ACTOR_IS_PET” | boolean | actor是否宝宝 | SL:GetMetaValue("ACTOR_IS_PET", actorID) |
| “ACTOR_IS_GATE” | boolean | actor是否沙巴克大门 | SL:GetMetaValue("ACTOR_IS_GATE", actorID) |
| “ACTOR_IS_WALL” | boolean | actor是否沙巴克城墙 | SL:GetMetaValue("ACTOR_IS_WALL", actorID) |
| “ACTOR_IS_DEATH” | boolean | actor是否死亡 | SL:GetMetaValue("ACTOR_IS_DEATH", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_IS_BORN” | boolean | actor是否出生 | SL:GetMetaValue("ACTOR_IS_BORN", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_IS_CAVE” | boolean | actor是否钻回洞穴 | SL:GetMetaValue("ACTOR_IS_CAVE", actorID) | 支持版本号3.40.2以上 |
| “ACTOR_BUFF_DATA” | table | actor身上所有buff数据 | SL:GetMetaValue("ACTOR_BUFF_DATA", actorID) |
| “ACTOR_HAS_ONE_BUFF” | boolean | actor是否有某个buff | SL:GetMetaValue("ACTOR_HAS_ONE_BUFF", actorID, buffID) |
| “ACTOR_BUFF_DATA_BY_ID” | table | 获取actor身上某个buff数据 | SL:GetMetaValue("ACTOR_BUFF_DATA_BY_ID", actorID, buffID) | 支持版本号3.40.2以上 |
返回值描述(int)：
类型：table
{
{
id          -- buffID
endTime     -- buff 结束时间
ol          -- buff 叠加层级
config      -- buff cfg_buff配置表中数据
name        -- buff 名字
tips        -- buff 描述
icon        -- buff icon
sort        -- buff 图标排序字段
}
}

其他

| 参数名 | 返回值类型 | 说明 | 例子 |
| --- | --- | --- | --- |
| “PKMODE” | int | 获取当前PK模式 |
0：全体
1：和平
2：夫妻
3：师徒
4：组队
5：公会
6：善恶
| 7：国家 | SL:GetMetaValue("PKMODE") |
| “PKMODE_CAN_USE” | boolean | 该PK模式是否可以切换 |
| param: PK模式 | SL:GetMetaValue("PKMODE_CAN_USE", 5) |
| “PET_PKMODE” | int | 获取宠物PK模式 |
1：跟随
2：战斗
3：锁定
| 4：休息 | SL:GetMetaValue("PET_PKMODE") |
| “PET_ALIVE” | boolean | 是否有存活的宝宝 | SL:GetMetaValue("PET_ALIVE") |
| “PET_LOCK_ID” | string | 宠物锁定的目标ID | SL:GetMetaValue("PET_LOCK_ID") |
| “KFSTATE” | boolean | 是否处于跨服 | SL:GetMetaValue("KFSTATE") |
| “SERVER_TIME” | int | 当前服务器时间 | SL:GetMetaValue("SERVER_TIME") |
| “X” | int | 人物当前坐标X | SL:GetMetaValue("X") |
| “Y” | int | 人物当前坐标Y | SL:GetMetaValue("Y") |
| “BUBBLETIPS_INFO” | table | 根据气泡index获取气泡数据 |
气泡类型：
1: 可提升提示
2: 邮件
3: 组队邀请
4: 交易邀请
5: 好友邀请
6: 行会邀请
7: 拍卖行提醒
8: 经验存储提醒
9: 装备首曝提示
10: 行会申请提示
11: 药品不足提示
12: 装备推送
13: 结盟申请
| 14: 私聊提示 | SL:GetMetaValue("BUBBLETIPS_INFO", index) |
| “BONUSPOINT” | int | 转生属性点 | SL:GetMetaValue("BONUSPOINT") |
| “IS_PICK_STATE” | boolean | 是否是自动拾取状态 | SL:GetMetaValue("IS_PICK_STATE") |
| “PC_POS_Y” | int | PC端Y轴适配 | SL:GetMetaValue("PC_POS_Y") |
| “MENU_LAYERS_BY_GROUNP” | int | 通过 cfg_menulayer 表中的组ID(group_id)获取该组界面配置信息 | SL:GetMetaValue("MENU_LAYERS_BY_GROUNP", groupID) |
| “DARK_STATE” | int | 黑夜当前状态 | SL:GetMetaValue("DARK_STATE") |
| “UIMODEL_HAIR_OFFSET” | table | 内观头发偏移配置 | SL:GetMetaValue("UIMODEL_HAIR_OFFSET") |
| “UIMODEL_EQUIP_OFFSET” | table | 内观装备偏移配置 | SL:GetMetaValue("UIMODEL_EQUIP_OFFSET") |
| “TOUCH_STATE” | boolean | 屏幕点击状态 | SL:GetMetaValue("TOUCH_STATE") |
| “BEST_RING_WIN_ISOPEN” | boolean | 首饰盒界面是否打开 |
| param1: 1: 自己人物、2：自己英雄、11：其他玩家人物、12：其他玩家英雄、21：交易行人物、22：交易行英雄 | SL:GetMetaValue("BEST_RING_WIN_ISOPEN", 1) |
| “BEST_RING_OPENSTATE” | boolean | 首饰盒开启状态 |
| param1: 1: 自己人物、2：自己英雄、11：其他玩家人物、12：其他玩家英雄、21：交易行人物、22：交易行英雄 | SL:GetMetaValue("BEST_RING_OPENSTATE", 1) |
| “CHECK_FUNCBTN_SHOW” | boolean | 检查当前类别功能菜单的某种按钮是否显示 |
param1:功能类别 FuncDock.FuncDockType可查
| param2: 按钮类型 FuncDock.BtnOperatorType可查 | SL:GetMetaValue("CHECK_FUNCBTN_SHOW", dockType, btnType) |
| “MOUSE_MOVE_POS” | table | 鼠标移动位置 | SL:GetMetaValue("MOUSE_MOVE_POS") |
| “CHECK_MINIMAP_OPEN” | boolean | 小地图界面是否打开 | SL:GetMetaValue("CHECK_MINIMAP_OPEN") |
| “TRADINGBANK_OPENSTATUS” | boolean | 交易行开启状态 |
| 进入游戏和打开交易行会请求后台更新状态 | SL:GetMetaValue("TRADINGBANK_OPENSTATUS") | 支持版本号3.40.2以上 |
| “OPEN_SERVER_TIME” | int | 开服时间戳 | SL:GetMetaValue("OPEN_SERVER_TIME") | 支持版本号3.40.2以上 |
| “OPEN_SERVER_DAY” | int | 开服天数 | SL:GetMetaValue("OPEN_SERVER_DAY") | 支持版本号3.40.2以上 |
| “MERGE_SERVER_COUNT” | int | 合服次数 | SL:GetMetaValue("MERGE_SERVER_COUNT") | 支持版本号3.40.2以上 |
| “MERGE_SERVER_TIME” | int | 合服时间戳 | SL:GetMetaValue("MERGE_SERVER_TIME") | 支持版本号3.40.2以上 |
| “MERGE_SERVER_DAY” | int | 合服天数 | SL:GetMetaValue("MERGE_SERVER_DAY") | 支持版本号3.40.2以上 |
| “BUFF_CONFIG” | table | 获取buffID的配置表数据 |
param1: buffID
| 无参, 则整个buff表数据 | SL:GetMetaValue("BUFF_CONFIG") | 支持版本号3.40.2以上 |
| “SHOW_STATUS_PERMIT” | boolean | 允许在附近显示状态 | SL:GetMetaValue("SHOW_STATUS_PERMIT") | 支持版本号3.40.3以上 |
| “GAMEPAD_MOVE_PARAM” | int, int | 获取游戏摇杆移动参数, 返回第一个参数: 移动方向 int 0 ~ 8 |
| 返回第二个参数: 移动步长 int | SL:GetMetaValue("GAMEPAD_MOVE_PARAM") | 支持版本号3.40.3以上 |
| “TARGET_MAPPOS_DIR” | int | 获取目标地图坐标到初始地图坐标的方向/朝向 0 ~ 8 |
param1: 初始地图坐标 table
| param2: 目标地图坐标 table | SL:GetMetaValue("TARGET_MAPPOS_DIR", srcPos, destPos) | 支持版本号3.40.3以上 |
| “CHECK_REDPOINT_ID” | boolean | 检测红点表对应id是否满足条件 | SL:GetMetaValue("CHECK_REDPOINT_ID", id) | 支持版本号3.40.4以上 |
| “CTRL_PRESSED” | boolean | PC端 CTRL键是否按下 | SL:GetMetaValue("CTRL_PRESSED") | 支持版本号3.40.4以上 |
| “PC_NP_STATUS” | boolean | PC端 是否开启NP反外挂 | SL:GetMetaValue("PC_NP_STATUS") |
| “SELECT_SHIFT_ATTACK_ID” | int | 获取PC持续攻击目标 | SL:GetMetaValue("SELECT_SHIFT_ATTACK_ID") | 支持版本号3.40.5以上 |
| “IS_PICKABLE_DROPITEM” | boolean | 掉落物是否可拾取 |
param1: 掉落物 actorID
| param2: 归属ID | SL:GetMetaValue("IS_PICKABLE_DROPITEM", actorID, mainPlayerID) | 支持版本号3.40.5以上 |
| “AUTOUSE_MAKEINDEX_BY_POS” | int | 获取已添加的自动使用弹窗物品唯一ID |
| param1: 类型 （1: 人物 2: 英雄） param2: 装备位 | SL:GetMetaValue("AUTOUSE_MAKEINDEX_BY_POS", playerType, equipPos) | 支持版本号3.40.7以上 |
| “CHECK_IN_GUIDE” | boolean | 是否在引导中 [Lua添加的引导] | SL:GetMetaValue("CHECK_IN_GUIDE") | 支持版本号3.40.7以上 |
| “PICK_ACTORID_BY_POS” | actorID | PC 按坐标选中actor | SL:GetMetaValue("PICK_ACTORID_BY_POS", pos) | 支持版本号3.40.7以上 |
| “TARGET_ID” | string | 功能菜单选中目标ID | SL:GetMetaValue("TARGET_ID") |
| “TARGET_NAME” | string | 功能菜单选中目标名字 | SL:GetMetaValue("TARGET_NAME") |
聊天

| 参数名 | 返回值类型 | 说明 | 例子 |
| --- | --- | --- | --- |
| “CHAT_EMOJI” | table | 获取聊天表情包 | SL:GetMetaValue(“CHAT_EMOJI”) |
| “CHAT_INPUT_CACHE” | table | 获取聊天输入历史记录缓存 | SL:GetMetaValue(“CHAT_INPUT_CACHE”) |
| “CHAT_SHOW_ITEMS” | table | 获取聊天显示的道具 | SL:GetMetaValue(“CHAT_SHOW_ITEMS”) |
| “CHAT_CHANNEL_ISRECEIVE” | boolean | 当前频道是否接受聊天信息 | SL:GetMetaValue(“CHAT_CHANNEL_ISRECEIVE”, 3) |
| “DROP_TYPE_ISRECEIVE” | boolean | 是否接收该分类掉落信息 |
| param1: 掉落分类id 1-10 | SL:GetMetaValue(“DROP_TYPE_ISRECEIVE”, 1) | 支持版本号3.40.5以上 |
| “CHATANDTIPS_USE_FONT” | string | 聊天 Tips使用的字体路径 | SL:GetMetaValue(“CHATANDTIPS_USE_FONT”) |
| “CUR_CHAT_CHANNEL” | int | 获取当前聊天频道 | SL:GetMetaValue(“CUR_CHAT_CHANNEL”) | 支持版本号3.40.3以上 |
| “CHAT_TARGETS” | table | 获取聊天目标 {{name = 玩家名, uid = 玩家ID}, ..} | SL:GetMetaValue(“CHAT_TARGETS”) | 支持版本号3.40.3以上 |
| “CHAT_CUR_CDTIME” | int | 获取当前聊天CD时间 | SL:GetMetaValue(“CHAT_CUR_CDTIME”) | 支持版本号3.40.3以上 |
| “IS_CLOSE_FAKEDROP” | boolean | 是否关闭假掉落 | SL:GetMetaValue(“IS_CLOSE_FAKEDROP”) | 支持版本号3.40.7以上 |
| “CHAT_MSGTYPE_ENUM” | table | 聊天消息类型列表, 详情如下 | SL:GetMetaValue(“CHAT_MSGTYPE_ENUM”) | 支持版本号3.40.3以上 |
| “CHAT_CHANNEL_ENUM” | table | 聊天频道列表, 详情如下 | SL:GetMetaValue(“CHAT_MSGTYPE_ENUM”) | 支持版本号3.40.3以上 |
聊天消息类型：
{
Normal     = 1,     -- 普通消息
Position   = 2,     -- 坐标
Equip      = 3,     -- 装备
SystemTips = 5,     -- 系统通知消息，需使用特定的富文本解析
FColorText = 6,     -- 系统通知消息，需使用FColor富文本解析
SRText     = 7,     -- 系统通知消息，需使用SRText富文本解析
}








聊天频道:
{
Common    = 0,  -- 综合
System    = 1,  -- 系统
Shout     = 2,  -- 喊话
Private   = 3,  -- 私聊
Guild     = 4,  -- 行会
Team      = 5,  -- 组队
Near      = 6,  -- 附近
World     = 7,  -- 世界
Nation    = 8,  -- 国家
Union     = 9,  -- 联盟
GuildTips = 40, -- 行会通知
}

组队

| 参数名 | 返回值类型 | 说明 | 例子 |
| --- | --- | --- | --- |
| “TEAM_NEAR” | table | 附近队伍列表 | SL:GetMetaValue("TEAM_NEAR") |
| “TEAM_MEMBER_LIST” | table | 队伍成员列表 | SL:GetMetaValue("TEAM_MEMBER_LIST") |
| “TEAM_COUNT” | int | 当前队伍人数 | SL:GetMetaValue("TEAM_COUNT") |
| “TEAM_MAC_COUNT” | int | 队伍最大人数 | SL:GetMetaValue("TEAM_MAC_COUNT") |
| “TEAM_IS_MEMBER” | boolean | 是否是队伍成员 | SL:GetMetaValue("TEAM_IS_MEMBER") |
| “TEAM_STATUS_PERMIT” | boolean | 允许组队状态 | SL:GetMetaValue("TEAM_STATUS_PERMIT") |
| “TEAM_APPLY” | table | 入队申请列表 | SL:GetMetaValue("TEAM_APPLY") |
| “DOCKTYPE_NENUM” | table | func dock enum,返回值如下：data | SL:GetMetaValue("DOCKTYPE_NENUM") |
data = {
Func_Player_Head        = 1,  -- 点击玩家头像
Func_Friend             = 2,  -- 好友界面
Func_Team               = 3,  -- 左侧组队导航栏
Func_Guild              = 4,  -- 行会界面
Func_Friend_Recent      = 5,  -- 好友最近联系界面
Func_Friend_Enemy       = 6,  -- 好友仇敌界面
Func_Friend_BlackList   = 7,  -- 好友黑名单界面
Func_TeamLayer          = 8,  -- 组队界面
Func_Monster_Head       = 9,  -- 点击人形怪头像
Func_Near_Player        = 10  -- 附近玩家
}

邮件

| 参数名 | 返回值类型 | 说明 | 例子 |
| --- | --- | --- | --- |
| “MAIL_LIST” | table | 邮件列表 | SL:GetMetaValue("MAIL_LIST") |
| “MAIL_BY_ID” | string | 根据邮件ID获取邮件 | SL:GetMetaValue("MAIL_BY_ID", mailID) |
| “MAIL_HAVE_DEL_ITEM” | boolean | 是否有邮件可以删除 | SL:GetMetaValue("MAIL_HAVE_DEL_ITEM") |
| “MAIL_CURRENT_ID” | int | 当前邮件ID | SL:GetMetaValue("MAIL_CURRENT_ID") |
拍卖行

| 参数名 | 返回值类型 | 说明 | 例子 |
| --- | --- | --- | --- |
| “AUCTION_BIDPRICE_MIN” | int | 默认最低竞拍价 | SL:GetMetaValue("AUCTION_BIDPRICE_MIN") |
| “AUCTION_BIDPRICE_MAX” | int | 默认最高竞拍价 | SL:GetMetaValue("AUCTION_BIDPRICE_MAX") |
| “AUCTION_BUYPRICE_MIN” | int | 默认最低一口价 | SL:GetMetaValue("AUCTION_BUYPRICE_MIN") |
| “AUCTION_BUYPRICE_MAX” | int | 默认最高一口价 | SL:GetMetaValue("AUCTION_BUYPRICE_MAX") |
| “AUCTION_DEFAULT_SHELF” | int | 默认货架数量 | SL:GetMetaValue("AUCTION_DEFAULT_SHELF") |
| “AUCTION_PUT_LIST_CNT” | int | 上架列表数量 | SL:GetMetaValue("AUCTION_PUT_LIST_CNT") |
| “AUCTION_MONEY” | int | 拍卖行货币 | SL:GetMetaValue("AUCTION_MONEY") |
| “AUCTION_CAN_BID” | boolean | 是否可竞价 |
| param1: 拍卖物品数据 | SL:GetMetaValue("AUCTION_CAN_BID", item) |
| “AUCTION_CAN_BUY” | boolean | 是否可一口价 |
| param1: 拍卖物品数据 | SL:GetMetaValue("AUCTION_CAN_BUY", item) |
| “AUCTION_HAVE_MY_BIDDING” | boolean | 是否有我的竞拍物品 | SL:GetMetaValue("AUCTION_HAVE_MY_BIDDING") |
| “AUCTION_ITEM_STATE” | int, string | 拍卖行物品状态 |
传入参数：拍卖物品数据
返回值两个：
value1：
0：未知
2：竞拍中
3：已超时，
| value2：剩余时间 | SL:GetMetaValue("AUCTION_ITEM_STATE", itemData) |
| “AUCTION_MY_SHOW_LIST” | table | 获取拍卖行我的展示可寄售道具 | SL:GetMetaValue("AUCTION_MY_SHOW_LIST") | 支持版本号3.40.3以上 |
好友

| 参数名 | 返回值类型 | 说明 | 例子 |
| --- | --- | --- | --- |
| “FRIEND_MAX_COUNT” | int | 最大好友人数 | SL:GetMetaValue("FRIEND_MAX_COUNT") |
| “FRIEND_INFO_BY_UID” | table | 根据userID获取好友信息 | SL:GetMetaValue("FRIEND_INFO_BY_UID", userID) |
| “FRIEND_INFO_BY_NAME” | table | 根据userName获取好友信息 | SL:GetMetaValue("FRIEND_INFO_BY_NAME, userName") |
| “SOCIAL_IS_FRIEND” | boolean | 是否是好友 |
| param1: 玩家名字 | SL:GetMetaValue("SOCIAL_IS_FRIEND", userName) |
| “SOCIAL_IS_BLICKLIST” | boolean | 是否在黑名单 |
| param1: 玩家名字 | SL:GetMetaValue("SOCIAL_IS_BLICKLIST", userName) |
| “FRIEND_LIST” | table | 获取好友列表 | SL:GetMetaValue("FRIEND_LIST") |
| “FRIEND_BLACKLIST” | table | 获取黑名单数据 | SL:GetMetaValue("FRIEND_BLACKLIST") |
| “FRIEND_APPLYLIST” | table | 好友申请列表 | SL:GetMetaValue("FRIEND_APPLYLIST") |
| “ADD_STATUS_PERMIT” | boolean | 允许添加状态 | SL:GetMetaValue("ADD_STATUS_PERMIT") |
行会

| 参数名 | 返回值类型 | 说明 | 例子 |
| --- | --- | --- | --- |
| “GUILD_MEMBER_LIST” | table | 行会成员列表 | SL:GetMetaValue("GUILD_MEMBER_LIST") |
| “GUILD_APPLY_LIST” | table | 行会申请列表 | SL:GetMetaValue("GUILD_APPLY_LIST") |
| “GUILD_ALLY_APPLY_LIST” | table | 行会结盟申请列表 | SL:GetMetaValue("GUILD_ALLY_APPLY_LIST") |
| “GUILD_WORLD_LIST” | table | 获取世界行会列表 param1: 分页id | SL:GetMetaValue("GUILD_WORLD_LIST", 1) |
| “GUILD_WORLD_TOTAL_PAGES” | int | 获取世界行会列表总页数 | SL:GetMetaValue("GUILD_WORLD_TOTAL_PAGES") |
| “GUILD_CREATE” | table | 获取创建公会消耗信息 | SL:GetMetaValue("GUILD_CREATE") |
| “GUILD_INFO” | table | 我的行会信息 |
rank: int — 职位id
contribute: int —贡献
todayDonateGold: int —当天捐钱
isJoinGuild: boolean — 是否加入行会
guildName: string —行会名称
guildId: int —行会id
| isChairMan: boolean —是否是会长或者副会长 | SL:GetMetaValue("GUILD_INFO") |
| “GUILD_OFFICIAL” | string | 获取行会职位名称 param1: 职位id | SL:GetMetaValue("GUILD_OFFICIAL", 1) |
| “GUILD_MEMBER_INFO” | table | 通过uid获取行会成员信息 | SL:GetMetaValue("GUILD_MEMBER_INFO", targetId) |
面对面交易

| 参数名 | 返回值类型 | 说明 | 例子 |
| --- | --- | --- | --- |
| “TRADE_DATA” | table | 要交易的玩家信息 | SL:GetMetaValue("TRADE_DATA") |
| “TRADE_MY_LOCK_STATUS” | boolean | 交易自己锁定状态 | SL:GetMetaValue("TRADE_MY_LOCK_STATUS") |
| “TRADE_OTHER_LOCK_STATUS” | boolean | 交易对方锁定状态 | SL:GetMetaValue("TRADE_OTHER_LOCK_STATUS") |
| “DEAL_STATUS_PERMIT” | boolean | 允许交易状态 | SL:GetMetaValue("DEAL_STATUS_PERMIT") | 支持版本号3.40.3以上 |
排行榜

| 参数名 | 返回值类型 | 说明 | 例子 |
| --- | --- | --- | --- |
| “RANK_DATA_BY_TYPE” | table | 根据页签index获取排行榜数据 | SL:GetMetaValue("RANK_DATA_BY_TYPE", index) |
任务

| 参数名 | 类型 | 说明 | 例子 |
| --- | --- | --- | --- |
| “MISSION_ITEM_ORDER” | int | 根据任务类型/ID获取任务排序值 | SL:GetMetaValue("MISSION_ITEM_ORDER", type) |
| “MISSION_ITEM_BY_ID” | table | 根据任务类型/ID获取任务数据 | SL:GetMetaValue("MISSION_ITEM_BY_ID", type) | 支持版本号3.40.9以上 |
技能

| 参数名 | 返回值类型 | 说明 | 例子 |
| --- | --- | --- | --- |
| “SKILL_INFO_FILTER” | table | 筛选技能数据 |
param1：技能类型
param2：职业
param3：是否学习
| param4：是否不是基础技能 | SL:GetMetaValue("SKILL_INFO_FILTER", param1, param2, param3, param4) |
| “SKILL_NAME” | string | 获取技能名字 | SL:GetMetaValue("SKILL_NAME", skillID) |
| “SKILL_ICON_PATH” | string | 获取技能图标 | SL:GetMetaValue("SKILL_ICON_PATH", skillID) |
| “SKILL_RECT_ICON_PATH” | string | 获取矩形技能图标 | SL:GetMetaValue("SKILL_RECT_ICON_PATH", skillID) |
| “SKILL_IS_ONOFF_SKILL” | boolean | 是否是开关型技能 | SL:GetMetaValue("SKILL_IS_ONOFF_SKILL", skillID) |
| “SKILL_IS_ON_SKILL” | boolean | 技能是否开启 | SL:GetMetaValue("SKILL_IS_ON_SKILL", skillID) |
| “LEARNED_SKILLS” | table | 获取已学技能 |
param1:是否排除普攻
| param2:是否只获取主动技能 | SL:GetMetaValue("LEARNED_SKILLS", true) |
| “SKILL_IS_ACTIVE” | boolean | 是否是主动技能 | SL:GetMetaValue("SKILL_IS_ACTIVE", skillID) |
| “SKILL_DATA” | table | 获取技能数据 |
| param1: 技能ID | SL:GetMetaValue("SKILL_DATA", skillID) |
| “SKILL_TRAIN_DATA” | table | 获取技能的等级熟练度数据 |
| param1: 技能ID | SL:GetMetaValue("SKILL_TRAIN_DATA", skillID) |
| “SKILL_CONFIG” | table | 获取技能配置 |
| param1: 技能ID | SL:GetMetaValue("SKILL_CONFIG", skillID) |
| “SKILL_KEY” | int | 获取技能快捷键 |
| param1: 技能ID | SL:GetMetaValue("SKILL_KEY", skillID) |
| “SKILL_LEVEL” | int | 获取技能等级 |
| param1: 技能ID | SL:GetMetaValue("SKILL_LEVEL", skillID) |
背包

| 参数名 | 返回值类型 | 说明 | 例子 |
| --- | --- | --- | --- |
| “MAX_BAG” | int | 背包最大格子数量 | SL:GetMetaValue("MAX_BAG") |
| “H_MAX_BAG” | int | 英雄背包最大格子数量 | SL:GetMetaValue("H_MAX_BAG") |
| “N_MAX_BAG” | int | 仓库最大格子数量 | SL:GetMetaValue("N_MAX_BAG") |
| “BAG_PAGE_CUR” | int | 当前选中的背包页签 | SL:GetMetaValue("BAG_PAGE_CUR") |
| “BAG_IS_FULL” | boolean | 背包是否满 |
| param1: boolean 是否弹出提示 | SL:GetMetaValue("BAG_IS_FULL", param1) |
| “BAG_REMAIN_COUNT” | int | 背包剩余格子数 | SL:GetMetaValue("BAG_REMAIN_COUNT") |
| “BAG_USED_COUNT” | int | 背包已使用格子数 | SL:GetMetaValue("BAG_USED_COUNT") |
| “BAG_CHECK_NEED_SPACE” | boolean | 检测物品背包是否有富余格子数存放 |
param1: 物品ID
param2: 物品数量
| param3: 不足时是否需要提示 boolean | SL:GetMetaValue("BAG_CHECK_NEED_SPACE", 4, 11, true) | 支持版本号3.40.3以上 |
内挂设置

| 参数名 | 返回值类型 | 说明 | 例子 |
| --- | --- | --- | --- |
| “SETTING_ENABLED” | int | 设置是否生效 |
param1: 内挂设置index
| 返回值：0 或者 1 | SL:GetMetaValue("SETTING_ENABLED", param1) |
| “SETTING_VALUE” | table | 获取设置的数据 |
| param1: 内挂设置index | SL:GetMetaValue("SETTING_VALUE", param1) |
| “SETTING_CONFIG” | table | 获取设置的配置 |
| param1: 内挂设置ID | SL:GetMetaValue("SETTING_CONFIG", param1) |
| “SETTING_PICK_VALUE” | table | 获取物品拾取设置 |
| param1: 内挂设置index | SL:GetMetaValue("SETTING_PICK_VALUE", param1) |
| “SETTING_PICK_CONFIG” | table | 可以拣的物品配置 |
| param1: 内挂设置index | SL:GetMetaValue("SETTING_PICK_CONFIG", param1) |
| “SETTING_IS_ITEM_PICK_CAN_SET” | table | 物品是否可以设置 | SL:GetMetaValue("SETTING_IS_ITEM_PICK_CAN_SET") |
| “SETTING_PICK_GROUP_VALUE” | table | 拾取组的数据 |
| param1: 内挂设置组ID | SL:GetMetaValue("SETTING_PICK_GROUP_VALUE", param1) |
| “MAPSCALE_PER” | int | 通过值获取地图缩放对应百分比 |
| param1: 地图缩放值 | SL:GetMetaValue("MAPSCALE_PER", param1) |
| “MAPSCALE_VALUE” | int | 通过百分比获取地图缩放值 |
| param1:百分比 | SL:GetMetaValue("MAPSCALE_VALUE", param1) |
ItemTips

| 参数名 | 返回值类型 | 说明 | 例子 |
| --- | --- | --- | --- |
| “EQUIPMAP_BY_STDMODE” | table | 装备Map | SL:GetMetaValue("EQUIPMAP_BY_STDMODE") |
| “EX_SHOWLAST_MAP” | table | 除装备Map 显示持久的stdmode | SL:GetMetaValue("EX_SHOWLAST_MAP") |
| “EQUIP_POS_BY_STDMODE” | int | 通过stdmode获取装备位 |
| param1：装备的stdmode | SL:GetMetaValue("EQUIP_POS_BY_STDMODE", param1) |
| “EQUIP_POSLIST_BY_STDMODE” | table | 通过stdmode获取装备位列表 |
param1：装备的stdmode
| param2: 是否英雄 | SL:GetMetaValue("EQUIP_POSLIST_BY_STDMODE", param1) |
| “TIP_POSLIST_BY_STDMODE” | table | 通过stdmode获取TIPS装备位列表 |
param1：装备的stdmode
| param2: 是否英雄 | SL:GetMetaValue("TIP_POSLIST_BY_STDMODE", param1) | 支持版本号3.40.3以上 |
| “IS_SAMESEX_EQUIP” | boolen | 是否是该玩家性别装备 |
param1：装备数据
| param2: 是否英雄 | SL:GetMetaValue("IS_SAMESEX_EQUIP", param1) |
| “CUSTOM_DESC” | string | cfg_custpro_caption表 |
根据key获取描述
| param1：表中的key | SL:GetMetaValue("CUSTOM_DESC", param1) |
| “CUSTOM_ICON” | table | cfg_custpro_caption表 |
根据key获取自定义图片/特效配置
| param1：表中的key | SL:GetMetaValue("CUSTOM_ICON", param1) |
| “ATTR_CONFIG” | table | cfg_att_score表 |
获取对应属性配置
| param1：表中的key | SL:GetMetaValue("ATTR_CONFIG", param1) |
| “ATTR_CONFIGS” | table | cfg_att_score表 |
| 获取所有属性配置 | SL:GetMetaValue("ATTR_CONFIGS") |
| “SUIT_CONFIG” | string | cfg_suit表 |
获取对应套装id配置
| param1：表中的suitid | SL:GetMetaValue("SUIT_CONFIG", param1) |
| “SUITEX_CONFIG” | string | cfg_suitex表 |
获取对应套装id配置
| param1：表中的suitid | SL:GetMetaValue("SUITEX_CONFIG", param1) |
| “ITEMFROMUI_ENUM” | table | 物品来自UI,返回值如下：data | SL:GetMetaValue("ITEMFROMUI_ENUM") |
data = {
BAG                  = 1,          -- 背包
PALYER_EQUIP         = 2,          -- 玩家身上
QUICK_USE            = 3,          -- 快捷栏
STORAGE              = 4,          -- 仓库
BAG_GOLD             = 5,          -- 背包金币
SELL                 = 6,          -- 摆摊
REQUIRE              = 7,          -- npc商店
TRADE                = 8,          -- 面对面交易
STALL                = 9,
TRADE_GOLD           = 10,         -- 交易
BEST_RINGS           = 11,         -- 极品首饰
AUTO_TRADE           = 12,         -- 摆摊
ITEMBOX              = 13,         -- 自定义UI ITEMBOX
NPC_DO_SOMETHING     = 14,         -- NPC自定义放入框
NEWTYPE              = 15,
HERO_BAG             = 66,         -- 英雄背包
HERO_EQUIP           = 67,         -- 英雄装备
HERO_BEST_RINGS      = 68,         -- 英雄极品首饰
SSR_ITEM_BOX         = 77,         -- ssr 自定义ItemBox
PETS_EQUIP           = 78,         -- 宠物装备
SKILL_WIN            = 79,         -- PC 技能
OTHER                = 99          -- 其他
}

| 参数名 | 返回值类型 | 说明 | 例子 |
| --- | --- | --- | --- |
| “ITEMTYPE_ENUM” | table | 物品类型，返回值如下：data | SL:GetMetaValue("ITEMTYPE_ENUM") |

此分类依据【道具表】和【装备表】中的 StdMode

data = {
DruaAndSomething = 1,       -- 道具表 StdMode 0~3 的道具
SkillBook        = 2,       -- 技能书 道具表 StdMode 4  的道具
Equip            = 3,       -- 装备
Bundle           = 4,       -- 困束  道具表 StdMode 31  的道具
Box              = 5,       -- 盒子  道具表 StdMode 200 的道具
TreasureMap      = 6,       -- StdMode 为 101 的道具
FashionItem      = 7,       -- 时装道具  道具表 StdMode 102 的道具
MonsterCard      = 8,       -- 怪物卡片  道具表 StdMode 103 的道具
SomethingCanUse  = 9,       -- 道具表 StdMode 为 49 的道具
BoxKey           = 10,      -- 箱子钥匙  道具表 StdMode 40 的道具
Collimator       = 11,      -- 准星道具  道具表 StdMode 47 的道具
WishBox          = 12,      -- StdMode 为 96 的道具
NewPet           = 13,      -- 宠物道具 道具表 StdMode 201 的道具
Other            = 99       -- 其他
}

| 参数名 | 返回值类型 | 说明 | 例子 |
| --- | --- | --- | --- |
| “ITEMTYPE” | int | 根据道具数据获取物品类型 | SL:GetMetaValue("ITEMTYPE", itemData) |
| “CUST_ABIL_MAP” | table | 自定义属性ID映射Map | SL:GetMetaValue("CUST_ABIL_MAP") | 支持版本号3.40.5以上 |
充值

| 参数名 | 返回值类型 | 说明 | 例子 | 版本 |
| --- | --- | --- | --- | --- |
| “RECHARGE_PRODUCTS” | table | 充值商品信息列表 | SL:GetMetaValue("RECHARGE_PRODUCTS") | 支持版本号3.40.3以上 |
| “RECHARGE_PRODUCT_BY_ID” | table | 通过商品Id获取商品信息 | SL:GetMetaValue("RECHARGE_PRODUCT_BY_ID", id) | 支持版本号3.40.3以上 |
| “IS_SDK_PAY” | boolean | 是否接入第三方SDK | SL:GetMetaValue("IS_SDK_PAY") | 支持版本号3.40.3以上 |
摆摊

| 参数名 | 返回值类型 | 说明 | 例子 | 版本 |
| --- | --- | --- | --- | --- |
| “ONSELL_DATA_BY_MAKEINDEX” | table | 获取购买摊位的对应物品信息 |
| param1: 物品唯一ID | SL:GetMetaValue("ONSELL_DATA_BY_MAKEINDEX", makeIndex) | 支持版本号3.40.3以上 |
| “MYSELL_DATA_BY_MAKEINDEX” | table | 获取我的摊位的对应物品信息 |
| param1: 物品唯一ID | SL:GetMetaValue("MYSELL_DATA_BY_MAKEINDEX", makeIndex) | 支持版本号3.40.3以上 |
| “SELL_SHOW_NAME” | string | 获取购买摊位名字 | SL:GetMetaValue("SELL_SHOW_NAME", makeIndex) | 支持版本号3.40.3以上 |
| “ONSELL_DATA” | table | 获取购买摊位物品信息 | SL:GetMetaValue("ONSELL_DATA") | 支持版本号3.40.3以上 |
| “MYSELL_DATA” | table | 获取我的摊位物品信息 | SL:GetMetaValue("MYSELL_DATA") | 支持版本号3.40.3以上 |
宝箱

| 参数名 | 返回值类型 | 说明 | 例子 | 版本 |
| --- | --- | --- | --- | --- |
| “HAVE_GOLDBOX_OPENTIME” | boolean | 是否还有重摇/开启次数 | SL:GetMetaValue("HAVE_GOLDBOX_OPENTIME") | 支持版本号3.40.3以上 |
合成

| 参数名 | 返回值类型 | 说明 | 例子 | 版本 |
| --- | --- | --- | --- | --- |
| “COMPOUND_OPEN_ID” | int | 获取合成打开的ID （合成表id） | SL:GetMetaValue("COMPOUND_OPEN_ID") | 支持版本号3.40.3以上 |
| “COMPOUND_CONFIG_BY_INDEX” | table | 通过id获取合成对应配置 |
| param1: 合成表id | SL:GetMetaValue("COMPOUND_CONFIG_BY_INDEX", id) | 支持版本号3.40.3以上 |
| “COMPOUND_PAGE_BY_ID” | int | 通过id获取合成页签组合id [合成表page1 * 1000 + 合成表page2] |
| param1: 合成表id | SL:GetMetaValue("COMPOUND_PAGE_BY_ID", id) | 支持版本号3.40.3以上 |
| “COMPOUND_LIST_DATA” | table | 获取合成数据 | SL:GetMetaValue("COMPOUND_LIST_DATA") | 支持版本号3.40.3以上 |
| “COMPOUND_LIST_DATA_BY_INDEX” | table | 通过id获取合成数据 |
| param1: 合成表page1 * 1000 + 合成表page2 | SL:GetMetaValue("COMPOUND_LIST_DATA_BY_INDEX", id) | 支持版本号3.40.3以上 |
| “COMPOUND_CHECK_LIST_IS_SHOW” | boolean | 检测该合成页签是否显示 |
param1: 合成表page1
| param2: 合成表page1 * 1000 + 合成表page2 | SL:GetMetaValue("COMPOUND_CHECK_LIST_IS_SHOW", page1) | 支持版本号3.40.3以上 |
| “COMPOUND_CHECK_LIST_RED_POINT” | boolean | 检测合成红点 |
param1: 合成表page1
| param2: 合成表page1 * 1000 + 合成表page2 | SL:GetMetaValue("COMPOUND_CHECK_LIST_RED_POINT", page1) | 支持版本号3.40.3以上 |
| “COMPOUND_PAGE_NAME” | string | 获取合成页签名字 |
| param1: 合成表page1 * 1000 + 合成表page2 | SL:GetMetaValue("COMPOUND_PAGE_NAME", page1) | 支持版本号3.40.3以上 |
| “COMPOUND_SHOW_CONDITION” | boolean | 判断合成条件是否显示红点 |
| param1: 条件配置 string | SL:GetMetaValue("COMPOUND_SHOW_CONDITION", conditionStr) | 支持版本号3.40.3以上 |
| “COMPOUND_RED_POINT_BY_ID” | boolean | 获取合成红点状态 |
| param1: 合成表id | SL:GetMetaValue("COMPOUND_RED_POINT_BY_ID", id) | 支持版本号3.40.3以上 |
| “COMPOUND_CHECK_OK” | boolean | 检查是否可以合成 |
param1: 合成配置 table
| param2: 是否提示 boolean | SL:GetMetaValue("COMPOUND_PAGE_NAME", page2) | 支持版本号3.40.3以上 |
新版属性加点 [3.40.4]

| 参数名 | 返回值类型 | 说明 | 例子 | 版本 |
| --- | --- | --- | --- | --- |
| “IS_NEW_BOUNS” | boolean | 是否启用新版属性加点 | SL:GetMetaValue("IS_NEW_BOUNS") | 支持版本号3.40.4以上 |
| “NEW_BOUNS_CONFIG” | table | 获取新版属性加点配置数据 | SL:GetMetaValue("NEW_BOUNS_CONFIG") | 支持版本号3.40.4以上 |
| “NEW_BOUNS_ADD_DATA” | table | 获取新版属性已加点数据 | SL:GetMetaValue("NEW_BOUNS_ADD_DATA") | 支持版本号3.40.4以上 |
求购系统 [3.40.5]
求购菜单配置 等同 拍卖行配置 (cfg_auction_type)

| 参数名 | 返回值类型 | 说明 | 例子 | 版本 |
| --- | --- | --- | --- | --- |
| “PURCHASE_FILTER_LIST” | table | 世界求购菜单列表 | SL:GetMetaValue("PURCHASE_FILTER_LIST") | 支持版本号3.40.5以上 |
| “PURCHASE_MENU_CONFIG_BY_ID” | table | 对应ID 菜单栏配置 | SL:GetMetaValue("PURCHASE_MENU_CONFIG_BY_ID", id) | 支持版本号3.40.5以上 |
| “PURCHASE_ITEM_LIST_BY_TYPE” | table | 分类物品列表 param1: 一级菜单id param2: 二级菜单id | SL:GetMetaValue("PURCHASE_ITEM_LIST_BY_TYPE", 2, 1) | 支持版本号3.40.5以上 |
| “PURCHASE_CURRENCIES” | table | 求购货币列表 | SL:GetMetaValue("PURCHASE_CURRENCIES") | 支持版本号3.40.5以上 |
角色相关

| 参数名 | 返回值类型 | 说明 | 例子 |
| --- | --- | --- | --- |
| “USER_ID” | string | 玩家ID | SL:GetMetaValue("USER_ID") |
| “USER_NAME” | string | 玩家名字 | SL:GetMetaValue("USER_NAME") |
| “JOB” | int | 玩家职业 |
0：战士
1：法师
| 2：道士 | SL:GetMetaValue("JOB") |
| “LEVEL” | int | 玩家等级 | SL:GetMetaValue("LEVEL") |
| “RELEVEL” | int | 玩家转生等级 | SL:GetMetaValue("RELEVEL") |
| “JOB_NAME” | string | 职业名字 | SL:GetMetaValue("JOB_NAME") |
| “SEX” | int | 玩家性别 |
0：男
| 1：女 | SL:GetMetaValue("SEX") |
| “REAL_USER_NAME” | string | 玩家真实姓名 | SL:GetMetaValue("REAL_USER_NAME") |
| “USER_NAME_COLOR” | int | 玩家名字颜色值 | SL:GetMetaValue("USER_NAME_COLOR") |
| “DIR” | int | 人物方向 |
0：上
1：右上
2：右
3：右下
4：下
5：左下
6：左
7：左上
| 0xff：无效位置 | SL:GetMetaValue("DIR") |
| “USER_IS_DIE” | boolean | 角色是否死亡 | SL:GetMetaValue("USER_IS_DIE") |
| “USER_IS_CANREVIVE” | boolean | 角色是否能复活 | SL:GetMetaValue("USER_IS_CANREVIVE") | 支持版本号3.40.3以上 |
| “HP” | int | 当前血量 | SL:GetMetaValue("HP") |
| “MAXHP” | string | 最大血量 | SL:GetMetaValue("MAXHP") |
| “MP” | int | 当前蓝量 | SL:GetMetaValue("MP") |
| “MAXMP” | string | 最大蓝量 | SL:GetMetaValue("MAXMP") |
| “BURST” | int | 暴击几率 | SL:GetMetaValue("BURST") |
| “BURST_DAM” | int | 暴击伤害 | SL:GetMetaValue("BURST_DAM") |
| “IMM_ATT” | int | 物伤减免 | SL:GetMetaValue("IMM_ATT") |
| “IMM_MAG” | int | 魔伤减免 | SL:GetMetaValue("IMM_MAG") |
| “DROP” | int | 怪物爆率 | SL:GetMetaValue("DROP") |
| “LUCK” | int | 幸运 | SL:GetMetaValue("LUCK") |
| “AC” | int | 最小物防 | SL:GetMetaValue("AC") |
| “MAXAC” | int | 最大物防 | SL:GetMetaValue("MAXAC") |
| “MAC” | int | 最小魔防 | SL:GetMetaValue("MAC") |
| “MAXMAC” | int | 最大魔防 | SL:GetMetaValue("MAXMAC") |
| “DC” | int | 最小物理 | SL:GetMetaValue("DC") |
| “MAXDC” | int | 最大物理 | SL:GetMetaValue("MAXDC") |
| “MC” | int | 最小魔法 | SL:GetMetaValue("MC") |
| “MAXMC” | int | 最大魔法 | SL:GetMetaValue("MAXMC") |
| “SC” | int | 最小道术 | SL:GetMetaValue("SC") |
| “MAXSC” | int | 最大道术 | SL:GetMetaValue("MAXSC") |
| “HIT” | int | 准确 | SL:GetMetaValue("HIT") |
| “SPD” | int | 敏捷 | SL:GetMetaValue("SPD") |
| “EXP” | int | 当前经验 | SL:GetMetaValue("EXP") |
| “MAXEXP” | int | 最大经验 | SL:GetMetaValue("MAXEXP") |
| “HITSPD” | int | 攻速 | SL:GetMetaValue("HITSPD") |
| “HW” | int | 腕力 | SL:GetMetaValue("HW") |
| “MAXHW” | int | 最大可穿戴腕力 | SL:GetMetaValue("MAXHW") |
| “BW” | int | 重量 | SL:GetMetaValue("BW") |
| “MAXBW” | int | 玩家最大负重 | SL:GetMetaValue("MAXBW") |
| “WW” | int | 穿戴负重 | SL:GetMetaValue("WW") |
| “MAXWW” | int | 最大穿戴负重 | SL:GetMetaValue("MAXWW") |
| “HUNGER” | int | 体力恢复 | SL:GetMetaValue("HUNGER") |
| “LUCK” | int | 幸运值 | SL:GetMetaValue("LUCK") | 支持版本号3.40.3以上 |
| “DRESS” | string | 获取玩家身上衣服的名字 | SL:GetMetaValue("DRESS") |
| “WEAPON” | string | 获取玩家身上武器的名字 | SL:GetMetaValue("WEAPON") |
| “RIGHTHAND” | string | 获取玩家身上勋章的名字 | SL:GetMetaValue("RIGHTHAND") |
| “HELMET” | string | 获取玩家身上头盔的名字 | SL:GetMetaValue("HELMET") |
| “NECKLACE” | string | 获取玩家身上项链的名字 | SL:GetMetaValue("NECKLACE") |
| “RINGR” | string | 获取玩家身上右戒指的名字 | SL:GetMetaValue("RINGR") |
| “RINGL” | string | 获取玩家身上左戒指的名字 | SL:GetMetaValue("RINGL") |
| “ARMRINGR | string | 获取玩家身上右手镯的名字 | SL:GetMetaValue("ARMRINGR"") |
| “ARMRINGL” | string | 获取玩家身上左手镯的名字 | SL:GetMetaValue("ARMRINGL") |
| “BUJUK” | string | 获取玩家身上护符、玉佩、宝珠的名字 | SL:GetMetaValue("BUJUK") |
| “BELT” | string | 获取玩家身上腰带的名字 | SL:GetMetaValue("BELT") |
| “BOOTS” | string | 获取玩家身上鞋子的名字 | SL:GetMetaValue("BOOTS") |
| “CHARM” | string | 获取玩家身上宝石的名字 | SL:GetMetaValue("CHARM") |
| “EQUIPBYPOS” | string | 获取玩家某一装备位的装备名 | SL:GetMetaValue("EQUIPBYPOS", 1) |
| “EX_ATTR” | string | 脚本变量额外属性 | SL:GetMetaValue("EX_ATTR") |
| “ATT_BY_TYPE” | int | 根据类型id获取属性值 | SL:GetMetaValue("ATT_BY_TYPE", 94) |
| “EQUIP_DATA” | table | 获取玩家某一装备数据 |
| param1: 装备位id 或者 装备名称 param2: 是否多个装备位共享 | SL:GetMetaValue("EQUIP_DATA", 30) |
| “EQUIP_DATA_LIST” | table | 获取玩家对应装备位数据列表 |
| param1: 装备位id | SL:GetMetaValue("EQUIP_DATA_LIST", 30) | 支持版本号3.40.8以上 |
| “ALL_EQUIP_DATAS” | table | 获取玩家所有装备数据 | SL:GetMetaValue("ALL_EQUIP_DATAS") | 支持版本号3.40.9以上 |
| “EMBATTLE” | table | 获取玩家法阵数据 |
| 后端UpdateEquipEffect命令添加 | SL:GetMetaValue("EMBATTLE") | 支持版本号3.40.8以上 |
| “FEATURE” | table | 玩家外观数据 | SL:GetMetaValue("FEATURE") |
| “HAIR” | int | 发型ID | SL:GetMetaValue("HAIR") |
| “EQUIP_POS_DATAS” | table | 获取装备位对应MakeIndex数据 | SL:GetMetaValue("EQUIP_POS_DATAS") |
| “TITLES” | table | 玩家的称号数据 | SL:GetMetaValue("TITLES") |
| “TITLE_DATA_BY_ID” | table | 获取玩家对应ID的称号数据 | SL:GetMetaValue("TITLE_DATA_BY_ID", id) | 支持版本号3.40.3以上 |
| “ACTIVATE_TITLE” | int | 玩家激活的称号id | SL:GetMetaValue("ACTIVATE_TITLE") |
| “INTERNAL_FORCE” | int | 人物内功当前内力值 | SL:GetMetaValue("INTERNAL_FORCE") | 支持版本号3.40.2以上 |
| “INTERNAL_MAXFORCE” | int | 人物内功最大内力值 | SL:GetMetaValue("INTERNAL_MAXFORCE") | 支持版本号3.40.2以上 |
| “INTERNAL_EXP” | int | 人物内功当前经验值 | SL:GetMetaValue("INTERNAL_EXP") | 支持版本号3.40.2以上 |
| “INTERNAL_MAXEXP” | int | 人物内功最大经验值 | SL:GetMetaValue("INTERNAL_MAXEXP") | 支持版本号3.40.2以上 |
| “INTERNAL_LEVEL” | int | 人物内功等级 | SL:GetMetaValue("INTERNAL_LEVEL") | 支持版本号3.40.2以上 |
| “INTERNAL_DZ_CURVALUE” | int | 人物内功当前斗转星移值 | SL:GetMetaValue("INTERNAL_DZ_CURVALUE") | 支持版本号3.40.2以上 |
| “INTERNAL_DZ_MAXVALUE” | int | 人物内功最大斗转星移值 | SL:GetMetaValue("INTERNAL_DZ_MAXVALUE") | 支持版本号3.40.2以上 |
| “INTERNAL_SKILLS” | table | 获取人物拥有内功技能列表 | SL:GetMetaValue("INTERNAL_SKILLS") | 支持版本号3.40.2以上 |
| “INTERNAL_SKILL_DATA” | table | 获取人物内功技能数据 |
param1: 技能ID
| param2: 技能类型 | SL:GetMetaValue("INTERNAL_SKILL_DATA", skillID, skillType) | 支持版本号3.40.2以上 |
| “INTERNAL_SKILL_TRAIN_DATA” | table | 获取人物内功技能等级熟练度数据 |
param1: 技能ID
| param2: 技能类型 | SL:GetMetaValue("INTERNAL_SKILL_TRAIN_DATA", skillID, skillType) | 支持版本号3.40.2以上 |
| “INTERNAL_SKILL_ONOFF” | int | 获取人物内功技能开关 |
param1: 技能ID
| param2: 技能类型 | SL:GetMetaValue("INTERNAL_SKILL_ONOFF", skillID, skillType) | 支持版本号3.40.2以上 |
| “INTERNAL_SKILL_RECT_ICON_PATH” | string | 获取人物内功技能矩形图标路径 |
param1: 技能ID
| param2: 技能类型 | SL:GetMetaValue("INTERNAL_SKILL_RECT_ICON_PATH", skillID, skillType) | 支持版本号3.40.2以上 |
| “INTERNAL_SKILL_NAME” | table | 获取人物内功技能名字 |
param1: 技能ID
| param2: 技能类型 | SL:GetMetaValue("INTERNAL_SKILL_NAME", skillID, skillType) | 支持版本号3.40.2以上 |
| “INTERNAL_SKILL_DESC” | table | 获取人物内功技能描述 |
param1: 技能ID
| param2: 技能类型 | SL:GetMetaValue("INTERNAL_SKILL_DESC", skillID, skillType) | 支持版本号3.40.2以上 |
| “MERIDIAN_DESC” | table | 获取人物内功经络的穴位描述 | SL:GetMetaValue("MERIDIAN_DESC") | 支持版本号3.40.2以上 |
| “MERIDIAN_AUCPOINT_STATE” | table | 获取人物内功对应经络的穴位是否激活列表 |
| param1: 经络ID | SL:GetMetaValue("MERIDIAN_AUCPOINT_STATE", 2) | 支持版本号3.40.2以上 |
| “MERIDIAN_OPEN_LIST” | table | 获取人物内功经络的开关列表 | SL:GetMetaValue("MERIDIAN_OPEN_LIST") | 支持版本号3.40.2以上 |
| “MERIDIAN_LV” | int | 获取人物内功对应经络等级 | SL:GetMetaValue("MERIDIAN_LV", 2) | 支持版本号3.40.2以上 |
| “HAVE_COMBO_SKILLS” | table | 获取人物所有拥有的连击技能 | SL:GetMetaValue("HAVE_COMBO_SKILLS") | 支持版本号3.40.2以上 |
| “COMBO_SKILL_DATA” | table | 获取人物对应连击技能 |
| param1: 技能ID | SL:GetMetaValue("COMBO_SKILL_DATA", 104) | 支持版本号3.40.2以上 |
| “COMBO_SKILL_TRAIN_DATA” | table | 获取人物连击技能等级熟练度数据 |
| param1: 技能ID | SL:GetMetaValue("COMBO_SKILL_TRAIN_DATA", skillID) | 支持版本号3.40.2以上 |
| “SET_COMBO_SKILLS” | table | 获取人物设置为连击的数据 | SL:GetMetaValue("SET_COMBO_SKILLS") | 支持版本号3.40.2以上 |
| “OPEN_COMBO_NUM” | int | 人物开启的连击个数 | SL:GetMetaValue("OPEN_COMBO_NUM") | 支持版本号3.40.2以上 |
| “IS_LEARNED_INTERNAL” | boolean | 人物是否学习内功 | SL:GetMetaValue("IS_LEARNED_INTERNAL") | 支持版本号3.40.2以上 |
| “EXTRA_COMBO_BJRATE” | int | 获取对应连击格子额外加暴击几率 |
| param1: 连击格子index(1-4) | SL:GetMetaValue("EXTRA_COMBO_BJRATE", 1) | 支持版本号3.40.3以上 |
| “RUN_STEP” | int | 跑步移动格子数 | SL:GetMetaValue("RUN_STEP") | 支持版本号3.40.3以上 |
| “CAN_RUN_ABLE” | boolean | 能否跑 | SL:GetMetaValue("CAN_RUN_ABLE") | 支持版本号3.40.3以上 |
| “LOOK_USER_ID” | string | 当前查看他人角色ID | SL:GetMetaValue("LOOK_USER_ID") |
| “LOOK_USER_NAME” | string | 当前查看他人角色名字 | SL:GetMetaValue("LOOK_USER_NAME") |
| “LOOK_USER_NAME_COLOR” | int | 当前查看他人角色名字颜色ID | SL:GetMetaValue("LOOK_USER_NAME_COLOR") |
| “PLAYER_INITED” | boolean | 玩家属性初始化完成 | SL:GetMetaValue("PLAYER_INITED") | 支持版本号3.40.7以上 |
其他角色相关

| 参数名 | 返回值类型 | 说明 |
| --- | --- | --- |
| L.M.JOB | int | 当前查看玩家职业 |
| L.M.HAIR | int | 当前查看玩家发型 |
| L.M.LEVEL | int | 当前查看玩家等级 |
| L.M.SEX | int | 当前查看玩家性别 |
| L.M.PLAYER_DATA | table | 当前查看玩家数据 |
| L.M.EQUIP_DATA | table | 当前查看玩家某个装备位数据 param1: 装备位id 或者 装备名称 |
| L.M.EQUIP_DATA_LIST | table | 当前查看玩家某个装备位数据列表 param1: 装备位id | 支持版本号3.40.8以上 |
| L.M.EQUIP_POS_DATAS | table | 当前查看玩家的所有装备位数据 |
| L.M.GUILD_INFO | table | 当前查看玩家的行会信息 |
| L.M.TITLES | table | 当前查看玩家的称号数据 |
| L.M.ACTIVATE_TITLE | int | 当前查看玩家激活的称号id |
| L.M.EMBATTLE | table | 当前查看玩家法阵数据 | 支持版本号3.40.8以上 |
英雄相关

| 参数名 | 返回值类型 | 说明 |
| --- | --- | --- |
| H.USERNAME | string | 英雄名字 |
| H.LEVEL | int | 英雄等级 |
| H.RELEVEL | int | 转生等级 |
| H.EXP | int | 当前经验 |
| H.MAXEXP | int | 最大经验 |
| H.JOBNAME | string | 职业名称 |
| H.JOB | int | 职业 |
| H.SEX | int | 性别 |
| H.HAIR | int | 发型ID |
| H.MAXHP | int | 最大生命值 |
| H.MAXMP | int | 最大魔法值 |
| H.HP | int | 当前生命值 |
| H.MP | int | 当前魔法值 |
| H.HPPercent | int | 当前血量百分比 |
| H.MPPercent | int | 当前蓝量百分比 |
| H.EXPPercent | int | 当前经验百分比 |
| H.MIN_ATK | int | 攻击下限 |
| H.MAX_ATK | int | 攻击上限 |
| H.MIN_MAT | int | 魔攻下限 |
| H.MAX_MAT | int | 魔攻上限 |
| H.MIN_DAO | int | 道术下限 |
| H.MAX_DAO | int | 道术上限 |
| H.MIN_DEF | int | 物防下限 |
| H.MAX_DEF | int | 物防上限 |
| H.MIN_MDF | int | 魔防下限 |
| H.MAX_MDF | int | 魔防上限 |
| H.HIT | int | 命中 |
| H.HITSPD | int | 攻击速度 |
| H.BURST | int | 暴击几率 |
| H.BURST_DAM | int | 暴击伤害 |
| H.IMM_ATT | int | 物伤减免 |
| H.IMM_MAG | int | 魔伤减免 |
| H.IGN_DEF | int | 物理穿透 |
| H.SUCK_HP | int | 吸血 |
| H.LUCK | int | 幸运 |
| H.DROP | int | 怪物爆率 |
| H.BW | int | 当前重量 |
| H.MAXBW | int | 英雄最大负重 |
| H.WW | int | 穿戴负重 |
| H.MAXWW | int | 最大穿戴负重 |
| H.HW | int | 腕力 |
| H.MAXHW | int | 当前最大可穿戴腕力 |
| H.ANGER | int | 当前愤怒 |
| H.MAXANGER | int | 最大愤怒 |
| H.SHAN | boolen | 英雄怒气值是否满 |
| H.SPEED | int | 单次怒气增加值 |
| H.DELAYT | int | 怒气增加间隔时间 |
| H.EQUIP_DATA | table | 获取英雄某一装备数据 |
param1: 装备位id 或者 装备名称 param2: 是否多个装备位共享
| H.EQUIP_DATA_LIST | table | 获取英雄对应装备位数据列表 |
| param1: 装备位id | SL:GetMetaValue("H.EQUIP_DATA_LIST", 12) | 支持版本号3.40.8以上 |
| H.ALL_EQUIP_DATAS | table | 获取英雄所有装备数据 | SL:GetMetaValue("H.ALL_EQUIP_DATAS") | 支持版本号3.40.9以上 |
| H.EMBATTLE | table | 获取英雄法阵数据 |
| 后端UpdateEquipEffect命令添加 | SL:GetMetaValue("H.EMBATTLE") | 支持版本号3.40.8以上 |
| H.EQUIP_POS_DATAS | table | 获取装备位对应MakeIndex数据 |
| H.TITLES | table | 英雄的称号数据 |
| H.ACTIVATE_TITLE | int | 英雄激活的称号id |
| H.SKILL_TRAIN_DATA | table | 获取技能的等级熟练度数据 |
param1: 技能ID
| H.SKILL_DATA | table | 获取技能数据 param1: 技能ID |
| H.SKILL_NAME | string | 获取技能名 param1: 技能ID |
| H.SKILL_KEY | int | 获取技能快捷键 param1: 技能ID |
| H.LEARNED_SKILLS | table | 获取已有技能数据 |
param1:是否排除普攻
param2:是否只获取主动技能
| “H.INTERNAL_FORCE” | int | 英雄内功当前内力值 | SL:GetMetaValue("INTERNAL_FORCE") | 支持版本号3.40.2以上 |
| “H.INTERNAL_MAXFORCE” | int | 英雄内功最大内力值 | SL:GetMetaValue("INTERNAL_MAXFORCE") | 支持版本号3.40.2以上 |
| “H.INTERNAL_EXP” | int | 英雄内功当前经验值 | SL:GetMetaValue("INTERNAL_EXP") | 支持版本号3.40.2以上 |
| “H.INTERNAL_MAXEXP” | int | 英雄内功最大经验值 | SL:GetMetaValue("INTERNAL_MAXEXP") | 支持版本号3.40.2以上 |
| “H.INTERNAL_LEVEL” | int | 英雄内功等级 | SL:GetMetaValue("INTERNAL_LEVEL") | 支持版本号3.40.2以上 |
| “H.INTERNAL_DZ_CURVALUE” | int | 英雄内功当前斗转星移值 | SL:GetMetaValue("INTERNAL_DZ_CURVALUE") | 支持版本号3.40.2以上 |
| “H.INTERNAL_DZ_MAXVALUE” | int | 英雄内功最大斗转星移值 | SL:GetMetaValue("INTERNAL_DZ_MAXVALUE") | 支持版本号3.40.2以上 |
| “H.INTERNAL_SKILLS” | table | 获取英雄拥有内功技能列表 | SL:GetMetaValue("INTERNAL_SKILLS") | 支持版本号3.40.2以上 |
| “H.INTERNAL_SKILL_DATA” | table | 获取英雄内功技能数据 |
param1: 技能ID
| param2: 技能类型 | SL:GetMetaValue("INTERNAL_SKILL_DATA", skillID, skillType) | 支持版本号3.40.2以上 |
| “H.INTERNAL_SKILL_TRAIN_DATA” | table | 获取英雄内功技能等级熟练度数据 |
param1: 技能ID
| param2: 技能类型 | SL:GetMetaValue("INTERNAL_SKILL_TRAIN_DATA", skillID, skillType) | 支持版本号3.40.2以上 |
| “H.INTERNAL_SKILL_ONOFF” | int | 获取英雄内功技能开关 |
param1: 技能ID
| param2: 技能类型 | SL:GetMetaValue("INTERNAL_SKILL_ONOFF", skillID, skillType) | 支持版本号3.40.2以上 |
| “H.INTERNAL_SKILL_RECT_ICON_PATH” | string | 获取英雄内功技能矩形图标路径 |
param1: 技能ID
| param2: 技能类型 | SL:GetMetaValue("INTERNAL_SKILL_RECT_ICON_PATH", skillID, skillType) | 支持版本号3.40.2以上 |
| “H.INTERNAL_SKILL_NAME” | table | 获取英雄内功技能名字 |
param1: 技能ID
| param2: 技能类型 | SL:GetMetaValue("INTERNAL_SKILL_NAME", skillID, skillType) | 支持版本号3.40.2以上 |
| “H.INTERNAL_SKILL_DESC” | table | 获取英雄内功技能描述 |
param1: 技能ID
| param2: 技能类型 | SL:GetMetaValue("INTERNAL_SKILL_DESC", skillID, skillType) | 支持版本号3.40.2以上 |
| “H.MERIDIAN_AUCPOINT_STATE” | table | 获取英雄内功对应经络的穴位是否激活列表 |
| param1: 经络ID | SL:GetMetaValue("MERIDIAN_AUCPOINT_STATE", 2) | 支持版本号3.40.2以上 |
| “H.MERIDIAN_OPEN_LIST” | table | 获取英雄内功经络的开关列表 | SL:GetMetaValue("MERIDIAN_OPEN_LIST") | 支持版本号3.40.2以上 |
| “H.MERIDIAN_LV” | int | 获取英雄内功对应经络等级 | SL:GetMetaValue("MERIDIAN_LV", 2) | 支持版本号3.40.2以上 |
| “H.HAVE_COMBO_SKILLS” | table | 获取英雄所有拥有的连击技能 | SL:GetMetaValue("H.HAVE_COMBO_SKILLS") | 支持版本号3.40.2以上 |
| “H.COMBO_SKILL_DATA” | table | 获取英雄对应连击技能 |
| param1: 技能ID | SL:GetMetaValue("H.COMBO_SKILL_DATA", 104) | 支持版本号3.40.2以上 |
| “H.COMBO_SKILL_TRAIN_DATA” | table | 获取英雄连击技能等级熟练度数据 |
| param1: 技能ID | SL:GetMetaValue("H.COMBO_SKILL_TRAIN_DATA", skillID) | 支持版本号3.40.2以上 |
| “H.SET_COMBO_SKILLS” | table | 获取英雄设置为连击的数据 | SL:GetMetaValue("H.SET_COMBO_SKILLS") | 支持版本号3.40.2以上 |
| “H.OPEN_COMBO_NUM” | int | 英雄开启的连击个数 | SL:GetMetaValue("H.OPEN_COMBO_NUM") | 支持版本号3.40.2以上 |
| “H.IS_LEARNED_INTERNAL” | boolean | 英雄是否学习内功 | SL:GetMetaValue("H.IS_LEARNED_INTERNAL") | 支持版本号3.40.2以上 |
| “H.SKILL_ICON_PATH” | string | 获取英雄技能图标 | SL:GetMetaValue("H.SKILL_ICON_PATH", skillID) | 支持版本号3.40.5以上 |
| “H.SKILL_RECT_ICON_PATH” | string | 获取英雄矩形技能图标 | SL:GetMetaValue("H.SKILL_RECT_ICON_PATH", skillID) | 支持版本号3.40.5以上 |
| “HERO_INITED” | boolean | 英雄属性初始化完成 | SL:GetMetaValue("HERO_INITED") | 支持版本号3.40.7以上 |
| “H.LOCK_TARGET_ID” | int | 英雄锁定ActorID | SL:GetMetaValue("H.LOCK_TARGET_ID") | 支持版本号3.40.7以上 |
交易行角色

| 参数名 | 返回值类型 | 说明 |
| --- | --- | --- |
| T.M.USERNAME | string | 玩家名字 |
| T.M.LEVEL | int | 玩家等级 |
| T.M.RELEVEL | int | 转生等级 |
| T.M.EXP | int | 当前经验 |
| T.M.MAXEXP | int | 最大经验 |
| T.M.JOB | int | 职业 |
| T.M.JOBNAME | string | 职业名 |
| T.M.SEX | int | 性别 |
| T.M.HAIR | int | 发型ID |
| T.M.MAXHP | int | 最大生命值 |
| T.M.MAXMP | int | 最大魔法值 |
| T.M.HP | int | 当前生命值 |
| T.M.MP | int | 当前魔法值 |
| T.M.MIN_ATK | int | 攻击下限 |
| T.M.MAX_ATK | int | 攻击上限 |
| T.M.MIN_MAT | int | 魔攻下限 |
| T.M.MAX_MAT | int | 魔攻上限 |
| T.M.MIN_DAO | int | 道术下限 |
| T.M.MAX_DAO | int | 道术上限 |
| T.M.MIN_DEF | int | 物防下限 |
| T.M.MAX_DEF | int | 物防上限 |
| T.M.MIN_MDF | int | 魔防下限 |
| T.M.MAX_MDF | int | 魔防上限 |
| T.M.HIT | int | 命中 |
| T.M.HITSPD | int | 攻击速度 |
| T.M.BURST | int | 暴击几率 |
| T.M.BURST_DAM | int | 暴击伤害 |
| T.M.IMM_ATT | int | 物伤减免 |
| T.M.IMM_MAG | int | 魔伤减免 |
| T.M.SUCK_HP | int | 吸血 |
| T.M.LUCK | int | 幸运 |
| T.M.DROP | int | 怪物爆率 |
| T.M.BW | int | 当前重量 |
| T.M.MAXBW | int | 玩家最大负重 |
| T.M.WW | int | 穿戴负重 |
| T.M.MAXWW | int | 最大穿戴负重 |
| T.M.HW | int | 腕力 |
| T.M.MAXHW | int | 当前最大可穿戴腕力 |
| T.M.USERNAME_COLOR | int | 玩家名字颜色值 |
| T.M.TITLES | table | 玩家的称号数据 |
| T.M.ACTIVATE_TITLE | int | 当前查看玩家激活的称号id |
| T.M.SKILL_TRAIN_DATA | table | 获取技能的等级熟练度数据 |
param1: 技能ID
| T.M.SKILL_DATA | table | 获取技能数据 param1: 技能ID |
| T.M.LEARNED_SKILLS | table | 获取已有技能数据 |
param1:是否排除普攻
param2:是否只获取主动技能
| T.M.ATT_BY_TYPE | int | 根据类型ID获取属性值 |
param1: 类型ID
| T.M.EQUIP_POS_DATAS | table | 当前查看玩家的所有装备位数据 |
| T.M.GUILD_INFO | table | 当前查看玩家的行会信息 |
| T.M.EQUIP_DATA | table | 获取当前查看玩家对应装备位的装备数据 |
| T.M.EQUIP_DATA_LIST | table | 获取当前查看玩家对应装备位的装备数据列表 | 支持版本号3.40.8以上 |
| T.M.EQUIP_DATA_BY_MAKEINDEX | table | 通过MakeIndex获取查看交易行他人装备数据 | 支持版本号3.40.8以上 |
交易行英雄

| 参数名 | 返回值类型 | 说明 |
| --- | --- | --- |
| T.H.USERNAME | string | 英雄名字 |
| T.H.LEVEL | int | 英雄等级 |
| T.H.RELEVEL | int | 转生等级 |
| T.H.EXP | int | 当前经验 |
| T.H.MAXEXP | int | 最大经验 |
| T.H.JOB | int | 职业 |
| T.H.JOBNAME | string | 职业名 |
| T.H.SEX | int | 性别 |
| T.H.HAIR | int | 发型ID |
| T.H.MAXHP | int | 最大生命值 |
| T.H.MAXMP | int | 最大魔法值 |
| T.H.HP | int | 当前生命值 |
| T.H.MP | int | 当前魔法值 |
| T.H.MIN_ATK | int | 攻击下限 |
| T.H.MAX_ATK | int | 攻击上限 |
| T.H.MIN_MAT | int | 魔攻下限 |
| T.H.MAX_MAT | int | 魔攻上限 |
| T.H.MIN_DAO | int | 道术下限 |
| T.H.MAX_DAO | int | 道术上限 |
| T.H.MIN_DEF | int | 物防下限 |
| T.H.MAX_DEF | int | 物防上限 |
| T.H.MIN_MDF | int | 魔防下限 |
| T.H.MAX_MDF | int | 魔防上限 |
| T.H.HIT | int | 命中 |
| T.H.HITSPD | int | 攻击速度 |
| T.H.BURST | int | 暴击几率 |
| T.H.BURST_DAM | int | 暴击伤害 |
| T.H.IMM_ATT | int | 物伤减免 |
| T.H.IMM_MAG | int | 魔伤减免 |
| T.H.SUCK_HP | int | 吸血 |
| T.H.LUCK | int | 幸运 |
| T.H.DROP | int | 怪物爆率 |
| T.H.BW | int | 当前重量 |
| T.H.MAXBW | int | 英雄最大负重 |
| T.H.WW | int | 穿戴负重 |
| T.H.MAXWW | int | 最大穿戴负重 |
| T.H.HW | int | 腕力 |
| T.H.MAXHW | int | 当前最大可穿戴腕力 |
| T.H.TITLES | table | 英雄的称号数据 |
| T.H.ACTIVATE_TITLE | int | 当前查看英雄激活的称号id |
| T.H.SKILL_TRAIN_DATA | table | 获取技能的等级熟练度数据 |
param1: 技能ID
| T.H.SKILL_DATA | table | 获取技能数据 param1: 技能ID |
| T.H.LEARNED_SKILLS | table | 获取已有技能数据 |
param1:是否排除普攻
param2:是否只获取主动技能
| T.H.ATT_BY_TYPE | int | 根据类型ID获取属性值 |
param1: 类型ID
| T.H.EQUIP_POS_DATAS | table | 当前查看英雄的所有装备位数据 |
| T.H.EQUIP_DATA | table | 获取当前查看英雄对应装备位的装备数据 |
| T.H.EQUIP_DATA_LIST | table | 获取当前查看英雄对应装备位的装备数据列表 | 支持版本号3.40.8以上 |
| T.H.EQUIP_DATA_BY_MAKEINDEX | table | 通过MakeIndex获取查看交易行他人英雄装备数据 | 支持版本号3.40.8以上 |
打印函数
日志打印
SL:release_print(...)
DEBUG下日志打印
SL:Print(...)
SL:PrintEx(...)
SL:PrintTraceback()
SL:dump(data, desciption, nesting)
| 字段 | 类型 | 注释 |
| data | table | 需要打印的表 |
| desciption | string | 打印表描述 |
| nesting | int | 需要打印的深度 |
JSON
特殊：json过程中已下违禁词不可用
违禁词：lib function then end _G return index set %( %) _
json字符串解密
SL:JsonDecode(jsonStr, isfilter)
| 字段 | 类型 | 注释 |
| jsonStr | string | json字符串 |
| isfilter | boolean | 是否过滤违禁词 默认为true |
返回值： json table
代码示例
-- [[{"index":1, "value":2}]] --> {index = 1, value = 2}

local jsonStr = [[{"index":1, "value":2}]]
local jsonData = SL:JsonDecode(jsonStr)

json字符串加密
SL:JsonEncode(jsonData, isfilter)
| 字段 | 类型 | 注释 |
| jsonData | table | json表 |
| isfilter | boolean | 是否过滤违禁词 默认为true |
返回值： json string
代码示例
-- {index = 1, value = 2} --> [[{"index":1, "value":2}]

local tab = {"1","2"}
local jsonStr = SL:JsonEncode(tab)
SL:Print(jsonStr)

常用函数
颜色转换函数

SL:ConvertColorFromHexString(hexStr)

从16进制字符转为{r, g, b}

返回值： table

示例

local color = SL:ConvertColorFromHexString("#FFFFFF")
SL:dump(color)

文件路径是否存在

SL:IsFileExist(path)

path ：文件路径

返回值 ：true / false

示例

if SL:IsFileExist("E:/1.png") then
SL:Print("文件存在")
else
SL:Print("文件不存在")
end

深拷贝
SL:CopyData(data)
字符串分割

SL:Split(str, delimiter)

按分隔符去拆分一串字符

返回值 ： table

示例

local spt = SL:Split("11#22#33", "|")
SL:dump(spt)

文本提示

SL:ShowSystemTips(str)

str : string 提示文本

哈希表转成按数组

SL:HashToSortArray(hashTab, sortFunc)

将hashTab转换成有序table，并可以按sortFunc排序，sortFunc可选参数

示例

local cfg = {["测试表1"] = {"表1", 1},["测试表2"] = {"表2", 2},["测试表3"] = {"表3", 3},["测试表4"] = {"表4", 4},["测试表5"] = {"表5", 5}}
local function sort_cfg(a, b)
return a[1] < b[1]
end
local new_cfg = SL:HashToSortArray(cfg, sort_cfg)
SL:dump(new_cfg, "new_cfg")

显示提示文本框
SL:SHOW_DESCTIP(str, width, pos, anchorPoint)
| 字段 | 必选 | 类型 | 注释 |
| str | 是 | string | 显示文本 |
| width | 否 | int | 显示宽度, 默认: 1136 |
| pos | 否 | table | 坐标, 默认: {x = 0, y = 0} |
| anchorPoint | 否 | table | 锚点, 默认: {x = 0, y = 1} |
加载文件
SL:Require(file, reload)
| 字段 | 必选 | 类型 | 注释 |
| file | 是 | string | 文件名 |
| reload | 否 | boolean | 是否重新加载文件，填true时，会先释放文件再加载 |

SL:RequireFile(file)

DEBUG下默认重新加载文件

| 字段 | 必选 | 类型 | 注释 |
| file | 是 | string | 文件名 |
拆解文件 [3.40.4版本]

SL:LoadTxtFile(path, delimiter, callBack)

以指定分隔符拆解一个文件

| 字段 | 必选 | 类型 | 注释 |
| path | 是 | string | 文件路径 |
| delimiter | 否 | string | 指定分隔符 |
| callback | 是 | function | 拆解回调方法 传入拆分后table参数 |

示例

local function callback(data)
SL:PrintTable(data, "LINE======")
end
SL:LoadTxtFile("data_config/msg_decoder_config.txt", "#", callback)

数字转换成万、亿单位
SL:GetSimpleNumber(num, places)
| 字段 | 必选 | 类型 | 注释 |
| num | 是 | int | 数值 |
| places | 否 | int | 显示小数点后几位数 [3.40.3版本] |
将数字 num 转换成 xx万、xx亿
血量单位显示

SL:HPUnit(hp, pointBit)

将血量数值转换有单位显示 过十亿(单位：E) 10w-99999w(单位：W）

| 字段 | 必选 | 类型 | 注释 |
| hp | 是 | int | 血量数值 |
| pointBit | 否 | int | 显示小数点后几位, 默认保留后两位 |
中文转换成竖着显示
SL:ChineseToVertical(str)
阿拉伯数字转中文大写
SL:NumberToChinese(num)
获取字符串的byte长度
SL:GetUTF8ByteLen(str)
时间格式化成字符串显示

SL:TimeFormatToStr(time)

将时间 time 大于 1 天时转换成 xx天xx时xx分， 否则 xx:xx:xx

SL:SecondToHMS(sec, isToStr, isSimple) [3.40.2版本]

秒转时分秒

| 字段 | 必选 | 类型 | 注释 |
| sec | 是 | int | 秒数 |
| isToStr | 否 | boolean | 是否转成字符串输出, 空或false则返回table |
{d = 天数, h = 小时, m = 分钟, s = 秒}
| isSimple | 否 | boolean | 是否简化字符串[基于isToStr 为 true] |
返回字符串格式 : xx天xx时xx分xx秒
阿拉伯数字转中文大写
SL:NumberToChinese(num)
数字转化为千分位字符串
SL:GetThousandSepString(num)
返回字符串格式 : 例: 10,000,000
lua table转成config配置表
SL:SaveTableToConfig(tab, name, destPath, sortFunc)
| 字段 | 必选 | 类型 | 注释 |
| tab | 是 | table | 需要转换的table |
| name | 是 | string | 转出文件名 |
| destPath | 否 | string | 文件保存的路径, 默认目录：dev/scripts/game_config/ |
| sortFunc | 否 | function | 外层排序函数 |
十六进制转十进制
SL:HexToInt(hexStr)
MD5加密
SL:GetStrMD5(str)
UTF8转GBK编码[3.40.8版本]
SL:UTF8ToGBK(str)
GBK转UTF8编码 [3.40.8版本]
SL:GBKToUTF8(str)
计算两坐标间的平方距离 [3.40.3版本]
SL:GetPointDistanceSQ(pt1, pt2)
| 字段 | 必选 | 类型 | 注释 |
| pt1 | 是 | table | 起始坐标 GUI:p(x, y) 或 |
{x = x, y = y}
| pt2 | 是 | table | 结束坐标 GUI:p(x, y) 或 |
{x = x, y = y}
计算两坐标间的距离 [3.40.3版本]
SL:GetPointDistance(pt1, pt2)
| 字段 | 必选 | 类型 | 注释 |
| pt1 | 是 | table | 起始坐标 GUI:p(x, y) 或 |
{x = x, y = y}
| pt2 | 是 | table | 结束坐标 GUI:p(x, y) 或 |
{x = x, y = y}
计算向量长度 [3.40.3版本]
SL:GetPointLength(pt)
| 字段 | 必选 | 类型 | 注释 |
| pt | 是 | table | GUI:p(x, y) 或 |
{x = x, y = y}
计算向量长度平方 [3.40.3版本]
SL:GetPointLengthSQ(pt)
| 字段 | 必选 | 类型 | 注释 |
| pt | 是 | table | GUI:p(x, y) 或 |
{x = x, y = y}
计算两点中心点坐标 [3.40.3版本]
SL:GetMidPoint(pt1, pt2)
| 字段 | 必选 | 类型 | 注释 |
| pt1 | 是 | table | 坐标 GUI:p(x, y) 或 |
{x = x, y = y}
| pt2 | 是 | table | 坐标 GUI:p(x, y) 或 |
{x = x, y = y}
计算两点相加坐标 [3.40.3版本]
SL:GetAddPoint(pt1, pt2)
| 字段 | 必选 | 类型 | 注释 |
| pt1 | 是 | table | 坐标 GUI:p(x, y) 或 |
{x = x, y = y}
| pt2 | 是 | table | 坐标 GUI:p(x, y) 或 |
{x = x, y = y}
计算两点相减坐标 [3.40.3版本]
SL:GetSubPoint(pt1, pt2)
pt1坐标 减 pt2坐标
| 字段 | 必选 | 类型 | 注释 |
| pt1 | 是 | table | 坐标 GUI:p(x, y) 或 |
{x = x, y = y}
| pt2 | 是 | table | 坐标 GUI:p(x, y) 或 |
{x = x, y = y}
标准向量化坐标 [3.40.3版本]
SL:GetNormalizePoint(pt)
| 字段 | 必选 | 类型 | 注释 |
| pt | 是 | table | 坐标 GUI:p(x, y) 或 |
{x = x, y = y}
计算两向量夹角弧度值 [3.40.3版本]
SL:GetPointAngle(pt1, pt2)
| 字段 | 必选 | 类型 | 注释 |
| pt1 | 是 | table | 坐标 GUI:p(x, y) 或 |
{x = x, y = y}
| pt2 | 是 | table | 坐标 GUI:p(x, y) 或 |
{x = x, y = y}
计算两向量夹角角度值 [3.40.3版本]
SL:GetPointRotate(pt1, pt2)
| 字段 | 必选 | 类型 | 注释 |
| pt1 | 是 | table | 坐标 GUI:p(x, y) 或 |
{x = x, y = y}
| pt2 | 是 | table | 坐标 GUI:p(x, y) 或 |
{x = x, y = y}
计算自身弧度值 [3.40.3版本]
SL:GetPointAngleSelf(pt)
| 字段 | 必选 | 类型 | 注释 |
| pt | 是 | table | 坐标 GUI:p(x, y) 或 |
{x = x, y = y}
计算自身角度值 [3.40.3版本]
SL:GetPointRotateSelf(pt)
| 字段 | 必选 | 类型 | 注释 |
| pt | 是 | table | 坐标 GUI:p(x, y) 或 |
{x = x, y = y}
-- 获取坐标 pt1 到 pt2 的角度值
local pt1 = GUI:p(100, 100)
local pt2 = GUI:p(100, 200)
local p = SL:GetSubPoint(pt2, pt1)
local rotate = SL:GetPointRotateSelf(p)
SL:Print(rotate)

-- 两向量夹角 角度值
local tRotate = SL:GetPointRotate(pt1, pt2)
SL:Print(tRotate)

获取高16位值 [3.40.4版本]
SL:GetH16Bit(value)
获取低16位值 [3.40.4版本]
SL:GetL16Bit(value)
跳转到某个超链

SL:JumpTo(id)

id : 对应界面的跳转id
跳转id参考如下:

Equip               = 1,            -- 角色-装备
State               = 2,            -- 角色-状态
Attri               = 3,            -- 角色-属性
Skill               = 4,            -- 角色-技能
Title               = 5,            -- 角色-装备
BestRing            = 6,            -- 角色-首饰盒
Bag                 = 7,            -- 背包
Stall               = 8,            -- 摆摊
StoreHot            = 9,            -- 商城-热销
StoreBeauty         = 10,           -- 商城-装饰
StoreEngine         = 11,           -- 商城-功能
StoreFestival       = 12,           -- 商城-节日
GuildMain           = 13,           -- 行会-主界面
GuildMember         = 14,           -- 行会成员列表
GuildList           = 15,           -- 行会列表
Mail                = 16,           -- 邮件
Team                = 17,           -- 组队
NearPlayer          = 18,           -- 附近玩家

Setting             = 23,           -- 设置
MiniMap             = 24,           -- 小地图
SkillSetting        = 25,           -- 技能设置
StoreRecharge       = 26,           -- 充值
Auction             = 27,           -- 拍卖行
Friend              = 28,           -- 好友
ExitToRole          = 29,           -- 小退
GuildCreate         = 30,           -- 行会创建
Guild               = 31,           -- 智能行会界面
Rank                = 32,           -- 排行榜
Trade               = 33,           -- 面对面交易 请求
ForceExitToRole     = 34,           -- 强制小退
TradingBank         = 35,           -- 交易行
GuideEnter          = 36,           -- 引导进入
SuperEquip          = 37,           -- 角色-神装
HeroEquip           = 41,           -- 英雄-装备
HeroState           = 42,           -- 英雄-状态
HeroAttri           = 43,           -- 英雄-属性
HeroSkill           = 44,           -- 英雄-技能
HeroTitle           = 45,           -- 英雄-称号
HeroBestRing        = 46,           -- 英雄-首饰盒
HeroBag             = 47,           -- 英雄-背包
HeroSuperEquip      = 48,           -- 英雄-神装
ReinAttrPoint       = 51,           -- 转生属性点
Chat                = 52,           -- 聊天
PCPrivate           = 53,           -- PC 私聊记录页

MagicJointAttack    = 99,           -- 释放合击

AssistChange        = 110,          -- 主界面-任务栏
Box996              = 111,          -- 盒子称号
MainMiniMapChange   = 112,          -- 小地图伸缩
PCResolution        = 113,          -- PC 分辨率设置
ChatExtendEmoj      = 114,          -- 角色-表情
ChatExtendBag       = 115,          -- 聊天小框-背包
MainNear            = 116,          -- 主界面-附近列表
CallPay             = 117,          -- 调用-支付

SettingBasic        = 300,          -- 基础设置
SettingWindowRange  = 301,          -- 视距
SettingFight        = 302,          -- 战斗
SettingProtect      = 303,          -- 保护
SettingAuto         = 304,          -- 挂机
SettingHelp         = 305,          -- 帮助

KeFu                = 310,          -- 调用客服界面
Compound            = 2201,         -- 合成

PlayerInternalState     = 401,      -- 人物内功状态
PlayerInternalSkill     = 402,      -- 人物内功技能
PlayerInternalMeridian  = 403,      -- 人物内功经络
PlayerInternalCombo     = 404,      -- 人物内功连击

HeroInternalState       = 501,      -- 英雄内功状态
HeroInternalSkill       = 502,      -- 英雄内功技能
HeroInternalMeridian    = 503,      -- 英雄内功经络
HeroInternalCombo       = 504,      -- 英雄内功连击

ReviewGift = 311, -- 好评有礼
Community = 320, -- 社区帖子

退出到选角界面

SL:ExitToRoleUI()

小退时, 有弹窗提示

SL:ForceExitToRoleUI()

强制小退, 无弹窗提示

退出到登录界面
SL:ExitToLoginUI()
退出游戏 [3.40.8版本]
- SL:ExitGame()
发送GM命令到聊天

SL:SendGMMsgToChat(msg)

msg : 字符串

创建一个红点到节点

SL:CreateRedPoint(targetNode, offset)

返回红点 widget

| 字段 | 必选 | 类型 | 注释 |
| targetNode | 是 | widget | 目标控件 |
| offset | 否 | table | 偏移位置 例: {x = 5, y = 5} |
设置文本样式(按钮、文本)

SL:SetColorStyle(widget, colorID)

widget ：按钮或者文本对象

colorID ：0 - 255 色值ID

获取对应色值ID的配置
SL:GetColorCfg(colorID)
检查是否满足条件
SL:CheckCondition(conditionStr)
返回值 : true / false
显示气泡提醒

SL:AddBubbleTips(id, path, callback)

id ：气泡ID

path：气泡图片资源路径

callback：气泡点击回调

SL:AddBubbleTips(996, "private/main/bubble_tips/1900012605_1.png", function ()
SL:DelBubbleTips(996)
end)

删除气泡提醒

SL:DelBubbleTips(ID)

id ：气泡ID

重新加载地图
SL:ReloadMap()
请求HTTP Get方式
SL:HTTPRequestGet(url, httpsCB)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| url | 是 | string | 链接地址 |
| httpsCB | 是 | function | 回调函数 |

示例

local function httpsCB(success, response)
-- success: boolean 请求是否成功
-- response: string 请求返回数据
end
SL:HTTPRequestGet("https://www.baidu.com/", httpsCB)

请求HTTP Post方式
SL:HTTPRequestPost(url, httpsCB, suffix, head, notForce)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| url | 是 | string | 链接地址 |
| httpsCB | 是 | function | 回调函数 |
| suffix | 是 | string | 请求信息 |
| head | 否 | table | 请求头 |
| notForce | 否 | boolean | 不强行设置header “Content-type”为”application/x-www-form-urlencoded” [3.40.7版本新增] |

示例

local function httpsCB(success, response)
-- success: boolean 请求是否成功
-- response: string 请求返回数据
end
local suffix = "appid=1&device_id=PCDV-6ct5fzZ&game_id=1&platform=0&type=1&username=wuuhui&sign=30a51e6"
SL:HTTPRequestPost("https://www.baidu.com/", httpsCB, suffix)

本地公告展示 [3.40.3版本]
SL:ShowLocalNoticeByType(data)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| data | 是 | table | 具体参数配置 |

参数说明：

Type     -- 公告类型
【
4: 顶部跑马灯公告 (Msg、 FColor、 BColor) 5: 屏幕跑马灯公告 可控制Y轴坐标 (Msg、 FColor、 BColor、 Y、 Count)
6: 聊天上方公告 (Msg、 FColor、 BColor、 Time、 Label) 9: 普通通用提示 (Msg)
10: 可控制X轴Y轴公告 (Msg、 FColor、 BColor、 X、 Y) 11: 屏幕跑马灯公告 (系统公告) (Type、 Msg、 FColor、 BColor)
12: 系统频道公告 (Msg、 FColor、 BColor) 13: 带缩放效果的公告 可设置Y轴 (Msg、 FColor、 BColor、Y)
】
Msg     -- 提示内容
FColor     -- 文字色值ID
BColor     -- 背景色值ID
X     -- 坐标X
Y     -- 坐标Y
Time     -- 倒计时
Count     -- 播放次数
Label     -- 响应Link

震屏 [3.40.3版本]
SL:ShakeScene(time, distance)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| time | 否 | int | 震动时间 (毫秒) |
| distance | 否 | int | 震动距离 |

例 :

-- 无参默认 time为700 、distance为10
SL:ShakeScene()

游戏事件函数
注册控件事件
SL:RegisterWndEvent(widget, desc, msgtype, callback)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| widget | 是 | object | 控件对象 |
| msg | 是 | string | 描述 |
| msgtype | 是 | int | 窗体事件id |
| callback | 是 | function | 回调函数 |
！同一控件注册不同事件需统一描述
窗口事件 msgtype
WND_EVENT_MOUSE_LB_DOWN             = 1                                         -- 鼠标左键按下事件
WND_EVENT_MOUSE_LB_UP               = 2                                         -- 鼠标左键弹起事件
WND_EVENT_MOUSE_LB_CLICK            = 3                                         -- 鼠标左键点击事件
WND_EVENT_MOUSE_LB_DBCLICK          = 4                                         -- 鼠标左键双击事件
WND_EVENT_MOUSE_RB_DOWN             = 5                                         -- 鼠标右键按下事件
WND_EVENT_MOUSE_RB_UP               = 6                                         -- 鼠标右键弹起事件
WND_EVENT_MOUSE_RB_CLICK            = 7                                         -- 鼠标右键点击事件
WND_EVENT_MOUSE_RB_DBCLICK          = 8                                         -- 鼠标右键双击事件
WND_EVENT_MOUSE_MOVE                = 9                                         -- 鼠标移动事件
WND_EVENT_MOUSE_WHEEL               = 10                                        -- 鼠标滚轮滚动事件
WND_EVENT_MOUSE_IN                  = 11                                        -- 鼠标进入控件事件
WND_EVENT_MOUSE_OUT                 = 12                                        -- 鼠标离开控件事件

WND_EVENT_WND_VISIBLE               = 21                                        -- 可见状态发生变化事件
WND_EVENT_WND_POS_CHANGE            = 22                                        -- 控件位置发生变化事件
WND_EVENT_WND_SIZECHANGE            = 23                                        -- 窗口大小发生变化事件
WND_EVENT_WND_DESTROY               = 24                                        -- 窗体被销毁事件


示例

SL:RegisterWndEvent(btn, "npc", WND_EVENT_MOUSE_LB_UP, function()
SL:Print("2")
end)

注销控件事件
SL:UnRegisterWndEvent(widget, desc, msgtype)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| widget | 是 | object | 控件对象 |
| msg | 是 | string | 描述 |
| msgtype | 是 | int | 窗体事件id |

示例

SL:UnRegisterWndEvent(btn, "npc", WND_EVENT_MOUSE_LB_UP)

窗体控件自定义属性
添加窗体控件自定义属性 *
SL:AddWndProperty(widget, desc, key, value)
删除窗体控件自定义属性*
SL:DelWndProperty(widget, desc, key)
获取窗体控件自定义属性*
SL:GetWndProperty(widget, desc, key)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| widget | 是 | object | 控件对象 |
| desc | 是 | string | 描述 |
| key | 是 | string | 属性名称 |
| value | 是 | any | 属性值 |

示例

SL:AddWndProperty(btn, "test", "key", 1)
local a = SL:GetWndProperty(btn, "test", "key")
SL:Print(a, type(a))
SL:DelWndProperty(btn, "test", "key")

定时器
开启一个定时器
SL:Schedule(callback, time)
停止一个定时器
SL:UnSchedule(scheduleID)
开启一个单次定时器
SL:ScheduleOnce(callback, time)
开启一个定时器, 绑定node节点
SL:schedule(node, callback, time)
开启一个单次定时器, 绑定node节点
SL:scheduleOnce(node, callback, time)

示例

local time = 0.5
local function callback()
SL:Print("callback...")
end

-- 每隔0.5s执行一次 callback
local sch1 = SL:Schedule(callback, time)

-- 停止上面的定时器 sch1
SL:UnSchedule(sch1)

-- 0.5s后执行一次 callback
SL:ScheduleOnce(callback, time)

-- 创建一个Node节点
local node = GUI:Node_create(parent, "Node", 0 , 0)
-- node 节点每隔0.5s执行一次 callback
SL:schedule(node, callback, time)

-- node 节点0.5s后执行一次 callback
SL:scheduleOnce(node, callback, time)

-- node 节点取消定时器操作
GUI:stopAllActions(node)

引导相关
打开引导

SL:StartGuide(data)

返回值 : 引导对象

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| data | 是 | table | 数据结构如下, 参考示例 |

table特殊参数
mainIdx — int 如若指引界面加在主界面节点 需要配置对应标识 :
1 --左上 2 --中上 3 --右上 4 --左下 5 --中下 6 --右下

示例 1 ：

local function callback()
SL:Print("callback".....)
end
local data = {}
data.dir = 8 -- 方向（1~8）从左按瞬时针
data.guideWidget = btn_close -- 当前节点
data.guideParent = _parent -- 父窗口
data.guideDesc = "测试" -- 文本描述
data.clickCB = callback -- 回调
data.autoExcute = 3 -- 自动执行秒数
data.isForce = true -- 强制引导
data.hideMask = true -- 隐藏蒙版 [仅不强制引导时有效]

SL:StartGuide(data)


针对引导一些引擎原生界面 必需参数 :

id — int 提供的原生界面指引ID
param — int 指引参数 提供的一些原生界面对应位置指引所需参数 比如任务ID

示例 2 ：

SL:StartGuide({
id = 1,                -- 背包引导窗口ID
param = 2682001,        -- 背包物品唯一ID
guideDesc = "测试引导"
})

关闭引导

SL:CloseGuide(guide)

参数 : 传入开始引导返回的 引导对象

本地存储
存储字符到本地
SL:SetLocalString(key, data)
存储数据到本地，存储的文件名为：”GUIStorage” + 角色ID

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| key | 是 | 任意类型 | 字段名 |
| data | 是 | table、int、string | 数据 |

示例

-- 把数据 t 存储到本地配置的 key 字段里
local t = {
val1 = "111", val2 = "222"
}
local jsonStr = SL:JsonEncode(t)
SL:SetLocalString("key", jsonStr)

从本地读取字符
SL:GetLocalString(key)

读取存储到本地的key数据

返回值 : string

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| key | 是 | 任意类型 | 字段名 |

示例

-- 把数据从本地存储配置中取出来
local data = {}
local jsonStr = SL:GetLocalString("key")
if jsonStr and string.len(jsonStr) > 0 then
local jsonData = SL:JsonDecode(jsonStr)
if jsonData then
data = jsonData
end
end
SL:dump( data )

背包常用函数 [3.40.2版本]
背包刷新
SL:RefreshBagPos()
使用物品
SL:UseItemByIndex(Index)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| Index | 是 | int | 物品Index |
批量勾选背包物品 [3.40.3版本]
SL:SetBagItemChoose(data)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| data | 是 | table | 物品唯一ID 数组 |
丢弃物品 [3.40.3版本]
SL:IntoDropBagItem(itemData)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| itemData | 是 | table | 装备数据 |
装备常用函数
检测人物是否可穿戴
SL:CheckItemUseNeed(itemData)

参数： itemData 装备数据

检测英雄是否可穿戴
SL:CheckItemUseNeed_Hero(itemData)

参数： itemData 装备数据

获得需要比较的装备
SL:GetDiffEquip(itemData, isHero)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| itemData | 是 | table | 装备数据 |
| isHero | 否 | boolean | 是否对比英雄 |

返回值： table, 具体用法参考官方 GUILayout/ItemTips.lua

对比传入装备和自身穿戴的装备
SL:CheckEquipPowerThanSelf(itemData, from)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| itemData | 是 | table | 装备数据 |
| from | 否 | int | 物品来自(界面位置), 可参照元变量”ITEMFROMUI_ENUM” |

*返回值： table

人物装备穿戴 [3.40.2版本]
SL:TakeOnPlayerEquip(itemData, pos, isFromHero)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| itemData | 是 | table | 装备数据 |
| pos | 是 | int | 装备位置 |
| isFromHero | 否 | boolean | 是否来自英雄背包 |
人物装备脱下 [3.40.2版本]
SL:TakeOffPlayerEquip(itemData, isToHero)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| itemData | 是 | table | 装备数据 |
| isToHero | 否 | boolean | 是否脱到英雄背包 |
英雄装备穿戴 [3.40.2版本]
SL:TakeOnHeroEquip(itemData, pos, isFromPlayer)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| itemData | 是 | table | 装备数据 |
| pos | 是 | int | 装备位置 |
| isFromPlayer | 否 | boolean | 是否来自人物背包 |
英雄装备脱下 [3.40.2版本]
SL:TakeOffHeroEquip(itemData, isToPlayer)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| itemData | 是 | table | 装备数据 |
| isToPlayer | 否 | boolean | 是否脱到人物背包 |
界面相关 Menulayer
SL:CheckMenuLayerConditionByID(layerID)

通过 cfg_menulayer 表中的界面ID检测该界面的条件配置，是否满足显示

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| layerID | 是 | int | cfg_menulayer 表中的界面ID |

返回值： boolean

SL:OpenMenuLayerByID(layerID，parent， extent)

通过 cfg_menulayer 表中的界面ID打开该界面

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| layerID | 是 | int | cfg_menulayer 表中的界面ID |
| parent | 是 | object | 挂接点 |
| extent | 否 | int | 可选参数 |
SL:CloseMenuLayerByID(layerID)

通过 cfg_menulayer 表中的界面ID关闭该界面

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| layerID | 是 | int | cfg_menulayer 表中的界面ID |

返回值： boolean

打开、关闭相关功能界面
设置界面
SL:OpenSettingUI(pageID)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| pageID | 否 | int | 页签ID 不填默认基础设置 |
1 : 基础设置
2 : 视距
3 : 战斗
4 : 保护
5 : 挂机
6 : 帮助
SL:CloseSettingUI()
行会界面
SL:OpenGuildMainUI(pageID)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| pageID | 否 | int | 页签ID 不填默认行会主页 |
1 : 主页
2 : 成员
3 : 列表
SL:CloseGuildMainUI()
行会申请界面

SL:OpenGuildApplyListUI()

SL:CloseGuildApplyListUI()

行会创建界面

SL:OpenGuildCreateUI()

SL:CloseGuildCreateUI()

行会结盟申请界面

SL:OpenGuildAllyApplyUI()

SL:CloseGuildAllyApplyUI()

行会宣战/结盟界面 [关闭]
SL:CloseGuildWarSponsorUI()
人物背包
SL:OpenBagUI(data)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| data | 否 | table | pos : 背包打开位置 |
bag_page : 背包打开页签ID

例:

local data = {pos = {x = 200, y = 0}, bag_page = 2}
SL:OpenBagUI(data)

SL:CloseBagUI()
英雄背包

SL:OpenHeroBagUI()

SL:CloseHeroBagUI()

拍卖行

SL:OpenAuctionUI()

SL:CloseAuctionUI()

摆摊界面

SL:OpenStallLayerUI()

SL:CloseStallLayerUI()

玩家交易界面

SL:OpenTradeUI()

SL:CloseTradeUI()

排行榜
SL:OpenRankUI(type)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| type | 否 | int | 打开 指定页签ID |
SL:CloseRankUI()
聊天界面(手机端)

SL:OpenChatUI()

SL:CloseChatUI()

聊天扩展框
SL:OpenChatExtendUI(index)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| index | 否 | int | 打开 指定分组 |
1 : 快捷命令
2 : 表情
3 : 背包
SL:CloseChatExtendUI()
社区帖子 [3.40.3版本]
需要后台配置社区地址

SL:OpenCommunityUI()

SL:CloseCommunityUI()

交易行

SL:OpenTradingBankUI()

SL:CloseTradingBankUI()

商城
SL:OpenStoreUI(page)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| page | 否 | int | 打开 商城对应分页 |
SL:CloseStoreUI()
商城商品购买框
SL:OpenStoreDetailUI(storeIndex, limitStr)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| storeIndex | 是 | int | 商品index cfg_store商城表配置的id |
| limitStr | 否 | string | 超出限制购买的提示 |
SL:CloseStoreDetailUI()
技能配置界面
SL:OpenSkillSettingUI(data)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| data | ！PC端必填 | table | 对应技能数据 打开技能快捷键配置页 |
SL:CloseSkillSettingUI()
社交
SL:OpenSocialUI(page)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| page | 否 | int | 页签ID ( 不填默认1附近 ) |
1附近玩家、2组队、3好友、4邮件
SL:CloseSocialUI()
分辨率修改界面(PC端)

SL:OpenResolutionSetUI()

SL:CloseResolutionSetUI()

玩家角色界面
SL:OpenMyPlayerUI(data)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| data | 否 | table | extent: 子页id |
1装备、2状态、3属性、4技能、6称号、11时装
isFast: boolen 是否快捷键打开

例 :

SL:OpenMyPlayerHeroUI({extent = 1})


SL:CloseMyPlayerUI()

SL:CloseMyPlayerPageUI(data)

移除对应子页id内容

查看他人角色界面
SL:OpenOtherPlayerUI(data)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| data | 否 | table | extent: 子页id |
1装备、2状态、3属性、4技能、6称号、11时装

SL:CloseOtherPlayerUI()

SL:CloseOtherPlayerPageUI(data)

移除对应子页id内容

英雄角色界面
SL:OpenMyPlayerHeroUI(data)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| data | 否 | table | extent: 子页id |
1装备、2状态、3属性、4技能、6称号、11时装

SL:CloseMyPlayerHeroUI()

SL:CloseMyPlayerHeroPageUI(data)

移除对应子页id内容

查看他人英雄界面
SL:OpenOtherPlayerHeroUI(data)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| data | 否 | table | extent: 子页id |
1装备、2状态、3属性、4技能、6称号、11时装

SL:CloseOtherPlayerHeroUI()

SL:CloseOtherPlayerHeroPageUI(data)

移除对应子页id内容

交易行查看他人界面

SL:CloseTradingBankPlayerPageUI(data)

移除他人角色对应子页id内容

SL:CloseTradingBankHeroPageUI(data)

移除他人英雄对应子页id内容

首饰盒界面
SL:OpenBestRingBoxUI(param)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| param | 是 | int | param: |
1: 自己人物
2：自己英雄
11：其他玩家人物
12：其他玩家英雄
21：交易行人物
22：交易行英雄

SL:CloseBestRingBoxUI(param)

param参数同上

打开装备面板
SL:OpenPlayerEquipUI(param)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| param | 是 | int | param: |
1: 自己人物
2：自己英雄
11：其他玩家人物
12：其他玩家英雄
21：交易行人物
22：交易行英雄
打开状态面板
SL:OpenPlayerBaseAttrUI(param)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| param | 是 | int | param: |
1: 自己人物
2：自己英雄
11：其他玩家人物
12：其他玩家英雄
21：交易行人物
22：交易行英雄
打开属性面板
SL:OpenPlayerExtraAttrUI(param)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| param | 是 | int | param: |
1: 自己人物
2：自己英雄
11：其他玩家人物
12：其他玩家英雄
21：交易行人物
22：交易行英雄
打开技能面板
SL:OpenPlayerSkillUI(param)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| param | 是 | int | param: |
1: 自己人物
2：自己英雄
11：其他玩家人物
12：其他玩家英雄
21：交易行人物
22：交易行英雄
打开称号面板
SL:OpenPlayerTitleUI(param)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| param | 是 | int | param: |
1: 自己人物
2：自己英雄
11：其他玩家人物
12：其他玩家英雄
21：交易行人物
22：交易行英雄
打开时装面板
SL:OpenPlayerSuperEquipUI(param)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| param | 是 | int | param: |
1: 自己人物
2：自己英雄
11：其他玩家人物
12：其他玩家英雄
21：交易行人物
22：交易行英雄
打开人物BUFF面板 [3.40.6版本]
SL:OpenPlayerBuffUI(param)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| param | 是 | int | param: |
1: 自己人物
2：自己英雄
11：其他玩家人物
12：其他玩家英雄 [英雄BUFF页3.40.8版本新增]
称号提示界面
SL:OpenTitleTipsUI(data)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| data | 是 | table | id: 称号id |
pos: Tips放置位置
type: 1未激活 2已激活
time: 时间
SL:CloseTitleTipsUI()
他人称号提示界面
SL:OpenOtherTitleTipsUI(data)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| data | 是 | table | id: 称号id |
pos: Tips放置位置
type: 1未激活 2已激活
time: 时间
SL:CloseOtherTitleTipsUI()
关闭交易行查看他人容器
SL:CloseTradingBankLookPanelUI()
关闭交易行查看他人界面
SL:CloseTradingBankLookInfoUI()
邀请组队界面

SL:OpenTeamInvite()

SL:CloseTeamInvite()

入队申请列表页

SL:OpenTeamApply()

SL:CloseTeamApply()

小地图界面

SL:OpenMiniMap()

SL:CloseMiniMap()

主界面技能按钮区域切换显示

SL:OpenGuideEnter(param)

SL:CloseGuideEnter()

转生点分配界面

SL:OpenReinAttrUI()

SL:CloseReinAttrUI()

导航栏栏收缩切换

SL:OpenAssistUI()

SL:CloseAssistUI()

SL:SwitchToMainMission() [3.40.9版本]

导航栏切换到任务面板
主界面小地图收缩切换[手机端]

SL:OpenMiniMapChangeUI()

SL:CloseMiniMapChangeUI()

附近展示页

SL:OpenMainNearUI()

SL:CloseMainNearUI()

直接调用支付
SL:OpenCallPayUI()
打开客服UI
SL:OpenKefuUI()
PC端私聊界面

SL:OpenPCPrivateUI()

SL:ClosePCPrivateUI()

PC端小地图变换
SL:OpenPCMiniMapUI()
添加好友界面

SL:OpenAddFriendUI()

SL:CloseAddFriendUI()

添加黑名单界面

SL:OpenAddBlackListUI()

SL:CloseAddBlackListUI()

好友添加申请页

SL:OpenFriendApplyUI()

SL:CloseFriendApplyUI()

拍卖行-世界拍卖/行会拍卖
SL:OpenAuctionWorldUI(parent, source)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| parent | 是 | widget | 挂接父节点 |
| source | 是 | int | 类别 |
0: 世界拍卖
1: 行会拍卖
SL:CloseAuctionWorldUI()
拍卖行-我的竞拍
SL:OpenAuctionBiddingUI(parent)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| parent | 是 | widget | 挂接父节点 |
SL:CloseAuctionBiddingUI()
拍卖行-我的上架
SL:OpenAuctionPutListUI(parent)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| parent | 是 | widget | 挂接父节点 |
SL:CloseAuctionPutListUI()
拍卖行上架界面
SL:OpenAuctionPutinUI(itemData)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| itemData | 是 | table | 背包物品数据 |
SL:CloseAuctionPutinUI()
拍卖行下架界面
SL:OpenAuctionPutoutUI(item)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| item | 是 | table | 拍卖行上架的物品数据 |
SL:CloseAuctionPutoutUI()
拍卖行竞拍界面
SL:OpenAuctionBidUI(item)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| item | 是 | table | 拍卖行上架的物品数据 |
SL:CloseAuctionBidUI()
拍卖行一口价界面
SL:OpenAuctionBuyUI(item)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| item | 是 | table | 拍卖行上架的物品数据 |
SL:CloseAuctionBuyUI()
拍卖行超时界面
SL:OpenAuctionTimeoutUI(item)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| item | 是 | table | 拍卖行上架的物品数据 |
SL:CloseAuctionTimeoutUI()
合成界面

SL:OpenCompoundItemsUI()

SL:CloseCompoundItemsUI()

怪物提示列表-设置界面

SL:OpenBossTipsUI()

SL:CloseBossTipsUI()

拾取列表-设置界面

SL:OpenPickSettingUI()

SL:ClosePickSettingUI()

保护配置-设置界面
SL:OpenProtectSettingUI(data)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| data | 是 | table | cfg_setup对应保护配置 |
SL:CloseProtectSettingUI()
增加怪物名字-设置界面
SL:OpenAddNameUI(data)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| data | 否 | table | ignoreName: boolean 是否是挂机忽略名字 |
SL:CloseAddNameUI()
增加BOSS类型-设置界面

SL:OpenAddBossTypeUI()

SL:CloseAddBossTypeUI()

技能排行-设置界面
SL:OpenSkillRankPanelUI(data)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| data | 是 | table | cfg_setup对应保护配置 |
SL:CloseSkillRankPanelUI(data)
新增技能-设置界面

SL:OpenSkillPanelUI()

SL:CloseSkillPanelUI()

选择下拉框
SL:OpenSelectListUI(list, position, cellwidth, cellheight, func)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| list | 是 | table | 下拉要显示的内容 |
| position | 是 | table | 初始位置 |
| cellwidth | 否 | int | 单条cell的宽 |
| cellheight | 否 | int | 单条cell的高 |
| func | 否 | function | 回调 选中的编号1~n 0是关闭 |
SL:CloseSelectListUI()
996盒子界面
SL:OpenBox996UI(index)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| index | 否 [ 3.40.4版本新增参数 ] | int | 盒子打开默认分页id |
1: 特权称号 2: 每日礼包 3: 超级礼包 4: 会员礼包 5: SVIP
SL:CloseBox996UI()
英雄状态选择界面

SL:OpenHeroStateSelectUI(data)

SL:CloseHeroStateSelectUI(data)

打开快捷使用框
SL:OpenAutoUseTip(itemData, equipPos, isBook, isHero)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| itemData | 是 | table | 真实物品数据 |
| equipPos | 否 | int | 物品为装备时装戴的装备位置 |
| isBook | 否 | boolean | 是否是技能书 |
| isHero | 否 | boolean | 是否为英雄 |
关闭快捷使用框
SL:CloseAutoUseTip(makeIndex, isHero)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| makeIndex | 是 | int | 物品唯一ID |
| isHero | 否 | boolean | 是否为英雄 |
开宝箱动画页 [3.40.3版本]
SL:OpenTreasureBoxShow(itemData)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| itemData | 是 | table | 宝箱物品数据 |
SL:CloseTreasureBoxShow()
宝箱奖励界面 [3.40.3版本]
SL:OpenGoldBoxUI(itemData)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| itemData | 是 | table | 宝箱物品数据 |
SL:CloseGoldBoxUI()
摇骰子界面 [3.40.4版本]
SL:OpenPlayDice(data)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| data | 是 | table | 字段说明如下 |
{
arr = table 投掷值 {xx, xx}
count = 数量
callback = @xxx 脚本触发
}

SL:ClosePlayDice()
求购界面 [3.40.5版本]

SL:OpenPurchaseUI()

SL:ClosePurchaseUI()

求购 - 世界求购 [3.40.5版本]
SL:OpenPurchaseWorldUI(parent)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| parent | 是 | widget | 挂接父节点 |
SL:ClosePurchaseWorldUI()
求购 - 我的求购 [3.40.5版本]
SL:OpenPurchaseMyUI(parent)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| parent | 是 | widget | 挂接父节点 |
SL:ClosePurchaseMyUI()
求购出售页 [3.40.5版本]
SL:OpenPurchaseSellUI(data)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| data | 是 | table | 单条世界求购数据 |
SL:ClosePurchaseSellUI()
求购上架页 [3.40.5版本]

SL:OpenPurchasePutInUI()

SL:ClosePurchasePutInUI()

仓库 - 关闭
SL:CloseStorageUI()
通用描述Tips
SL:OpenCommonDescTipsPop(data)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| data | 是 | table | str: 描述内容 |
worldPos: 提示位置
width: 描述内容宽度
anchorPoint: 锚点
formatWay: 设置为1 解析富文本格式: <font></font>[！否则默认解析老脚本富文本<RText/FCOLOR=254>]
local data = {width = 1136, str = "测试文本", worldPos = {x = 568, y = 320}, anchorPoint = {x = 0, y = 1}}
SL:OpenCommonDescTipsPop(data)

SL:CloseCommonDescTipsPop()
通用弹窗
SL:OpenCommonTipsPop(data)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| data | 是 | table | str: 文本 |
btnType: 按钮类型 int 1:”确定” 2:{“确定”,”取消”}
btnDesc: 按钮描述 table
showEdit: 是否显示输入框
editParams: 输入框参数table
{ inputMode: 键盘编辑类型, maxLength: 可输入最大长度, str: 默认文本内容}
callback: 按钮回调 [参数1: 点击的按钮id 参数2: 额外参数 table: {editStr=输入框字符串}]

例 :

local data = {}
data.str = "请输入邀请玩家的名字"
data.btnType = 2
data.showEdit = true
data.callback = function(atype, param)
if atype == 1 then
if param and param.editStr and string.len(param.editStr) > 0 then
SL:RequestInviteJoinTeam(nil, param.editStr)
end
end
end
SL:OpenCommonTipsPop(data)

SL:CloseCommonTipsPop()
道具装备Tips
SL:OpenItemTips(data)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| data | 是 | table | itemData: 物品数据 |
pos: 提示位置
from:非必要 物品来自(界面位置), 可参照元变量ITEMFROMUI_ENUM
SL:CloseItemTips()
道具拆分弹窗
SL:OpenItemSplitPop(itemData)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| itemData | 是 | table | 物品数据 |
SL:CloseItemSplitPop()
通用功能选择提示
SL:OpenFuncDockTips(data)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| data | 是 | table | 参数说明: |
type : 类型 可参照元变量DOCKTYPE_NENUM
targetId : 选中目标id
targetName :目标名称
pos : 展示位置

示例可参照 MainTarget文件内 点击查看菜单功能。

SL:CloseFuncDockTips()
NPC进度条提示 [3.40.3版本]
SL:OpenProgressBarUI(data)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| data | 是 | table | 参数说明: |
time : 时间
msg : 显示内容
SL:CloseProgressBarUI()
多条选项弹窗提示 [3.40.3版本]
SL:OpenCommonBubbleInfo(data)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| data | 是 | table | 参数说明: |
pos : 坐标
list : 多条选项列表
[单条数据参考:
{str = 文本, agreeCall = 同意按钮回调(function), disAgreeCall = 拒绝回调(function)}
]
SL:CloseCommonBubbleInfo()

例 :

local tt = {
[1] = "11111",
[2] = "22222",
[3] = "33333",
}

local data = {}
data.pos = {x = 200, y = 400}
data.list = {}
for _, v in pairs(tt) do
local info = {}
info.str = v
info.agreeCall = function()
SL:Print("AgreeCall____" .. v)
end
info.disAgreeCall = function()
SL:Print("disAgreeCall___" .. v)
end
table.insert(data.list, info)
end
SL:OpenCommonBubbleInfo(data)

打开好评有礼 [3.40.3版本]
SL:ReviewGift()
打开网址/链接 [3.40.3版本]
SL:OpenURL(url)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| url | 是 | string | 网址/链接 |

示例

SL:OpenURL("https://www.baidu.com/")

颜色
SL:GetColorByStyleId(id)

把 cfg_colour_style 表中的对应 id 的颜色转换成 RGB 格式

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| id | 是 | int | cfg_colour_style 表中的对应 id |

返回值类型： table {r = 255, g = 255, b = 255}

SL:GetHexColorByStyleId(id)

把 cfg_colour_style 表中的对应 id 的颜色转换成 16进制 格式

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| id | 是 | int | cfg_colour_style 表中的对应 id |
返回值类型： string “#FFFFFF”
SL:GetSizeByStyleId(id)

把 cfg_colour_style 表中的对应 id 的颜色大小

返回值类型： int size
SL:GetColorHexFromRGB(color3B)
Color3B颜色转化为hex 16进制

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| color3B | 是 | table | 例: {r = 255, g = 255, b = 255} |
返回值类型： string “#FFFFFF”
颜色Id(0-255) 对应 16进制Hex(#000000-#ffffff)
Id：(0) Hex：(#000000)
Id：(1) Hex：(#800000)
Id：(2) Hex：(#008000)
Id：(3) Hex：(#808000)
Id：(4) Hex：(#000080)
Id：(5) Hex：(#800080)
Id：(6) Hex：(#008080)
Id：(7) Hex：(#c0c0c0)
Id：(8) Hex：(#558097)
Id：(9) Hex：(#9db9c8)
Id：(10) Hex：(#7b7373)
Id：(11) Hex：(#2d2929)
Id：(12) Hex：(#5a5252)
Id：(13) Hex：(#635a5a)
Id：(14) Hex：(#423939)
Id：(15) Hex：(#1d1818)
Id：(16) Hex：(#181010)
Id：(17) Hex：(#291818)
Id：(18) Hex：(#100808)
Id：(19) Hex：(#f27971)
Id：(20) Hex：(#e1675f)
Id：(21) Hex：(#ff5a5a)
Id：(22) Hex：(#ff3131)
Id：(23) Hex：(#d65a52)
Id：(24) Hex：(#941000)
Id：(25) Hex：(#942918)
Id：(26) Hex：(#390800)
Id：(27) Hex：(#731000)
Id：(28) Hex：(#b51800)
Id：(29) Hex：(#bd6352)
Id：(30) Hex：(#421810)
Id：(31) Hex：(#ffaa99)
Id：(32) Hex：(#5a1000)
Id：(33) Hex：(#733929)
Id：(34) Hex：(#a54a31)
Id：(35) Hex：(#947b73)
Id：(36) Hex：(#bd5231)
Id：(37) Hex：(#522110)
Id：(38) Hex：(#7b3118)
Id：(39) Hex：(#2d1810)
Id：(40) Hex：(#8c4a31)
Id：(41) Hex：(#942900)
Id：(42) Hex：(#bd3100)
Id：(43) Hex：(#c67352)
Id：(44) Hex：(#6b3118)
Id：(45) Hex：(#c66b42)
Id：(46) Hex：(#ce4a00)
Id：(47) Hex：(#a56339)
Id：(48) Hex：(#5a3118)
Id：(49) Hex：(#2a1000)
Id：(50) Hex：(#150800)
Id：(51) Hex：(#3a1800)
Id：(52) Hex：(#080000)
Id：(53) Hex：(#290000)
Id：(54) Hex：(#4a0000)
Id：(55) Hex：(#9d0000)
Id：(56) Hex：(#dc0000)
Id：(57) Hex：(#de0000)
Id：(58) Hex：(#fb0000)
Id：(59) Hex：(#9c7352)
Id：(60) Hex：(#946b4a)
Id：(61) Hex：(#734a29)
Id：(62) Hex：(#523118)
Id：(63) Hex：(#8c4a18)
Id：(64) Hex：(#884411)
Id：(65) Hex：(#4a2100)
Id：(66) Hex：(#211810)
Id：(67) Hex：(#d6945a)
Id：(68) Hex：(#c66b21)
Id：(69) Hex：(#ef6b00)
Id：(70) Hex：(#ff7700)
Id：(71) Hex：(#a59484)
Id：(72) Hex：(#423121)
Id：(73) Hex：(#181008)
Id：(74) Hex：(#291808)
Id：(75) Hex：(#211000)
Id：(76) Hex：(#392918)
Id：(77) Hex：(#8c6339)
Id：(78) Hex：(#422910)
Id：(79) Hex：(#6b4218)
Id：(80) Hex：(#7b4a18)
Id：(81) Hex：(#944a00)
Id：(82) Hex：(#8c847b)
Id：(83) Hex：(#6b635a)
Id：(84) Hex：(#4a4239)
Id：(85) Hex：(#292118)
Id：(86) Hex：(#463929)
Id：(87) Hex：(#b5a594)
Id：(88) Hex：(#7b6b5a)
Id：(89) Hex：(#ceb194)
Id：(90) Hex：(#a58c73)
Id：(91) Hex：(#8c735a)
Id：(92) Hex：(#b59473)
Id：(93) Hex：(#d6a573)
Id：(94) Hex：(#efa54a)
Id：(95) Hex：(#efc68c)
Id：(96) Hex：(#7b6342)
Id：(97) Hex：(#6b5639)
Id：(98) Hex：(#bd945a)
Id：(99) Hex：(#633900)
Id：(100) Hex：(#d6c6ad)
Id：(101) Hex：(#524229)
Id：(102) Hex：(#946318)
Id：(103) Hex：(#efd6ad)
Id：(104) Hex：(#a58c63)
Id：(105) Hex：(#635a4a)
Id：(106) Hex：(#bda57b)
Id：(107) Hex：(#5a4218)
Id：(108) Hex：(#bd8c31)
Id：(109) Hex：(#353129)
Id：(110) Hex：(#948463)
Id：(111) Hex：(#7b6b4a)
Id：(112) Hex：(#a58c5a)
Id：(113) Hex：(#5a4a29)
Id：(114) Hex：(#9c7b39)
Id：(115) Hex：(#423110)
Id：(116) Hex：(#efad21)
Id：(117) Hex：(#181000)
Id：(118) Hex：(#292100)
Id：(119) Hex：(#9c6b00)
Id：(120) Hex：(#94845a)
Id：(121) Hex：(#524218)
Id：(122) Hex：(#6b5a29)
Id：(123) Hex：(#7b6321)
Id：(124) Hex：(#9c7b21)
Id：(125) Hex：(#dea500)
Id：(126) Hex：(#5a5239)
Id：(127) Hex：(#312910)
Id：(128) Hex：(#cebd7b)
Id：(129) Hex：(#635a39)
Id：(130) Hex：(#94844a)
Id：(131) Hex：(#c6a529)
Id：(132) Hex：(#109c18)
Id：(133) Hex：(#428c4a)
Id：(134) Hex：(#318c42)
Id：(135) Hex：(#109429)
Id：(136) Hex：(#081810)
Id：(137) Hex：(#081818)
Id：(138) Hex：(#082910)
Id：(139) Hex：(#184229)
Id：(140) Hex：(#a5b5ad)
Id：(141) Hex：(#6b7373)
Id：(142) Hex：(#182929)
Id：(143) Hex：(#18424a)
Id：(144) Hex：(#31424a)
Id：(145) Hex：(#63c6de)
Id：(146) Hex：(#44ddff)
Id：(147) Hex：(#8cd6ef)
Id：(148) Hex：(#736b39)
Id：(149) Hex：(#f7de39)
Id：(150) Hex：(#f7ef8c)
Id：(151) Hex：(#f7e700)
Id：(152) Hex：(#6b6b5a)
Id：(153) Hex：(#5a8ca5)
Id：(154) Hex：(#39b5ef)
Id：(155) Hex：(#4a9cce)
Id：(156) Hex：(#3184b5)
Id：(157) Hex：(#31526b)
Id：(158) Hex：(#deded6)
Id：(159) Hex：(#bdbdb5)
Id：(160) Hex：(#8c8c84)
Id：(161) Hex：(#f7f7de)
Id：(162) Hex：(#000818)
Id：(163) Hex：(#081839)
Id：(164) Hex：(#081029)
Id：(165) Hex：(#081800)
Id：(166) Hex：(#082900)
Id：(167) Hex：(#0052a5)
Id：(168) Hex：(#007bde)
Id：(169) Hex：(#10294a)
Id：(170) Hex：(#10396b)
Id：(171) Hex：(#10528c)
Id：(172) Hex：(#215aa5)
Id：(173) Hex：(#10315a)
Id：(174) Hex：(#104284)
Id：(175) Hex：(#315284)
Id：(176) Hex：(#182131)
Id：(177) Hex：(#4a5a7b)
Id：(178) Hex：(#526ba5)
Id：(179) Hex：(#293963)
Id：(180) Hex：(#4169E1)
Id：(181) Hex：(#292921)
Id：(182) Hex：(#4a4a39)
Id：(183) Hex：(#292918)
Id：(184) Hex：(#4a4a29)
Id：(185) Hex：(#7b7b42)
Id：(186) Hex：(#9c9c4a)
Id：(187) Hex：(#5a5a29)
Id：(188) Hex：(#424214)
Id：(189) Hex：(#393900)
Id：(190) Hex：(#595900)
Id：(191) Hex：(#ca352c)
Id：(192) Hex：(#6b7321)
Id：(193) Hex：(#293100)
Id：(194) Hex：(#313910)
Id：(195) Hex：(#313918)
Id：(196) Hex：(#424a00)
Id：(197) Hex：(#526318)
Id：(198) Hex：(#5a7329)
Id：(199) Hex：(#314a18)
Id：(200) Hex：(#182100)
Id：(201) Hex：(#183100)
Id：(202) Hex：(#183910)
Id：(203) Hex：(#63844a)
Id：(204) Hex：(#6bbd4a)
Id：(205) Hex：(#63b54a)
Id：(206) Hex：(#63bd4a)
Id：(207) Hex：(#5a9c4a)
Id：(208) Hex：(#4a8c39)
Id：(209) Hex：(#63c64a)
Id：(210) Hex：(#63d64a)
Id：(211) Hex：(#52844a)
Id：(212) Hex：(#317329)
Id：(213) Hex：(#63c65a)
Id：(214) Hex：(#52bd4a)
Id：(215) Hex：(#10ff00)
Id：(216) Hex：(#182918)
Id：(217) Hex：(#4a884a)
Id：(218) Hex：(#4ae74a)
Id：(219) Hex：(#005a00)
Id：(220) Hex：(#008800)
Id：(221) Hex：(#009400)
Id：(222) Hex：(#00de00)
Id：(223) Hex：(#00ee00)
Id：(224) Hex：(#00fb00)
Id：(225) Hex：(#4a5a94)
Id：(226) Hex：(#6373b5)
Id：(227) Hex：(#7b8cd6)
Id：(228) Hex：(#6b7bd6)
Id：(229) Hex：(#7788ff)
Id：(230) Hex：(#c6c6ce)
Id：(231) Hex：(#94949c)
Id：(232) Hex：(#9c94c6)
Id：(233) Hex：(#313139)
Id：(234) Hex：(#291884)
Id：(235) Hex：(#180084)
Id：(236) Hex：(#4a4252)
Id：(237) Hex：(#52427b)
Id：(238) Hex：(#635a73)
Id：(239) Hex：(#ceb5f7)
Id：(240) Hex：(#8c7b9c)
Id：(241) Hex：(#7722cc)
Id：(242) Hex：(#ddaaff)
Id：(243) Hex：(#f0b42a)
Id：(244) Hex：(#df009f)
Id：(245) Hex：(#e317b3)
Id：(246) Hex：(#fffbf0)
Id：(247) Hex：(#a0a0a4)
Id：(248) Hex：(#808080)
Id：(249) Hex：(#ff0000)
Id：(250) Hex：(#00ff00)
Id：(251) Hex：(#ffff00)
Id：(252) Hex：(#4169E1)
Id：(253) Hex：(#ff00ff)
Id：(254) Hex：(#00ffff)
Id：(255) Hex：(#ffffff)

音效
播放按钮点击音效
SL:PlayBtnClickAudio()
播放音效
SL:PlaySound(id, isLoop)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| id | 是 | int | cfg_sound表对应id |
| isLoop | 否 | boolean | 是否循环 |
播放登陆-选角音效
SL:PlaySelectRoleAudio()
播放开宝箱音效 [3.40.6版本]
SL:PlayOpenBoxAudio()
播放宝箱内选中音效 [3.40.6版本]
SL:PlayFlashBoxAudio()
停止音效
SL:StopSound(id)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| id | 是 | int | cfg_sound表对应id |
停止所有音效
SL:StopAllAudio()
聊天
发送文本显示到聊天页输入框
SL:SendInputMsgToChat(str)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| str | 是 | string | 文本内容 |
发送[普通消息]到聊天 [3.40.2版本]
SL:SendNormalMsgToChat(msg, channel)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| msg | 是 | string | 消息内容 |
| channel | 否 | int | 设置频道, 不设置默认当前聊天频道 |
发送[系统提示]到聊天框 [3.40.2版本]
SL:SendSystemMsgToChat(data)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| data | 是 | table | Msg: 提示内容 |
FColor: 字体颜色ID
BColor: 背景颜色ID
local mdata = {
Msg        = string.format("自动移动坐标点(%s:%s)不可到达", mapX, mapY),
FColor     = 154,
BColor     = 255,
}
SL:SendSystemMsgToChat(mdata)

发送[装备]到聊天
SL:SendEquipMsgToChat(itemData, channel)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| itemData | 是 | table | 装备数据 |
| channel | 否 | int | 设置频道, 不设置默认当前聊天频道 |
发送[位置]到聊天
SL:SendPosMsgToChat(channel)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| channel | 否 | int | 设置频道, 不设置默认当前聊天频道 |
发送[表情]到聊天
SL:SendEmojiMsgToChat(data, channel)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| data | 是 | table | 表情配置 |
| channel | 否 | int | 设置频道, 不设置默认当前聊天频道 |
私聊目标
SL:PrivateChatWithTarget(targetID, targetName)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| targetID | 是 | string | 目标玩家ID |
| targetName | 是 | string | 目标玩家名字 |
新增本地掉落消息到聊天 [3.40.7版本]
SL:AddDropChatMsgShow(data)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| data | 是 | table | Msg: 掉落内容富文本 |
FColor: 字体颜色ID
BColor: 背景颜色ID
dropType: 掉落分类ID (1-10)

例:

SL:AddDropChatMsgShow({
FColor = 253,
BColor = 255,
Msg = "测试掉落<outline size='1' color='#000'><font color='#ffffff'>物品 </font><font color='#ffffff'> 从 </font><font color='#28ef01'>一只牛</font><font color='#ffffff'> 身上掉落在 </font><font color='#FFA500'>盟重省(222,333)</font><font color='#ffffff'> 附近</font></outline>",
dropType = 1,
})

资源下载
SL:DownLoadRes(path, url, downloadCB)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| path | 是 | string | 保存的文件路径 |
| url | 是 | string | 下载资源地址 |
| downloadCB | 否 | function | 回调函数 |
SL:DownLoadRes("res/02.png", "https://engine-doc.996m2.com/Public/Uploads/2022-08-09/62f25c9fe04c0.png",test)

function test(...)
print("test",...)
end


小地图资源下载
SL:DownloadMiniMapRes(mapId, callback)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| mapId | 是 | int | 小地图Id |
| callback | 是 | function | 回调函数 |
local function callBack(isOk, path) -- isOk 下载是否成功, path 返回小地图路径
if isOk then
print("下载成功")
else
print("下载失败")
end
print("小地图路径",path)
end
SL:DownloadMiniMapRes(100, callBack)

删除GM缓存资源 [3.40.6版本]
SL:RemoveGMResFile(filePath)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| filePath | 是 | string | 文件路径 |
Actor
清空选中目标actor
SL:ClearTarget()
快速选择目标
SL:QuickSelectTarget(data)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| data | 是 | table | type: |
0: 玩家
50: 怪物
400: 英雄
imgNotice: 没有目标时是否创建范围圈
systemTips: 没有目标时是否弹提示
获取视野内的玩家
SL:FindPlayerInCurrViewField(noMainPlayer)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| noMainPlayer | 否 | boolean | false: 包含自己， 反之不包含 |
返回值：table
获取视野内的怪物
SL:FindMonsterInCurrViewField(noPetOfMainPlayer, noPetOfNetPlayer)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| noPetOfMainPlayer | 否 | boolean | true: 不包含自己的宠物， 反之包含 |
| noPetOfNetPlayer | 否 | boolean | false: 包含别人的宠物， 反之不包含 |
返回值：table
控件加入到元变量自动刷新的组件
SL:CustomAttrWidgetAdd(metaValue, widget)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| metaValue | 是 | string | 传入已配置元变量的字符串 |
&<元变量KEY/参数>&
例 :
红点变量U91: &<REDKEY/U91>&
角色名: &<USER_NAME>&
| widget | 是 | object | 文本控件 Text |
示例
local Text_count = GUI:Text_Create(GUI:Attach_LeftBottom(), "MONEY_COUNT", 200, 100, 16, "#00FF00", "")
SL:CustomAttrWidgetAdd("元宝数量: &<TMONEY/元宝>&", Text_count)
-- 多货币
-- SL:CustomAttrWidgetAdd("货币1,2总数量: &<TMONEY/1,2>&", Text_count)

检测控件是否可视 (用于检测在列表/滚动容器内控件)
SL:CheckNodeCanCallBack(node, touchPos)
默认检测层数 : 6

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| node | 是 | object | 控件 |
| touchPos | 是 | table | 当前接触坐标 |
示例
GUI:addMouseMoveEvent(node, {
onEnterFunc = function(touchPos)
if SL:CheckNodeCanCallBack(node, touchPos) then
local info = {
str = "tttt",
worldPos = touchPos,
}
SL:OpenCommonDescTipsPop(info)
end
end,
onLeaveFunc = function()
SL:CloseCommonDescTipsPop()
end
})

提升按钮
添加提升按钮

SL:AddUpgradeBtn(id, name, func)

等同TXT脚本命令addbutshow

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| id | 是 | int | 按钮id 必须唯一!!!! (同脚本命令加的id也不能重复) |
| name | 是 | string | 按钮展示文本 |
| func | 是 | function | 点击按钮跳转函数 |
删除提升按钮

SL:RemoveUpgradeBtn(id)

等同TXT脚本命令delbutshow

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| id | 是 | int | 按钮id 必须唯一!!!! (同脚本命令加的id也不能重复) |
鼠标模拟事件
模拟左键点击事件
SL:WinClick(widget)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| widget | 是 | 控件对象 |
坐标转换 [3.40.2版本]
世界坐标转化为地图坐标
SL:ConvertWorldPos2MapPos(worldX, worldY)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| worldX | 是 | 世界坐标X |
| worldY | 是 | 世界坐标Y |
地图坐标转化为世界坐标
SL:ConvertMapPos2WorldPos(mapX, mapY, centerOfGrid)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| mapX | 是 | 地图坐标X |
| mapY | 是 | 地图坐标Y |
| centerOfGrid | 否 | 是否在地图格中心 |
世界坐标转化为屏幕坐标
SL:ConvertWorldPos2Screen(worldX, worldY)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| worldX | 是 | 世界坐标X |
| worldY | 是 | 世界坐标Y |
屏幕坐标转化为世界坐标
SL:ConvertScreen2WorldPos(screenX, screenY)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| screenX | 是 | 屏幕坐标X |
| screenY | 是 | 屏幕坐标Y |
移动端交互 [3.40.2版本]
打开QQ
SL:OpenQQ()
加QQ
SL:JoinQQ(id)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| id | 是 | QQ号 |
加QQ群
SL:JoinQQGroup(key)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| key | 是 | QQ群key |
打开微信
SL:OpenWX()
添加地图特效 [3.40.4版本]
SL:AddMapSpecialEffect(ID, mapID, sfxId, x, y, loop)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| ID | 是 | int | 该地图特效标识 必须唯一!!!! |
| mapID | 是 | string | 添加到的地图ID |
| sfxId | 是 | int | 特效ID |
| x | 是 | int | 地图坐标X |
| y | 是 | int | 地图坐标Y |
| loop | 否 | boolean | 是否循环播放特效, 不填默认循环播放 |
| showType | 否 | int | 显示位置 0:在后面 1: 在前面 [3.40.8版本新增] |
删除地图特效 [3.40.4版本]
SL:RmvMapSpecialEffect(ID, mapID)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| ID | 是 | int | 该地图特效标识 必须唯一!!!! |
| mapID | 是 | string | 添加到的地图ID |
示例
local mapID = SL:GetMetaValue("MAP_ID")
SL:AddMapSpecialEffect(1111, mapID, 10, 295, 305)

添加Actor特效 [3.40.5版本]
SL:AddActorEffect(actorID, sfxID, isFront, offX, offY)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| actorID | 是 | int | 玩家id |
| sfxID | 是 | int | 特效ID |
| isFront | 否 | boolen | 是否在模型前 默认在前面 |
| offX | 否 | int | x偏移 |
| offY | 否 | int | y偏移 |
删除Actor特效 [3.40.5版本]
SL:RmvActorEffect(actorID, sfxID)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| actorID | 是 | int | 玩家id |
| sfxID | 是 | int | 特效ID |
强攻 [3.40.7版本]
SL:ForceAttack()
请求类
拉起充值
SL:RequestPay(payWay, currencyID, price, productIndex)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| payWay | 是 | int | 1 支付宝 2 花呗 3 微信 -1不选择(手机端接入SDK不选择支付渠道) |
| currencyID | 是 | int | 货币ID |
| price | 是 | int | 支付金额 |
| productIndex | 是 | int | 商品索引/商品ID |
兑换激活码
SL:RequestCDK(cdk)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| cdk | 是 | 激活码 |
请求改变PK模式
SL:RequestChangePKMode(pkmode)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| pkmode | 是 | pk模式 |
请求改变宠物战斗模式
SL:RequestChangePetPKMode(pkmode)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| pkmode | 是 | 宝宝模式 |
请求从仓库取出道具
SL:RequestPutOutStorageData(data)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| data | 是 | table — 道具数据 |
请求道具放入仓库
SL:RequestSaveItemToNpcStorage(data, pageIndex)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| data | 是 | table — 道具数据 |
| pageIndex | 否 | int — 指定仓库页下标 [3.40.9版本新增] |
请求使用道具
SL:RequestUseItem(itemData)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| itemData | 是 | table — 道具数据 |
请求使用英雄道具
SL:RequestUseHeroItem(itemData)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| itemData | 是 | table — 道具数据 |
拆分道具
SL:RequestSplitItem(data, num)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| data | 是 | table — 道具数据 |
| num | 是 | int — 数量 |
拆分道具(英雄)
SL:RequestSplitHeroItem(data, num)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| data | 是 | table — 道具数据 |
| num | 是 | int — 数量 |
请求购买商品 [3.40.3版本]
SL:RequestStoreBuy(index, count)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| index | 是 | int — 商品Index |
| count | 是 | int — 购买数量 |
召唤英雄或收回
SL:RequestCallOrOutHero()
请求玩家首饰盒状态
SL:RequestOpenPlayerBestRings()
请求英雄首饰盒状态
SL:RequestOpenHeroBestRings()
请求宠物锁定
SL:RequestLockPetID(targetID)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| targetID | 是 | 目标宠物ID |
请求取消宠物锁定
SL:RequestUnLockPetID(targetID)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| targetID | 是 | 目标宠物ID |
释放技能
SL:RequestLaunchSkill(skillID)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| skillID | 是 | 技能ID |
请求施法合击
SL:RequestMagicJointAttack()
查看目标玩家信息
SL:RequestLookPlayer(targetId, notForbid)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| targetID | 是 | 目标ID |
| notForbid | 否 | boolean —是否不判断地图禁止查看 |
请求开关开关型技能 [3.40.7版本]
SL:RequestOnOffSkill(skillID)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| skillID | 是 | 技能ID |
行会
请求行会申请列表
SL:RequestGuildAllyApplyList()
行会同盟申请操作
SL:RequestAllyOperate(guildID, param)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| guildID | 是 | 行会ID |
| param | 是 | 操作编号 1同意 2拒绝 |
请求行会成员列表
SL:RequestGuildMemberList()
请求世界行会列表
SL:RequestWorldGuildList(page)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| page | 是 | 分页id |
邀请玩家入会
SL:RequestGuildInviteOther(uid)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| uid | 是 | 玩家id |
踢出行会
SL:RequestSubGuildMember(uid)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| uid | 是 | 玩家id |
任命行会职位
SL:RequestAppointGuildRank(uid, rank)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| uid | 是 | 玩家id |
| rank | 是 | 职位id 1-5 |
组队
请求创建队伍
SL:RequestCreateTeam()
邀请玩家入队
SL:RequestInviteJoinTeam(uid, name)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| uid | 否 | 玩家id |
| name | 否 [ 两参数必须填一个 ] | 玩家昵称 |
拒绝组队邀请
SL:RequestRefuseTeamInvite(uid)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| uid | 是 | 玩家id |
同意组队邀请
SL:RequestAgreeTeamInvite(uid)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| uid | 是 | 玩家id |
同意申请入队
SL:RequestApplyAgree(uid)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| uid | 是 | 玩家id |
请求入队申请列表
SL:RequestApplyData()
请求附近队伍
SL:RequestNearTeam()
请求加入队伍
SL:RequestApplyJoinTeam(uid)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| uid | 是 | 队长id/队伍内任意玩家id |
召集队友
SL:RequestCallTeamMember()
离开队伍
SL:RequestLeaveTeam()
保存允许组队状态
SL:RequestSetTeamPermitStatus(status)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| status | 是 | int — 1允许 0不允许 |
踢出队伍
SL:RequestSubTeamMember(uid)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| uid | 是 | 玩家id |
移交队长
SL:RequestTransferTeamLeader(uid)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| uid | 是 | 玩家id |
交易
请求进行交易
SL:RequestTrade(uid)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| uid | 是 | 玩家id |
请求放入交易物品 [3.40.7版本]
SL:RequestPutInItem(makeindex, name)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| makeindex | 是 | 物品唯一ID |
| name | 是 | 物品名称 |
好友
请求好友列表
SL:RequestFriendList()
请求添加好友
SL:RequestAddFriend(uname)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| uname | 是 | 玩家昵称 |
删除好友
SL:RequestDelFriend(uid)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| uid | 是 | 玩家id |
好友加到黑名单
SL:RequestAddBlacklistByName(uname)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| uname | 是 | 玩家昵称 |
移出黑名单
SL:RequestOutBlacklist(uid)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| uid | 是 | 玩家id |
同意好友申请
SL:RequestAgreeFriendApply(uname)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| uname | 是 | 玩家昵称 |
删除好友申请数据
SL:RequestDelFriendApplyData(uname)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| uname | 是 | 玩家昵称 |
清空好友申请列表
SL:RequestClearFriendApplyList()
邮件
请求获取邮件列表 一次十条
SL:RequestMailList()
删除已读邮件
SL:RequestDelReadMail()
读邮件
SL:RequestReadMail(mailId)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| mailId | 是 | 邮件ID |
删除邮件
SL:RequestDelMail(mailId)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| mailId | 是 | 邮件ID |
邮件全部提取
SL:RequestGetAllMailItems()
邮件提取
SL:RequestGetMailItems(mailId)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| mailId | 是 | 邮件ID |
拍卖行
请求拍卖行上架列表
SL:RequestAuctionPutList(listType)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| listType | 是 | int — 1: 表示查询自己上架的物品，2: 表示查询参与过的 |
拍卖行请求上架
SL:RequestAuctionPutin(makeindex, count, bidPrice, buyPrice, currencyID, rebate)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| makeindex | 是 | 物品唯一ID |
| count | 是 | 数量 |
| bidPrice | 是 | 竞拍价格 |
| buyPrice | 是 | 一口价 |
| currencyID | 是 | 货币ID |
| rebate | 否 | 折扣 |
拍卖行请求下架
SL:RequestAuctionPutout(makeindex)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| makeindex | 是 | 物品唯一ID |
拍卖行请求重新上架
SL:RequestAuctionRePutin(makeindex, count, bidPrice, buyPrice, currencyID, rebate)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| makeindex | 是 | 物品唯一ID |
| count | 是 | 数量 |
| bidPrice | 是 | 竞拍价格 |
| buyPrice | 是 | 一口价 |
| currencyID | 是 | 货币ID |
| rebate | 否 | 折扣 |
拍卖行请求竞价
SL:RequestAuctionBid(makeindex, price)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| makeindex | 是 | 物品唯一ID |
| price | 是 | 竞拍价 |
拍卖行请求领取竞拍成功物品 [3.40.3版本]
SL:RequestAcquireBidItem(makeindex)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| makeindex | 是 | 物品唯一ID |
排行榜
请求排行榜数据
SL:RequestRankData(type)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| type | 是 | 类别ID |
请求玩家排行榜数据
SL:RequestPlayerRankData(userID, type)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| userID | 是 | 玩家ID |
| type | 是 | int — 玩家/英雄 1玩家 2英雄 |
任务
提交任务
SL:RequestSubmitMission(missionID)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| missionID | 是 | 任务ID |
玩家
请求玩家称号数据
SL:ResquestTitleList()
请求取下称号
SL:ResquestDisboardTitle()
请求激活称号
SL:ResquestActivateTitle(titleId)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| titleId | 是 | 称号id |
通知服务端 时装显示开关
SL:SendSuperEquipSetting(type)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| type | 是 | int — 2 : 设置显示神魔 |
1 : 设置时装显示
英雄
切换英雄状态
SL:RequestChangeHeroMode(type)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| type | 是 | 状态值 |
请求英雄称号数据
SL:ResquestTitleList_Hero()
英雄请求取下称号
SL:ResquestDisboardTitle_Hero()
英雄请求激活称号
SL:ResquestActivateTitle_Hero(titleId)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| titleId | 是 | 称号id |
通知服务端 英雄时装显示开关
SL:SendSuperEquipSetting_Hero(type)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| type | 是 | int — 2 : 设置显示神魔 |
1 : 设置时装显示
英雄请求锁定目标 [3.40.7版本]
SL:RequestLockTargetByHero(actorID, isPlayer)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| actorID | 是 | actorID |
| isPlayer | 是 | boolean — 是否人物 |
英雄取消锁定 [3.40.7版本]
SL:RequestCancelLockByHero()
合成
请求合成
SL:ResquestCompoundItem()
请求敏感词检测
SL:RequestCheckSensitiveWord(str, type, callback)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| str | 是 | string — 需要检测的文本 |
| type | 是 | 文本类型 int |
1 : 昵称类
2 : 聊天类
3 : 行会公告
| callback | 是 | function — 检测完毕的回调事件 |
事件传入参数: param1: boolean 能否通过 param2: 文本
邀请上马
SL:RequestInviteInHorse(uid)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| uid | 是 | 玩家id |
小地图 [3.40.2版本]
请求地图组队成员数据
SL:RequestMiniMapTeam()
请求地图怪物数据
SL:RequestMiniMapMonsters()
内功 [3.40.2版本]
请求内功技能数据
SL:RequestInternalSkillData(isHero)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| isHero | 否 | boolean — 是否请求英雄 |
请求经络穴位激活
SL:RequestAucPointOpen(typeID, aucPointID, isHero)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| typeID | 是 | 经络ID |
| aucPointID | 是 | 穴位ID |
| isHero | 否 | boolean — 是否请求英雄 |
修炼经络
SL:RequestMeridianLevelUp(typeID, isHero)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| typeID | 是 | 经络ID |
| isHero | 否 | boolean — 是否请求英雄 |
设置连击技能
SL:RequestSetComboSkill(key, skillID, isHero)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| key | 是 | int — 键位 (1, 2, 3, 4) |
| skillID | 是 | 技能ID |
| isHero | 否 | boolean — 是否请求英雄 |
请求设置内功条前置开关 并刷新显示 [3.40.8版本]
SL:RequestNGHudShow(show)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| show | 是 | boolean — 是否开启 默认true |
宝箱 [3.40.3版本]
请求获取宝箱物品奖励
SL:RequestGetGoldBoxReward()
请求再开启宝箱
SL:RequestOpenGoldBox()
属性加点 [3.40.4版本]
请求确认加属性点 [新版属性加点]
SL:RequestAddReinAttr_N(data, m_nBonusPoint)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| data | 是 | table — 加点数据table {"Bonus":[{"id":1,"value":1}, ...]} |
| m_nBonusPoint | 是 | int — 剩余加点数 |
求购 [3.40.5版本]
请求求购数据
SL:RequestPurchaseItemList(data)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| data | 是 | table — 请求参数 |
参数如下:
{
type      = 类型(int),                    -- 0: 世界求购, 1: 我的求购, 2: 我的已收
pageIndex = 请求页码(int),
stdmode     = 筛选的stdmode(string),        -- #分隔需要筛选的stdmode 例: "1#2#3#4"
currency    = 筛选货币(string),             -- ,分隔需要筛选的货币ID 例: "1,2,3"
sort        = 排序规则(int),                -- 0: 不排序 1: 单价正序 2: 单价倒序 3: 总价正序 4: 总价倒序
itemids     = 筛选道具idx(string),         -- ,分隔筛选的道具Index 例: "1001,1002,1003"
}

请求求购出售物品
SL:RequestPurchaseSell(data)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| data | 是 | table — 请求参数 {guid = 求购列表标识id, qty = 出售数量} |
请求上架求购物品
SL:RequestPurchasePutIn(data)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| data | 是 | table — 请求参数 |
参数如下:
{
qty     = 求购数量(int),
minqty    = 求购最小数量(int),
price     = 物品单价(int),
itemid    = 道具Index,
currency = 货币ID
}

请求下架求购物品
SL:RequestPurchasePutOut(guid)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| guid | 否 | 求购列表标识id, 不填则全部下架 |
请求取出求购已收物品
SL:RequestPurchaseTakeOut(guid)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| guid | 否 | 求购列表标识id, 不填则全部取出 |
请求点击NPC [3.40.5版本]
SL:RequestNPCTalk(npcID)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| npcID | 是 | NPCID |
996客服
请求打开996客服界面
SL:RequestOpen996ManualService()
鸿蒙 [3.40.4版本]
鸿蒙账号解绑
SL:HarmonyUnbind()
交易行截图相关 [3.40.7版本]
交易行截图测试
SL:TradingTestCapture()
PC端可以调用调试 报错的话可以查看控制台日志, 截图图片在当前项目cache中
交易行lua自定义截图
SL:AddTradingCustomCaptureTaskLua(openFunc, closeFunc, getNodeFunc)

| 参数名 | 必选 | 说明 |
| --- | --- | --- |
| openFunc | 是 | function — 打开当前界面方法 |
| closeFunc | 是 | function — 关闭当前界面方法 |
| getNodeFunc | 是 | function — 返回一个当前页面父节点panel，会截图这个父节点上所有子节点，并且这个父节点可以获取到getContentSize的可视截图大小 |
删除交易行lua自定义截图任务
SL:RemoveTradingCustomCaptureTask()
界面文件:
| UI ID | 说明 |
| MainLeftTop | 主界面 左上 |
| MainRightTop | 主界面 右上 |
| MainLeftBottom | 主界面 左下 |
| MainRightBottom | 主界面 右下 |
| MainMiniMap | 主界面 小地图 |
| MainAssist | 主界面 导航栏 |
| MainProperty | 主界面 属性栏 |
| MainSkill | 主界面 技能/按钮 |
| MainTarget | 主界面 目标栏 |
| MainTop | 主界面 最上方 |
| MainDig | 主界面 尸体挖掘 |
| MainSummons | 主界面 召唤物 |
| MainCollect | 主界面 采集怪 |
| MainProperty_win32 | PC 属性栏 |
| MainAssist_win32 | PC 导航栏 |
| MainNear | 附近列表展示 |
| MainBuffList | 主界面 buff图标配置展示 |
| LoginRolePanel | 人物登录界面 |
| SettingFrame | 设置 外框 |
| SettingBasic | 设置:基础 |
| SettingWinRange | 设置:视距 |
| SettingLaunch | 设置:战斗 |
| SettingProtect | 设置:保护 |
| SettingProtectSetting | 设置:保护相关设置 |
| SettingAuto | 设置:自动 |
| SettingSkillRank | 设置:技能优先级 |
| SettingSkillPanel | 设置:技能 |
| SettingPickSetting | 设置:拾取 |
| SettingAddMonsterName | 设置:增加怪物name |
| SettingAddMonsterType | 设置:增加怪物type |
| SettingBossTips | 设置:增加boss提醒 |
| SettingHelp | 设置:帮助 |
| SettingFrame_win32 | PC 设置:外框 |
| SettingBasic_win32 | PC 设置:基础 |
| SettingLaunch_win32 | PC 设置:战斗 |
| SettingProtect_win32 | PC 设置:保护 |
| SettingAuto_win32 | PC 设置:自动 |
| SettingHelp_win32 | PC 设置:帮助 |
| GameWorldConfirm | 游戏世界确认公告 |
| GuildFrame | 行会 外框 |
| GuildList | 行会列表 |
| GuildMain | 行会主界面 |
| GuildCreate | 行会创建 |
| GuildMember | 行会成员 |
| GuildEditTitle | 行会编辑 |
| GuildApplyList | 行会申请列表 |
| GuildAllyApply | 行会结盟申请列表 |
| GuildWarSponsor | 宣战、结盟结盟 |
| FuncDock | 功能菜单 |
| SocialFrame | 社交 外框 |
| Mail | 邮件 |
| NearPlayer | 附近 |
| Team | 组队 |
| Friend | 好友 |
| TeamApply | 组队申请 |
| TeamInvite | 组队邀请 |
| FriendApply | 好友申请 |
| FriendAdd | 添加好友 |
| FriendAddBlacklist | 添加黑名单 |
| TeamBeInvitedPop | 被邀请组队弹窗 |
| PlayerFrame | 玩家:人物面板外框 |
| PlayerEquip | 玩家:装备 |
| PlayerBaseAtt | 玩家:基础属性 |
| PlayerExtraAtt | 玩家:额外属性 |
| PlayerSkill | 玩家:技能 |
| PlayerSkillSetting | 技能设置 |
| PlayerTitle | 玩家:称号 |
| TitleTips | 称号提示 |
| PlayerSuperEquip | 玩家:神装 |
| PlayerBestRing | 玩家:生肖 |
| PlayerInternalState | 玩家:内功状态 |
| PlayerInternalSkill | 玩家:内功技能 |
| PlayerInternalMeridian | 玩家:内功经络 |
| PlayerInternalCombo | 玩家:内功连击 |
| HeroFrame | 英雄:主界面 |
| HeroEquip | 英雄:装备 |
| HeroBaseAtt | 英雄:基础属性 |
| HeroExtraAtt | 英雄:额外属性 |
| HeroSkill | 英雄:技能 |
| HeroTitle | 英雄:称号 |
| HeroSuperEquip | 英雄:神装 |
| HeroBestRing | 英雄:生肖 |
| HeroInternalState | 英雄:内功状态 |
| HeroInternalSkill | 英雄:内功技能 |
| HeroInternalMeridian | 英雄:内功经络 |
| HeroInternalCombo | 英雄:内功连击 |
| PlayerFrame_Look | 他人:玩家:主界面 |
| PlayerEquip_Look | 他人:玩家:装备 |
| PlayerTitle_Look | 他人:玩家:称号 |
| TitleTips_Look | 他人:称号提示 |
| PlayerSuperEquip_Look | 他人:玩家:神装 |
| PlayerBestRing_Look | 他人:玩家:生肖 |
| HeroFrame_Look | 他人:英雄:主界面 |
| HeroEquip_Look | 他人:英雄:装备 |
| HeroTitle_Look | 他人:英雄:称号 |
| HeroSuperEquip_Look | 他人:英雄:神装 |
| HeroBestRing_Look | 他人:英雄:生肖 |
| MergePlayerFrame | 人物和英雄二合一外框 |
| HeroState | 英雄状态 |
| HeroStateSelect | 英雄状态设置 |
| HeroStateThreeSelect | 英雄状态设置 |
| PlayerHeroFrame_Look_TradingBank | 交易行:玩家:主界面 |
| PlayerEquip_Look_TradingBank | 交易行:玩家:装备 |
| PlayerBaseAtt_Look_TradingBank | 交易行:玩家:基础属性 |
| PlayerExtraAtt_Look_TradingBank | 交易行:玩家:额外属性 |
| PlayerSkill_Look_TradingBank | 交易行:玩家:技能 |
| PlayerSuperEquip_Look_TradingBank | 交易行:玩家:神装 |
| PlayerTitle_Look_TradingBank | 交易行:玩家:称号 |
| PlayerBestRing_Look_TradingBank | 交易行:玩家:生肖 |
| HeroEquip_Look_TradingBank | 交易行:英雄:装备 |
| HeroBaseAtt_Look_TradingBank | 交易行:英雄:基础属性 |
| HeroExtraAtt_Look_TradingBank | 交易行:英雄:额外属性 |
| HeroSkill_Look_TradingBank | 交易行:英雄:技能 |
| HeroSuperEquip_Look_TradingBank | 交易行:英雄:神装 |
| HeroTitle_Look_TradingBank | 交易行:英雄:称号 |
| HeroBestRing_Look_TradingBank | 交易行:英雄:生肖 |
| TradingBankFrame | 交易行主界面 |
| Bag | 玩家:背包 |
| BagItem | 玩家:背包道具 |
| BagItemText | 玩家:背包文字 |
| BagItemEffect | 玩家:背包特效 |
| HeroBag | 英雄:背包 |
| MergeBag | 玩家、英雄:背包合并 |
| Storage | 仓库 |
| NPCStore | NPC商店 |
| NPCMakeDrug | 炼药 |
| NPCSellRepaire | 出售或修理 |
| ProgressBar | NPC 进度条 |
| AuctionMain | 拍卖行主界面 |
| AuctionWorld | 世界拍卖、行会拍卖 |
| AuctionBidding | 我的竞拍 |
| AuctionPutList | 我的上架 |
| AuctionPutin | 上架道具 |
| AuctionTimeout | 超时 |
| AuctionPutout | 下架道具 |
| AuctionBid | 竞拍 |
| AuctionBuy | 购买 |
| Stall | 摆摊 |
| StallSet | 摆摊:请输入商户信息 |
| StallPut | 摆摊:确认界面 |
| Trade | 交易 |
| TradeTips | 交易弹窗 |
| Rank | 排行榜 |
| StoreFrame | 商城外框 |
| StorePage | 商城内容 |
| StoreDetail | 商城快捷购买 |
| StoreRecharge | 商城充值 |
| RechargeQRCode | 充值二维码 |
| AutoUsePop | 自动使用 |
| CommonBubbleInfo | 被多人邀请组队、交易 |
| CommonTipsPop | 通用弹窗 |
| CommonDescTips | 通用描述tips |
| ItemSplitPop | 道具拆分弹窗 |
| TreasureBox | 宝箱道具 |
| GoldBox | 宝箱 |
| ItemTips | 道具tips |
| Chat | 聊天 |
| ChatExtend | 聊天拓展框 |
| PrivateChat_win32 | PC私聊记录 |
| Notice | 系统类通知 |
| MainMonster | 怪物大血条 |
| MonsterBelongNetPlayer | 快捷选中归属 |
| CompoundItem | 合成 |
| Item | 物品框 |
| ReinAttr | 转生加点 |
| SetWinSizePop | 设置分辨率 |
| CommonQuestion | 答题 |
| CommonVerification | 验证 |
| CommonSelectList | 选择下拉栏 |
| MiniMap | 小地图 |
| UIModel | 内观模型 |
| BeStrongUp | 提升按钮 |
| LoginServer | 登录账号 开门动画 |
| LoginAccount | 登录账号 |
| GUIFunction | 常用方法模块 |
| Notice | 系统类通知 |
| PurchaseMain | 求购主面板 |
| PurchaseWorld | 世界求购 |
| PurchaseMy | 我的求购 |
| PurchaseSell | 求购出售 |
| PurchasePutIn | 求购上架 |
| GUIUtil | 进入游戏最开始加载该文件, 在主界面加载之前 |
优先于原先的ssr/ssrgame/ssrmain.lua
！优先于LUA_EVENT_ENTER_WORLD 进游戏事件
派发事件

SL:onLUAEvent(eventID, data)

说明

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| eventID | 是 | string | 事件ID |
| data | 否 | any | 数据 |
返回值: 无
示例代码

SL:onLUAEvent(LUA_EVENT_EXPCHANGE, {value = 100})



注册游戏事件回调

SL:RegisterLUAEvent(eventID, eventTag, eventCB, widget)

说明

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| eventID | 是 | string | 事件ID |
| eventTag | 是 | string | 事件描述 |
| eventCB | 是 | function | 回调函数 |
| widget | 否 | obj | 界面对象 |
返回值: 无
示例代码

local function onRefAttr()
SL:Print("属性刷新...")
end
SL:RegisterLUAEvent(LUA_EVENT_EXPCHANGE, "属性刷新", onRefAttr)



注销游戏事件回调

SL:UnRegisterLUAEvent(eventID, eventTag)

说明

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| eventID | 是 | string | 事件ID |
| eventTag | 是 | string | 事件描述 |
返回值: 无
示例代码

SL:UnRegisterLUAEvent(LUA_EVENT_EXPCHANGE, "属性刷新")



事件ID
| 事件ID | 说明 | 参数 |
| LUA_EVENT_ROLE_PROPERTY_INITED | 玩家角色属性初始化完毕 | 无 |
| LUA_EVENT_ROLE_PROPERTY_CHANGE | 玩家属性变化时 | 无 |
| LUA_EVENT_LEVELCHANGE | 等级改变 | table — {currlevel = 当前等级, lastlevel = 上次等级} |
| LUA_EVENT_REINLEVELCHANGE | 转生等级改变 | table — {currReinLevel = 当前转生等级, lastReinLevel = 上次转生等级} |
| LUA_EVENT_HPMPCHANGE | HP/MP改变 | table — {curHP = curHP, maxHP = maxHP, curMP = curMP, maxMP = maxMP} |
| LUA_EVENT_EXPCHANGE | EXP改变 | table — {currexp = 当前经验值, changed = 改变值} |
| LUA_EVENT_BATTERYCHANGE | 电池电量改变 | int — 电池容量百分比值 |
| LUA_EVENT_NETCHANGE | 网络状态改变 | int — 网络类型 |
-1: 未知 0: wifi 1: 蜂窝
| LUA_EVENT_WEIGHTCHANGE | 负重改变 | table — {weight = 当前负重, wearWeight = 穿戴负重, handWeight = 腕力} |
| LUA_EVENT_PKMODECHANGE | pk模式改变 | int — 当前PK模式 |
| LUA_EVENT_AFKBEGIN | 自动挂机开始 |
| LUA_EVENT_AFKEND | 自动挂机结束 |
| LUA_EVENT_AUTOMOVEBEGIN | 自动寻路开始 | table — {mapID = 目标地图ID, x = 目标坐标X, y = 目标坐标Y} |
| LUA_EVENT_AUTOMOVEEND | 自动寻路结束 |
| LUA_EVENT_AUTOPICKBEGIN | 自动捡物开始 |
| LUA_EVENT_AUTOPICKEND | 自动捡物结束 |
| LUA_EVENT_MAINBUFFUPDATE | 主玩家buff刷新 | table — {actorID = 玩家id, buffID = buffID, type = 类型(0: 删除 1: 新增 2: 刷新)} |
| LUA_EVENT_BUFFUPDATE | 通用buff刷新 | table — {actorID = 玩家id, buffID = buffID, type = 类型(0: 删除 1: 新增 2: 刷新)} |
| LUA_EVENT_TALKTONPC | 与NPC对话 | table — {UserID = npcID, index = NPC配置ID, name = NPC名称} |
| LUA_EVENT_CHANGESCENE | 切换地图(包含同地图) | table — {mapID = mapID} |
| LUA_EVENT_MAPINFOCHANGE | 切换地图(不同地图) | table — {mapID = mapID, lastMapID = lastMapID} |
| LUA_EVENT_MAPINFOINIT | 地图初始化 | table — {mapID = mapID} |
| LUA_EVENT_MAP_STATE_CHANGE | 地图状态改变 | boolen — 是否在安全区域 |
| LUA_EVENT_MAP_SIEGEAREA_CHANGE | 地图攻城区域状态改变 | boolean — 是否进入攻城区域 | 支持版本号3.40.5以上 |
| LUA_EVENT_OPENWIN | 打开界面 | string — GUI界面ID | 支持版本号3.40.8以上 |
| LUA_EVENT_CLOSEWIN | 关闭界面 | string — GUI界面ID |
| LUA_EVENT_WINDOW_CHANGE | 窗体尺寸改变 |
| LUA_EVENT_DEVICE_ROTATION_CHANGED | 设备方向改变 |
| LUA_EVENT_MONEYCHANGE | 货币变化 | table — {id = 货币ID, count = 货币值} |
| LUA_EVENT_GUILD_MAIN_INFO | 行会信息刷新 |
| LUA_EVENT_GUILD_CREATE | 行会创建消耗 |
| LUA_EVENT_GUILD_WORLDLIST | 世界行会列表刷新 |
| LUA_EVENT_GUILD_APPLYLIST | 入会申请列表刷新 |
| LUA_EVENT_GUILDE_ALLY_APPLY_UPDATE | 结盟申请列表刷新 |
| LUA_EVENT_TRADE_MONEY_CHANGE | 对方交易货币改变 | table — {count = 货币数量} |
| LUA_EVENT_TRADE_MY_MONEY_CHANGE | 自己交易货币改变 | table — {count = 货币数量} |
| LUA_EVENT_TRADE_STATUS_CHANGE | 对方交易状态改变 |
| LUA_EVENT_TRADE_MY_STATUS_CHANGE | 自己交易状态改变 |
| LUA_EVENT_ADDFIREND | 添加好友 | string — 好友名 |
| LUA_EVENT_REMFIREND | 删除好友 | string — 好友名 |
| LUA_EVENT_JOINTEAM | 加入队伍 | string — 成员名 |
| LUA_EVENT_LEAVETEAM | 离开队伍 | string — 成员名 |
| LUA_EVENT_REF_ITEM_LIST | 刷新背包道具列表 |
| LUA_EVENT_PLAYER_EQUIP_CHANGE | 角色装备数据操作 | table — {MakeIndex = 唯一ID, Where = 装备位置, opera = 操作类型 ( 0:初始化 1:增加 2:删除 3:改变), ItemData = 装备数据} |
| LUA_EVENT_BAG_ITEM_CHANGE | 背包数据变化 | {opera = 操作类型 ( 0:初始化 1:增加 2:删除 3:改变), operID = 物品数据(table)} |
| LUA_EVENT_REF_HERO_ITEM_LIST | 刷新英雄背包道具列表 |
| LUA_EVENT_HERO_EQUIP_CHANGE | 英雄装备变化 | table — {MakeIndex = 唯一ID, Where = 装备位置, opera = 操作类型 ( 0:初始化 1:增加 2:删除 3:改变), ItemData = 装备数据} |
| LUA_EVENT_HERO_BAG_ITEM_CAHNGE | 英雄背包数据变化 | {opera = 操作类型 ( 0:初始化 1:增加 2:删除 3:改变), operID = 物品数据(table)} |
| LUA_EVENT_DISCONNECT | 断线 |
| LUA_EVENT_RECONNECT | 重连 |
| LUA_EVENT_TAKE_ON_EQUIP | 玩家穿戴装备 | table — {isSuccess = 是否成功, pos = 成功穿戴装备位} |
| LUA_EVENT_TAKE_OFF_EQUIP | 玩家脱掉装备 | table — {isSuccess = 是否成功, pos = 成功脱下装备位} |
| LUA_EVENT_HERO_TAKE_ON_EQUIP | 英雄穿戴装备 | table — {isSuccess = 是否成功} |
| LUA_EVENT_HERO_TAKE_OFF_EQUIP | 英雄脱掉装备 | table — {isSuccess = 是否成功} |
| LUA_EVENT_SETTING_CAHNGE | 设置项改变 |
| LUA_EVENT_BESTRINGBOX_STATE | 首饰盒状态改变 |
| LUA_EVENT_ACTOR_IN_OF_VIEW | 玩家/怪物/NPC进视野 | table — {id = ActorID} | 支持版本号3.40.3以上 |
| LUA_EVENT_ACTOR_OUT_OF_VIEW | 玩家/怪物/NPC出视野 | table — {id = ActorID} | 支持版本号3.40.3以上 |
| LUA_EVENT_DROPITEM_IN_OF_VIEW | 掉落物进视野 | table — {actorID = ActorID, item = 掉落物相关数据(table)} | 支持版本号3.40.5以上 |
| LUA_EVENT_DROPITEM_OUT_OF_VIEW | 掉落物出视野 | table — {actorID = ActorID} | 支持版本号3.40.5以上 |
| LUA_EVENT_TARGET_HP_CHANGE | 目标血量变化 | table — {actorID = 目标ID} |
| LUA_EVENT_TARGET_CAHNGE | 目标改变 | int — 目标ID |
| LUA_EVENT_ACTOR_OWNER_CHANGE | 目标归属改变 | table — {actorID = 目标ID} |
| LUA_EVENT_HERO_ANGER_CAHNGE | 英雄怒气改变 | table — {forceRefresh = boolean(true时禁止刷新)} |
| LUA_EVENT_PLAYER_BEHAVIOR_STATE_CAHNGE | 玩家行为状态改变（站立、走、跑等） | int — 主玩家动作 |
| LUA_EVENT_PLAYER_ACTION_BEGIN | 主玩家行为动作开始（站立、走、跑等） | table — {id = 玩家ID, act = 动作ID} | 支持版本号3.40.2以上 |
| LUA_EVENT_PLAYER_ACTION_COMPLETE | 主玩家行为动作结束（站立、走、跑等） | table — {id = 玩家ID, act = 动作ID} | 支持版本号3.40.2以上 |
| LUA_EVENT_NET_PLAYER_ACTION_BEGIN | 网络玩家行为动作开始（站立、走、跑等） | table — {id = 玩家ID, act = 动作ID} | 支持版本号3.40.2以上 |
| LUA_EVENT_NET_PLAYER_ACTION_COMPLETE | 网络玩家行为动作结束（站立、走、跑等） | table — {id = 玩家ID, act = 动作ID} | 支持版本号3.40.2以上 |
| LUA_EVENT_MONSTER_ACTION_BEGIN | 怪物行为动作开始（站立、走、跑等） | table — {id = 怪物ID, act = 动作ID} | 支持版本号3.40.2以上 |
| LUA_EVENT_MONSTER_ACTION_COMPLETE | 怪物行为动作结束（站立、走、跑等） | table — {id = 怪物ID, act = 动作ID} | 支持版本号3.40.2以上 |
| LUA_EVENT_ACTOR_GMDATA_UPDATE | 玩家/怪物 GM自定义数据改变 | table — {id = ActorID, data = GM自定义数据} | 支持版本号3.40.3以上 |
| LUA_EVENT_SKILL_INIT | 初始化技能 | table — 技能数据 |
| LUA_EVENT_SKILL_ADD | 新增技能 | table — 技能数据 |
| LUA_EVENT_SKILL_DEL | 删除技能 | table — 技能数据 |
| LUA_EVENT_SKILL_UPDATE | 技能更新 | table — 技能数据 |
| LUA_EVENT_SKILL_ONOFF | 开关型技能开关触发 | table — {skillID = 技能ID, isOn = boolen 是否开启} | 支持版本号3.40.8以上 |
| LUA_EVENT_HERO_SKILL_ADD | 英雄新增技能 | table — 技能数据 |
| LUA_EVENT_HERO_SKILL_DEL | 英雄删除技能 | table — 技能数据 |
| LUA_EVENT_HERO_SKILL_UPDATE | 英雄技能更新 | table — 技能数据 | 支持版本号3.40.9以上 |
| LUA_EVENT_SUMMON_MODE_CHANGE | 召唤物-状态改变 | table — {mode = int( 2:战斗 4:休息)} |
| LUA_EVENT_SUMMON_ALIVE_CHANGE | 召唤物-存活状态改变 | table — {status = boolean(是否存活)} |
| LUA_EVENT_BUBBLETIPS_STATUS_CHANGE | 气泡状态改变 | table — {id = 气泡id, status = 气泡状态 (boolean true: 加, false: 删), callback = function 气泡点击回调函数} |
| LUA_EVENT_PLAY_MAGICBALL_EFFECT | 脚本魔血球动画 | table — 各项参数 |
| LUA_EVENT_AUTOFIGHT_TIPS_SHOW | 自动战斗提示显示与否 | boolean |
| LUA_EVENT_AUTOMOVE_TIPS_SHOW | 自动寻路提示显示与否 | boolean |
| LUA_EVENT_AUTOPICK_TIPS_SHOW | 自动捡物提示显示与否 | boolean |
| LUA_EVENT_HERO_LOGIN_OROUT | 英雄登录/登出 | boolean true:登录, false:登出 |
| LUA_EVENT_REIN_ATTR_CHANGE | 转生点数据变化 |
| LUA_EVENT_ASSIST_MISSION_TOP | 主界面-辅助-任务置顶 | int — 置顶id |
| LUA_EVENT_ASSIST_MISSION_ADD | 主界面-辅助-任务增加 | table — 任务数据 |
| LUA_EVENT_ASSIST_MISSION_CHANGE | 主界面-辅助-任务改变 | table — 任务数据 |
| LUA_EVENT_ASSIST_MISSION_REMOVE | 主界面-辅助-任务移除 | table — 任务数据 |
| LUA_EVENT_ASSIST_MISSION_SHOW | 主界面-辅助-任务显示和隐藏 | boolean 是否显示任务栏 |
| LUA_EVENT_TEAM_MEMBER_UPDATE | 主界面-辅助-队伍刷新 |
| LUA_EVENT_TEAM_NEAR_UPDATE | 附近队伍刷新 |
| LUA_EVENT_TEAM_APPLY_UPDATE | 申请入队列表刷新 |
| LUA_EVENT_RANK_PLAYER_UPDATE | 排行榜个人数据刷新 | table — 选中排行榜个人数据 |
| LUA_EVENT_RANK_DATA_UPDATE | 排行榜分类数据刷新 | int — 分类ID |
| LUA_EVENT_BIND_MAINPLAYER | 绑定主玩家 |
| LUA_EVENT_PLAYER_MAPPOS_CHANGE | 主玩家位置改变 |
| LUA_EVENT_FRIEND_LIST_UPDATE | 好友列表刷新 |
| LUA_EVENT_FRIEND_APPLY | 收到好友申请 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_MAIL_UPDATE | 邮件列表刷新 |
| LUA_EVENT_ITEMTIPS_MOUSE_SCROLL | ITEMTIPS鼠标滚轮滚动 | 滚动位置 table — {x = x, y = y} |
| LUA_EVENT_PCMINIMAP_STATUS_CHANGE | PC 主界面小地图展示状态改变 | int — 展示状态 |
0: 不显示
1: 小地图尺寸1
2: 小地图尺寸2
3: 打开小地图界面
| LUA_EVENT_DARK_STATE_CHANGE | 黑夜状态改变 |
| LUA_EVENT_MONSTER_IGNORELIST_ADD | 设置-怪物忽略列表增加 | string — 怪物名字 |
| LUA_EVENT_BOSSTIPSLIST_ADD | 设置-boss提示-增加 | table — { 怪物名字, 1, “BOSS” } |
| LUA_EVENT_MONSTER_NAME_RM | 设置-怪物类型删除 | int — 怪物类型 |
| LUA_EVENT_SKILL_RANKDATA_ADD | 设置-技能数据添加 | table — 技能数据 |
| LUA_EVENT_SKILLBUTTON_DISTANCE_CHANGE | 技能边距调整 |
| LUA_EVENT_PLAYER_FRAME_PAGE_ADD | 角色框增加子页 | table — {child = 子页控件, index = 对应pageId, init = 是否初始化} |
| LUA_EVENT_PLAYER_FRAME_NAME_RRFRESH | 角色外框角色名刷新 |
| LUA_EVENT_PLAYER_LOOK_FRAME_PAGE_ADD | 查看他人角色框增加子页 | table — {child = 子页控件, index = 对应pageId, init = 是否初始化} |
| LUA_EVENT_PLAYER_GUILD_INFO_CHANGE | 玩家行会信息改变 |
| LUA_EVENT_HERO_FRAME_PAGE_ADD | 英雄框增加子页 | table — {child = 子页控件, index = 对应pageId, init = 是否初始化} |
| LUA_EVENT_HERO_FRAME_NAME_RRFRESH | 英雄框名字刷新 |
| LUA_EVENT_HERO_LOOK_FRAME_PAGE_ADD | 查看他人英雄框增加子页 | table — {child = 子页控件, index = 对应pageId, init = 是否初始化} |
| LUA_EVENT_TRAD_PLAYER_LOOK_FRAME_PAGE_ADD | 交易行查看他人玩家框增加子页 | table — {child = 子页控件, index = 对应pageId, init = 是否初始化} |
| LUA_EVENT_TRAD_HERO_LOOK_FRAME_PAGE_ADD | 交易行查看他人英雄框增加子页 | table — {child = 子页控件, index = 对应pageId, init = 是否初始化} |
| LUA_EVENT_SERVER_VALUE_CHANGE | 服务器下发的变量改变 | table — {key = key, value = value} |
| LUA_EVENT_MAIN_PLAYER_REVIVE | 主玩家复活 |
| LUA_EVENT_NET_PLAYER_REVIVE | 网络玩家复活 | table — {id = 玩家ID} | 支持版本号3.40.3以上 |
| LUA_EVENT_MONSTER_REVIVE | 怪物复活 | table — {id = 怪物ID} | 支持版本号3.40.3以上 |
| LUA_EVENT_MAIN_PLAYER_DIE | 主玩家死亡 |
| LUA_EVENT_NET_PLAYER_DIE | 网络玩家死亡 | table — {id = 玩家ID} | 支持版本号3.40.3以上 |
| LUA_EVENT_MONSTER_DIE | 怪物死亡 | table — {id = 怪物ID} | 支持版本号3.40.3以上 |
| LUA_EVENT_NPCLAYER_OPENSTATUS | NPC界面打开/关闭状态刷新 | boolean — true: 打开 false: 关闭 |
| LUA_EVENT_NPC_TALK | NPC对话 [打开TXT-NPC界面] | table — {id = NPCID, index = NPC配置ID, name = NPC名称} | 支持版本号3.40.2以上 |
| LUA_EVENT_MINIMAP_FIND_PATH | 寻路路径 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_MINIMAP_MONSTER | 小地图怪物数据刷新 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_MINIMAP_PLAYER | 小地图人物坐标刷新 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_MINIMAP_TEAM | 小地图组队成员数据刷新 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_MINIMAP_RELEASE | 小地图释放内存 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_PLAYER_INTERNAL_FORCE_CHANGE | 人物内力值改变 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_PLAYER_INTERNAL_EXP_CHANGE | 人物内功经验值改变 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_PLAYER_INTERNAL_LEVEL_CHANGE | 人物内功等级改变 | table — {lastLevel = 上次等级, curLevel = 当前等级} | 支持版本号3.40.3以上 |
| LUA_EVENT_INTERNAL_SKILL_ADD | 人物内功技能增加 | table — 技能数据 | 支持版本号3.40.2以上 |
| LUA_EVENT_INTERNAL_SKILL_DEL | 人物内功技能删除 | table — 技能数据 | 支持版本号3.40.2以上 |
| LUA_EVENT_INTERNAL_SKILL_UPDATE | 人物内功技能刷新 | table — 技能数据 | 支持版本号3.40.2以上 |
| LUA_EVENT_PLAYER_LEARNED_INTERNAL | 人物学习内功 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_MERIDIAN_DATA_REFRESH | 人物内功经络数据刷新 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_PLAYER_INTERNAL_DZVALUE_CHANGE | 人物内功斗转值改变/恢复 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_PLAYER_COMBO_SKILL_ADD | 人物连击技能增加 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_PLAYER_COMBO_SKILL_DEL | 人物连击技能删除 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_PLAYER_COMBO_SKILL_UPDATE | 人物连击技能刷新 | table — 技能数据 | 支持版本号3.40.2以上 |
| LUA_EVENT_PLAYER_SET_COMBO_REFRESH | 人物设置的连击技能刷新 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_PLAYER_COMBO_SKILLCD_STATE | 人物连击技能CD状态 | boolean — true: 可释放 |
| false: CD未到 | 支持版本号3.40.2以上 |
| LUA_EVENT_PLAYER_OPEN_COMBO_NUM | 人物开启连击格子数 | int — 格子数 | 支持版本号3.40.2以上 |
| LUA_EVENT_HERO_INTERNAL_FORCE_CHANGE | 英雄内力值改变 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_HERO_INTERNAL_EXP_CHANGE | 英雄内功经验值改变 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_HERO_INTERNAL_LEVEL_CHANGE | 英雄内功等级改变 | table — {lastLevel = 上次等级, curLevel = 当前等级} | 支持版本号3.40.3以上 |
| LUA_EVENT_HERO_INTERNAL_SKILL_ADD | 英雄内功技能增加 | table — 技能数据 | 支持版本号3.40.2以上 |
| LUA_EVENT_HERO_INTERNAL_SKILL_DEL | 英雄内功技能删除 | table — 技能数据 | 支持版本号3.40.2以上 |
| LUA_EVENT_HERO_INTERNAL_SKILL_UPDATE | 英雄内功技能刷新 | table — 技能数据 | 支持版本号3.40.2以上 |
| LUA_EVENT_HERO_LEARNED_INTERNAL | 英雄学习内功 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_HERO_MERIDIAN_DATA_REFRESH | 英雄内功经络数据刷新 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_HERO_INTERNAL_DZVALUE_CHANGE | 英雄内功斗转值改变/恢复 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_HERO_COMBO_SKILL_ADD | 英雄连击技能增加 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_HERO_COMBO_SKILL_DEL | 英雄连击技能删除 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_HERO_COMBO_SKILL_UPDATE | 英雄连击技能刷新 | table — 技能数据 | 支持版本号3.40.2以上 |
| LUA_EVENT_HERO_SET_COMBO_REFRESH | 英雄设置连击技能刷新 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_HERO_OPEN_COMBO_NUM | 英雄开启连击格子数 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_HERO_PROPERTY_CHANGE | 英雄属性变化 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_HERO_LEVEL_CHANGE | 英雄等级变化 | table — {currlevel = 当前等级, lastlevel = 上次等级} | 支持版本号3.40.9以上 |
| LUA_EVENT_HERO_REINLEVEL_CHANGE | 英雄转生等级变化 | table — {currReinLevel = 当前转生等级, lastReinLevel = 上次转生等级} | 支持版本号3.40.9以上 |
| LUA_EVENT_HERO_HPMP_CHANGE | 英雄HP/MP变化 | table — {curHP = curHP, maxHP = maxHP, curMP = curMP, maxMP = maxMP} | 支持版本号3.40.9以上 |
| LUA_EVENT_HERO_EXP_CHANGE | 英雄经验值变化 |  | 支持版本号3.40.9以上 |
| LUA_EVENT_NOTICE_SERVER | 顶部跑马灯 全服公告 | table — 消息参数内容 | 支持版本号3.40.2以上 |
| LUA_EVENT_NOTICE_SERVER_EVENT | 屏幕跑马灯 系统公告 | table — 消息参数内容 | 支持版本号3.40.2以上 |
| LUA_EVENT_NOTICE_SYSYTEM | 屏幕跑马灯公告 可控制Y轴 | table — 消息参数内容 | 支持版本号3.40.2以上 |
| LUA_EVENT_NOTICE_SYSYTEM_SCALE | 系统公告缩放 | table — 消息参数内容 | 支持版本号3.40.2以上 |
| LUA_EVENT_NOTICE_SYSYTEM_XY | 跑马灯公告 可控制XY轴 | table — 消息参数内容 | 支持版本号3.40.2以上 |
| LUA_EVENT_NOTICE_SYSYTEM_TIPS | 系统 提示弹窗 | table — 消息参数内容 | 支持版本号3.40.2以上 |
| LUA_EVENT_NOTICE_TIMER | 聊天上方倒计时公告 | table — 消息参数内容 | 支持版本号3.40.2以上 |
| LUA_EVENT_NOTICE_DELETE_TIMER | 移除倒计时公告 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_NOTICE_ITEM_TIPS | 飘字 物品获取/消耗提示 | table — 消息参数内容 | 支持版本号3.40.2以上 |
| LUA_EVENT_NOTICE_ATTRIBUTE | 飘字 属性变化 | table — 消息参数内容 | 支持版本号3.40.2以上 |
| LUA_EVENT_NOTICE_EXP | 飘字 经验变化 | table — 消息参数内容 | 支持版本号3.40.2以上 |
| LUA_EVENT_NOTICE_DROP | 公告 掉落物品提示 | table — 消息参数内容 | 支持版本号3.40.2以上 |
| LUA_EVENT_RICHTEXT_OPEN_URL | 富文本超链(href)点击触发 | string — href内容 | 支持版本号3.40.2以上 |
| LUA_EVENT_KF_STATUS_CHANGE | 跨服状态改变 | boolean — true:进入跨服 |
| false: 退出跨服 | 支持版本号3.40.2以上 |
| LUA_EVENT_QUICKUSE_DATA_OPER | 快捷栏道具数据变动触发 | table — {opera = 操作类型 ( 0:初始化 1:增加 2:删除 3:改变), param = 具体数据(table)} | 支持版本号3.40.2以上 |
| LUA_EVENT_ENTER_WORLD | 进入游戏世界 主界面已经初始化 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_LEAVE_WORLD | 离开游戏世界 小退触发 |  | 支持版本号3.40.2以上 |
| LUA_EVENT_PLAYER_IN_SAFEZONE_CHANGE | 主玩家安全区状态改变 |  | 支持版本号3.40.3以上 |
| LUA_EVENT_NET_PLAYER_IN_SAFEZONE_CHANGE | 网络玩家安全区状态改变 | table — {id = 玩家ID} | 支持版本号3.40.3以上 |
| LUA_EVENT_PLAYER_STALL_STATUS_CHANGE | 主玩家摆摊状态改变 |  | 支持版本号3.40.3以上 |
| LUA_EVENT_NET_PLAYER_STALL_STATUS_CHANGE | 网络玩家摆摊状态改变 | table — {id = 玩家ID} | 支持版本号3.40.3以上 |
| LUA_EVENT_PLAYER_HUSHEN_STATUS_CHANGE | 主玩家护身状态改变 |  | 支持版本号3.40.3以上 |
| LUA_EVENT_NET_PLAYER_HUSHEN_STATUS_CHANGE | 网络玩家护身状态改变 | table — {id = 玩家ID} | 支持版本号3.40.3以上 |
| LUA_EVENT_PLAYER_TEAM_STATUS_CHANGE | 主玩家组队状态改变 |  | 支持版本号3.40.3以上 |
| LUA_EVENT_NET_PLAYER_TEAM_STATUS_CHANGE | 网络玩家组队状态改变 | table — {id = 玩家ID} | 支持版本号3.40.3以上 |
| LUA_EVENT_PURCHASE_ITEM_LIST_PULL | 求购列表数据返回 | table | 支持版本号3.40.5以上 |
| LUA_EVENT_PURCHASE_ITEM_LIST_COMPLETE | 求购列表加载完成 | table — {type = 类型 0: 世界求购, 1: 我的求购, 2: 我的已收} | 支持版本号3.40.5以上 |
| LUA_EVENT_PURCHASE_SEARCH_ITEM_UPDATE | 求购搜索参数刷新 | string — 筛选的道具Index字符串 | 支持版本号3.40.5以上 |
| LUA_EVENT_PURCHASE_MYITEM_UPDATE | 我的求购数据刷新 | table — {type = 类型(1: 新增, 2: 删除, 3: 更新), isReceive = bool 是否为已收列表, item = 求购数据} | 支持版本号3.40.5以上 |
| LUA_EVENT_PURCHASE_WORLDITEM_UPDATE | 世界求购数据刷新 | table — {type = 类型(1: 新增, 2: 删除, 3: 更新), item = 求购数据} | 支持版本号3.40.5以上 |
| LUA_EVENT_RED_POINT_ADD | 红点增 (按红点表cfg_redpoint配置) | table — {id = 表配置id} | 支持版本号3.40.6以上 |
| LUA_EVENT_RED_POINT_DEL | 红点删 (按红点表cfg_redpoint配置) | table — {id = 表配置id} | 支持版本号3.40.6以上 |
| LUA_EVENT_FLYIN_BTN_ITEM_COMPLETE | 道具飞入指定按钮完成 | table — {itemIndex = 道具Index} | 支持版本号3.40.6以上 |
| LUA_EVENT_STORAGE_DATA_CHANGE | 仓库数据变动 | table — {opera = 操作类型 (1:增加 2:删除 3:改变 4:整理/刷新页), item = 物品数据, page = 仓库页签 } | 支持版本号3.40.7以上 |
| LUA_EVENT_HERO_LOCK_CHANGE | 英雄锁定刷新 |  | 支持版本号3.40.7以上 |
| LUA_EVENT_PLAYER_TITLE_CHANGE | 人物称号数据变动 | table — {opera = 类型 (1:初始化 2:增加 3:删除 4:激活 5:卸下 6: 清理全部称号)} | 支持版本号3.40.7以上 |
| LUA_EVENT_SKILL_ADD_TO_UI_WIN32 | PC端-添加技能到主界面触发 | table — {skill = 技能ID, pos = table 坐标位置} | 支持版本号3.40.7以上 |
| LUA_EVENT_SKILL_REMOVE_TO_UI_WIN32 | PC端-移除主界面技能触发 | table — {skill = 技能ID} | 支持版本号3.40.7以上 |
| LUA_EVENT_SKILL_CD_TIME_CHANGE | 技能CD时间变动 | table — {id = 技能ID, percent = 倒计时百分比(不为0时), time = 剩余CD时间} | 支持版本号3.40.7以上 |
| LUA_EVENT_PLAYER_EMBATTLE_CHANGE | 人物法阵刷新 |
| 后端UpdateEquipEffect命令添加 |  | 支持版本号3.40.8以上 |
| LUA_EVENT_PLAYER_SEX_CHANGE | 人物性别刷新 |  | 支持版本号3.40.8以上 |
| LUA_EVENT_HERO_EMBATTLE_CHANGE | 英雄法阵刷新 |
| 后端UpdateEquipEffect命令添加 |  | 支持版本号3.40.8以上 |
| LUA_EVENT_HERO_SEX_CHANGE | 英雄性别刷新 |  | 支持版本号3.40.8以上 |
| LUA_EVENT_HORSE_UP | 骑马上马事件 | table — {actorID = actorID} | 支持版本号3.40.8以上 |
| LUA_EVENT_HORSE_DOWN | 骑马下马事件 | table — {actorID = actorID} | 支持版本号3.40.8以上 |
| LUA_EVENT_ITEM_CUSTOM_ATTR | 物品变量变动 | table — { |
MakeIndex = 物品唯一id,
| data = 物品变量json } | 支持版本号3.40.8以上 |
| LUA_EVENT_MANUAL_SERVICE_MESSAGE_NEW | 客服会话新消息 | table — {message = 消息内容(string)} |
| LUA_EVENT_MANUAL_SERVICE_MESSAGE_UN_READ | 客服会话未读消息个数变化 | table — {unReadNums = 未读消息个数(int)} |
| LUA_EVENT_MANUAL_SERVICE_MESSAGE_CLOSE | 客服会话结束 |
| LUA_EVENT_NP_HACK_INFO_CALLBACK | NP回调触发 | table — {hackName = string 应用名, hackInfo = string 路径} | 支持版本号3.40.7以上 |
简单示例
主玩家添加足迹特效 :
SL:RegisterLUAEvent(LUA_EVENT_PLAYER_ACTION_BEGIN, "TTT", function(data)
local id = data and data.id
if id then
local posX = SL:GetMetaValue("ACTOR_POSITION_X", id)
local posY = SL:GetMetaValue("ACTOR_POSITION_Y", id)
if posX and posY then
local actBegin = data.act
if actBegin == 1 or actBegin == 6 or actBegin == 17 then
local eff = GUI:Effect_Create(GUI:Attach_SceneB(), string.format("foot_effect%s_%s%s", id, posX, posY), posX, posY, 0, 2133)
if eff then
GUI:Effect_addOnCompleteEvent(eff, function()
GUI:removeFromParent(eff)
end)
end
end
end
end
end)

触发函数返回true则阻断官方自带逻辑，返回false继续执行官方逻辑
触发函数会带参数

注册触发 SL:RegisterTrigger(eventName, eventCB)
注销触发 SL:UnRegisterTrigger(eventName)
例子 SL:RegisterTrigger(LUA_TRIGGER_CHAT_CLICK_PLAYER_NAME, function(userData) end)
| 触发名 | 触发参数 | 说明 |
| LUA_TRIGGER_CHAT_CLICK_PLAYER_NAME | table — {SendId = 角色ID, SendName = 角色名} | 聊天框点击玩家名 |
| LUA_TRIGGER_NOTICE_SHOW_ATTRIBUTES | table — 属性展示列表 | 属性提示通知 |
| LUA_TRIGGER_NOTICE_SHOW_GET_ITEM | table — {name = 物品名称, count = 数量, str = 文本, ishero = boolen(true为英雄)} | 获得物品提示 |
| LUA_TRIGGER_NOTICE_SHOW_COST_ITEM | table — {name = 物品名称, count = 数量, str = 文本, ishero = boolen(true为英雄)} | 消耗物品提示 |
| LUA_TRIGGER_NOTICE_SHOW_EXP_CHANGE | table — 显示参数 | 经验提示通知 |
视频教程
https://engine-doc.996m2.com/web/#/9/5026

20230422直播 透视戒指和目标下方显示拥有BUFF
20230422直播_buff和透视戒指功能.zip

buff示例
buff源码.zip

转盘示例
转盘.zip

PK模式源码
PK模式.zip

自动挂机按钮示例
自动挂机按钮.zip

充值面板
充值面板.zip

角色面板修改官方源码，增加页签
角色面板增加页签.zip

角色野蛮时增加特效，沿野蛮方向释放


-- 野蛮特效
local function moveEvent(data)
local actorID = data and data.id
if actorID then
local posX = SL:GetMetaValue("ACTOR_POSITION_X", actorID)
local posY = SL:GetMetaValue("ACTOR_POSITION_Y", actorID)
local dir = SL:GetMetaValue("ACTOR_DIR", actorID)
if data.act == 21 then
effectID = 131
local parent = SL:GetMetaValue("ACTOR_MOUNT_NODE", actorID)
local eff = GUI:Effect_Create(parent, string.format("%s_%s%s", actorID, posX, posY), 0, 0, 3, effectID, 0,0 , dir)
if eff then
GUI:Effect_addOnCompleteEvent(eff, function()
GUI:removeFromParent(eff)
end)
end
end
end
end
SL:RegisterLUAEvent(LUA_EVENT_PLAYER_ACTION_BEGIN, "GUIUtil", moveEvent)
SL:RegisterLUAEvent(LUA_EVENT_NET_PLAYER_ACTION_BEGIN, "GUIUtil", moveEvent)


登陆界面示例1.zip


登陆界面示例2.zip


登陆界面示例3.zip


裂神符.rar

超链广播.zip

轮盘-新框架.zip

BOSS墓碑.zip

场景特效示例.zip

背包示例.zip

前端获取装备的标记
function ssrGetItemFalg(addValues,pos)
local n = nil
if addValues then
for _, v in pairs(addValues) do
if v.Id == 19 then
n = v.Value
break
end
end
end
if not n then return 0 end
local mask = bit.lshift(1, pos)
local masked_n = bit.band(n, mask)
return bit.rshift(masked_n, pos)
end

local itemData = SL:GetMetaValue("EQUIP_DATA", 1)
if itemData and itemData.AddValues then
-- 对应TXT接口设置的1~32物品标记
for i = 0, 31 do
SL:Print("装备标记1111",i,ssrGetItemFalg(itemData.AddValues,i))
end
end

GmBox示例.zip

NPC界面(后端Say)添加动画
SL:RegisterLUAEvent("LUA_EVENT_NPCLAYER_OPENSTATUS", "GUIUtile", function(data)
local layer = SL:GetMetaValue("CURRENT_TALK_NPC_LAYER")
if layer then
GUI:Timeline_Window1(layer)
end
end)

地图场景特效示例
消息分为两种：一种是对 Lua 操作的； 另一种是对 TXT 进行操作
服务器使用Lua的技术 ：
接收网络消息 SL:RegisterLuaNetMsg(msgID, networkCB, widget), networkCB(msgID, n1, n2, n3, recvStr)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| msgID | 是 | int | 消息ID |
| networkCB | 是 | function | 接收消息的函数回调 |
| widget | 否 | obj | 绑定的界面(win)对象， 界面关闭则注销接收回调 |

注销网络消息接收 SL:UnRegisterLuaNetMsg(msgID)

发送网络消息 SL:SendLuaNetMsg(msgID, p1, p2, p3, sendStr)

Lua脚本接收客户端消息，代码写在 QFunction-0.lua
Lua自定义消息统一执行：handlerequest(actor, msgID, param1, param2, param3, str)
比如客户端发送消息号100

-- Lua脚本 接收消息
function handlerequest(actor, msgID, param1, param2, param3, str)
release_print("-----------------------------")
release_print(msgID)
release_print(param1)
release_print(param2)
release_print(param3)
release_print(str)
end

-- 客户端执行 发送消息
SL:SendLuaNetMsg(100, 1, 2, 3, "Hello World, This engine, for Lua!")


Lua脚本发送消息给客户端，支持 3个int和1个字符串，使用 sendluamsg
客户端注册对应消息号
比如脚本发送消息号1000

-- 客户端注册 接收消息
local function networkCB(msgID, p1, p2, p3, msgData)
SL:Print(msgID, p1, p2, p3, msgData)
end
SL:RegisterLuaNetMsg(1000, networkCB)

-- Lua脚本执行
sendluamsg(actor, 1000, 1, 2, 3, "我是来自服务器的消息 By Lua")

服务器使用TXT的技术 ：
接收网络消息 SL:RegisterNetMsg(msgID, networkCB, widget), networkCB(msgID, msgData)

| 参数名 | 必选 | 类型 | 说明 |
| --- | --- | --- | --- |
| msgID | 是 | int | 消息ID |
| networkCB | 是 | function | 接收消息的函数回调 |
| widget | 否 | obj | 绑定的界面(win)对象， 界面关闭则注销接收回调 |

注销网络消息接收 SL:UnRegisterNetMsg(msgID)

发送网络消息 SL:SendNetMsg(msgID, PARAM1, PARAM2, PARAM3, CUSTMSGPARAM)

注意！！！ 一个 msgID 只能注册一个回调

TXT脚本接收客户端消息，代码写在 QFunction-0.txt
TXT自定义消息监听触发：Message_xxx, xxx 为消息号ID
比如客户端发送消息号100

;接收来自客户端的消息号 100
[@Message_100]
#ACT
SENDMSG 0 收到消息，<$PARAM1>, <$PARAM2>, <$PARAM3>, <$CUSTMSGPARAM>

-- 客户端执行 发送消息
SL:SendNetMsg(100, 1, 2, 3, "Hello World, This engine, for TXT!")


TXT脚本发送消息给客户端，支持发字符串，使用 SENDCUSTMSG
客户端注册对应消息号
比如脚本发送消息号1000

-- 客户端注册 接收消息
local function networkCB(msgID, msgData)
SL:Print(msgID)
SL:Print(msgData)
end
SL:RegisterNetMsg(1000, networkCB)

TXT脚本执行
SENDCUSTMSG 1000 我是来自服务器的消息, By TXT

基础属性字段
| 字段名 | 类型 | 说明 | 示例用法 |
| Index | number | 道具索引ID | itemData.Index |
| MakeIndex | number | 道具唯一标识 | itemData.MakeIndex |
| Name | string | 道具名称 | itemData.Name |
| StdMode | number | 道具类型标准模式 | itemData.StdMode |
| Shape | number | 道具形状/子类型 | itemData.Shape |
| Looks | number | 道具外观ID | itemData.Looks |
| Color | number | 道具颜色品质 | itemData.Color |
| Desc | string | 道具描述 | itemData.Desc |
数量和持久度
| 字段名 | 类型 | 说明 | 示例用法 |
| OverLap | number | 道具数量/堆叠数 | itemData.OverLap |
| Dura | number | 当前持久度 | itemData.Dura |
| DuraMax | number | 最大持久度 | itemData.DuraMax |
| Weight | number | 道具重量 | itemData.Weight |
装备相关属性
| 字段名 | 类型 | 说明 | 示例用法 |
| Where | number | 装备位置 | itemData.Where |
| Source | number | 强化等级/强度 | itemData.Source |
| AniCount | number | 负重值或其他计数 | itemData.AniCount |
| Star | number | 星级 | itemData.Star |
| attribute | string | 基础属性字符串 | itemData.attribute |
特殊属性和效果
| 字段名 | 类型 | 说明 | 示例用法 |
| Values | table | 极品属性数组 | itemData.Values |
| sEffect | number | 特效ID | itemData.sEffect |
| bEffect | number | 背景特效ID | itemData.bEffect |
| newEffect | string | 新特效 | itemData.newEffect |
| newLooks | number | 新外观 | itemData.newLooks |
| show | number | 显示控制 | itemData.show |
绑定和限制
| 字段名 | 类型 | 说明 | 示例用法 |
| Bind | string | 绑定信息 | itemData.Bind |
| BindInfo | string | 绑定详细信息 | itemData.BindInfo |
| Need | number | 使用需求类型 | itemData.Need |
| startLimitTime | number | 限时开始时间 | itemData.startLimitTime |
| getServerTime | number | 服务器时间 | itemData.getServerTime |
扩展信息
| 字段名 | 类型 | 说明 | 示例用法 |
| ExtendInfo | table | 扩展信息对象 | itemData.ExtendInfo |
| ExtendInfo.Sockets | table | 宝石镶嵌槽 | itemData.ExtendInfo.Sockets |
| ExtendInfo.LH0 | table | 刀魂数据0 | itemData.ExtendInfo.LH0 |
| ExtendInfo.ItmSrc | string | 道具来源 | itemData.ExtendInfo.ItmSrc |
| ExAbil | table | 自定义属性 | itemData.ExAbil |
| ExAbil.abilex | string | 附加属性字符串 | itemData.ExAbil.abilex |
时间和计时
| 字段名 | 类型 | 说明 | 示例用法 |
| AddValues | table | 附加值数组(含时间) | itemData.AddValues |
| touBaoTimes | number | 投保次数 | itemData.touBaoTimes |
套装相关
| 字段名 | 类型 | 说明 | 示例用法 |
| suitid | string | 套装ID字符串 | itemData.suitid |
| originName | string | 原始名称 | itemData.originName |
回收和价值
| 字段名 | 类型 | 说明 | 示例用法 |
| huishou | string | 回收信息 | itemData.huishou |
| honour | string | 荣誉值信息 | itemData.honour |
| InsureGoldList | string | 投保金额列表 | itemData.InsureGoldList |
特殊道具字段
| 字段名 | 类型 | 说明 | 示例用法 |
| effectParam | string | 效果参数(药水等) | itemData.effectParam |
| TipsShowAttr | number | 是否显示属性(宠物装备) | itemData.TipsShowAttr |
| sDivParam1 | string | 物品装备表的ITEMPAEAM1 | itemData.sDivParam1 |
| sDivParam2 | string | 物品装备表的ITEMPAEAM2 | itemData.sDivParam2 |
具体用法可参考 ItemTips.lua
打开界面
Win_Open(filename)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| filename | 是 | string | 界面文件名, 目录默认GUILayout下 |
创建界面
Win_Create(ID, x, y, width, height, hideMain, hideLast, needVoice, escClose, isRevmsg, npcID, param)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| width | 是 | int | 宽度 |
| height | 是 | int | 高度 |
| hideMain | 否 | bool | 是否隐藏主界面 |
| hideLast | 否 | bool | 是否隐藏上一个界面 |
| needVoice | 否 | bool | 是否有音效 |
| escClose | 否 | bool | 是否按键盘ESC关闭界面 |
| isRevmsg | 否 | bool | 是否pc鼠标经过吞噬/触摸吞噬，默认true |
| npcID | 否 | int | 绑定的NPCID |
| param | 否 | int | 窗口创建层 0主界面层 1普通面板层 2通知层 默认1 |
[仅普通面板时 hideMain、hideLast、escClose参数生效]
注意此方法创建界面只做父节点
关闭界面
Win_Close(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 界面对象 |
Win_CloseByID(ID)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| ID | 是 | string | 界面ID |
通过界面ID关闭界面
Win_CloseByNPCID(NPCID)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| NPCID | 是 | int | NPCID |
通过NPCID关闭界面
Win_SetESCClose(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 界面对象 |
| value | 是 | bool | 是否关闭 |
通过键盘的Esc键关闭界面
Win_CloseAll()
关闭所有界面
获取界面控件
GetWindow(parent, ID)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 控件ID |
示例代码
local _parent = GUI:Win_Create("QSQ_challengeboss", 0, 0, 0, 0, false, false, true, false)
local LV_type = GUI:ListView_Create(_parent, "LV_type", 905, 65, 40, 450, 1)
if LV_type then
local template = GUI:Layout_Create(LV_type, "template", 0, 0, 40, 100)
if template then
GUI:Button_Create(template, "btn_switch", 0,0, "res/01/010022.png")
end
end
end
方法:一 根据父窗口对象与下级子控件ID获取对象
local LV_type = GUI:GetWindow(_parent,"LV_type")


方法:二 根据父窗口对象与多层子控件ID获取对象
local btn_switch = GUI:GetWindow(_parent,"LV_type/template/btn_switch")


方法:三 根据当前“桌面”打开的窗口控件ID获取对象
local _parent = GUI:GetWindow(nil,"QSQ_challengeboss")
local LV_type = GUI:GetWindow(nil,"QSQ_challengeboss/LV_type")

设置控件自定义参数
Win_SetParam(widget, param)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 界面对象 |
| param | 是 | int/string/bool | 参数内容 |
Win_GetParam(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 界面对象 |
获取控件自定义参数
设置界面拖拽

第一个参数 widget 必须是 GUI:Win_Create 创建的 第二个拖拽参数可以使用普通控件

Win_SetDrag(widget, dragLayer)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 界面对象 |
| dragLayer | 是 | obj | 拖拽区域控件 |
设置主界面隐藏
Win_SetMainHide(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 界面对象 |
| value | 是 | bool | 是否隐藏, 普通面板生效 |
设置是否按ESC键关闭窗口
Win_SetESCClose(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 界面对象 |
| value | 是 | bool | 能否关闭, 普通面板生效 |
设置界面绑定NPC
Win_BindNPC(widget, npcID)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 界面对象 |
| npcID | 是 | int | NPCID |
设置界面浮起
Win_SetZPanel(widget, zPanel)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 界面对象 |
| zPanel | 是 | obj | 控件对象 |
设置界面内鼠标右键吞噬
Win_SetSwallowRightMouseTouch(widget, state)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 界面对象 |
| state | 是 | bool | 是否吞噬 |
判断对象是否为空
Win_IsNull(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 对象 |
判断对象是否不为空
Win_IsNotNull(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 对象 |
加载UI文件
LoadExport(parent, filename)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| filename | 是 | string | 文件路径 |
Ctrl+f9 界面编辑器导出的lua文件

简单示例

local win = GUI:Win_Create("Win_1", 0, 0, 1136, 640)
GUI:LoadExport(win, "game_world_confirm")
-- ...

获取父节点的快捷子控件组
ui_delegate(parent)
返回值 : table [key 为控件名]

示例

local ui = GUI:ui_delegate(parent)
if ui.Text_attName then
GUI:Text_setString(ui.Text_attName, "------")
end

屏蔽自动修复坐标为整数
GUI:DisableFixPosition()

获取当前打开界面挂接点
Attach_Parent()
变化的
获取主界面左上挂接点
Attach_LeftTop()
获取主界面右上挂接点
Attach_RightTop()
获取主界面左下挂接点
Attach_LeftBottom()
获取主界面右下挂接点
Attach_RightBottom()
获取最上层UI挂接点
Attach_UITop()
获取上层场景挂接点
Attach_SceneF()
获取下层场景挂接点
Attach_SceneB()
获取主界面最底层左上挂接点
Attach_LeftTop_B()
获取主界面最底层右上挂接点
Attach_RightTop_B()
获取主界面最底层左下挂接点
Attach_LeftBottom_B()
获取主界面最底层右下挂接点
Attach_RightBottom_B()
获取主界面最顶层左上挂接点
Attach_LeftTop_T()
获取主界面最顶层右上挂接点
Attach_RightTop_T()
获取主界面最顶层左下挂接点
Attach_LeftBottom_T()
获取主界面最顶层右下挂接点
Attach_RightBottom_T()
获取自带父节点 [挂接点ID: 101-111]
Win_FindParent(ID)
设置坐标
setPosition(widget, x, y)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| x | 是 | int | 横坐标 |
| y | 是 | int | 纵坐标 |
getPosition(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
获取坐标
local pos = GUI:getPosition(widget)
SL:Print("x",pos.x)
SL:Print("y",pos.y)

setPositionX(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | int | 横坐标 |
设置横坐标（纵坐标不变）
getPositionX(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
获取横坐标
setPositionY(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | int | 纵坐标 |
设置纵坐标（横坐标不变）
getPositionY(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
获取纵坐标
设置控件锚点
setAnchorPoint(widget, x, y)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| x | 是 | int | 横坐标 |
| y | 是 | int | 纵坐标 |
示例代码
GUI:setAnchorPoint(parent, 0, 0)        -- 左 下
GUI:setAnchorPoint(parent, 0, 0.5)      -- 左 中
GUI:setAnchorPoint(parent, 0, 1)        -- 左 上
GUI:setAnchorPoint(parent, 0.5, 0)      -- 中 下
GUI:setAnchorPoint(parent, 0.5, 0.5)    -- 中 中
GUI:setAnchorPoint(parent, 0.5, 1)      -- 中 上
GUI:setAnchorPoint(parent, 1, 0)        -- 右 下
GUI:setAnchorPoint(parent, 1, 0.5)      -- 右 中
GUI:setAnchorPoint(parent, 1, 1)        -- 右 上

getAnchorPoint(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
获取控件锚点
设置控件尺寸大小
setContentSize(widget, sizeW, sizeH)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| sizeW | 是 | int | 宽度 |
| sizeH | 是 | int | 长度 |
getContentSize(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
获取控件尺寸大小(纹理大小 不考虑缩放)
getBoundingBox(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
获取控件尺寸大小(考虑缩放的真实大小)
设置忽略设置的自定义尺寸大小
setIgnoreContentAdaptWithSize(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | boolean | 是否忽略用户定义尺寸大小 |
设置控件标签
setTag(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | int | 标签值 |
getTag(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
获取控件标签
设置控件名字
setName(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | string | 名字 |
设置控件置灰
setGrey(widget, isGrey)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| isGrey | 是 | bool | 是否置灰 |
设置控件旋转角度
setRotation(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | int | 旋转角度（0 - 360） |
getRotation(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
设置控件X轴倾斜角度
setRotationSkewX(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | int | 倾斜角度（0 - 360） |
设置控件Y轴倾斜角度
setRotationSkewY(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | int | 倾斜角度（0 - 360） |
设置控件可见性
setVisible(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | bool | 是否显示 |
getVisible(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
获取控件是否显示状态
设置控件可用性
setEnabled(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | bool | 是否可用 |
设置控件不透明度
setOpacity(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | int | 不透明度(0-255), 默认255 |
getOpacity(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
获取控件不透明度
设置控件缩放
setScale(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | float | 缩放比例, 默认1.0 |
getScale(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
获取控件缩放比例
setScaleX(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | float | 缩放比例, 默认1.0 |
设置控件X轴方向缩放
getScaleX(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
获取控件X轴方向缩放比例
setScaleY(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | float | 缩放比例, 默认1.0 |
设置控件Y轴方向缩放
getScaleY(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
获取控件Y轴方向缩放比例
设置控件翻转
setFlippedX(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | bool | X轴方向是否翻转 |
设置水平X轴方向翻转
getFlippedX(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
获取是否水平翻转
setFlippedY(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| value | 是 | bool | Y轴方向是否翻转 |
垂直Y轴方向翻转
getFlippedY(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
获取是否垂直翻转
设置控件渲染层级
setLocalZOrder(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | int | 渲染层级, 值越大显示越靠前 |
设置控件在父节点的渲染层级
设置控件是否跟随父控件变化透明度
setCascadeOpacityEnabled(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | bool | 是否跟随 |
设置控件的所有子控件是否跟随变化透明度
setChildrenCascadeOpacityEnabled(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | bool | 是否跟随 |
获得控件世界坐标
getWorldPosition(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
convertToWorldSpace(widget, x, y)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| x | 是 | int | 节点坐标X |
| y | 是 | int | 节点坐标Y |
对应控件的节点坐标转换为世界坐标
convertToNodeSpace(widget, x, y)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| x | 是 | int | 世界坐标X |
| y | 是 | int | 世界坐标Y |
世界坐标转换为对应控件的节点坐标
加载子控件
addChild(widget, child)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 父控件对象 |
| child | 是 | obj | 子控件对象) |
克隆控件
Clone(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
引用计数加1
GUI:addRef(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
引用计数减1
GUI:decRef(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
自动释放
GUI:autoDecRef(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
设置控件是否可以触摸
setTouchEnabled(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | bool | 是否触摸 |
getTouchEnabled(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
获取控件是否可以触摸
delayTouchEnabled(widget, delay)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| delay | 否 | float | 延迟触摸间隔 |
设置延迟可触摸
setMouseEnabled(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | bool | 是否鼠标触摸 |
设置控件是否可以鼠标触摸
设置控件是否触摸吞噬
setSwallowTouches(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | bool | 是否触摸吞噬 |
getSwallowTouches(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
获取控件是否触摸吞噬
setMouseRSwallowTouches(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
设置控件吞噬鼠标按键事件 [检查自身触摸吞噬时]
获取控件节点
getParent(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 子控件对象 |
获取父节点
getChildren(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 父控件对象 |
获取控件所有子节点
getName(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
获取控件名字
getChildByName(widget, name)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 父控件对象 |
| name | 是 | string | 控件名字 |
通过控件名字获取子节点
getChildByTag(widget, tag)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 父控件对象 |
| tag | 是 | int | 控件标记 |
通过控件标记获取子节点
删除控件
removeAllChildren(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
移除传入控件的所有子节点
removeFromParent(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
将传入控件从父节点上移除
removeChildByName(widget, name)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| name | 是 | string | 控件名字 |
通过名字删除传入控件的对应子节点
设置控件点击事件
addOnClickEvent(widget, func)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| func | 是 | function | 回调函数 |
设置控件触摸事件
addOnTouchEvent(widget, func)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| func | 是 | function | 回调函数 |

示例 1

-- 添加长按事件, 长按0.5秒触发
GUI:addOnTouchEvent(btn, function(sender, type)
-- sender: 传入控件自身
-- type: 触摸类型 int 0 - 3
if type == SLDefine.TouchEventType.began then           -- 0 触摸开始
if not sender._clicking then
sender._clicking = true
SL:scheduleOnce(sender, function()
sender._clicking = false
SL:Print("长按触发---")
end, 0.5)
end
elseif type == SLDefine.TouchEventType.moved then       -- 1 触摸移动



elseif type == SLDefine.TouchEventType.ended or type == SLDefine.TouchEventType.canceled then       -- 2 触摸结束 3 触摸取消
if sender._clicking then
GUI:stopAllActions(sender)
sender._clicking = false
SL:Print("单击触发---")
end
end
end)


示例 2

-- 添加双击事件 0.3秒间隔
local function doubleCallBack()
SL:Print("双击触发---")
end
GUI:addOnTouchEvent(btn, function(sender, type)
-- sender: 传入控件自身
-- type: 触摸类型 int 0 - 3
if type == SLDefine.TouchEventType.ended then       -- 2 触摸结束
if doubleCallBack then -- 双击事件
if not sender._lastClick then
sender._lastClick = true
sender._clickDelayHandler = SL:ScheduleOnce(function()
SL:Print("单击触发---")
sender._lastClick = nil
end, 0.3)
else
if sender._clickDelayHandler then
SL:UnSchedule(sender._clickDelayHandler)
sender._clickDelayHandler = nil
end
-- 双击回调方法
if doubleCallBack then
doubleCallBack()
end
sender._lastClick = nil
end
end
end
end)

getTouchBeganPosition(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
获取控件触摸开始时位置
getTouchMovePosition(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
获取控件触摸移动时位置
getTouchEndPosition(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
获取控件触摸结束时位置
设置控件长按触发事件
addOnLongTouchEvent(widget, func)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| func | 是 | function | 回调函数 |
设置控件鼠标进入/移出事件
addMouseMoveEvent(widget, param)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| param | 是 | table | onEnterFunc: function 鼠标进入回调函数 |
onLeaveFunc: function 鼠标移出回调函数
onInsideFunc: function 鼠标一直在内部回调函数

例 :

GUI:addMouseMoveEvent(button,
{
onEnterFunc = function()
SL:Print("enter!")
end,
onLeaveFunc = function()
SL:Print("leave!")
end
}
)

设置鼠标按钮事件
addMouseButtonEvent(widget, param)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| param | 是 | table | onRightDownFunc: function 鼠标右键点击事件 |
OnRightUpFunc: function 鼠标右键松开事件
needTouchPos: boolean 需要传入鼠标触摸位置
OnScrollFunc: function 鼠标滚轮滚动事件[3.40.8版本新增]
OnDoubleLFunc: function 鼠标左键双击事件[3.40.9版本新增]
checkIsVisible: boolean 检查控件可见 [3.40.9版本新增]
checkTouchEnable: boolean 检查控件可点性[3.40.9版本新增]

例 :

GUI:addMouseButtonEvent(btn, {onRightDownFunc = function()
SL:Print("right!!!!")
end})

设置鼠标经过控件显示文本
addMouseOverTips(widget, str, pos, anr, param)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| str | 是 | string | 文本 |
| pos | 是 | table | 位置 |
| anr | 是 | table | 锚点 |
| param | 否 | table | checkCallback: function 检查接触点是否能展示[函数传入参数: pos |
返回: true / false ]

例 :

local param = {
checkCallback = function(touchPos)
if touchPos and GUI:isClippingParentContainsPoint(Image_icon, touchPos) then
return true
end
return false
end
}
GUI:addMouseOverTips(Image_icon, "DESC_____", nil, nil, param)

设置控件是否触摸吞噬
setSwallowTouches(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | bool | 是否吞噬 |

例 :

local layout1 = GUI:Layout_Create(parent, "layout1", 0, 0, 100, 100, true)
local layout2 = GUI:Layout_Create(layout1, "layout2", 0, 0, 100, 100, true)
GUI:setSwallowTouches(layout2,true) -- 触摸layer2层 不会触发 layer1层 触摸回调函数
GUI:setSwallowTouches(layout2,false) -- 触摸layer2层 同时触发 layer1层 触摸回调函数

获取控件是否触摸吞噬
getSwallowTouches(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
获取控件是否吞噬
检查触摸位置是否被父节点裁剪
isClippingParentContainsPoint(widget, position)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| position | 是 | table | 世界坐标 |
开启定时器
schedule(widget, callback, delay)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| callback | 是 | function | 回调函数 |
| delay | 是 | int | 时间间隔 |

例 :

local function showTime()
print("倒计时ing")
end
GUI:schedule(node, showTime, 1)

unSchedule(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
停止定时器
键盘监听事件
addKeyboardEvent(codeKeys, pressedCB, releaseCB, checkFullSort)
注册键盘监听(快捷键)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| codeKeys | 是 | string / table | 要监听的键盘键key |
| pressedCB | 是 | function | 按下回调 |
| releaseCB | 否 | function | 松开回调 |
| checkFullSort | 否 | boolean | 兼容全顺序键盘key排列, 针对监听多键 [3.40.7版本] |
键盘键key 如下 :
"KEY_NONE",
"KEY_PAUSE",
"KEY_SCROLL_LOCK",
"KEY_PRINT",
"KEY_SYSREQ",
"KEY_BREAK",
"KEY_ESCAPE",
"KEY_BACKSPACE",
"KEY_TAB",
"KEY_BACK_TAB",
"KEY_RETURN",
"KEY_CAPS_LOCK",
"KEY_SHIFT",
"KEY_RIGHT_SHIFT",
"KEY_CTRL",
"KEY_RIGHT_CTRL",
"KEY_ALT",
"KEY_RIGHT_ALT",
"KEY_MENU",
"KEY_HYPER",
"KEY_INSERT",
"KEY_HOME",
"KEY_PG_UP",
"KEY_DELETE",
"KEY_END",
"KEY_PG_DOWN",
"KEY_LEFT_ARROW",
"KEY_RIGHT_ARROW",
"KEY_UP_ARROW",
"KEY_DOWN_ARROW",
"KEY_NUM_LOCK",
"KEY_KP_PLUS",
"KEY_KP_MINUS",
"KEY_KP_MULTIPLY",
"KEY_KP_DIVIDE",
"KEY_KP_ENTER",
"KEY_KP_HOME",
"KEY_KP_UP",
"KEY_KP_PG_UP",
"KEY_KP_LEFT",
"KEY_KP_FIVE",
"KEY_KP_RIGHT",
"KEY_KP_END",
"KEY_KP_DOWN",
"KEY_KP_PG_DOWN",
"KEY_KP_INSERT",
"KEY_KP_DELETE",
"KEY_F1",
"KEY_F2",
"KEY_F3",
"KEY_F4",
"KEY_F5",
"KEY_F6",
"KEY_F7",
"KEY_F8",
"KEY_F9",
"KEY_F10",
"KEY_F11",
"KEY_F12",
"KEY_SPACE",
"KEY_EXCLAM",
"KEY_QUOTE",
"KEY_NUMBER",
"KEY_DOLLAR",
"KEY_PERCENT",
"KEY_CIRCUMFLEX",
"KEY_AMPERSAND",
"KEY_APOSTROPHE",
"KEY_LEFT_PARENTHESIS",
"KEY_RIGHT_PARENTHESIS",
"KEY_ASTERISK",
"KEY_PLUS",
"KEY_COMMA",
"KEY_MINUS",
"KEY_PERIOD",
"KEY_SLASH",
"KEY_0",
"KEY_1",
"KEY_2",
"KEY_3",
"KEY_4",
"KEY_5",
"KEY_6",
"KEY_7",
"KEY_8",
"KEY_9",
"KEY_COLON",
"KEY_SEMICOLON",
"KEY_LESS_THAN",
"KEY_EQUAL",
"KEY_GREATER_THAN",
"KEY_QUESTION",
"KEY_AT",
"KEY_CAPITAL_A",
"KEY_CAPITAL_B",
"KEY_CAPITAL_C",
"KEY_CAPITAL_D",
"KEY_CAPITAL_E",
"KEY_CAPITAL_F",
"KEY_CAPITAL_G",
"KEY_CAPITAL_H",
"KEY_CAPITAL_I",
"KEY_CAPITAL_J",
"KEY_CAPITAL_K",
"KEY_CAPITAL_L",
"KEY_CAPITAL_M",
"KEY_CAPITAL_N",
"KEY_CAPITAL_O",
"KEY_CAPITAL_P",
"KEY_CAPITAL_Q",
"KEY_CAPITAL_R",
"KEY_CAPITAL_S",
"KEY_CAPITAL_T",
"KEY_CAPITAL_U",
"KEY_CAPITAL_V",
"KEY_CAPITAL_W",
"KEY_CAPITAL_X",
"KEY_CAPITAL_Y",
"KEY_CAPITAL_Z",
"KEY_LEFT_BRACKET",
"KEY_BACK_SLASH",
"KEY_RIGHT_BRACKET",
"KEY_UNDERSCORE",
"KEY_GRAVE",
"KEY_A",
"KEY_B",
"KEY_C",
"KEY_D",
"KEY_E",
"KEY_F",
"KEY_G",
"KEY_H",
"KEY_I",
"KEY_J",
"KEY_K",
"KEY_L",
"KEY_M",
"KEY_N",
"KEY_O",
"KEY_P",
"KEY_Q",
"KEY_R",
"KEY_S",
"KEY_T",
"KEY_U",
"KEY_V",
"KEY_W",
"KEY_X",
"KEY_Y",
"KEY_Z",
"KEY_LEFT_BRACE",
"KEY_BAR",
"KEY_RIGHT_BRACE",
"KEY_TILDE",
"KEY_EURO",
"KEY_POUND",
"KEY_YEN",
"KEY_MIDDLE_DOT",
"KEY_SEARCH",
"KEY_DPAD_LEFT",
"KEY_DPAD_RIGHT",
"KEY_DPAD_UP",
"KEY_DPAD_DOWN",
"KEY_DPAD_CENTER",
"KEY_ENTER",
"KEY_PLAY",


例 :

local function pressedCB()
SL:Print("Presss!!!!!!!!!!!!!!")
end
local function releaseCB()
SL:Print("release!!!!!!!!!!!!!!")
end



GUI:addKeyboardEvent("KEY_F7", pressedCB, releaseCB)

removeKeyboardEvent(codeKeys)
移除键盘监听(快捷键)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| codeKeys | 是 | string / table | 要移除监听的键盘键key |

例 :

GUI:removeKeyboardEvent("KEY_F7")

添加控件状态监听事件
addStateEvent(widget, func)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| func | 是 | function | 回调函数 |
eventName: 事件名
"enter" : 控件加载
"exit"  : 控件移除


例:

local t = GUI:Image_Create(-1, "21", 500, 400, "res/private/npc/bg_zbhstips_01.png")
GUI:addStateEvent(t, function(eventName)
SL:Print(eventName)
end)
GUI:addChild(GUI:Attach_LeftBottom(), t)
SL:ScheduleOnce(function()
GUI:removeChildByID(GUI:Attach_LeftBottom(), "21")
end, 3)

ShowWorldTips(tips, worldPos, anchorPoint)
显示文本Tips

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| tips | 是 | string | 显示文本 |
| worldPos | 是 | table | 世界坐标 |
| anchorPoint | 是 | table | 锚点 |

例 ：

GUI:ShowWorldTips("测试", GUI:p(400, 400), GUI:p(0, 0))

HideWorldTips()
关闭文本Tips
UserUILayout(pNode, param)
自适应布局

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| pNode | 是 | obj | 控件对象 |
| param | 是 | table | 布局参数 |
返回值 : table {width = width, height = height}
布局参数说明
param = {
dir： 1：垂直; 2: 水平; 3： 两者
gap:  table值, 其中 x: 左右间距; y: 上下间距; l: 左边距; t: 上边距
addDir: 动画增长方式 1: 从上到下（从左到右）（多行从左上角）, 2：中间到两边（多行从右上角）, 3：从下到上（从右到左）
colnum: 多行列数（dir必须是3）
autosize: bool 根据内容自适应容器
sortfunc: function 排序函数
interval：增长方式动画播放时间间隔, 不传值则不播放动画
rownums ： 每一行的数量table ; 例如：rownums = {3, 2} （第一行3个元素，第二行2个元素）
}

[[示例代码]]
local Layout = GUI:Layout_Create(parent, "Layout", 50,50, 500.00, 200.00, false)
GUI:Layout_setBackGroundColorType(Layout, 1)
GUI:Layout_setBackGroundColor(Layout, "#96c8ff")
GUI:Layout_setBackGroundColorOpacity(Layout, 140)



local Button_1 = GUI:Button_Create(Layout, "button_1", 100.00, 0.00, "res/public/1900000660.png")
GUI:Win_SetParam(Button_1, 1)
GUI:Button_setTitleText(Button_1, "button_1")
local Button_2 = GUI:Button_Create(Layout, "button_2", 200.00, 0.00, "res/public/1900000660.png")
GUI:Win_SetParam(Button_2, 2)
GUI:Button_setTitleText(Button_2, "button_2")
local Button_3 = GUI:Button_Create(Layout, "button_3", 300.00, 100.00, "res/public/1900000660.png")
GUI:Win_SetParam(Button_3, 2)
GUI:Button_setTitleText(Button_3, "button_3")



GUI:UserUILayout(Layout, {
dir=2,
addDir=2,
interval=1,
gap = {x=1},
sortfunc = function (lists)
table.sort(lists, function (a, b)
return GUI:Win_GetParam(a) > GUI:Win_GetParam(b)
end)
end
})

创建图片
Image_Create(parent, ID, x, y, nimg)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| nimg | 是 | string | 图片路径 |
示例代码
local imgPath = "res/public/1900000600.png"
local Image_bg = GUI:Image_Create(parent, "Image_bg", 0, 0, imgPath)

加载纹理图片
Image_loadTexture(widget, filepath)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 图片对象 |
| filepath | 是 | string | 图片路径 |
设置图片九宫格
Image_setScale9Slice(widget, scale9l, scale9r, scale9t, scale9b)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 图片对象 |
| scale9l | 是 | int | 左边比例 |
| scale9r | 是 | int | 右边比例 |
| scale9t | 是 | int | 上边比例 |
| scale9b | 是 | int | 下边比例 |
设置图片是否变灰
Image_setGrey(widget, isGrey)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 图片对象 |
| isGrey | 是 | bool | 是否置灰 |
获取图片文件路径 [3.40.9版本]
GUI:Image_getTextureFile(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 图片对象 |
返回 图片资源路径 string
创建按钮
Button_Create(parent, ID, x, y, nimg)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| nimg | 是 | string | 图片路径 |
示例代码
local BtnOk = GUI:Button_Create(FrameLayout, "BtnOk", 0, 0, "res/public/1900000611.png")
GUI:setAnchorPoint(BtnOk, { x = 0.5, y = 0.5 })
GUI:Button_setTitleText(BtnOk, "确定")
GUI:Button_setTitleFontSize(BtnOk, 16)
GUI:addOnClickEvent(BtnOk, function()
-- do something
end)

设置按钮状态图片
Button_loadTextures(widget, Normalfilepath, Pressedfilepath, Disabledfilepath, TextureType)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 按钮对象 |
| Normalfilepath | 是 | string | 正常状态图片路径 |
| Pressedfilepath | 否 | string | 按压状态图片路径 |
| Disabledfilepath | 否 | string | 禁用状态图片路径 |
| TextureType | 否 | int | 加载类型： |
0 图片
1 图片集 plist文件
Button_loadTextureNormal(widget, filepath)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 按钮对象 |
| filepath | 是 | string | 图片路径 |
设置正常状态图片
Button_loadTexturePressed(widget, filepath)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 按钮对象 |
| filepath | 是 | string | 图片路径 |
设置按下状态图片
Button_loadTextureDisabled(widget, filepath)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 按钮对象 |
| filepath | 是 | string | 图片路径 |
设置禁用状态图片
设置按钮文字
Button_setTitleText(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 按钮对象 |
| value | 是 | string | 按钮显示文本 |
获取按钮文字 [3.40.6版本]
Button_getTitleText(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 按钮对象 |
设置按钮文字颜色
Button_setTitleColor(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 按钮对象 |
| value | 是 | string | 色值（#000000） |
设置按钮文字大小
Button_setTitleFontSize(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 按钮对象 |
| value | 是 | int | 字体大小（字号16） |
设置按钮文字样式
Button_setTitleFontName(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 按钮对象 |
| value | 是 | string | 字体样式（font.ttf） |
设置按钮文本最大宽度
Button_setMaxLineWidth(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 按钮对象 |
| value | 是 | int | 文本最大宽度 |
设置按钮文本加描边
Button_titleEnableOutline(widget, color, outline)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 按钮对象 |
| color | 是 | string | 描边色值（#000000） |
| outline | 是 | int | 描边大小 |
Button_titleDisableOutLine(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 按钮对象 |
取消按钮文本描边
设置按钮是否禁用
Button_setBright(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 按钮对象 |
| value | 是 | bool | 是否禁用（可触摸） |
Button_setBrightEx(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 按钮对象 |
| value | 是 | bool | 是否禁用（不可触摸） |
Button_setBrightStyle(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 按钮对象 |
| value | 是 | int | 状态（0正常 1按下） |
设置按钮是否灰态
Button_setGrey(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 按钮对象 |
| value | 是 | bool | 是否灰态 |
设置按钮九宫格
Button_setScale9Slice(widget, scale9l, scale9r, scale9t, scale9b)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 按钮对象 |
| scale9l | 是 | int | 左边比例 |
| scale9r | 是 | int | 右边比例 |
| scale9t | 是 | int | 上边比例 |
| scale9b | 是 | int | 下边比例 |
创建文本
Text_Create(parent, ID, x, y, fontSize, fontColor, str)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| fontSize | 是 | int | 字体大小 |
| fontColor | 是 | stirng | 字体颜色 |
| str | 是 | string | 文本 |
示例代码
local str = "我的名字" or ""
local Text_name = GUI:Text_Create(parent, "Text_name", 0, 0, 16, "#ffffff", str)

设置文本
Text_setString(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 对象 |
| value | 是 | string | 文本 |
获取文本
GUI:Text_getString(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 对象 |
设置文本颜色
Text_setTextColor(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 对象 |
| value | 是 | string | 色值(“#000000”) |
设置字体大小
Text_setFontSize(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 对象 |
| value | 是 | int | 字体大小 |
设置字体路径
Text_setFontName(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 对象 |
| value | 是 | string | 字体文件路径 |
例: “fonts/font.ttf”
设置字体描边
Text_enableOutline(widget, color, size)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 对象 |
| color | 是 | string | 色值(“#000000”) |
| size | 是 | int | 描边宽度 |
设置是否启用下划线
GUI:Text_enableUnderline(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 文本对象 |
设置文本最大行宽
Text_setMaxLineWidth(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 对象 |
| value | 是 | int | 宽度 |
-- 需要在设置文本最大行宽后再填充文本内容
local Text_name = GUI:Text_Create(parent, "Text_name", 0,0, 16, "#ffffff", "")
GUI:Text_setMaxLineWidth(Text_name, 100)
GUI:Text_setString(Text_name, "设置文本最大行宽这是一段神奇的文字")

禁用文本特效
Text_disableEffect(widget, param)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 对象 |
| value | 是 | int | 特效类型： |
0：正常
1：描边
2：阴影
3：发光
4：斜体
5：粗体
6：下划线
Text_disableNormal(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 对象 |
Text_disableOutLine(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 对象 |
Text_disableShadow(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 对象 |
Text_disableGlow(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 对象 |
设置文本垂直对齐
Text_setTextVerticalAlignment(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 对象 |
| value | 是 | int | 0：顶对齐 |
1：垂直居中
2：底对齐
设置文本水平对齐
Text_setTextHorizontalAlignment(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 对象 |
| value | 是 | int | 0：顶对齐 |
1：水平居中
2：底对齐
设置文本尺寸
Text_setTextAreaSize(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 对象 |
| value | 是 | table | {width = 0, height = 0} |
设置倒计时文本
Text_COUNTDOWN(widget, time, callback)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 对象 |
| time | 是 | int | 倒计时时间, 单位:秒 |
| callback | 否 | function | 每秒触发回调, 传入参数: 剩余时间 |
版本号[3.40.4]及以后改为倒计时结束触发
| showType | 否 | int | 倒计时时间显示方式 |
0: xx时xx分xx秒
1: 小于1天显示xx:xx:xx 大于显示xx天xx时xx分 [3.40.8版本新增]
创建Bmp文本
BmpText_Create(parent, ID, x, y, fontColor, str, fontPath)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| fontColor | 否 | stirng | 字体颜色, [3.40.7版本支持传空] |
| str | 是 | string | 文本 |
| fontPath | 是 | string | 字体文件路径, 例："fonts/stfont.fnt" |
PC端 12号宋体
示例代码
local str = "我的名字" or ""
local Text_name = GUI:BmpText_Create(parent, "Text_name", 0, 0, "#ffffff", str)

创建艺术字文本
TextAtlas_Create(parent, ID, x, y, stringValue, charMapFile, itemWidth, itemHeight, startCharMap, sheet)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| stringValue | 是 | string | 文本内容 |
| charMapFile | 是 | string | 艺术字路径 |
| itemWidth | 是 | int | 单个字体宽度 |
| itemHeight | 是 | int | 单个字体高度 |
| startCharMap | 是 | string | 起始字符设置(“/“) |
| sheet | 是 | string | 字体内容(H5专属) |
比如图片文字是“+-0123456789”,那这个sheet的值就是”+-0123456789”

示例代码1


local text = GUI:TextAtlas_Create(GUI:Attach_LeftBottom(), "aa", 100, 200, "123", "res/public/word_tywz_01.png", 18, 28, "0")


示例代码2

此图对应ASCII码字符依次为 /0123456789:;

-- 0前面的ASCII码 字符 / 代指 图片中减号, 艺术字起始字符为 /
local text = GUI:TextAtlas_Create(GUI:Attach_LeftBottom(), "TT", 200, 300, "/", "res/private/damage_num/word_ngnz_12.png", 14, 22, "/")
SL:ScheduleOnce(function()
-- 顺延0-9后ASCII码 :; 两字符代指 "怒"
GUI:TextAtlas_setString(text, ":;99/")
end, 1)


结果如下:

设置艺术字配置
TextAtlas_setProperty(widget, stringValue, charMapFile, itemWidth, itemHeight, startCharMap, sheet)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 艺术字对象 |
| stringValue | 是 | string | 文本内容 |
| charMapFile | 是 | string | 艺术字路径 |
| itemWidth | 是 | int | 字体宽度 |
| itemHeight | 是 | int | 字体高度 |
| startCharMap | 是 | string | 起始字符设置(“/“) |
| sheet | 是 | string | 字体内容(H5专属) |
比如图片文字是“+-0123456789”,那这个sheet的值就是”+-0123456789”
设置艺术字文本
TextAtlas_setString(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 艺术字对象 |
| value | 是 | string | 文本内容 |
获取艺术字文本
TextAtlas_getString(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 艺术字对象 |
创建富文本
RichText_Create(parent, ID, x, y, str, width, fontSize, fontColor, vspace, hyperlinkCB, defaultFontFace)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| str | 是 | string | 文本内容 |
| width | 是 | int | 富文本控件宽度 |
| fontSize | 否 | int | 字体大小 |
| fontColor | 否 | string | 字体颜色 |
| vspace | 否 | int | 富文本行间距 |
| hyperlinkCB | 否 | function | 超链回调函数 |
示例代码
local richText = GUI:RichText_Create(parent, "richText", 0, 0, "克里斯蒂亚罗", 100, 16, "#f8e6c6", 0, function()
-- do something
end)

创建原始富文本
RichTextFCOLOR_Create(parent, ID, x, y, str, width, fontSize, color, vspace, hyperlinkCB, fontPath, outlineParam)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| str | 是 | string | 文本内容 |
| width | 是 | int | 富文本控件宽度 |
| fontSize | 否 | int | 字体大小 |
| color | 否 | string | 字体颜色, 例: “#FFFFFF” |
| vspace | 否 | int | 富文本行间距 |
| hyperlinkCB | 否 | function | 超链回调函数 |
| fontPath | 否 | string | 字体文件路径 |
| outlineParam | 否 | table | 描边参数 |
outlineSize: 描边大小
outlineColor: 描边颜色 C3B
(描边颜色 例 : SL:ConvertColorFromHexString("#FFFFFF"))
示例代码
local rich = GUI:RichTextFCOLOR_Create(node, "rich", 100, 0, "<灼伤：%s几率灼烧目标/FCOLOR=254>\\<每秒燃烧目标5%生命值/FCOLOR=249>", 600, 16, "#28EF01", 5)

local rich = GUI:RichTextFCOLOR_Create(GUI:Win_FindParent(107), "rich", -300, 60, "<点击跳转/@llllll>", 600, 16, "#28EF01", 5,function (...)
SL:Print("超链回调",...)
end)

创建自定义组合富文本 [3.40.3版本]
RichTextCombine_Create(parent, ID, x, y, width, vspace)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| width | 是 | int | 富文本控件最大宽度 |
| vspace | 否 | int | 富文本行间距 |
添加自定义富文本cell
RichTextCombine_pushBackElements(widget, elements)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| elements | 是 | obj | [RichTextCombineCell] 单个元素控件对象 或 控件对象table |
添加cell完毕格式化富文本
RichTextCombine_format(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
创建自定义组合富文本cell [3.40.3版本]
RichTextCombineCell_Create(parent, ID, x, y, type, param)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 [RichTextCombine] |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| type | 是 | int/string | cell类型 |
文本类型：1或TEXT
节点类型：2或NODE
换行类型：3 或 NEWLINE[3.40.4新增]
| param | 是 | table | 额外参数, 参考如下: |
{
node             = 节点类型必需参数 object 控件对象,
color            = 颜色值 默认: "#FFFFFF",
opacity         = 不透明度 默认: 255,
str             = 文本内容 string,
fontSize         = 文本字号 默认: SL:GetMetaValue("GAME_DATA", "DEFAULT_FONT_SIZE"),
fontPath         = 文本字体路径 默认: "fonts/font2.ttf"
outlineColor     = 文本描边颜色 默认: "#000000",
outlineSize     = 文本描边大小 默认: 0,
link             = 文本点击触发传递内容 string
}

示例代码 :
local richText  = GUI:RichTextCombine_Create(GUI:Attach_LeftBottom(), "tt", 500, 320, 1000, 10)
local element   = GUI:RichTextCombineCell_Create(richText, "txt_1", 0, 0, "TEXT", {
str         = "1111111",
color       = "#FF0000",
fontSize    = 18
})

local element   = GUI:RichTextCombineCell_Create(richText, "txt_2", 0, 0, "TEXT", {
str         = "22222",
color       = "#0000FF",
fontSize    = 12
})

local layout = GUI:Layout_Create(-1, "panel", 0, 0, 50, 50)
GUI:addStateEvent(layout, function(state)
if state == "enter" then
GUI:removeAllChildren(layout)
local size = GUI:getContentSize(layout)
local emojiSfx = GUI:Effect_Create(layout, "sfx", size.width / 2, size.height / 2, 0, 1)
end
end)
local element = GUI:RichTextCombineCell_Create(richText, "node_1", 0, 0, "NODE", {node = layout})

示例 2 : [3.40.4版本]
local elements  = {}
local element   = GUI:RichTextCombineCell_Create(-1, "show", 0, 0, "TEXT", {
str         = "第一行文本11111",
color       = "#FF0000",
fontSize    = 16
})
table.insert(elements, element)

local element   = GUI:RichTextCombineCell_Create(-1, "111", 0, 0, "NEWLINE", {})
table.insert(elements, element)

local element   = GUI:RichTextCombineCell_Create(-1, "222", 0, 0, "TEXT", {
str         = "第二行文本222222",
color       = "#00FF00",
fontSize    = 16
})
table.insert(elements, element)

local richText = GUI:RichTextCombine_Create(GUI:Attach_LeftBottom(), "RichText", 200, 300, 200, 0)
GUI:RichTextCombine_pushBackElements(richText, elements)
GUI:RichTextCombine_format(richText)
GUI:RichText_setBackgroundColor(richText, "#FFFFFF")

设置富文本背景颜色 [3.40.3版本]
RichText_setBackgroundColor(widget, color)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| color | 是 | string | 颜色值, 例: “#000000” |
添加富文本url点击触发事件 [3.40.3版本]
RichText_setOpenUrlEvent(widget, handle)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| handle | 是 | function | 触发函数 (param1: 富文本控件, param2: string 文本传递内容) |
示例:
local str = string.format("<a href='position#%s#200#200'>TTTT</a>", SL:GetMetaValue("MAP_ID"))
local richText = GUI:RichText_Create(GUI:Attach_LeftBottom(), "rr", 500, 320, str, 1000)
GUI:RichText_setOpenUrlEvent(richText, function(sender, str)
SL:Print(str)
local slices  = string.split(str, "#")
local command = slices[1]
if command == "position" then
local originScale = GUI:getScale(sender)
GUI:setScale(sender, originScale + 0.2)
local function reback()
GUI:setScale(sender, originScale)
end
SL:scheduleOnce(sender, reback, 0.03)

-- find position
local mapID   = slices[2]
local x       = tonumber(slices[3])
local y       = tonumber(slices[4])
SL:SetMetaValue("BATTLE_MOVE_BEGIN", mapID, x, y)
end
end)

创建滚动文本
ScrollText_Create(parent, ID, x, y, width, fontSize, fontColor, str, scrollTime, fontPath)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| width | 是 | int | 文本宽度 |
| fontSize | 是 | int | 字体大小 |
| fontColor | 是 | int | 字体颜色 |
| str | 是 | string | 文本内容 |
| scrollTime | 否 [3.40.4版本生效] | int | 滚动时长 (秒) |
| fontPath | 否 [3.40.6版本生效] | string | 字体文件路径 |
示例代码
local scrollText = GUI:ScrollText_Create(parent, "scrollText", 0, 0, 100, 16, "#000000", "文本内容")

设置滚动文本内容
ScrollText_setString(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 滚动文本对象 |
| value | 是 | string | 文本内容 |
获取滚动文本内容
ScrollText_getString(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 滚动文本对象 |
设置滚动文本描边
ScrollText_enableOutline(widget, color, size)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 滚动文本对象 |
| color | 是 | string | 描边色值(“#000000”) |
| size | 是 | int | 描边大小 |
设置滚动文本水平对齐
ScrollText_setHorizontalAlignment(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 滚动文本对象 |
| value | 是 | int | 对齐方式： |
1 左对齐
2 水平居中
3 右对齐
设置滚动文本颜色
ScrollText_setTextColor(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 滚动文本对象 |
| value | 是 | string | 色值(“#000000”) |
创建节点
Node_Create(parent, ID, x, y)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
示例代码
local node = GUI:Node_Create(parent, "node", 0, 0)

创建Widget
Widget_Create(parent, ID, x, y, width, height)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| width | 是 | int | 宽 |
| height | 是 | int | 高 |
示例代码
local widget =  GUI:Widget_Create(parent, "widget_1", 0, 0, 300, 200)
创建物品框
ItemShow_Create(parent, ID, x, y, setData)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| setData | 是 | table | 配置数据 |
配置数据详细参数 示例
local setData  = {}
setData.index = 4                     -- 物品Index
setData.look  = true                  -- 是否显示tips
setData.bgVisible = true              -- 是否显示背景框
setData.count = 1                     -- 物品数量
setData.color = 225                   -- 颜色ID （0~255）
--setData.starLv = false -- 是否显示星级
--setData.checkPower = true           -- 是否检查战力从而显示提升小箭头
--setData.showModelEffect = true      -- 只显示内观特效不显示背包特效
--setData.onlyShowSFX = true          -- 只显示道具特效其它都不显示
--setData.noSwallow = true            -- 是否触摸吞噬
--setData.noMouseTips = true -- 鼠标移入不显示tips
--setData.mouseCheckTimes = 6 -- 鼠标移入检测物品框是否可见时查找父节点层数, 默认6
--setData.itemData = table -- 物品数据 ( ！有真实物品数据可直接传, 避免Tips缺漏 )

local item = GUI:ItemShow_Create(ui_icon, "item", 0, 0, setData)

示例代码2 (等同于EquipShow创建)
-- 获取装备位1的装备数据
local equipData    = SL:GetMetaValue("EQUIP_DATA", 1)
if equipData then
local info = {}
info.index = equipData.Index
info.itemData = equipData        -- 传入装备数据
info.look = true
info.bgVisible = true
info.starLv = true
local item = GUI:ItemShow_Create(parent, "item", 0, 0, info)
end

设置物品框单击事件
ItemShow_addReplaceClickEvent(widget, eventCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 物品框对象 |
| eventCB | 是 | function | 单击事件函数 |
设置物品框双击事件
ItemShow_addDoubleEvent(widget, eventCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 物品框对象 |
| eventCB | 是 | function | 双击事件函数 |
设置物品框长按事件
ItemShow_addPressEvent(widget, eventCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 物品框对象 |
| eventCB | 是 | function | 长按事件函数 |
设置物品框是否置灰
ItemShow_setIconGrey(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 物品框对象 |
| value | 是 | bool | 是否置灰 |
设置物品框是否选中
ItemShow_setItemShowChooseState(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 物品框对象 |
| value | 是 | bool | 是否选中 |
设置物品框是否拖动
ItemShow_setMoveEable(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 物品框对象 |
| value | 是 | bool | 是否拖动 |
更新物品框内容
ItemShow_updateItem(widget, itemData)
不建议使用！ 更不建议高频使用！简单更新可以调用下方函数调用方式 自定义刷新内容。

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 物品框对象 |
| setData | 是 | table | 配置数据 |
调用GUILayout/Item.lua中的函数
ItemShow_OnRunFunc(widget, funcname, …)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 物品框对象 |
| funcname | 是 | string | GUILayout/Item.lua中的函数名字 |
| … | 否 | any | 可变参数 |

例如

-- 设置ItemShow的显示道具数量为20
local ItemShow = GUI:ItemShow_Create(parent, "Item", 0, 0, itemData)
ItemShow_OnRunFunc(ItemShow, "SetCount", 20)

设置物品框是否触摸吞噬
ItemShow_setItemTouchSwallow(widget, bool)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 物品框对象 |
| value | 是 | bool | 是否触摸吞噬 |
创建物品放入框
ItemBox_Create(parent, ID, x, y, img, boxindex, stdmode)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| img | 是 | string | 放置框底图资源路径 |
| boxindex | 是 | int | 放置框 唯一ID |
| stdmode | 是 | string/number/table | 允许传入的StdMode (“*”: 所有 、单个用number 、多个用table) |
获取对应ID放置框的物品数据
ItemBox_GetItemData(widget, boxindex)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 物品放入框控件对象 |
| boxindex | 是 | int | 放置框 唯一ID |
清空对应ID放置框的传入数据
ItemBox_RemoveBoxData(widget, boxindex)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 物品放入框控件对象 |
| boxindex | 是 | int | 放置框 唯一ID |
更新对应ID放置框的物品数据 [3.40.4]
ItemBox_UpdateBoxData(widget, boxindex)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 物品放入框控件对象 |
| boxindex | 是 | int | 放置框 唯一ID |
| itemData | 否 | tbl | 填充指定的ItemData数据 |
[支持版本号3.40.7以上]
创建复选框
CheckBox_Create(parent, ID, x, y, nimg, pimg)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| nimg | 是 | string | 正常图片路径 |
| pimg | 是 | string | 选中图片路径 |
示例代码
local nimg = "res/private/gui_edit/CheckBox_Normal.png"
local pimg = "res/private/gui_edit/CheckBox_Press.png"
local checkBox = GUI:CheckBox_Create(parent, "checkBox", 0, 0, nimg, pimg)

设置复选框背景图片
CheckBox_loadTextureBackGround(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 复选框对象 |
| value | 是 | string | 默认状态图片路径 |
CheckBox_loadTextureFrontCross(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 复选框对象 |
| value | 是 | string | 选中状态图片路径 |
CheckBox_loadTextureFrontCrossDisabled(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 复选框对象 |
| value | 是 | string | 禁用状态图片路径 |
设置复选框选中或取消
CheckBox_setSelected(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 复选框对象 |
| value | 是 | bool | 选中或取消 |
获取复选框是否选中
CheckBox_isSelected(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 复选框对象 |
设置复选框监听事件
CheckBox_addOnEvent(widget, eventCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 复选框对象 |
| eventCB | 是 | function | 事件函数 |
创建输入框
TextInput_Create(parent, ID, x, y, width, height, fontSize)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| width | 是 | int | 宽度 |
| height | 是 | int | 高度 |
| fontSize | 是 | int | 字体大小 |
示例代码
local TextField_input = GUI:TextInput_Create(parent, "TextField_input", 0, 0, 30, 33, 16)

设置输入框字体颜色
TextInput_setFontColor(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 输入框对象 |
| value | 是 | string | 色值(“#000000”) |
设置输入框字体 [仅支持移动端设置]
TextInput_setFont(widget, value, value2)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 输入框对象 |
| value | 是 | string | 字体路径 |
| value2 | 是 | int | 字号 |
设置输入框字体大小
TextInput_setFontSize(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 输入框对象 |
| value | 是 | int | 字号 |
设置输入框占位文本字体
TextInput_setPlaceholderFont(widget, value, value2)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 输入框对象 |
| value | 是 | string | 字体路径 |
| value2 | 是 | string | 字体(“font.ttf”) |
设置输入框占位文本字体颜色
TextInput_setPlaceholderFontColor(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 输入框对象 |
| value | 是 | string | 色值(“#000000”) |
设置输入框占位文本字体大小
TextInput_setPlaceholderFontSize(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 输入框对象 |
| value | 是 | int | 字号 |
设置输入框占位文本
TextInput_setPlaceHolder(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 输入框对象 |
| value | 是 | string | 输入内容 |
设置输入框文本
TextInput_setString(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 输入框对象 |
| value | 是 | string | 输入内容 |
获取输入框文本
TextInput_getString(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 输入框对象 |
设置输入框行宽
TextInput_setMaxLength(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 输入框对象 |
| value | 是 | int | 输入框控件宽度 |
设置输入框水平对齐
TextInput_setTextHorizontalAlignment(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 输入框对象 |
| value | 是 | int | 对齐方式： |
0 左对齐
1 水平居中
2 右居中
设置输入框文本类型
TextInput_setInputFlag(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 输入框对象 |
| value | 是 | int | 类型 |
类型如下
0   -- 密码形式
1   -- 敏感数据输入
2   -- 每个单词首字符大写，并有提示
3   -- 第一句首字符大写，并有提示
4 -- 自动大写

设置输入框键盘编辑类型
TextInput_setInputMode(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 输入框对象 |
| value | 是 | int | 类型 |
类型如下
0 -- 开启任何文本的输入键盘(含换行)
1   -- 开启邮箱地址输入类型键盘
2   -- 开启数字符号输入类型键盘
3   -- 开启电话号码输入类型键盘
4   -- 开启URL输入类型键盘
5   -- 开启数字输入类型键盘(含小数点)
6   -- 开启任何文本的输入键盘(不含换行)

设置输入框弹出式键盘返回类型
TextInput_setReturnType(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 输入框对象 |
| value | 是 | int | 类型 |
设置输入框监听事件
TextInput_addOnEvent(widget, eventCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 输入框对象 |
| eventCB | 是 | function | 事件处理函数 |
关闭输入框输入 [3.40.5版本]
TextInput_closeInput(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 输入框对象 |
创建滚动条
Slider_Create(parent, ID, x, y, barimg, pbarimg, nimg)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| barimg | 是 | string | 滚动条背景图片 |
| pbarimg | 是 | string | 滚动条图片 |
| nimg | 是 | string | 滚动条拖动块图片 |
示例代码
local barimg = "res/private/new_setting/bg_progress.png"
local pbarimg = "res/private/new_setting/bg_progress2.png"
local nimg = "res/private/new_setting/icon_xdtzy_17.png"
local Slider_progress = GUI:Slider_Create(parent, "Slider_progress", 0, 0, barimg, pbarimg, nimg)

设置滚动条背景图
Slider_loadBarTexture(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 滚动条对象 |
| value | 是 | string | 背景图路径 |
设置滚动条图片
Slider_loadProgressBarTexture(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 滚动条对象 |
| value | 是 | string | 滚动条图片路径 |
设置滚动条拖动块普通图片
Slider_loadSlidBallTextureNormal(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 滚动条对象 |
| value | 是 | string | 拖动块图片路径 |
设置滚动条进度
Slider_setPercent(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 滚动条对象 |
| value | 是 | int | 滚动条进度(0-100) |
获得滚动条进度
Slider_getPercent(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 滚动条对象 |
返回值：滚动条进度
设置滚动条最大进度值 [3.40.3版本]
Slider_setMaxPercent(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 滚动条对象 |
| value | 是 | int | 滚动条最大进度值 |
设置滚动条触摸事件
Slider_addOnEvent(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 滚动条对象 |
| value | 是 | function | 事件函数 |
创建圆形进度条
ProgressTimer_Create(parent, ID, x, y, img)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| img | 是 | string | 图片路径 |
示例代码
local ui_img = "res/private/main/Skill/hero2/0_0001.png"
local heroProgress = GUI:ProgressTimer_Create(parent, "heroProgress", 0, 0, ui_img)

设置圆形进度条百分比
ProgressTimer_setPercentage(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | int | 进度(0-100) |
获取圆形进度条百分比
ProgressTimer_getPercentage(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
设置圆形进度条方向
ProgressTimer_setReverseDirection(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | bool | true 顺时针 |
false 逆时针
设置圆形进度条动作和回调函数
ProgressTimer_progressFromTo(widget, time, from, to, completeCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| time | 是 | int | 时间 |
| from | 是 | int | 开始进度(0-100) |
| to | 是 | int | 结束进度(0-100) |
| completeCB | 是 | function | 回调函数 |
ProgressTimer_progressTo(widget, time, to, completeCB, tag)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| time | 是 | int | 时间 |
| to | 是 | int | 结束进度(0-100) |
| completeCB | 是 | function | 回调函数 |
| tag | 是 | int | 标记 |
设置圆形进度条背景图
ProgressTimer_ChangeImg(widget, img)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| img | 是 | string | 图片路径 |
创建进度条
LoadingBar_Create(parent, ID, x, y, nimg, direction)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| nimg | 是 | string | 图片路径 |
| direction | 是 | int | 方向： |
0 从左到右
1 从右到左
示例代码
local imgBar = "res/private/gui_edit/LoadingBar.png"
local loadingBar = GUI:LoadingBar_Create(parent, "loadingBar", 0, 0, imgBar, 0)

设置进度条图片
LoadingBar_loadTexture(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 进度条对象 |
| value | 是 | string | 图片路径 |
设置进度条方向
LoadingBar_setDirection(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 进度条对象 |
| value | 是 | int | 方向： |
0 从左到右
1 从右到左
设置进度条进度
LoadingBar_setPercent(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 进度条对象 |
| value | 是 | int | 进度(0-100) |
获取进度条进度
LoadingBar_getPercent(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 进度条对象 |
返回值：进度条进度
设置进度条颜色
LoadingBar_setColor(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 进度条对象 |
| value | 是 | string | 色值(“#000000”) |
获取进度条颜色
LoadingBar_getColor(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 进度条对象 |
返回值：string 进度条颜色值
创建特效
Effect_Create(parent, ID, x, y, effecttype, effectid, sex, act, dir, speed)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| effecttype | 是 | int | 0 特效 |
1 NPC
2 怪物
3 技能
4 人物
5 武器
6 翅膀
7 发型
8 盾牌[3.40.3版本]
| effectid | 是 | int | 特效id |
| sex | 否 | int | 性别(0 男 1 女) |
| act | 否 | int | 0 待机 |
1 走
2 攻击
3 施法
4 死亡
5 跑步
| dir | 否 | int | 方向 |
| speed | 否 | int | 播放速度 |
代码示例
-- 特效展示 Ctrl + F4 查看
local sfx = GUI:Effect_Create(parent, "sfx", 0, 0, 0, 4004, 0, 0, 3, 1)

特效播放
Effect_play(widget, act, dir, isLoop, speed, isSequence)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 特效对象 |
| act | 是 | int | 0 待机 |
1 走
2 攻击
3 施法
4 死亡
5 跑步
| dir | 是 | int | 方向 |
| isLoop | 是 | bool | 是否循环播放 |
| speed | 否 | int | 播放速度 |
| isSequence | 否 | boolean | 倒放参数 [仅false为倒放特效 ] |
特效停止
Effect_stop(widget, frameIndex, act, dir)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 特效对象 |
| frameIndex | 否 | int | 第几帧 |
| act | 否 | int | 0 待机 |
1 走
2 攻击
3 施法
4 死亡
5 跑步
| dir | 否 | int | 方向 |
特效播放完成事件
Effect_addOnCompleteEvent(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 特效对象 |
| value | 是 | function | 播放完成回调函数 |
设置特效播放完自动移除 [3.40.3版本]
Effect_setAutoRemoveOnFinish(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 特效对象 |
界面弹窗特效
Timeline_Window1(widget, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| timelineCB | 是 | function | 回调函数 |
弹窗效果

Timeline_Window2(widget, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| timelineCB | 是 | function | 回调函数 |
弹窗效果

Timeline_Window3(widget, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| timelineCB | 是 | function | 回调函数 |
弹窗效果

Timeline_Window4(widget, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| timelineCB | 是 | function | 回调函数 |
弹窗效果

Timeline_Window5(widget, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| timelineCB | 是 | function | 回调函数 |
弹窗效果

Timeline_Window6(widget, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| timelineCB | 是 | function | 回调函数 |
弹窗效果

设置动画标记
Timeline_SetTag(action, tag)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| tag | 是 | int | 标记值 |
停止所有动画
Timeline_StopAll(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
Timeline_StopByTag(widget, tag)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| tag | 是 | int | 标记值 |
通过标记停止动画
动画淡出效果
Timeline_FadeOut(widget, time, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| time | 是 | int | 时间 |
| timelineCB | 是 | function | 回调函数 |
淡出效果

Timeline_FadeIn(widget, time, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| time | 是 | int | 时间 |
| timelineCB | 是 | function | 回调函数 |

淡入需要先设置控件透明度

淡入效果

Timeline_FadeTo(widget, value, time, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | int | 透明度(0-255) |
| time | 是 | int | 时间 |
| timelineCB | 是 | function | 回调函数 |
修改透明度到某个值

放大缩小动画
Timeline_ScaleTo(widget, value, time, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | int | 缩放比例(0-100) |
| time | 是 | int | 时间 |
| timelineCB | 是 | function | 回调函数 |
放大缩小到某个比例（放大缩小到原始的倍数）
-- 实际上图片只放大了2倍
local img = GUI:Image_Create(parent, "img", 0, 0, "res/bg.png")
GUI:Timeline_ScaleTo(img, 2, 1, nil)
GUI:Timeline_ScaleTo(img, 2, 1, nil)

Timeline_ScaleBy(widget, value, time, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | int | 缩放比例(0-100) |
| time | 是 | int | 时间 |
| timelineCB | 是 | function | 回调函数 |
放大缩小到某个比例（放大缩小多少倍数）
-- 实际上图片放大了4倍
local img = GUI:Image_Create(parent, "img", 0, 0, "res/bg.png")
GUI:Timeline_ScaleBy(img, 2, 1, nil)
GUI:Timeline_ScaleBy(img, 2, 1, nil)

旋转动画
Timeline_RotateTo(widget, value, time, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | int | 旋转角度(0-360) |
| time | 是 | int | 时间 |
| timelineCB | 是 | function | 回调函数 |
旋转到某个角度（旋转到指定角度）

Timeline_RotateBy(widget, value, time, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | int | 旋转角度(0-360) |
| time | 是 | int | 时间 |
| timelineCB | 是 | function | 回调函数 |
旋转到某个角度（从原来角度 旋转到 某个角度）
移动动画
Timeline_MoveTo(widget, value, time, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | table | {x = 0, y = 0} |
| time | 是 | int | 时间 |
| timelineCB | 是 | function | 回调函数 |
移动到某坐标（移动绝对位置）

Timeline_MoveBy(widget, value, time, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | table | {x = 0, y = 0} |
| time | 是 | int | 时间 |
| timelineCB | 是 | function | 回调函数 |
移动到某坐标（移动相对位置）
闪烁动画
Timeline_Blink(widget, value, time, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | int | 闪烁次数 |
| time | 是 | int | 时间 |
| timelineCB | 是 | function | 回调函数 |
闪烁效果

震动动画
Timeline_Shake(widget, time, x, y, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| time | 是 | int | 时间 |
| x | 是 | int | X轴震动像素 |
| y | 是 | int | Y轴震动像素 |
| timelineCB | 是 | function | 回调函数 |
震动效果

疯狂抖动动画
Timeline_Waggle(widget, time, angle)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| time | 是 | int | 时间 |
| angle | 是 | int | 抖动幅度（0-360） |
震动效果
动画延迟播放
Timeline_DelayTime(widget, time, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| time | 是 | int | 延迟时间 |
| timelineCB | 是 | function | 回调函数 |
动画回调方法
Timeline_CallFunc(widget, time, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| time | 是 | int | 延迟时间 |
| timelineCB | 是 | function | 回调函数 |
动画延迟显示
Timeline_Show(widget, time)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| time | 是 | int | 延迟时间 |
动画延迟隐藏
Timeline_Hide(widget, time)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| time | 是 | int | 延迟时间 |
缓动动画
Timeline_EaseSineIn_MoveTo(widget, value, time, callback)

widget 对象由慢到快，移动到目标位置

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 对象 |
| value | 是 | table | 目标坐标位置 |
| time | 是 | int | 动作时间 |
| callback | 否 | function | 动作执行完的回调 |
Timeline_EaseSineOut_MoveTo(widget, value, time, callback)

widget 对象由快到慢，移动到目标位置

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 对象 |
| value | 是 | table | 目标坐标位置 |
| time | 是 | int | 动作时间 |
| callback | 否 | function | 动作执行完的回调 |
Timeline_DigitChange(widget, cur, target, interval)

widget 数字滚动动画

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 对象 [ 仅限Button、Text控件] （3.40.8支持TextAtlas控件） |
| cur | 是 | int | 当前数值 |
| target | 是 | int | 目标数值 |
| interval | 否 | int | 变动间隔（秒） |
界面弹窗特效
Timeline_Window1(widget, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| timelineCB | 是 | function | 回调函数 |
弹窗效果

Timeline_Window2(widget, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| timelineCB | 是 | function | 回调函数 |
弹窗效果

Timeline_Window3(widget, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| timelineCB | 是 | function | 回调函数 |
弹窗效果

Timeline_Window4(widget, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| timelineCB | 是 | function | 回调函数 |
弹窗效果

Timeline_Window5(widget, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| timelineCB | 是 | function | 回调函数 |
弹窗效果

Timeline_Window6(widget, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| timelineCB | 是 | function | 回调函数 |
弹窗效果

设置动画标记
Timeline_SetTag(action, tag)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| tag | 是 | int | 标记值 |
停止所有动画
Timeline_StopAll(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
Timeline_StopByTag(widget, tag)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| tag | 是 | int | 标记值 |
通过标记停止动画
动画淡出效果
Timeline_FadeOut(widget, time, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| time | 是 | int | 时间 |
| timelineCB | 是 | function | 回调函数 |
淡出效果

Timeline_FadeIn(widget, time, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| time | 是 | int | 时间 |
| timelineCB | 是 | function | 回调函数 |

淡入需要先设置控件透明度

淡入效果

Timeline_FadeTo(widget, value, time, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | int | 透明度(0-255) |
| time | 是 | int | 时间 |
| timelineCB | 是 | function | 回调函数 |
修改透明度到某个值

放大缩小动画
Timeline_ScaleTo(widget, value, time, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | int | 缩放比例(0-100) |
| time | 是 | int | 时间 |
| timelineCB | 是 | function | 回调函数 |
放大缩小到某个比例（放大缩小到原始的倍数）
-- 实际上图片只放大了2倍
local img = GUI:Image_Create(parent, "img", 0, 0, "res/bg.png")
GUI:Timeline_ScaleTo(img, 2, 1, nil)
GUI:Timeline_ScaleTo(img, 2, 1, nil)

Timeline_ScaleBy(widget, value, time, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | int | 缩放比例(0-100) |
| time | 是 | int | 时间 |
| timelineCB | 是 | function | 回调函数 |
放大缩小到某个比例（放大缩小多少倍数）
-- 实际上图片放大了4倍
local img = GUI:Image_Create(parent, "img", 0, 0, "res/bg.png")
GUI:Timeline_ScaleBy(img, 2, 1, nil)
GUI:Timeline_ScaleBy(img, 2, 1, nil)

旋转动画
Timeline_RotateTo(widget, value, time, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | int | 旋转角度(0-360) |
| time | 是 | int | 时间 |
| timelineCB | 是 | function | 回调函数 |
旋转到某个角度（旋转到指定角度）

Timeline_RotateBy(widget, value, time, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | int | 旋转角度(0-360) |
| time | 是 | int | 时间 |
| timelineCB | 是 | function | 回调函数 |
旋转到某个角度（从原来角度 旋转到 某个角度）
移动动画
Timeline_MoveTo(widget, value, time, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | table | {x = 0, y = 0} |
| time | 是 | int | 时间 |
| timelineCB | 是 | function | 回调函数 |
移动到某坐标（移动绝对位置）

Timeline_MoveBy(widget, value, time, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | table | {x = 0, y = 0} |
| time | 是 | int | 时间 |
| timelineCB | 是 | function | 回调函数 |
移动到某坐标（移动相对位置）
闪烁动画
Timeline_Blink(widget, value, time, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | int | 闪烁次数 |
| time | 是 | int | 时间 |
| timelineCB | 是 | function | 回调函数 |
闪烁效果

震动动画
Timeline_Shake(widget, time, x, y, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| time | 是 | int | 时间 |
| x | 是 | int | X轴震动像素 |
| y | 是 | int | Y轴震动像素 |
| timelineCB | 是 | function | 回调函数 |
震动效果

疯狂抖动动画
Timeline_Waggle(widget, time, angle)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| time | 是 | int | 时间 |
| angle | 是 | int | 抖动幅度（0-360） |
震动效果
动画延迟播放
Timeline_DelayTime(widget, time, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| time | 是 | int | 延迟时间 |
| timelineCB | 是 | function | 回调函数 |
动画回调方法
Timeline_CallFunc(widget, time, timelineCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| time | 是 | int | 延迟时间 |
| timelineCB | 是 | function | 回调函数 |
动画延迟显示
Timeline_Show(widget, time)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| time | 是 | int | 延迟时间 |
动画延迟隐藏
Timeline_Hide(widget, time)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| time | 是 | int | 延迟时间 |
缓动动画
Timeline_EaseSineIn_MoveTo(widget, value, time, callback)

widget 对象由慢到快，移动到目标位置

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 对象 |
| value | 是 | table | 目标坐标位置 |
| time | 是 | int | 动作时间 |
| callback | 否 | function | 动作执行完的回调 |
Timeline_EaseSineOut_MoveTo(widget, value, time, callback)

widget 对象由快到慢，移动到目标位置

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 对象 |
| value | 是 | table | 目标坐标位置 |
| time | 是 | int | 动作时间 |
| callback | 否 | function | 动作执行完的回调 |
Timeline_DigitChange(widget, cur, target, interval)

widget 数字滚动动画

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 对象 [ 仅限Button、Text控件] （3.40.8支持TextAtlas控件） |
| cur | 是 | int | 当前数值 |
| target | 是 | int | 目标数值 |
| interval | 否 | int | 变动间隔（秒） |
创建层容器
Layout_Create(parent, ID, x, y, width, height, isClip)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| width | 是 | int | 宽度 |
| height | 是 | int | 长度 |
| isClip | 是 | bool | 是否裁切 |
示例代码
local layout = GUI:Layout_Create(parent, "layout", 0, 0, 100, 100, false)

设置层背景颜色
Layout_setBackGroundColor(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 层对象 |
| value | 是 | string | 色值(“#000000”) |
! 渐变色需传参table {"#FF0000", "#FFFFFF"}
设置层背景颜色类型
Layout_setBackGroundColorType(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 层对象 |
| value | 是 | int | 类型(1单色，2渐变色) |
设置层背景颜色不透明度
Layout_setBackGroundColorOpacity(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 层对象 |
| value | 是 | int | 不透明度(0-255) |
设置层背景是否裁切
Layout_setClippingEnabled(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 层对象 |
| value | 是 | bool | 是否裁切 |
设置层背景图片
Layout_setBackGroundImage(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 层对象 |
| value | 是 | string | 图片路径 |
设置层背景图片九宫格
Layout_setBackGroundImageScale9Slice(widget, scale9l, scale9r, scale9t, scale9b)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 层对象 |
| scale9l | 是 | int | 左边比例 |
| scale9r | 是 | int | 右边比例 |
| scale9t | 是 | int | 上边比例 |
| scale9b | 是 | int | 下边比例 |
设置层背景图片不透明度 [3.40.9版本]
Layout_setBackGroundImageOpacity(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 层对象 |
| value | 是 | int | 不透明度(0-255) |
移除层背景图片设置 [3.40.5版本]
Layout_removeBackGroundImage(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 层对象 |
获取层背景图片文件路径 [3.40.8版本]
Layout_getBackGroundImageFile(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 层对象 |
创建层容器
Layout_Create(parent, ID, x, y, width, height, isClip)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| width | 是 | int | 宽度 |
| height | 是 | int | 长度 |
| isClip | 是 | bool | 是否裁切 |
示例代码
local layout = GUI:Layout_Create(parent, "layout", 0, 0, 100, 100, false)

设置层背景颜色
Layout_setBackGroundColor(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 层对象 |
| value | 是 | string | 色值(“#000000”) |
! 渐变色需传参table {"#FF0000", "#FFFFFF"}
设置层背景颜色类型
Layout_setBackGroundColorType(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 层对象 |
| value | 是 | int | 类型(1单色，2渐变色) |
设置层背景颜色不透明度
Layout_setBackGroundColorOpacity(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 层对象 |
| value | 是 | int | 不透明度(0-255) |
设置层背景是否裁切
Layout_setClippingEnabled(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 层对象 |
| value | 是 | bool | 是否裁切 |
设置层背景图片
Layout_setBackGroundImage(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 层对象 |
| value | 是 | string | 图片路径 |
设置层背景图片九宫格
Layout_setBackGroundImageScale9Slice(widget, scale9l, scale9r, scale9t, scale9b)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 层对象 |
| scale9l | 是 | int | 左边比例 |
| scale9r | 是 | int | 右边比例 |
| scale9t | 是 | int | 上边比例 |
| scale9b | 是 | int | 下边比例 |
设置层背景图片不透明度 [3.40.9版本]
Layout_setBackGroundImageOpacity(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 层对象 |
| value | 是 | int | 不透明度(0-255) |
移除层背景图片设置 [3.40.5版本]
Layout_removeBackGroundImage(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 层对象 |
获取层背景图片文件路径 [3.40.8版本]
Layout_getBackGroundImageFile(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 层对象 |
创建滚动容器
ScrollView_Create(parent, ID, x, y, width, height, direction)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| width | 是 | int | 宽度 |
| height | 是 | int | 高度 |
| direction | 是 | int | 1：垂直; 2：水平 |
示例代码
local scrollView = GUI:ScrollView_Create(parent, "scrollView", 0, 0, 300, 500, 1)

设置滚动容器滚动范围大小
ScrollView_setInnerContainerSize(widget, value1, value2)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
| value1 | 是 | int 或 table | 宽度 或 尺寸 |
| value2 | 否 | int | 高度 |
代码示例
local width = 300
local height = 400
local size = {width = 300, height = 400}
GUI:ScrollView_setInnerContainerSize(ScrollView, width, height)
GUI:ScrollView_setInnerContainerSize(ScrollView, size)

获取滚动容器滚动范围大小
ScrollView_getInnerContainerSize(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
返回值：滚动容器滚动范围大小
获取容器内部滚动区域坐标 [3.40.3版本]
ScrollView_getInnerContainerPosition(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
返回值 容器内部滚动区域坐标
设置滚动容器滚动方向
ScrollView_setDirection(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
| value | 是 | int | 1：垂直; 2：水平 |
设置滚动容器是否有回弹
ScrollView_setBounceEnabled(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
| value | 是 | bool | 是否有回弹 |
设置滚动容器是否有裁切
ScrollView_setClippingEnabled(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
| value | 是 | bool | 是否有裁切 |
设置滚动容器背景颜色
ScrollView_setBackGroundColor(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
| value | 是 | string | 色值(“#000000”) |
! 渐变色需传参table {"#FF0000", "#FFFFFF"}
设置滚动容器背景颜色类型
ScrollView_setBackGroundColorType(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
| value | 是 | int | 1：单色，2：渐变色 |
设置滚动容器背景透明度
ScrollView_setBackGroundOpacity(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
| value | 是 | int | 透明度(0-255) |
设置滚动容器背景图片
ScrollView_setBackGroundImage(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
| value | 是 | string | 图片路径 |
设置滚动器背景图片九宫格
ScrollView_setBackGroundImageScale9Slice(widget, scale9l, scale9r, scale9t, scale9b)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
| scale9l | 是 | int | 左边比例 |
| scale9r | 是 | int | 右边比例 |
| scale9t | 是 | int | 上边比例 |
| scale9b | 是 | int | 下边比例 |
移除滚动容器背景图片设置 [3.40.5版本]
ScrollView_removeBackGroundImage(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
设置滚动容器滚动事件
ScrollView_addOnScrollEvent(widget, eventCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
| eventCB | 是 | function | 事件函数 |
滚动容器加载子节点
ScrollView_addChild(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
| value | 是 | obj | 子节点对象 |
滚动容器删除所有子节点
ScrollView_removeAllChildren(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
滚动容器衰减滚动
ScrollView_scrollToTop(widget, time, boolvalue)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
| time | 是 | int | 时间 |
| boolvalue | 是 | bool | 是否衰减（顶部） |
ScrollView_scrollToBottom(widget, time, boolvalue)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
| time | 是 | int | 时间 |
| boolvalue | 是 | bool | 是否衰减（底部） |
ScrollView_scrollToTopLeft(widget, time, boolvalue)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
| time | 是 | int | 时间 |
| boolvalue | 是 | bool | 是否衰减（顶左） |
ScrollView_scrollToRight(widget, time, boolvalue)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
| time | 是 | int | 时间 |
| boolvalue | 是 | bool | 是否衰减（右边） |
ScrollView_scrollToLeft(widget, time, boolvalue) [3.40.5版本]

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
| time | 是 | int | 时间 |
| boolvalue | 是 | bool | 是否衰减（左边） |
ScrollView_scrollToPercentVertical(widget, percent, time, bool) [3.40.5版本]

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
| percent | 是 | int | 百分比 |
| time | 是 | int | 时间 |
| boolvalue | 是 | bool | 是否衰减滚动速度 |
垂直方向滚动
ScrollView_scrollToPercentHorizontal(widget, percent, time, bool) [3.40.5版本]

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
| percent | 是 | int | 百分比 |
| time | 是 | int | 时间 |
| boolvalue | 是 | bool | 是否衰减滚动速度 |
水平方向滚动
滚动容器添加滚动条
SetScrollViewVerticalBar(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| param | 是 | table | 布局参数 |
GUI:SetScrollViewVerticalBar(parent, {
bgPic       = "res/private/gui_edit/scroll/line.png",   -- 背景图
barPic      = "res/private/gui_edit/scroll/p.png",      -- 滑动按钮图片
Arr1PicN    = "res/private/gui_edit/scroll/t.png",      -- 上（正常图）
Arr1PicP    = "res/private/gui_edit/scroll/t_1.png",    -- 上（按下图）可不传
Arr2PicN    = "res/private/gui_edit/scroll/b.png",      -- 下（正常图）
Arr2PicP    = "res/private/gui_edit/scroll/b_1.png",    -- 下（按下图）可不传
default     = 0,                    -- 进度条值（默认是0）
x           = 0,                   -- 进度条坐标 x
y           = 0,                   -- 进度条坐标 y
list        = listHandle,    -- 滚动的容器 list
callFunc    = function (send) -- 容器滚动的回调函数
SL:Print("回调函数")
end,
})

创建翻页容器
PageView_Create(parent, ID, x, y, width, height)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| width | 是 | int | 宽度 |
| height | 是 | int | 高度 |
示例代码
local pageView = GUI:PageView_Create(parent, "pageView", 0, 0, 300, 500)

设置翻页容器是否有裁切
PageView_setClippingEnabled(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
| value | 是 | bool | 是否有裁切 |
设置翻页容器背景颜色
PageView_setBackGroundColor(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
| value | 是 | string | 色值(“#000000”) |
! 渐变色需传参table {"#FF0000", "#FFFFFF"}
设置翻页容器背景颜色类型
PageView_setBackGroundColorType(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
| value | 是 | int | 1：单色，2：渐变色 |
设置翻页容器背景透明度
PageView_setBackGroundColorOpacity(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
| value | 是 | int | 透明度(0-255) |
设置翻页容器滚动到子页面
PageView_scrollToItem(widget, index)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
| index | 是 | int | 子页面序列号 |
获取当前子页面序列号
PageView_getCurrentPageIndex(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
返回值：子页面序列号
设置翻页容器当前子页序列号 [3.40.3版本]
PageView_setCurrentPageIndex(widget, index)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
| index | 是 | int | 子页面序列号 |
获取翻页容器子页面
PageView_getItems(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
返回值：子页面对象
获取翻页容器子页面数量
PageView_getItemCount(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
返回值：子页面数量
翻页容器加载子页面
PageView_addPage(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
| value | 是 | obj | 子页面对象 |
翻页容器加监听事件
PageView_addOnEvent(widget, eventCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 容器对象 |
| eventCB | 是 | function | 监听事件函数 |
创建滚动容器子节点
QuickCell_Create(parent, ID, x, y, w, h, createCB)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| w | 是 | int | 宽度 |
| h | 是 | int | 高度 |
| createCB | 是 | function | 创建子节点内容回调 [函数返回 widget] |
| activeCB | 否 | function | 判断是否需要激活/创建 [函数返回 boolean值] |
| ext_param | 否 | table | 附加参数 |
event_x: boolean 是否横向, 默认false
tick_interval: 检测间隔,默认0.02 [3.40.9版本新增]
示例代码
local listviewCells = GUI:ListView_Create(_parent, "listviewCells", 200, 80, 587, 200, 1)
for i = 1, 10 do
GUI:QuickCell_Create(listviewCells, "QuickCell_Create"..i, 0, 0, 587, 200, function(quickParent)
local item = GUI:Layout_Create(quickParent, "cell_", 0, 0, 571, 70)
-- 图标
local itemIcon = GUI:Image_Create(item, "item_icon", 80, 35, "res/01/010001.png")
GUI:setAnchorPoint(itemIcon, 0.5, 0.5)
-- name
local itemDesc = GUI:Text_Create(item, "item_name", 120, 40, 20, "#D6C6AD", "name.."..i)

-- tips
local itemDesc = GUI:Text_Create(item, "item_desc", 120, 15, 16, "#D6C6AD", "tips")

-- 分割线
local Image_line = GUI:Image_Create(item, "item_line", 0, 0, "res/buff/bg_buffzy_02.png")
GUI:setAnchorPoint(Image_line, 0.5, 0)
GUI:setPosition(Image_line, 571/2, 0)

return item
end)
end

刷新展示
QuickCell_Refresh(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | QuickCell对象 |
强制退出/ 清理内容
QuickCell_Exit(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | QuickCell对象 |
-- 顺序使用 通常用于刷新单个cell内容 [可参照 GUILayout/AuctionPutList 等..]
GUI:QuickCell_Exit(quickCell)
GUI:QuickCell_Refresh(quickCell)

播放动作
runAction(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| value | 是 | obj | 动作内容 |
getActionByTag(widget, tag)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| tag | 是 | int | 动作标记 |

— 通过标记获取动作内容

停止所有动作
stopAllActions(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
stopActionByTag(widget, tag)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 控件对象 |
| tag | 是 | int | 动作标记 |

— 通过标记停止动作

移动
ActionMoveTo(time, x, y)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| time | 是 | int | 时间 |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
移动到B点：以世界坐标系为原点(0,0)
ActionMoveBy(time, x, y)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| time | 是 | int | 时间 |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
A点移动到B点 移动相对位置：以A点为原点(0,0)
缩放
ActionScaleTo(time, ratio, …)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| time | 是 | int | 时间 |
| ratio | 是 | int | 缩放比例（百分比） |
放大或缩小到某一比例
有第三个参数时, 后两位参数分别表示X轴缩放比、Y轴缩放比 3.40.8版本新增
ActionScaleBy(time, ratio, …)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| time | 是 | int | 时间 |
| ratio | 是 | int | 缩放比例（百分比） |
放大或缩小到原来的某一比例
有第三个参数时, 后两位参数分别表示X轴缩放比、Y轴缩放比 3.40.8版本新增
旋转
ActionRotateTo(time, angle)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| time | 是 | int | 时间 |
| angle | 是 | int | 旋转角度 |
旋转到多少角度
ActionRotateBy(time, angle)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| time | 是 | int | 时间 |
| angle | 是 | int | 旋转角度 |
旋转到原来的多少角度
淡入淡出
ActionFadeIn(time)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| time | 是 | int | 时间 |
淡入
ActionFadeOut(time)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| time | 是 | int | 时间 |
淡出
闪烁
ActionBlink(time, num)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| time | 是 | int | 时间 |
| num | 是 | int | 闪烁次数 |
动画回调函数
CallFunc(callback)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| callback | 是 | function | 回调函数 |
延迟
DelayTime(time)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| callback | 是 | int | 延迟时间 |
显示与隐藏
ActionShow() 显示
ActionHide() 隐藏
移除自身
ActionRemoveSelf()
播放顺序
ActionSequence(action, …) 多个动作顺序播放

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| action | 是 | obj | 动作对象 |

示例 :

local function callback()
SL:Print("_____")
end
GUI:runAction(item., GUI:ActionSequence(GUI:ActionScaleTo(0.1, 1.4), GUI:ActionScaleTo(0.1, 1), GUI:CallFunc(callback)))

ActionSpawn(action, …) 多个动作同时播放

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| action | 是 | obj | 动作对象 |
循环播放
ActionRepeat(action, time)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| action | 是 | obj | 动作对象 |
| value | 是 | int | 循环次数 |
ActionRepeatForever(action)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| action | 是 | obj | 动作对象（一直循环） |
复合动作
ActionEaseBackIn(action) 加速度向右，反方向缓慢移动

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| action | 是 | obj | 动作对象 |
ActionEaseBackOut(action) 快速移动到结束，然后缓慢返回到结束

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| action | 是 | obj | 动作对象 |
贝塞尔曲线运动
ActionBezierTo(time, controlPoint_1, controlPoint_2, endPosition)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| time | 是 | int | 时间 |
| controlPoint_1 | 是 | table | 控制点1 坐标 |
| controlPoint_2 | 是 | table | 控制点2 坐标 |
| endPosition | 是 | table | 结束坐标 |

示例 :

local btn = GUI:Button_Create(GUI:Attach_LeftBottom(), "btn1", 200, 200, "res/public/1900000510.png")
local startPos = GUI:p(200, 200)
local endPos = GUI:p(600, 200)
local controlPoint_1 = GUI:p(200, 800)
local controlPoint_2 = GUI:p(600, 500)
local endPosition = endPos
local bezier = GUI:ActionBezierTo(2, controlPoint_1, controlPoint_2, endPosition)
GUI:runAction(btn, bezier)

指数缓冲动作
ActionEaseExponentialIn(action) 缓慢开始, 加速结束

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| action | 是 | obj | 动作对象 |
ActionEaseExponentialOut(action) 加速开始, 缓慢结束

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| action | 是 | obj | 动作对象 |
ActionEaseExponentialInOut(action) 动作缓慢开始和终止

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| action | 是 | obj | 动作对象 |
创建序列帧动画
Frames_Create(parent, ID, x, y, prefix, suffix, beginframe, finishframe, ext)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| prefix | 是 | string | 前缀 |
| suffix | 是 | string | 后缀 |
| beginframe | 否 | int | 起始帧, 默认1 |
| finishframe | 否 | int | 结束帧 |
| ext | 否 | table | 附加参数 {speed = 播放速度(毫秒), |
count = 图片数量,
loop = 播放次数(-1: 循环),
finishhide = 播放结束是否隐藏(1: 隐藏)
callback = 播放结束回调
示例代码
local ext = {
count = 10,
speed = 100,
loop = 1,
finishhide = 1,
callback  = function ()
SL:Print("创建序列帧动画结束回调")
end
}
local frames = GUI:Frames_Create(wnd, "Frames_1", 200, 200, "res/public/word_fubentg_", ".png", 1, 10, ext)

创建粒子特效
ParticleEffect_Create(parent, ID, x, y, res)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| res | 是 | string | 粒子特效资源路径 plist文件 |
设置持续时间
ParticleEffect_setDuration(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 粒子特效 |
| value | 是 | int | 持续时间, 单位: 秒 |
-1 表示永久
设置总粒子数量
ParticleEffect_setTotalParticles(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 粒子特效 |
| value | 是 | int | 数量 |

示例代码
对应资源: petal_1.zip

local widget = GUI:ParticleEffect_Create(GUI:Attach_LeftBottom(), "TT", 568, 320, "res/private/particles/petal_1.plist")
GUI:ParticleEffect_setDuration(widget, -1)
GUI:ParticleEffect_setTotalParticles(widget, 999)

创建Spine动画
SpineAnim_Create(parent, ID, x, y, jsonPath, atlasPath, trackIndex, name, loop)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| jsonPath | 是 | string | json文件路径 |
| atlasPath | 是 | string | atlas文件路径 |
| trackIndex | 是 | int | 轨道索引 |
| name | 是 | string | 动画名 |
| loop | 是 | boolean | 动画是否循环 |
示例代码
示例资源： nandaoshi.zip
GUI:SpineAnim_Create(GUI:Attach_LeftBottom(), "Spine_1", 200, 100, "res/custom/nandaoshi/nandaoshi.json", "res/custom/nandaoshi/nandaoshi.atlas", 1, "animation", true)

Spine38Anim_Create(parent, ID, x, y, jsonPath, atlasPath, trackIndex, name, loop)
3.8版本spine动画 参数同上.
示例代码
示例资源：hero.zip
GUI:Spine38Anim_Create(GUI:Attach_LeftBottom(), "Spine_hero", 400, 200, "res/custom/hero-ess.json", "res/custom/hero.atlas", 1, "attack", true)

3.40.xx 版本使用示例
if SL:GetMetaValue("SPINE_VERSION") == "spine 2.1" then
-- 创建2.1版本spine
GUI:SpineAnim_Create(GUI:Attach_LeftBottom(), "Spine_1", 200, 100, "res/custom/nandaoshi/nandaoshi.json", "res/custom/nandaoshi/nandaoshi.atlas", 1, "animation", true)

elseif SL:GetMetaValue("SPINE_VERSION") == "spine 3.8" then
-- 创建3.8版本spine
GUI:Spine38Anim_Create(GUI:Attach_LeftBottom(), "Spine_hero", 400, 200, "res/custom/hero-ess.json", "res/custom/hero.atlas", 1, "attack", true)

else
-- 不支持spine
end

设置动画播放
SpineAnim_setAnimation(widget, trackIndex, name, loop)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | widget | SpineAnim对象 |
| trackIndex | 是 | int | 轨道索引 |
| name | 是 | string | 动画名 |
| loop | 是 | boolean | 动画是否循环 |
在指定轨道添加动画播放
SpineAnim_addAnimation(widget, trackIndex, name, loop)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | widget | SpineAnim对象 |
| trackIndex | 是 | int | 轨道索引 |
| name | 是 | string | 动画名 |
| loop | 是 | boolean | 动画是否循环 |
等指定轨道当前动画结束单次循环后, 开始这个动画的播放
在指定轨道添加动画播放
SpineAnim_addAnimation(widget, trackIndex, name, loop)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | widget | SpineAnim对象 |
| trackIndex | 是 | int | 轨道索引 |
| name | 是 | string | 动画名 |
| loop | 是 | boolean | 动画是否循环 |
等指定轨道当前动画结束单次循环后, 开始这个动画的播放
动画衔接
SpineAnim_setMix(widget, fromAnimName, toAnimName, duration)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | widget | SpineAnim对象 |
| fromAnimName | 是 | string | 起始动画名 |
| toAnimName | 是 | string | 目标动画名 |
| duration | 是 | float | 过渡时间 |
设置从指定动画过渡到另一动画时的mix持续时间
以下接口供 spine3.8版本 使用! 3.40.9版本新增!
清除轨道所有动画
SpineAnim_clearTracks(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | widget | SpineAnim对象 |
清除指定轨道动画
SpineAnim_clearTrack(widget, trackIndex)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | widget | SpineAnim对象 |
| trackIndex | 是 | int | 轨道索引 |
获取动画播放速度
SpineAnim_getTimeScale(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | widget | SpineAnim对象 |
返回 float 数值
设置动画播放速度
SpineAnim_setTimeScale(widget, scale)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | widget | SpineAnim对象 |
| scale | 是 | float | 播放间隙缩放值 / 播放速度 |
默认为1, 数值越大 播放越快
重置初始姿态
SpineAnim_setToSetupPose(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | widget | SpineAnim对象 |
重置插槽到初始设定
SpineAnim_setSlotsToSetupPose(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | widget | SpineAnim对象 |
查找动画
SpineAnim_findAnimation(widget, name)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | widget | SpineAnim对象 |
| name | 是 | string | 动画名称 |
返回为nil 则动画不存在
设置皮肤
SpineAnim_setSkin(widget, name)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | widget | SpineAnim对象 |
| skinName | 是 | string | 皮肤名称 |
是否绕X轴翻转
SpineAnim_setFlipX(widget, bool)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | widget | SpineAnim对象 |
| bool | 是 | boolean | 是否翻转 |
是否绕Y轴翻转
SpineAnim_setFlipY(widget, bool)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | widget | SpineAnim对象 |
| bool | 是 | boolean | 是否翻转 |
设置插槽内附件
SpineAnim_setAttachment(widget, slotName, attachmentName)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | widget | SpineAnim对象 |
| slotName | 是 | string | 插槽名称 |
| attachmentName | 是 | string | 附件名称 |
此附件在本插槽内
获取插槽内附件
SpineAnim_getAttachment(widget, slotName, attachmentName)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | widget | SpineAnim对象 |
| slotName | 是 | string | 插槽名称 |
| attachmentName | 是 | string | 附件名称 |
返回 SpineAttachment 附件
查找插槽对象
SpineAnim_findSlot(widget, slotName)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | widget | SpineAnim对象 |
| slotName | 是 | string | 插槽名称 |
返回 SpineSlot 插槽对象
获取所有插槽对象
SpineAnim_getSlots(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | widget | SpineAnim对象 |
返回 SpineSlot 插槽对象 列表
注册监听事件回调
SpineAnim_registerSpineEventHandler(widget, handler, eventType)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | widget | SpineAnim对象 |
| handler | 是 | function | 回调方法 |
| eventType | 是 | int | 事件类型 |
参考:SLDefine.SpineAnimEventType
handler 回调参数 param1: table值, 参考如下:
{
animation: "xxanimation",   -- 动画名
loopCount: 1,               -- 循环次数
trackIndex: 0,              -- 轨道索引
type: "xxx"                 -- 事件类型 "start" "interrupt" "end" "dispose" "complete" "event"
eventData: table            -- 自定义事件数据 {name: "xx", floatValue: 0, intValue: 0, stringValue: ""}
}

spineAnim事件类型如下:
SLDefine.SpineAnimEventType = {
Start       = 0,
Interrupt   = 1,
End         = 2,
Complete    = 3,
Dispose     = 4,
Event       = 5
}

插槽对象 SpineSlot
获取插槽对象颜色
SpineSlot_getColor(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | widget | SpineSlot对象 |
返回颜色table, {r = 1, g = 1, b = 1, a = 1} 数值0-1
设置插槽对象颜色
SpineSlot_setColor(widget, r, g, b, a)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | widget | SpineSlot对象 |
| r | 是 | float | 红 (数值0-1) |
| g | 是 | float | 绿 (数值0-1) |
| b | 是 | float | 蓝 (数值0-1) |
| a | 是 | float | 透明度 (数值0-1) |
0: 完全透明 1: 完全不透明
设置插槽对象可见性
SpineSlot_setVisible(widget, isVisible)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | widget | SpineSlot对象 |
| isVisible | 是 | boolean | 是否可见 |
设置插槽对象的附件
SpineSlot_setAttachment(widget, attachment)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | widget | SpineSlot对象 |
| attachment | 是 | widget | SpineAttachment对象 |
接口示例代码
示例资源: custom.zip
-- 3.40.9 测试代码
-- 1. 动画衔接
local parent = GUI:Attach_LeftBottom()
local spineBoyAnim = GUI:Spine38Anim_Create(parent, "spineBoy", 300, 300, "res/custom/spine/spineboy/spineboy-ess.json", "res/custom/spine/spineboy/spineboy.atlas", 0, "walk", false)
GUI:setScale(spineBoyAnim, 0.4)

-- 注册事件
GUI:SpineAnim_registerSpineEventHandler(spineBoyAnim, function(eventData)
SL:PrintTable(eventData, "____START")
end, SLDefine.SpineAnimEventType.Start)
GUI:SpineAnim_registerSpineEventHandler(spineBoyAnim, function(eventData)
SL:PrintTable(eventData, "____INTERRUPT")
end, SLDefine.SpineAnimEventType.Interrupt)
GUI:SpineAnim_registerSpineEventHandler(spineBoyAnim, function(eventData)
SL:PrintTable(eventData, "____END")
end, SLDefine.SpineAnimEventType.End)
GUI:SpineAnim_registerSpineEventHandler(spineBoyAnim, function(eventData)
SL:PrintTable(eventData, "____COMPLETE")
end, SLDefine.SpineAnimEventType.Complete)
GUI:SpineAnim_registerSpineEventHandler(spineBoyAnim, function(eventData)
SL:PrintTable(eventData, "____DISPOSE")
end, SLDefine.SpineAnimEventType.Dispose)
GUI:SpineAnim_registerSpineEventHandler(spineBoyAnim, function(eventData)
SL:PrintTable(eventData, "____EVENT")
end, SLDefine.SpineAnimEventType.Event)

GUI:SpineAnim_setTimeScale(spineBoyAnim, 1.4)
GUI:SpineAnim_setToSetupPose(spineBoyAnim)
GUI:SpineAnim_setAnimation(spineBoyAnim, 0, "run", false)
GUI:SpineAnim_addAnimation(spineBoyAnim, 0, "jump", true)
GUI:SpineAnim_setMix(spineBoyAnim, "run", "jump", 0.3)

SL:ScheduleOnce(function()
-- GUI:SpineAnim_clearTracks(spineBoyAnim)
GUI:SpineAnim_clearTrack(spineBoyAnim, 0)
end, 3)

-- 2. 更换武器/皮肤
local goblinsAnim = GUI:Spine38Anim_Create(parent, "goblinsAnim", 600, 300, "res/custom/spine/goblins/goblins-ess.json", "res/custom/spine/goblins/goblins.atlas", 0, "walk", true, 0.8)
GUI:SpineAnim_setSkin(goblinsAnim, "goblin")
-- GUI:SpineAnim_setSkin(goblinsAnim, "goblingirl")

local btn_1 = GUI:Button_Create(parent, "btn_1", 800, 500, "res/public/1900000673.png")
GUI:Button_setTitleText(btn_1, "还原动画")
GUI:addOnClickEvent(btn_1, function()
GUI:SpineAnim_setToSetupPose(goblinsAnim)
-- 重置插槽
-- GUI:SpineAnim_setSlotsToSetupPose(goblinsAnim)
end)

local btn_2 = GUI:Button_Create(parent, "btn_2", 800, 420, "res/public/1900000673.png")
GUI:Button_setTitleText(btn_2, "更换附件")
GUI:addOnClickEvent(btn_2, function()
-- 左手
GUI:SpineAnim_setAttachment(goblinsAnim, "left-hand-item", "dagger")
-- 将左手一插槽附件设置到右手插槽附件
local daggerAttach = GUI:SpineAnim_getAttachment(goblinsAnim, "left-hand-item", "spear")
local slot = GUI:SpineAnim_findSlot(goblinsAnim, "right-hand-item-top")
print(slot, daggerAttach)
if slot and daggerAttach then
GUI:SpineSlot_setAttachment(slot, daggerAttach)
end
end)

local btn_3 = GUI:Button_Create(parent, "btn_3", 800, 340, "res/public/1900000673.png")
GUI:Button_setTitleText(btn_3, "调整插槽")
GUI:addOnClickEvent(btn_3, function()
-- 不可见
local slot = GUI:SpineAnim_findSlot(goblinsAnim, "right-hand-item-top")
if slot then
GUI:SpineSlot_setVisible(slot, false)
end
-- 颜色
local leftSlot = GUI:SpineAnim_findSlot(goblinsAnim, "left-hand-item")
if leftSlot then
GUI:SpineSlot_setColor(leftSlot, 0, 0, 0, 1)
end
-- 所有插槽
-- local slots = GUI:SpineAnim_getSlots(goblinsAnim)
-- for i = 1, #slots do
--     local slot = slots[i]
--     GUI:SpineSlot_setColor(slot, 1, 0, 0, 1)
-- end
end)

local btn_4 = GUI:Button_Create(parent, "btn_4", 800, 260, "res/public/1900000673.png")
GUI:Button_setTitleText(btn_4, "翻转")
GUI:addOnClickEvent(btn_4, function()
-- GUI:SpineAnim_setFlipX(goblinsAnim, true)
-- Y轴
GUI:SpineAnim_setFlipY(goblinsAnim, true)
end)

创建拖拽容器
MoveWidget_Create(parent, ID, x, y, width, height, from, ext)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| width | 是 | int | 宽 |
| height | 是 | int | 高 |
| from | 是 | int | 控件来自(界面位置) 官方默认的可参照元变量 ITEMFROMUI_ENUM, |
自定义类型的示例 : SL:GetMetaValue("ITEMFROMUI_ENUM").xxx
[xxx: 自定义类型名]
| ext | 否 | table | 额外参数 |
beginMoveCB : 开始移动回调
endMoveCB : 结束移动回调
cancelMoveCB : 取消移动回调
equipPos: 放置装备的装备位置【来源 SL:GetMetaValue("ITEMFROMUI_ENUM").PALYER_EQUIP 时生效】
pcDoubleCB : pc双击回调 [3.40.8版本]
mouseScrollCB: 鼠标滚轮回调 [3.40.8版本]

装备位30的装备拖动穿脱 的示例代码

local bg = GUI:Image_Create(GUI:Attach_LeftBottom(), "bg_TT", 400, 300, "res/public/btn_npcsm_01.png")
local function beginMoveCallBack(node)
GUI:setVisible(node, false)
end
local function endMoveCallBack(node)
GUI:setVisible(node, true)
end
local function cancelMoveCallBack(node)
GUI:setVisible(node, true)
end
local moveWidget = GUI:MoveWidget_Create(bg, "moveWidget", 35, 35, 70, 70, SL:GetMetaValue("ITEMFROMUI_ENUM").PALYER_EQUIP, {equipPos = 30, beginMoveCB = beginMoveCallBack, cancelMoveCB = cancelMoveCallBack, endMoveCB = endMoveCallBack})
local itemData = SL:GetMetaValue("EQUIP_DATA", 30)
if itemData then
local item = GUI:ItemShow_Create(moveWidget, "equipItem", 35, 35, {index = itemData.Index, itemData = itemData, look = true})
GUI:ItemShow_setItemTouchSwallow(item, false)
GUI:setAnchorPoint(item, 0.5, 0.5)
end
-- 穿戴触发
local function takeOnEquip(data)
if data.isSuccess and data.pos == 30 then
GUI:removeAllChildren(moveWidget)
GUI:setVisible(moveWidget, true)
local itemData = SL:GetMetaValue("EQUIP_DATA", 30)
if itemData then
local item = GUI:ItemShow_Create(moveWidget, "equipItem", 35, 35, {index = itemData.Index, itemData=itemData, look = true})
GUI:ItemShow_setItemTouchSwallow(item, false)
GUI:setAnchorPoint(item, 0.5, 0.5)
end
end
end
-- 脱下触发
local function takeOffEquip(data)
if data.isSuccess and data.pos == 30 then
GUI:removeAllChildren(moveWidget)
GUI:setVisible(moveWidget, true)
end
end

SL:RegisterLUAEvent(LUA_EVENT_TAKE_ON_EQUIP, "TESTMove", takeOnEquip)
SL:RegisterLUAEvent(LUA_EVENT_TAKE_OFF_EQUIP, "TESTMove", takeOffEquip)

新增拖拽类型和拖拽事件
AddMoveWidgetTypeEvent(fromType, toType, fromToEvent, toFromEvent)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| fromType | 是 | string | 控件来自位置类型名 |
| toType | 是 | string | 控件到达位置类型名 |
| fromToEvent | 否 | function | 从fromType类型控件 拖拽到 toType类型控件 触发的函数 |
| toFromEvent | 否 | function | 从toType类型控件 拖拽到 fromType类型控件 触发的函数 |
fromToEvent/toFromEvent 起码实现一个.

示例代码

--- 自新增移动类型 来自/去达
local function fromToEvent(_, data)
SL:PrintTable(data)
SL:print("++++++FromToEvent 111 -> 222")
end
local function toFromEvent(_, data)
SL:PrintTable(data)
SL:print("++++++ToFromEvent 222 -> 111")
end
GUI:AddMoveWidgetTypeEvent("from", "to", fromToEvent, toFromEvent)
local moveWidget11 = GUI:MoveWidget_Create(GUI:Attach_LeftBottom(), "moveWidget11", 500, 300, 70, 70, SL:GetMetaValue("ITEMFROMUI_ENUM").from, {cancelMoveCB = cancelMoveCallBack, endMoveCB = endMoveCallBack})
local img = GUI:Image_Create(moveWidget11, "img", 0, 0, "res/public/word_fubentg_1.png")
local tt11 = GUI:Text_Create(moveWidget11, "tt", 0, 35, 18, "#000000", "111")

local moveWidget22 = GUI:MoveWidget_Create(GUI:Attach_LeftBottom(), "moveWidget22", 300, 300, 70, 70, SL:GetMetaValue("ITEMFROMUI_ENUM").to, {cancelMoveCB = cancelMoveCallBack, endMoveCB = endMoveCallBack})
local img = GUI:Image_Create(moveWidget22, "img", 0, 0, "res/public/word_fubentg_2.png")
local tt11 = GUI:Text_Create(moveWidget22, "tt", 0, 35, 18, "#000000", "222")

创建刮图
ScrapePic_Create(parent, ID, x, y, showImg, maskImg, clearHei, moveTime, beginTime, callback)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| showImg | 是 | string | 展示图片资源 |
| maskImg | 是 | string | 遮罩图片资源 |
| clearHei | 否 | int | 刮除高度, 默认16 |
| moveTime | 是 | int | 刮除时间, 单位: 秒 |
| beginTime | 否 | int | 开始点击到结束触发间隔, 单位: 秒 |
示例代码
-- 刮图两秒 自动展示
local TT = GUI:ScrapePic_Create(GUI:Attach_LeftBottom(), "ScrapePic", 250, 200, "res/public/word_fubentg_11.png", "res/public/mask_1.png", 18, 2, 5, function()
SL:Print("刮图完毕|||")
end)

创建列表容器[优化加载]
TableView_Create(parent, ID, x, y, width, height, direction, cellWid, cellHei, num)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| width | 是 | int | 容器宽度 |
| height | 是 | int | 容器高度 |
| direction | 是 | int | 1：垂直; 2：水平 |
| cellWid | 是 | int | 单个cell 宽 |
| cellHei | 是 | int | 单个cell 高 |
| num | 是 | int | 需创建cell个数 |
设置子cell创建方法
TableView_setCellCreateEvent(widget, func)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | tableView对象 |
| func | 是 | function | 创建函数 传入参数(cell父节点, cell下标) |
设置滚动方向
TableView_setDirection(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | tableView对象 |
| value | 是 | int | 滚动方向 1：垂直; 2：水平 |
获取滚动方向 [3.40.9版本]
GUI:TableView_getDirection(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | tableView对象 |
设置背景颜色
TableView_setBackGroundColor(widget, value)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | tableView对象 |
| value | 是 | string | 十六进制颜色值 例: “#FFFFFF” |
设置内部区域偏移位置 [3.40.3版本]
TableView_setContentOffset(widget, x, y)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | tableView对象 |
| x | 是 | int | 偏移坐标X |
| y | 是 | int | 偏移坐标Y |
获取内部区域偏移位置 [3.40.3版本]
TableView_getContentOffset(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | tableView对象 |
添加点击cell事件
TableView_addOnTouchedCellEvent(widget, func)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | tableView对象 |
| func | 是 | function | 点击cell触发回调 |
滚动到某cell位置
TableView_scrollToCell(widget, index)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | tableView对象 |
| index | 是 | int | 对应cell下标 |
添加容器滚动回调 [3.40.3版本]
GUI:TableView_addOnScrollEvent(widget, func)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | tableView对象 |
| func | 是 | function | 容器滚动回调函数 param1: TableView控件 |
设置容器cell个数 [3.40.5版本]
GUI:TableView_setTableViewCellsNumHandler(widget, func)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | tableView对象 |
| func | 是 | int/function | cell总个数(int)/返回cell总个数的函数(func) |
加载容器所有列表数据 [3.40.5版本]
GUI:TableView_reloadData(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | tableView对象 |
结合GUI:TableView_setTableViewCellsNumHandler方法 改变数据使用
加载容器所有列表数据，且维持当前容器偏移位置 [3.40.6版本]
GUI:TableView_reloadDataEx(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | tableView对象 |
结合GUI:TableView_setTableViewCellsNumHandler方法 改变数据使用
添加容器鼠标滚动事件 [3.40.5版本]
GUI:TableView_addMouseScrollEvent(widget, func)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | tableView对象 |
| func | 否 | function | 鼠标滚动回调函数传参{widget = widget, x = 滚动坐标X, y = 滚动坐标Y} [不填采用官方默认添加滚动] |
TableViewCell
获取容器cell的下标/序列号
GUI:TableViewCell_getIdx(cell)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | tableViewCell对象 |

示例代码

local winWidth = 900
local winHeight = 600
local wnd = GUI:Win_Create("Win_1", 0, 0, winWidth, winHeight)

local tableView = GUI:TableView_Create(wnd, "TABLEVIEW", 200, 100, 600, 400, 1, 600, 40, 200)
GUI:TableView_setBackGroundColor(tableView, "#FFFFFF")
GUI:TableView_setDirection(tableView, 2)
-- 设置cell创建方法
GUI:TableView_setCellCreateEvent(tableView, function(parent, idx, ID)
if ID == "TABLEVIEW" then
local panel = GUI:Layout_Create(parent, string.format("layout_%s", idx), 0, 0, 600, 40)
local text = GUI:Text_Create(panel, "TEXT", 0, 20, 18, "#00FF00", "IDX----------------"..idx)
GUI:setAnchorPoint(text, 0, 0.5)
end
end)

local function touchCellFunc(tv, cell)
local idx = GUI:TableViewCell_getIdx(cell)
local panel = GUI:getChildByID(cell, string.format("layout_%s", idx))
GUI:Layout_setBackGroundColorType(panel, 1)
GUI:Layout_setBackGroundColor(panel, "#00EEAA")
if idx == 15 then
GUI:TableView_scrollToCell(tv, 18)
end
end
-- 添加cell点击事件
GUI:TableView_addOnTouchedCellEvent( tableView, touchCellFunc )
SL:ScheduleOnce(function ()
GUI:TableView_scrollToCell(tableView, 6)
end, 1/60)

创建旋转容器
RotateView_Create(parent, ID, x, y, width, scrollGap, param)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| width | 是 | int | 宽度 |
| height | 是 | int | 高度 |
| scrollGap | 是 | int | 滑动间隙, 默认100 |
| param | 是 | table | 子节点参数, 参考如下 |
列表各子节点参数 scale: 缩放大小 img: 图片路径 string node:自定义控件 (img和node不同时存在)
{
[1] = {scale = 0.4},
[2] = {scale = 0.6},
[3] = {scale = 0.8},
}

添加子节点到旋转容器对应下标item
RotateView_addChild(widget, value, index)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 旋转容器对象 |
| value | 是 | obj | 控件对象 |
| index | 是 | int | 对应下标 |
获取对应下标item添加的子节点
RotateView_getChildByIndex(widget, index)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 旋转容器对象 |
| index | 是 | int | 对应下标 |
仅能获取RotateView_addChild方法添加的控件.
获取对应下标item
RotateView_getItemByIndex(widget, index)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 旋转容器对象 |
| index | 是 | int | 对应下标 |
示例代码
local param = {
[1] = {scale = 0.4, img = "res/public/word_fubentg_1.png"},
[2] = {scale = 0.6, img = "res/public/word_fubentg_2.png"},
[3] = {scale = 0.8, img = "res/public/word_fubentg_3.png"},
[4] = {scale = 1.0, img = "res/public/word_fubentg_4.png"},
[5] = {scale = 0.8, img = "res/public/word_fubentg_5.png"},
[6] = {scale = 0.6, img = "res/public/word_fubentg_6.png"},
[7] = {scale = 0.4, img = "res/public/word_fubentg_7.png"},
}
local view = GUI:RotateView_Create(GUI:Attach_LeftBottom(), "rotateView_1", 500, 320, 1000, 500, 100, param)
local item = GUI:RotateView_getItemByIndex(view, 3)
local itemSize = GUI:getContentSize(item)
local layout = GUI:Layout_Create(item, "clickLayout", 0, 0, itemSize.width, itemSize.height)
GUI:setTouchEnabled(layout, true)
GUI:setSwallowTouches(layout, false)
GUI:addOnClickEvent(layout, function()
SL:Print("Click item index 3 !")
GUI:removeFromParent(view)
end)

创建装备框
GUI:EquipShow_Create(parent, ID, x, y, pos, isHero, data)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| parent | 是 | obj | 父节点对象 |
| ID | 是 | string | 唯一ID |
| x | 是 | int | 位置 横坐标 |
| y | 是 | int | 位置 纵坐标 |
| pos | 是 | int | 装备装戴位置 |
| isHero | 否 | boolean | 是否英雄装备 |
| data | 否 | table | 额外参数 |
复制
额外参数 参考如下:
{
look  = true                  -- boolean 是否显示tips
noMouseTips = true            -- boolean PC端鼠标移入不显示tips
bgVisible = true              -- boolean 是否显示背景框
movable = true                -- boolean 是否可拖动
doubleTakeOff = true,         -- boolean 能否双击穿戴
lookPlayer = true,            -- boolean 查看他人数据
}


示例 :

local equipShow = GUI:EquipShow_Create(GUI:Attach_LeftBottom(), "equipShow1", 400, 300, 1, false, {bgVisible = true, look = true, doubleTakeOff = true})
-- 装戴后自动刷新
GUI:EquipShow_setAutoUpdate(equipShow)

设置装备框显示自动刷新
GUI:EquipShow_setAutoUpdate(widget)

| 参数 | 必选 | 类型 | 注释 |
| --- | --- | --- | --- |
| widget | 是 | obj | 装备框对象 |