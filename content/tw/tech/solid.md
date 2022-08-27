---
title: "SOLID設計"
date: 2022-08-27T20:05:29+08:00
description: "clean architecture"
tags: ["architecture"]
---
## SOLID設計

屬於良好架構的基礎核心觀念，其中主要描述五項原則

- SRP：單一職責原則

  > 軟體只有唯一的理由需要改變
  >
- OCP：開放-封閉原則

  > 要使軟體意於改變要設計成可透過新增來改變這些需求的行為，而
  >
- LSP：liskov替換原則

  > 建置軟體必須來自可互換的部分，這些部分必須遵守允許這些部分相呼替換的契約
  >
- ISP：介面隔離原則

  > 避免使用者依賴不使用的東西
  >
- DIP：依賴反向原則

  > 實作策略的高層程式碼不得依賴實作細節，細節應該依賴策略
  >

### SRP單一職責原則

原描述為『一個模組應該只有一個，且只有一個理由會使其改變』，但後來發現使用者和利益關係者是原則提出的改變理由另外申述該原則『一個模組應該只對唯一的一個使用者或利益相關者負責』


### OCP開放封閉原則

一個軟體應對擴展是開放的，但修改是封閉的

### LSP Liskov替換原則

若對型態Ｓ的每個物件o1，都存在一個型態為T的物件o2，使得在所有針對T編寫的程式Ｐ，用o1替換o2後，程式Ｐ行為功能不變,則S是Ｔ的子型態

### ISP 介面隔離元則

你依賴的模組包含你所需要的，那就是有害的，對原始碼的依賴性這顯然是對的

### DIP 依賴反向原則

最靈活的設計就是原始碼依賴關係只涉及抽象不涉及具體實現