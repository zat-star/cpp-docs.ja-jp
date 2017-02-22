---
title: "nothrow_t 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "nothrow_t"
  - "std.nothrow_t"
  - "std::nothrow_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "nothrow_t クラス"
ms.assetid: dc7d5d42-ed5a-4919-88fe-bbad519b7a1d
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# nothrow_t 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

新しい演算子への関数のパラメーターとして構造体の割り当てのエラーを報告するために関数が null ポインターを返す必要があることを示すのではなく、スローします例外を使用します。  
  
## 構文  
  
```  
struct std::nothrow_t {};  
```  
  
## 解説  
 構造体は、コンパイラがコンストラクターの正しいバージョンを選択できます。  [nothrow](../Topic/nothrow%20\(%3Cnew%3E\).md) は 型 `std::nothrow_t`オブジェクトのシノニムです。  
  
## 使用例  
 `std::nothrow_t` が関数パラメーターとして方法の例については、使用する [operator new](../Topic/operator%20new%20\(%3Cnew%3E\).md) と [新しい演算子&#91;&#93;](../Topic/operator%20new\(%3Cnew%3E\).md) を参照してください。  
  
## 必要条件  
 新しい \<**ヘッダー:** \>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)