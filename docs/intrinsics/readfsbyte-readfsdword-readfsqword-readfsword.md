---
title: "__readfsbyte、__readfsdword、__readfsqword、__readfsword | Microsoft Docs"
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
  - "__readfsword"
  - "__readfsdword"
  - "__readfsbyte"
  - "__readfsqword"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__readfsword 組み込み"
  - "readfsword 組み込み"
  - "__readfsdword 組み込み"
  - "readfsbyte 組み込み"
  - "__readfsbyte 組み込み"
  - "readfsdword 組み込み"
  - "readfsqword 組み込み"
  - "__readfsqword 組み込み"
ms.assetid: f6ee7203-4179-402c-a464-0746c84ce6ac
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __readfsbyte、__readfsdword、__readfsqword、__readfsword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 FS セグメントの先頭を基準としたオフセットで指定された場所からメモリを読み取る。  
  
## 構文  
  
```  
unsigned char __readfsbyte(   
   unsigned long Offset   
);  
unsigned short __readfsword(   
   unsigned long Offset   
);  
unsigned long __readfsdword(   
   unsigned long Offset  
);  
unsigned __int64 __readfsqword(   
   unsigned long Offset   
);  
```  
  
#### パラメーター  
 \[入力\] `Offset`  
 から読み取る `FS` の先頭からのオフセット。  
  
## 戻り値  
 \(呼び出された関数の名前が示す位置\) `FS:[``Offset``]` のバイトワードまたはダブル ワード間のメモリの内容。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__readfsbyte`|x86|  
|`__readfsdword`|x86|  
|`__readfsqword`|x86|  
|`__readfsword`|x86|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 解説  
 これらのルーチンは組み込みとしてのみ使用できます。  
  
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [\_\_writefsbyte、\_\_writefsdword、\_\_writefsqword、\_\_writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)   
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)