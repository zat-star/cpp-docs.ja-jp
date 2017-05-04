---
title: "ArrayReference::operator= 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::ArrayReference::operator="
dev_langs: 
  - "C++"
ms.assetid: 131a4612-d66b-48e4-90af-c665ccc0cce4
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# ArrayReference::operator= 演算子
移動セマンティクスを使用して、現在の [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) オブジェクトに指定したオブジェクトを割り当てます。  
  
## 構文  
  
```cpp  
  
ArrayReference& operator=(ArrayReference&& __otherArg);  
  
```  
  
#### パラメーター  
 `__ otherArg`  
 現在の `ArrayReference` オブジェクトに移動されたオブジェクト。  
  
## 戻り値  
 `ArrayReference` 型のオブジェクトへの参照。  
  
## 解説  
 `Platform::ArrayReference` は、ref クラスではなく、標準 C\+\+ クラス テンプレートです。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **ヘッダー:** vccorlib.h  
  
## 参照  
 [Platform::ArrayReference クラス](../cppcx/platform-arrayreference-class.md)