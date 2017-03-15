---
title: "__readgsbyte、__readgsdword、__readgsqword、__readgsword | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__readgsbyte"
  - "__readgsdword"
  - "__readgsqword"
  - "__readgsword"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__readgsword 組み込み"
  - "__readgsdword 組み込み"
  - "__readgsqword 組み込み"
  - "__readgsbyte 組み込み"
ms.assetid: f822632d-854c-4558-a71b-cdfc3eea2236
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# __readgsbyte、__readgsdword、__readgsqword、__readgsword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 GS セグメントの先頭を基準としたオフセットで指定された場所からメモリを読み取る。  
  
## 構文  
  
```  
unsigned char __readgsbyte(   
   unsigned long Offset   
);  
unsigned short __readgsword(   
   unsigned long Offset   
);  
unsigned long __readgsdword(   
   unsigned long Offset  
);  
unsigned __int64 __readgsqword(   
   unsigned long Offset   
);  
```  
  
#### パラメーター  
 \[入力\] `Offset`  
 から読み取る `GS` の先頭からのオフセット。  
  
## 戻り値  
 \(呼び出された関数の名前が示す位置\) `GS:[``Offset``]` のバイトワードまたはダブル ワード間のメモリの内容。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__readgsbyte`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`__readgsdword`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`__readgsqword`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`__readgsword`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 解説  
 これらの組み込みはカーネル モードでのみ使用できルーチンは組み込みとしてのみ使用できます。  
  
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [\_\_writegsbyte、\_\_writegsdword、\_\_writegsqword、\_\_writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)   
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)