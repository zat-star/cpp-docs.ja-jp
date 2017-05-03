---
title: "Agile::Agile コンストラクター | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::Agile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::Agile"
ms.assetid: 33c1df82-f5db-4750-98cc-0daa03be4e59
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Agile::Agile コンストラクター
アジャイル クラスの新しいインスタンスを初期化します。  
  
## 構文  
  
```cpp  
  
 Agile();  
  
Agile(T^ object);   
  
Agile(const Agile<T>& object);  
  
Agile(Agile<T>&& object);  
  
```  
  
#### パラメーター  
 `T`  
 テンプレート型名パラメーターで指定される型。  
  
 `object`  
 このコンストラクターの 2 番目のバージョンでは、新しいアジャイル インスタンスを初期化するために使用されるオブジェクト。 3 番目のバージョンでは、新しいアジャイル インスタンスにコピーされるオブジェクト。 4 番目のバージョンでは、新しいアジャイル インスタンスに移動されるオブジェクト。  
  
## 解説  
 このコンストラクターの最初のバージョンは、既定のコンストラクターです。 2 番目のバージョンは、`object` パラメーターで指定されたオブジェクトから新しいアジャイル インスタンス クラスを初期化します。 3 番目のバージョンは、コピー コンストラクターです。 4 番目のバージョンは、移動コンストラクターです。 このコンストラクターは例外をスローできません。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **ヘッダー:** vccorlib.h  
  
## 参照  
 [Platform::Agile クラス](../cppcx/platform-agile-class.md)