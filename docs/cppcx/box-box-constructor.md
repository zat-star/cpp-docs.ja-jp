---
title: "Box::Box コンストラクター | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box::Box"
dev_langs: 
  - "C++"
ms.assetid: 3c4777f0-801c-4b24-9426-6d658dfaecf8
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Box::Box コンストラクター
指定された型の値をカプセル化する `Box` を作成します。  
  
## 構文  
  
```cpp  
Box(T valueArg);  
```  
  
#### パラメーター  
 `valueArg`  
 ボックス化される値の型 \(たとえば、`int`、`bool`、`float64`、`DateTime`。\)  
  
## 必要条件  
 **ヘッダー:** vccorlib.h  
  
 **名前空間:** Platform  
  
## 参照  
 [Platform::Box クラス](../cppcx/platform-box-class.md)   
 [ボックス化とボックス化解除](../cppcx/boxing-c-cx.md)