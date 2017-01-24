---
title: "__writegsbyte、__writegsdword、__writegsqword、__writegsword | Microsoft Docs"
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
  - "__writegsbyte"
  - "__writegsqword"
  - "__writegsdword"
  - "__writegsword"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__writegsqword 組み込み"
  - "__writegsbyte 組み込み"
  - "__writegsword 組み込み"
  - "__writegsdword 組み込み"
ms.assetid: 7746cf6d-2259-4139-9aab-c07dd75c8037
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __writegsbyte、__writegsdword、__writegsqword、__writegsword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 GS セグメントの先頭を基準としたオフセットで指定された場所にメモリを記述します。  
  
## 構文  
  
```  
void __writegsbyte(   
   unsigned long Offset,   
   unsigned char Data   
);  
void __writegsword(   
   unsigned long Offset,   
   unsigned short Data   
);  
void __writegsdword(   
   unsigned long Offset,   
   unsigned long Data   
);  
void __writegsqword(   
   unsigned long Offset,   
   unsigned __int64 Data   
);  
```  
  
#### パラメーター  
 \[入力\] `Offset`  
 GS への書き込みの先頭からのオフセットされます。  
  
 \[入力\] `Data`  
 書き込む値。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__writegsbyte`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`__writegsdword`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`__writegsqword`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`__writegsword`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 解説  
 これらの組み込みはカーネル モードでのみ使用できこれらのルーチンは組み込みとしてのみ使用できます。  
  
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [\_\_readgsbyte、\_\_readgsdword、\_\_readgsqword、\_\_readgsword](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)   
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)