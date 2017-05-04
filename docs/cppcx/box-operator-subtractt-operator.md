---
title: "Box::operator T Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box::operator T"
dev_langs: 
  - "C++"
ms.assetid: 7445ef5b-563c-4ff0-829d-f22aa558b5ec
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Box::operator T Operator
値クラス `T` または `enum` クラスの `T` から `Box<T>` へのボックス化変換を有効にします。  
  
## 構文  
  
```cpp  
operator Box<T>^(T valueType);  
```  
  
#### パラメーター  
 `T`  
 列挙型、値クラス、または値構造体。[既定の名前空間](../cppcx/default-namespace.md) に組み込み型を含めます。  
  
## 戻り値  
 ref クラスでボックス化された元の値を表す `Platform::Box<T>``^` インスタンス。  
  
## 必要条件  
 **ヘッダー:** vccorlib.h  
  
 **名前空間:** Platform  
  
## 参照  
 [Platform::Box クラス](../cppcx/platform-box-class.md)   
 [Platform::IBox インターフェイス](../cppcx/platform-ibox-interface.md)   
 [ボックス化とボックス化解除](../cppcx/boxing-c-cx.md)