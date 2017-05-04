---
title: "String::Concat メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::Concat"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::Concat"
ms.assetid: 68052d22-3df0-4777-828d-fc3a8e8a3ab7
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::Concat メソッド
指定された 2 つの String オブジェクトの値を連結します。  
  
## 構文  
  
```cpp  
  
String^ Concat( String ^ str1,   
String ^ str2  
)  
  
```  
  
#### パラメーター  
 `str1`  
 1 つ目の String オブジェクト、または `null`。  
  
 `str2`  
 2 つ目の String オブジェクト、または `null`。  
  
## 戻り値  
 `str1` と `str2` を連結した値を持つ新しい String^ オブジェクト。  
  
 `str1` が `null` で、`str2` がそうでない場合は、`str1` が返されます。`str2` が `null` で、`str1` がそうでない場合は、`str2` が返されます。`str1` と `str2` の両方が `null` の場合は、空の文字列 \(L""\) が返されます。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** vccorlib.h  
  
## 参照  
 [Platform::String クラス](../cppcx/platform-string-class.md)