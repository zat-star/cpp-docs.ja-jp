---
title: "__inword | Microsoft Docs"
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
  - "__indword_cpp"
  - "__indword"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "in 命令"
  - "__inword 組み込み"
ms.assetid: 5c617edd-6709-40a1-aad2-40d5e39283c6
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __inword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 `in` 命令を使用して指定したポートからデータを読み込みます。  
  
## 構文  
  
```  
unsigned short __inword(  
   unsigned short Port  
);  
```  
  
#### パラメーター  
 \[入力\] `Port`  
 から読み取るポート。  
  
## 戻り値  
 読み込まれたデータの単語に一致します。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__inword`|x86[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 解説  
 このルーチンは組み込みとしてのみ使用できます。  
  
## Microsoft 固有の仕様→を終了  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)