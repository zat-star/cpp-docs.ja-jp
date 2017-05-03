---
title: "ArrayReference::ArrayReference コンストラクター | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::ArrayReference::ArrayReference"
dev_langs: 
  - "C++"
ms.assetid: 9fc7dfcf-47af-40ba-a697-da476fb90efc
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# ArrayReference::ArrayReference コンストラクター
[Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) クラスの新しいインスタンスを初期化します。  
  
## 構文  
  
```cpp  
ArrayReference(TArg* ataArg, unsigned int sizeArg, bool needsInitArg = false);  
ArrayReference(ArrayReference&& otherArg)  
  
```  
  
#### パラメーター  
 `dataArg`  
 配列データへのポインター。  
  
 `sizeArg`  
 ソース配列の要素数。  
  
 `otherArg`  
 新しいインスタンスを初期化するためにデータが移動される `ArrayReference` オブジェクト。  
  
## 解説  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **ヘッダー:** vccorlib.h  
  
## 参照  
 [Platform::ArrayReference クラス](../cppcx/platform-arrayreference-class.md)   
 [Array と WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)