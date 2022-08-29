---
title: "Telegram"
date: 2022-08-29T23:05:43+08:00
tags: ["元件"]
---
Telegram是跨平台的即時通訊軟體，其用戶端是自由及開放原始碼軟體，但伺服器端是專有軟體。使用者可以相互交換加密與自毀訊息，傳送相片、影片等所有類型檔案。官方提供手機版、電腦版和網頁版等多種平台用戶端；同時官方開放應用程式介面，因此擁有許多第三方的用戶端可供選擇


## 專案使用目的

* 透過即時訊息，即刻掌握系統狀態
* 透過指令進行操作服務


### 程式設計規則

建立BotCmdService(機器人指令服務)，註冊機器人命令規則，透過呼叫BotCmdService.exeCmd方式處理該命令方式。



```java
/**
 * 機器人命令
 * @author andy
 *
 */
public interface IBotCmd {

	/**
	 * 
	 * @param arg 命令
	 * @param context 訊息上下文
	 * @return 命令回訊方式
	 */ 
	BotCmdResponse execute(String arg, BotContext context);
}
```
