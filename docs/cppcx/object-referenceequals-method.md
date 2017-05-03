---
title: "Object::ReferenceEquals メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Object::ReferenceEquals"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "プラットフォーム、Object::ReferenceEquals"
ms.assetid: a179e74a-46c7-4bfd-b848-b89ef3ff7197
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Object::ReferenceEquals メソッド
指定された Object インスタンスが同一のインスタンスかどうかを判断します。  
  
## 構文  
  
```cpp  
public:static bool ReferenceEquals(  Object^ obj1,   Object^ obj2)  
```  
  
## パラメーター  
 obj1  
 比較する最初のオブジェクト。  
  
 obj2  
 比較する 2 番目のオブジェクト。  
  
## 戻り値  
 2 つのオブジェクトが同一である場合は `true`。それ以外の場合は `false`。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **ヘッダー:** vccorlib.h  
  
## 参照  
 [Platform::Object クラス](../cppcx/platform-object-class.md)