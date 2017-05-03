---
title: "Agile::operator= 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::operator="
ms.assetid: 2c413bef-f103-4911-afb3-0dac5f6a760e
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Agile::operator= 演算子
指定されたオブジェクトを現在のアジャイル オブジェクトに割り当てます。  
  
## 構文  
  
```cpp  
  
   Agile<T> operator=(  
   T^ object  
) throw();  
  
   Agile<T> operator=(  
      const Agile<T>& object  
) throw();  
  
   Agile<T> operator=(  
      Agile<T>&& object  
) throw();  
  
   T^ operator=(  
      IUnknown* lp  
) throw();  
  
```  
  
#### パラメーター  
 `T`  
 テンプレート型名で指定される型。  
  
 `object`  
 現在のアジャイル オブジェクトにコピーまたは移動されるオブジェクト、またはオブジェクトへのハンドル。  
  
 `lp`  
 オブジェクトの IUnknown インターフェイス ポインター。  
  
## 戻り値  
 `T` 型のオブジェクトへのハンドル。  
  
## 解説  
 代入演算子の 1 つ目のバージョンは、参照型へのハンドルを現在のアジャイル オブジェクトにコピーします。 2 つ目のバージョンは、アジャイル型への参照を現在のアジャイル オブジェクトにコピーします。 3 つ目のバージョンは、アジャイル型を現在のアジャイル オブジェクトに移動します。 4 つ目のバージョンは、COM オブジェクトへのポインターを現在のアジャイル オブジェクトに移動します。  
  
 代入演算は、現在のアジャイル オブジェクトのコンテキストを自動的に保持します。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **ヘッダー:** vccorlib.h  
  
## 参照  
 [Platform::Agile クラス](../cppcx/platform-agile-class.md)