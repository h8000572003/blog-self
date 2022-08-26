---
title: "Hitachi Content Platform 雲端平台"
date: 2022-08-10T20:05:29+08:00
tag: "#java"
toc: true
description: "歡迎同仁互相討論，若發現文章有問題請寫信告知"
---
## [Hitachi Content Platform](https://www.hitachivantara.com/en-us/products/data-storage/object-storage/content-platform.html)

此為Hitachi提供之檔案放置雲端平台之解決方案，參考API說明書，撰寫該元件之共用元件建立

提供以下服務

- 新增
- 刪除
- 更新
- 查詢

### 查詢範例

```
@Test
void test_get_file_then_HcpGet_then_file() {

   HcpGet hcpDownloadInfo = new HcpGet();
   String restPath = HcpUtil.toRestPath("x.pdf", "1", "2", "3", "4");
   hcpDownloadInfo.setPath(restPath);

   GetHcpInfo execute;
   try {
      execute = hcpService.execute(hcpDownloadInfo);
      String size = execute.getSize();
      assertThat(size).isNotBlank();
   } catch (HcpCodeExcepton e) {
      fail("");
   }

}
```

### 刪除範例

```
@Test
void test_delet_file_then_HcpGet_then_ok() {
   HcpDelete cmd = new HcpDelete();
   String restPath = HcpUtil.toRestPath("x.pdf", "1", "2", "3", "4");
   cmd.setPath(restPath);

   try {
      BaseHcpInfo execute = hcpService.execute(cmd);
   } catch (HcpCodeExcepton e) {
      e.printStackTrace();
   }

}
```

新增範例

```
@Test
void test_put_file_then_put_then_ok() throws IOException, URISyntaxException {

   String restPath = HcpUtil.toRestPath("x.pdf", "1", "2", "3", "4");
   URL resource = HcpServiceTest.class.getClassLoader().getResource("test.zip");

   byte[] myByte = FileUtils.readFileToByteArray(new File(resource.toURI()));

   HcpPut cmd = new HcpPut(restPath, myByte);

   try {
      BaseHcpInfo execute = hcpService.execute(cmd);
      log.info("execute:{}", execute);
   } catch (HcpCodeExcepton e) {
      log.info("error code:{}", e.getCode(), e);
   }

}
```


### maven設定

<dependency>
  <groupId>io.github.h8000572003</groupId>
  <artifactId>hcp</artifactId>
  <version>0.0.5</version>
</dependency>


```
<dependency>
  <groupId>io.github.h8000572003</groupId>
  <artifactId>hcp-start</artifactId>
  <version>0.0.1</version>
</dependency>
```
