---
title: "Agile::GetAddressOf メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::GetAddressOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::GetAddressOf"
ms.assetid: f015edf9-4155-4992-a6fc-7ff1edcc5d1e
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Agile::GetAddressOf メソッド
現在の Agile オブジェクトを再初期化し、`T` 型のオブジェクトへのハンドルのアドレスを返します。  
  
## 構文  
  
```cpp  
  
       T^* GetAddressOf()   
throw();  
```  
  
#### パラメーター  
 `T`  
 テンプレート型名パラメーターで指定される型。  
  
## 戻り値  
 `T` 型のオブジェクトへのハンドルのアドレス。  
  
## 解説  
 この操作は、`T` 型のオブジェクト \(存在する場合\) の現在の表現を解放し、Agile オブジェクトのデータ メンバーを再初期化し、現在のスレッドのコンテキストを取得し、非アジャイル オブジェクトを表現できるオブジェクトへのハンドル変数のアドレスを返します。 Agile クラス インスタンスが 1 つのオブジェクトを表現するようにするには、代入演算子 \([Agile::operator\=](../cppcx/agile-operator-assign-operator.md)\) を使用して、Agile クラス インスタンスにオブジェクトを代入します。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **ヘッダー:** vccorlib.h  
  
## 参照  
 [Platform::Agile クラス](../cppcx/platform-agile-class.md)