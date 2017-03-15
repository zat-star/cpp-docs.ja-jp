---
title: "国/地域識別文字列 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.strings"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "国/地域別文字列"
ms.assetid: 5baf0ccf-0d9b-40dc-83bd-323705287930
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# 国/地域識別文字列
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

国\/地域識別文字列を言語識別文字列と組み合わせて、`setlocale`、`_wsetlocale`、`_create_locale`、および `_wcreate_locale` の関数のロケール指定を作成できます。 さまざまな Windows オペレーティング システムのバージョンでサポートされている国\/地域名のリストについては、「[各国語サポート \(NLS\) API のリファレンス](http://msdn.microsoft.com/goglobal/bb896001.aspx)」をご覧ください。以下のリストの国\/地域識別文字列は、**\[Locale – Language Country\/Region\]** 列にある国の値、または **\[Country or Region name abbreviation\]** 列にある省略形を表しています。  
  
 C ランタイム ライブラリの実装では、次の追加の国\/地域識別文字列および省略形もサポートされています。  
  
|国\/地域識別文字列|省略形|同等のロケール名|  
|----------------|---------|--------------|  
|america|USA|en\-US|  
|britain|GBR|en\-GB|  
|china|CHN|zh\-CN|  
|czech|CZE|cs\-CZ|  
|england|GBR|en\-GB|  
|great britain|GBR|en\-GB|  
|holland|NLD|nl\-NL|  
|hong\-kong|HKG|zh\-HK|  
|new\-zealand|NZL|en\-NZ|  
|nz|NZL|en\-NZ|  
|pr china|CHN|zh\-CN|  
|pr\-china|CHN|zh\-CN|  
|puerto\-rico|PRI|es\-PR|  
|slovak|SVK|sk\-SK|  
|south africa|ZAF|af\-ZA|  
|south korea|KOR|ko\-KR|  
|south\-africa|ZAF|af\-ZA|  
|south\-korea|KOR|ko\-KR|  
|trinidad & tobago|TTO|en\-TT|  
|uk|GBR|en\-GB|  
|united\-kingdom|GBR|en\-GB|  
|united\-states|USA|en\-US|  
|us|USA|en\-US|  
  
## 参照  
 [ロケール名、言語、および国\/地域識別文字列](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [言語識別文字列](../c-runtime-library/language-strings.md)   
 [setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [\_create\_locale、\_wcreate\_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)