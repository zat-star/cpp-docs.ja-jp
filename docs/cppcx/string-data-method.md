---
title: "String::Data メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::Data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::Data"
ms.assetid: 9be4e015-dfb8-431e-a252-8498bd833f03
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::Data メソッド
`char16` \(`wchar_t`\) 要素の C スタイル配列としてオブジェクトのデータ バッファーの先頭へのポインターを返します。  
  
## 構文  
  
```  
const char16* Data()  
```  
  
## 戻り値  
 Unicode 文字の `const` `char16` 配列の先頭へのポインター \(`char16` は `wchar_t` の typedef\) です。  
  
## 解説  
 `Platform::String^` から `wchar_t*` に変換するには、このメソッドを使用します。`String` オブジェクトがスコープ外に出ると、データ ポインターが有効であるという保証がなくなります。 元の `String` オブジェクトの有効期間以上にデータを格納しておくには、[wcscpy\_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) を使用して配列を自分で割り当てたメモリにコピーします。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** vccorlib.h  
  
## 参照  
 [Platform::String クラス](../cppcx/platform-string-class.md)   
 [String::Begin メソッド](../cppcx/string-begin-method.md)