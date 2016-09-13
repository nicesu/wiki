## Daemon(守護進程) [Back](./../pt.md)
- 守護進程: 指運行在系統後臺的進程
- 系統初始化時被init進程啟動
- 生存期: 系統執行時間
- 一直等待事件發生並處理事件
- 不和任何中斷發生聯繫
- 啟動守護進程
	- 系統啟動時, init進程根據系統啟動文件啟動守護進程, 並以超級進程權限執行
	- **Internet 超級服務器** inetfd可以啟動守護進程
		- 服务器
			- 併發服務器(等待狀態字段為**nowait**)
			- 循環服務器(等待狀態字段為**wait**)
		- 配置文件: /etc/inetd.conf
		<img src="./inetd_list.png">
		<img src="./create_with_inetd.png">
	- **定時任務進程** cron可以週期性啟動守護進程
	- 終端用戶啟動守護進程
