# 数据分析平台使用说明

## 基本使用说明

### 网站功能
1. 数据导入
   - 支持上传 Excel 文件（.xlsx, .xls 格式）
   - 可以通过拖拽或点击选择文件按钮上传
   - 上传成功后自动启用"开始分析排名"按钮

2. 分析参数设置
   - 平均在线人数：填写直播间实际平均在线人数
   - 整场单品成交比例要求：设置期望的成交比例（默认10%）
   - 讲解期望成交比例：设置单次讲解的期望成交比例（默认5%）
   - 系统会自动计算期望每次讲解的成交单量

3. 权重编辑
   - 提供四种预设权重方案
   - 支持实时编辑和保存权重设置
   - 权重总和必须为100%

4. 数据展示
   - 支持显示前10名或前20名商品
   - 显示每个商品的详细得分和总分
   - 提供原始数据预览功能

## 密码配置

系统使用 `password.txt` 文件来存储访问密码。该文件应放置在网站根目录下，与 index.html 同级。

### 修改密码步骤：
1. 打开 `password.txt` 文件
2. 直接修改文件内容为新的密码
3. 保存文件

注意：密码文件中不要包含空格或换行符，只需要写入密码本身。

## 权重预设配置

系统的权重预设配置存储在 `weightPresets.js` 文件中。该文件包含四种预设方案：

### 预设方案说明：
1. 曝光成交率优先
   - 讲解效率分权重：15%
   - 曝光点击分权重：35%
   - 点击成交分权重：35%
   - 成交件数分权重：15%

2. 成交件数优先
   - 讲解效率分权重：15%
   - 曝光点击分权重：15%
   - 点击成交分权重：20%
   - 成交件数分权重：50%

3. 讲解效率优先
   - 讲解效率分权重：50%
   - 曝光点击分权重：20%
   - 点击成交分权重：15%
   - 成交件数分权重：15%

4. 自定义
   - 讲解效率分权重：15%
   - 曝光点击分权重：35%
   - 点击成交分权重：35%
   - 成交件数分权重：15%

### 修改权重预设步骤：
1. 打开 `weightPresets.js` 文件
2. 找到需要修改的预设方案
3. 修改对应的权重值
4. 保存文件

注意：每个预设方案的权重总和必须等于100%

### 示例：
```javascript
// 修改"曝光成交率优先"的权重配置
exposureConversion: {
    name: "曝光成交率优先",
    weights: {
        efficiency: 15,    // 讲解效率分权重
        exposure: 35,      // 曝光点击分权重
        conversion: 35,    // 点击成交分权重
        transaction: 15    // 成交件数分权重
    }
}
```

## 在线修改权重
除了直接修改配置文件外，系统也支持通过界面修改权重预设：

1. 在"权重编辑"区域，选择想要修改的预设方案
2. 点击"编辑预设"按钮
3. 在弹出的对话框中修改各项权重值
4. 点击"保存"按钮确认修改

注意：通过界面修改的权重值会保存在浏览器的本地存储中，刷新页面后仍然有效。但如果清除浏览器数据，修改的值会恢复到配置文件中的默认值。 