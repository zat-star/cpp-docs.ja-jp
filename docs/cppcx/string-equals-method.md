---
title: "String::Equals メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::Equals"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::Equals"
ms.assetid: b0c78419-242d-4d38-93e3-ff2818412624
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::Equals メソッド
指定された String に現在のオブジェクトと同じ値が存在するかどうかを示します。  
  
## 構文  
  
```cpp  
  
bool String::Equals(Object^ str);  
  
bool String::Equals(String^ str);  
  
```  
  
#### パラメーター  
 `str`  
 比較対象のオブジェクト。  
  
## 戻り値  
 `true` が現在のオブジェクトに等しい場合は `str`。それ以外の場合は、`false`。  
  
## 解説  
 このメソッドは [String::CompareOrdinal メソッド](../cppcx/string-compareordinal-method.md)と同等です。 最初のオーバーロードでは、`str` パラメーターが String^ オブジェクトにキャストできることが想定されています。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** vccorlib.h  
  
## 参照  
 [Platform::String クラス](../cppcx/platform-string-class.md)