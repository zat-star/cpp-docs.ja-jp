---
title: "typeof から T::typeid への移行 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - " __typeof キーワード"
  - "typeid キーワード [C++]"
  - "typeid 演算子"
ms.assetid: 6a0d35a7-7a1a-4070-b187-cff37cfdc205
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# typeof から T::typeid への移行
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] では、C\+\+ マネージ拡張で使用されていた `typeof` 演算子の代わりに `typeid` キーワードが使用されます。  
  
 マネージ拡張では、`__typeof()` 演算子は、マネージ型の名前を渡すと関連する `Type*` オブジェクトを返します。  たとえば、次のようになります。  
  
```  
// Creates and initializes a new Array instance.  
Array* myIntArray =   
   Array::CreateInstance( __typeof(Int32), 5 );  
```  
  
 新しい構文では、`__typeof` は `typeid` の追加フォームで置き換えられ、マネージ型が指定されると `Type^` を返します。  
  
```  
// Creates and initializes a new Array instance.  
Array^ myIntArray =   
   Array::CreateInstance( Int32::typeid, 5 );  
```  
  
## 参照  
 [言語の変更の概要](../Topic/General%20Language%20Changes%20\(C++-CLI\).md)   
 [typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md)