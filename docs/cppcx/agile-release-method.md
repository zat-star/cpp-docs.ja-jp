---
title: "Agile::Release メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::Release"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::Release"
ms.assetid: aa825134-943f-425d-857e-449ec104765e
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Agile::Release メソッド
現在の Agile オブジェクトの基になるオブジェクトとコンテキストを破棄します。  
  
## 構文  
  
```cpp  
  
void Release() throw();  
  
```  
  
## 解説  
 現在の Agile オブジェクトの基になるオブジェクトとコンテキスト \(存在する場合\) が破棄され、Agile オブジェクトの値が null に設定されます。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **ヘッダー:** vccorlib.h  
  
## 参照  
 [Platform::Agile クラス](../cppcx/platform-agile-class.md)