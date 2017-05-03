---
title: "StringReference::StringReference コンストラクター | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::StringReference::StringReference"
dev_langs: 
  - "C++"
ms.assetid: 87dd9201-e638-4913-b37c-7091ae3f91ea
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# StringReference::StringReference コンストラクター
`StringReference` クラスの新しいインスタンスを初期化します。  
  
## 構文  
  
```cpp  
  
    StringReference();  
  
   StringReference(const StringReference& __fstrArg)  
  
StringReference(const ::default::char16* __strArg)  
  
StringReference(const ::default::char16* __strArg, size_t __lenArg)  
```  
  
#### パラメーター  
 `__fstrArg`  
 新しいインスタンスを初期化するためにデータが使用される `StringReference`。  
  
 `__strArg`  
 新しいインスタンスを初期化するために使用される char16 値の配列へのポインター。  
  
 `__lenArg`  
 `__strArg` にある要素の数。  
  
## 解説  
 このコンストラクターの最初のバージョンは、既定のコンストラクターです。 2 番目のバージョンは、`StringReference` パラメーターで指定されたオブジェクトから新しい `__fstrArg` インスタンス クラスを初期化します。 3 番目と 4 番目のオーバー ロードは、新しい初期化 `StringReference` char16 値の配列からのインスタンス   。char16 は、16 ビット UNICODE 文字を表します。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **ヘッダー:** vccorlib.h  
  
## 参照  
 [Platform::StringReference クラス](../cppcx/platform-stringreference-class.md)