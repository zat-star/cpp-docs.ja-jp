---
title: "Agile::Get メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::Get"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::Get"
ms.assetid: d6295e21-ddbe-4302-9158-3498da4d9669
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Agile::Get メソッド
現在の Agile オブジェクトによって表されるオブジェクトへのハンドルを返します。  
  
## 構文  
  
```cpp  
  
          T^ Get() const  
;  
```  
  
## 戻り値  
 現在の Agile オブジェクトによって表されるオブジェクトへのハンドル。  
  
 戻り値の型は、実際には非公開の内部型です。 戻り値を保持する便利な方法は、[auto](../Topic/auto%20\(C++\).md) 型推論キーワードで宣言された変数に戻り値を代入することです。 たとえば、`auto x = myAgileTvariable->Get();` のようにします。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **ヘッダー:** vccorlib.h  
  
## 参照  
 [Platform::Agile クラス](../cppcx/platform-agile-class.md)