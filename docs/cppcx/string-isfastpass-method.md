---
title: "String::IsFastPass メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::IsFastPass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::IsFastPass"
ms.assetid: 0a8c2db7-e44f-45fe-9570-3dc82fbbacdd
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::IsFastPass メソッド
現在の文字列オブジェクトを*高速渡し*操作に含めるかどうかを示します。 高速渡し操作では、参照カウントは中断されます。  
  
## 構文  
  
```cpp  
  
bool IsFastPass();  
```  
  
## 戻り値  
 現在の文字列オブジェクトが高速渡しの場合は `true`。それ以外の場合は `false`。  
  
## 解説  
 参照カウントを使用するオブジェクトがパラメーターであり、呼び出された関数がそのオブジェクトだけを読み取る場合の関数への呼び出しでは、コンパイラは安全に参照カウントを中断し、呼び出しのパフォーマンスを改善することができます。 このプロパティをコード内で活用することはできません。 システムがすべての詳細を処理します。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** vccorlib.h  
  
## 参照  
 [Platform::String クラス](../cppcx/platform-string-class.md)