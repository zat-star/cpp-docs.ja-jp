---
title: "__writecr4 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_writecr4"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_writecr4 組み込み"
ms.assetid: ab7651d7-b86b-4be7-a0a0-7263099c70fc
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __writecr4
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 CR4 レジスタに値 `Data` を書き込みます。  
  
## 構文  
  
```  
void writecr4(   
   unsigned __int64 Data   
);  
```  
  
#### パラメーター  
 \[入力\] `Data`  
 CR4 登録に書き込む値。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__writecr4`|x86[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 解説  
 この組み込みではカーネル モードでのみ使用できルーチンは組み込みとしてのみ使用できます。  
  
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)