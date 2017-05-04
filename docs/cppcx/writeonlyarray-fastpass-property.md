---
title: "WriteOnlyArray::FastPass プロパティ | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::WriteOnlyArray::FastPass"
dev_langs: 
  - "C++"
ms.assetid: f7a54ae0-afa0-4728-8736-c63933f789aa
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# WriteOnlyArray::FastPass プロパティ
内部の FastPass 最適化を実行できるかどうかを示します。 ユーザー コードでの使用を目的としたものではありません。  
  
## 構文  
  
```cpp  
property bool FastPass{  
   bool get() const;  
}  
```  
  
## 戻り値  
 配列が FastPass かどうかを示すブール値。  
  
## 必要条件  
 **ヘッダー:** vccorlib.h  
  
 **名前空間:** Platform  
  
## 参照  
 [Platform::WriteOnlyArray クラス](../cppcx/platform-writeonlyarray-class.md)