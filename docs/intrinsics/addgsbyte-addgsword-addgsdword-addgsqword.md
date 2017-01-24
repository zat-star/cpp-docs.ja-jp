---
title: "__addgsbyte、__addgsword、__addgsdword、__addgsqword | Microsoft Docs"
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
  - "__addgsdword"
  - "__addgsqword"
  - "__addgsword_cpp"
  - "__addgsword"
  - "__addgsbyte_cpp"
  - "__addgsqword_cpp"
  - "__addgsbyte"
  - "__addgsdword_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__addgsword 組み込み"
  - "__addgsqword 組み込み"
  - "__addgsdword 組み込み"
  - "__addgsbyte 組み込み"
ms.assetid: 4fa03e69-d849-49ed-ba37-1d3aa23c2a21
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __addgsbyte、__addgsword、__addgsdword、__addgsqword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 `GS` セグメントの先頭を基準としたオフセットが指定したメモリ位置に値を追加します。  
  
## 構文  
  
```  
void __addgsbyte(   
   unsigned long Offset,   
   unsigned char Data   
);  
void __addgsword(   
   unsigned long Offset,   
   unsigned short Data   
);  
void __addgsdword(   
   unsigned long Offset,   
   unsigned long Data   
);  
void __addgsqword(   
   unsigned long Offset,   
   unsigned __int64 Data   
);  
```  
  
#### パラメーター  
 \[入力\] `Offset`  
 `GS` の先頭からのオフセット。  
  
 \[入力\] `Data`  
 メモリ位置に追加する値。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__addgsbyte`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`__addgsword`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`__addgsdword`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`__addgsqword`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
## 解説  
 これらの組み込みはカーネル モードでのみ使用できこれらのルーチンは組み込みとしてのみ使用できます。  
  
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [\_\_incgsbyte、\_\_incgsword、\_\_incgsdword、\_\_incgsqword](../intrinsics/incgsbyte-incgsword-incgsdword-incgsqword.md)   
 [\_\_readgsbyte、\_\_readgsdword、\_\_readgsqword、\_\_readgsword](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)   
 [\_\_writegsbyte、\_\_writegsdword、\_\_writegsqword、\_\_writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)   
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)