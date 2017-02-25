---
title: "delete 演算子 (CRT) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "delete"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "delete 演算子"
  - "スカラー delete"
ms.assetid: bcd0066a-0022-45f5-af4c-9007c64a6b89
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# delete 演算子 (CRT)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

frees ブロックを代入します。  
  
## 構文  
  
```  
  
      void __cdecl operator delete(  
   void * object  
);  
void __cdecl operator delete(  
   void * object,   
   void * memory  
) throw();  
void __cdecl operator delete(  
   void * object,   
   const std::nothrow_t&  
) throw();  
```  
  
#### パラメーター  
 *memory*  
 解放するメモリ位置。  
  
 *object*  
 削除したオブジェクトへのポインター。  
  
## 解説  
 **演算子 削除** のこのフォームはベクターの削除のフォーム \([&#91;&#93;演算子の削除](../c-runtime-library/delete-operator-crt.md)\) とは対照的スカラー delete と呼びます。  
  
 **演算子 削除** は [新しい演算子](../c-runtime-library/operator-new-crt.md)によって割り当てられたメモリを解放します。  
  
 この演算子の最初のフォームは nonplacement のフォームと呼ばれます。  この演算子の 2 番目と 3 番目のフォームはコードから呼び出す場合には、通常、仮引数付きの new が失敗すると、存在するコンパイラに一致の削除を許可するが、呼び出されません。  
  
 演算子の最初のフォームはコンパイラによって定義され、new.h をプログラムに含まれる必要がありません。  
  
 スローするか、非スローする動作を除き、CRT **演算子 削除** は、標準 C\+\+ ライブラリの [演算子の削除](../Topic/operator%20delete%20\(%3Cnew%3E\).md) と同様に動作します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|**delete**|\<new.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 使用例  
 演算子を使用 **削除**の例については [新しい演算子](../c-runtime-library/operator-new-crt.md) を参照してください。  
  
## 参照  
 [メモリ割り当て](../c-runtime-library/memory-allocation.md)