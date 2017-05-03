---
title: "StringReference::operator= Operator | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::StringReference::operator="
dev_langs: 
  - "C++"
ms.assetid: 03a33467-d65f-4508-bcb4-17d7cc99398f
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# StringReference::operator= Operator
指定されたオブジェクトを現在の `StringReference` オブジェクトに割り当てます。  
  
## 構文  
  
```cpp  
  
   StringReference& operator=(const StringReference& __fstrArg);  
  
StringReference& operator=(const ::default::char16* __strArg);  
  
```  
  
#### パラメーター  
 `__fstrArg`  
 現在の `StringReference` オブジェクトを初期化するために使用される、`StringReference` オブジェクトのアドレス。  
  
 `__strArg`  
 現在の `StringReference` オブジェクトを初期化するために使用される char16 値の配列へのポインター。  
  
## 戻り値  
 `StringReference` 型のオブジェクトへの参照。  
  
## 解説  
 `StringReference` は ref クラスではなく標準 C\+\+ クラスであるため、**オブジェクト ブラウザー**に表示されません。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **ヘッダー:** vccorlib.h  
  
## 参照  
 [Platform::StringReference クラス](../cppcx/platform-stringreference-class.md)