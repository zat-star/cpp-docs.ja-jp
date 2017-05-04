---
title: "Agile::GetAddressOfForInOut メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::GetAddressOfForInOut"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::GetAddressOfForInOut"
ms.assetid: 8bb27b4c-c325-49ee-91db-9adf87c530c4
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Agile::GetAddressOfForInOut メソッド
現在の Agile オブジェクトによって表されるオブジェクトへのハンドルのアドレスを返します。  
  
## 構文  
  
```cpp  
  
       T^* GetAddressOfForInOut()   
throw();  
  
```  
  
#### パラメーター  
 `T`  
 テンプレート型名パラメーターで指定される型。  
  
## 戻り値  
 現在の Agile オブジェクトによって表されるオブジェクトへのハンドルのアドレス。  
  
## 解説  
 この操作は、現在のスレッドのコンテキストを取得し、基になるオブジェクトへのハンドルのアドレスを返します。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **ヘッダー:** vccorlib.h  
  
## 参照  
 [Platform::Agile クラス](../cppcx/platform-agile-class.md)