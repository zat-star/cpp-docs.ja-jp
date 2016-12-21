---
title: "allocator&lt;void&gt; クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "memory/std::allocator<void>"
  - "std::allocator<void>"
  - "std.allocator<void>"
  - "allocator<void>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator<void> クラス"
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
caps.latest.revision: 18
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# allocator&lt;void&gt; クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このコンテキストの意味を適切な型を定義する `void`を入力するテンプレート クラスの特殊化。  
  
## 構文  
  
```  
template<>  
   class allocator<void> {  
   typedef void *pointer;  
   typedef const void *const_pointer;  
   typedef void value_type;  
   template<class Other>  
      struct rebind;  
   allocator( );  
   allocator(  
      const allocator<void>&  
   );  
   template<class Other>  
      allocator(  
         const allocator<Other>&  
      );  
   template<class Other>  
      allocator<void>& operator=(  
         const allocator<Other>&  
      );  
   };  
```  
  
## 解説  
 クラスは明示的に *void*型のテンプレート クラス [アロケーター](../standard-library/allocator-class.md) を簡単にします。そのコンストラクターと代入演算子は、テンプレート クラスの場合と同じように動作しますが、次の型を定義する:  
  
-   [const\_pointer](../Topic/allocator::const_pointer.md)。  
  
-   [ポインタ](../Topic/allocator::pointer.md)。  
  
-   [value\_type](../Topic/allocator::value_type.md)。  
  
-   [バインド](../Topic/allocator::rebind.md)の入れ子になったテンプレート クラスです。  
  
## 必要条件  
 **ヘッダー:** の\<メモリ\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)