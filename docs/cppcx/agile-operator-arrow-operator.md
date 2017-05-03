---
title: "Agile::operator-&gt; 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::operator->"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::operator->"
ms.assetid: 570f4b0b-1735-49b3-8a30-4a302ac57074
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Agile::operator-&gt; 演算子
現在の Agile オブジェクトによって表されるオブジェクトへのハンドルを取得します。  
  
## 構文  
  
```cpp  
  
       T^ operator->()   
const throw();  
```  
  
## 戻り値  
 現在の Agile オブジェクトによって表されるオブジェクトへのハンドル。  
  
 この演算子は、実際には、非公開の内部型を返します。 戻り値を保持する便利な方法は、[auto](~/cpp/auto-cpp.md) 型推論キーワードで宣言された変数に戻り値を代入することです。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **ヘッダー:** vccorlib.h  
  
## 参照  
 [Platform::Agile クラス](../cppcx/platform-agile-class.md)