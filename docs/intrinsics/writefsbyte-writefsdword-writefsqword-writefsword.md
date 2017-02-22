---
title: "__writefsbyte、__writefsdword、__writefsqword、__writefsword | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__writefsword"
  - "__writefsbyte"
  - "__writefsqword"
  - "__writefsdword"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "writefsbyte 組み込み"
  - "__writefsword 組み込み"
  - "writefsqword 組み込み"
  - "writefsdword 組み込み"
  - "__writefsdword 組み込み"
  - "__writefsqword 組み込み"
  - "__writefsbyte 組み込み"
  - "writefsword 組み込み"
ms.assetid: 23ac6e8e-bc91-4e90-a4c6-da02993637ad
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __writefsbyte、__writefsdword、__writefsqword、__writefsword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 FS セグメントの先頭を基準としたオフセットで指定された場所にメモリを記述します。  
  
## 構文  
  
```  
void __writefsbyte(   
   unsigned long Offset,   
   unsigned char Data   
);  
void __writefsword(   
   unsigned long Offset,   
   unsigned short Data   
);  
void __writefsdword(   
   unsigned long Offset,   
   unsigned long Data   
);  
void __writefsqword(   
   unsigned long Offset,   
   unsigned __int64 Data   
);  
```  
  
#### パラメーター  
 \[入力\] `Offset`  
 書き込みに FS の先頭からのオフセットされます。  
  
 \[入力\] `Data`  
 書き込む値。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__writefsbyte`|x86|  
|`__writefsword`|x86|  
|`__writefsdword`|x86|  
|`__writefsqword`|x86|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 解説  
 これらのルーチンは組み込みとしてのみ使用できます。  
  
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [\_\_readfsbyte、\_\_readfsdword、\_\_readfsqword、\_\_readfsword](../intrinsics/readfsbyte-readfsdword-readfsqword-readfsword.md)   
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)