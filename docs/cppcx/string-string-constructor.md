---
title: "String::String コンストラクター | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::String"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::String"
ms.assetid: 80b6461a-5b12-4dcb-9323-f2c5f310bbc6
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::String コンストラクター
入力文字列データのコピーで String クラスの新しいインスタンスを初期化します。  
  
## 構文  
  
```cpp  
  
String();  
  
String(  
  char16* s  
)  
  
String(  
  char16* s,   
  unsigned int n  
)  
```  
  
## パラメーター  
 `s`  
 文字列を初期化する一連のワイド文字。 char16  
  
 `n`  
 文字列の長さを指定する数値。  
  
## 解説  
 パフォーマンスが重要で、かつソース文字列の有効期間を管理する場合は、String の代わりに[Platform::StringReference](../cppcx/platform-stringreference-class.md) を使用することができます。  
  
## 使用例  
  
```  
String^ s = L”Hello!”;  
```  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** vccorlib.h  
  
## 参照  
 [Platform::String クラス](../cppcx/platform-string-class.md)