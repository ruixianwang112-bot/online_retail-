### online_retail-
========================================
RFM 客户价值分层分析 — 作品集说明
========================================
作者：王睿娴
学校：UTM 商业智能硕士
日期：2026.11

一、项目简介
基于 Online Retail II 零售交易数据（2009-12 至 2011-12-09），
完成数据清洗、RFM 指标计算与客户分层，识别高价值客户、
流失客户与低价值客户，并用 Power BI 搭建交互看板，
输出客户运营建议。

二、文件目录与对应关系
00_raw/
    online_retail_II.csv          原始交易数据（未清洗）

01_code/
    online_retail_II.ipynb        数据清洗脚本,RFM 计算与分层脚本

02_clean_data/
    clean_data_online_retail_II.csv   清洗后数据（中间版）
    clean_final.csv                   清洗后数据（最终版，报告以此为准）
    cleaning_report.txt               清洗日志（剔除规则与行数变化）

03_rfm/
    rfm_result.csv                每位客户的 R/F/M 值与分层结果
    rfm_1117_作品集.xlsx           分层统计、汇总与图表底稿

04_powerbi/
    online_retail.pbix            Power BI 看板源文件

05_report/
    RFM_作品集_王睿娴.pdf          最终作品集（封面+方法+看板+结论）
    charts/                       看板截图与图表导出

三、运行顺序
1. 运行 01_code/ online_retail_II.ipynb，读取 00_raw/online_retail_II.csv，
   输出清洗结果到 02_clean_data/
2. 运行 01_code/online_retail_II.ipynb，基于清洗后数据计算 RFM，
   输出 03_rfm/rfm_result.csv
3. 用 03_rfm 结果更新 04_powerbi/online_retail.pbix 看板
4. 导出看板截图，与 05_report 中的方法页、结论页合成最终 PDF

四、数据处理说明
- 剔除取消订单与负数量记录
- 剔除缺失 CustomerID 的记录
- 剔除异常金额记录
- 清洗前记录数：[填]   清洗后记录数：[填]
- R = 距最近一次购买天数；F = 订单频次；M = 消费总额
- 按分位数打分，分层为高价值 / 流失 / 低价值客户

五、口径说明
- 数据截至 2011-12-09
- 营收统计为当前筛选窗口内金额，邮费未完全剔除
- 看板总计与结论页占比均基于同一筛选口径

六、局限
- 数据时间窗较短，未含成本与利润
- 缺少营销触达与渠道信息
- 分层阈值依赖分位数，换数据需重新校准 ###
