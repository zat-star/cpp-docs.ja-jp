---
title: "STAThreadAttribute::Equals | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::STAThreadAttribute::Equals"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "STAThreadAttribute::Equals"
ms.assetid: 8a63d242-6da9-4064-a091-fbfd792708f3
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# STAThreadAttribute::Equals
指定したオブジェクトが、現在のオブジェクトと等しいかどうかを判断します。  
  
## 構文  
  
```cpp  
public:virtual override bool Equals(  Object^ obj)  
```  
  
## パラメーター  
 obj  
 比較対象のオブジェクト。  
  
## 戻り値  
 オブジェクトが等しい場合は `true`。それ以外の場合は `false`。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **ヘッダー:** vccorlib.h  
  
## 参照  
 [Platform::STAThreadAttribute クラス](../cppcx/platform-stathreadattribute-class.md)