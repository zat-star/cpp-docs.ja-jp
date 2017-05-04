---
title: "String::operator== 演算子 (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::operator=="
ms.assetid: c804b269-64f9-4bc0-929b-2dfa87bf46ac
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::operator== 演算子 (C++/CX)
指定された 2 つの String オブジェクトのテキスト値が同じかどうかを示します。  
  
## 構文  
  
```cpp  
  
bool String::operator==( String^ str1,  
                         String^ str2)  
  
```  
  
#### パラメーター  
 `str1`  
 比較する最初の String オブジェクト。  
  
 `str2`  
 比較する 2 番目の String オブジェクト。  
  
## 戻り値  
 `true` の中身が `str1` と等しい場合は `str2`。それ以外の場合は `false`。  
  
## 解説  
 この演算子は [String::CompareOrdinal メソッド](../cppcx/string-compareordinal-method.md)と同等です。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** vccorlib.h  
  
## 参照  
 [Platform::String クラス](../cppcx/platform-string-class.md)