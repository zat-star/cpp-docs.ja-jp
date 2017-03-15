---
title: "文字テスト | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 376ba061-bae3-427e-9569-33fa5949a199
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 文字テスト
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 4.3.1** `isalnum`、`isalpha`、`iscntrl`、`islower`、`isprint`、および `isupper` 関数がテストする文字セット  
  
 次の一覧は、Microsoft C コンパイラによって実装された、これらの関数について説明します。  
  
|関数|テスト対象|  
|--------|-----------|  
|`isalnum`|文字 0 ～ 9、A ～ Z、a ～ z、ASCII 48 ～ 57、65 ～ 90、97 ～ 122|  
|`isalpha`|文字 A ～ Z、a ～ z、ASCII 65 ～ 90、97 ～ 122|  
|`iscntrl`|ASCII 0 ～ 31、127|  
|`islower`|文字 a ～ z、ASCII 97 ～ 122|  
|`isprint`|文字 A ～ Z、a ～ z、0 ～ 9、句読点、スペース、ASCII 32 ～ 126|  
|`isupper`|文字 A ～ Z、ASCII 65 ～ 90|  
  
## 参照  
 [ライブラリ関数](../c-language/library-functions.md)