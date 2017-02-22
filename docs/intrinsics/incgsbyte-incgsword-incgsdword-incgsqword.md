---
title: "__incgsbyte、__incgsword、__incgsdword、__incgsqword | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__incgsdword"
  - "__incgsqword_cpp"
  - "__incgsword_cpp"
  - "__incgsword"
  - "__incgsbyte"
  - "__incgsbyte_cpp"
  - "__incgsqword"
  - "__incgsdword_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__incgsbyte 組み込み"
  - "__incgsword 組み込み"
  - "__incgsqword 組み込み"
  - "__incgsdword 組み込み"
ms.assetid: 06bfdf4f-7643-4fe0-8455-60ce3068073e
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __incgsbyte、__incgsword、__incgsdword、__incgsqword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 `GS` セグメントの先頭を基準としたオフセットが指定したメモリ位置に値に 1 を加算します。  
  
## 構文  
  
```  
void __incgsbyte(   
   unsigned long Offset   
);  
void __incgsword(   
   unsigned long Offset   
);  
void __incgsdword(   
   unsigned long Offset  
);  
void __incgsqword(   
   unsigned long Offset   
);  
```  
  
#### パラメーター  
 \[入力\] `Offset`  
 `GS` の先頭からのオフセット。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__incgsbyte`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`__incgsword`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`__incgsdword`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`__incgsqword`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
## 解説  
 これらの組み込みはカーネル モードでのみ使用できルーチンは組み込みとしてのみ使用できます。  
  
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [\_\_addgsbyte、\_\_addgsword、\_\_addgsdword、\_\_addgsqword](../intrinsics/addgsbyte-addgsword-addgsdword-addgsqword.md)   
 [\_\_readgsbyte、\_\_readgsdword、\_\_readgsqword、\_\_readgsword](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)   
 [\_\_writegsbyte、\_\_writegsdword、\_\_writegsqword、\_\_writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)   
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)