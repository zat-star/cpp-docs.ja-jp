---
title: "String::operator&gt; 演算子 (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::operator>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::operator>"
ms.assetid: d32ad538-b992-4487-a1d3-ad7ba84dbdff
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::operator&gt; 演算子 (C++/CX)
1 つの String オブジェクトの値が、2 番目の String オブジェクトの値より大きいかどうかを示します。  
  
## 構文  
  
```cpp  
  
bool String::operator>( String^ str1,  
                         String^ str2)  
  
```  
  
#### パラメーター  
 `str1`  
 1 つ目の String オブジェクト。  
  
 `str2`  
 2 つ目の String オブジェクト。  
  
## 戻り値  
 `str1` の値が `str2` の値より大きい場合は `true`。それ以外の場合は `false`。  
  
## 解説  
 この演算子は明示的に [String::CompareOrdinal](../cppcx/string-compareordinal-method.md) を呼び出し、0 より大きな結果を取得する操作と同じです。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** vccorlib.h  
  
## 参照  
 [Platform::String クラス](../cppcx/platform-string-class.md)