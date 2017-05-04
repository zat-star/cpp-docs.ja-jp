---
title: "String::operator+ 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::operator+"
dev_langs: 
  - "C++"
ms.assetid: 919b5ba4-3d3b-47a4-9893-9a9ce51fb9c8
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::operator+ 演算子
指定された 2 つの [String](../cppcx/platform-string-class.md) オブジェクトの値が同じかどうかを示します。  
  
## 構文  
  
```cpp  
  
bool String::operator+( String^ str1,  
                         String^ str2)  
  
```  
  
#### パラメーター  
 `str1`  
 最初の `String` オブジェクト。  
  
 `str2`  
 内容が `String` に追加される 2 番目の `str1` オブジェクト。  
  
## 戻り値  
 `true` が `str1` に等しい場合は `str2`。それ以外の場合は `false`。  
  
## 解説  
 この演算子は、2 種類のオペランドのデータを含む `String^` オブジェクトを作成します。 パフォーマンスを極端に高める必要がない場合には、便宜上、この演算子を使用します。 関数で "`+`" を数回呼び出しても目立つことはないと思われますが、サイズの大きなオブジェクトまたはテキスト データを頻繁に操作するときには、標準的な C\+\+ の機構と型を使用してください。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** vccorlib.h  
  
## 参照  
 [Platform::String クラス](../cppcx/platform-string-class.md)