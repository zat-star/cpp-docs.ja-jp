---
title: "__writecr8 | Microsoft Docs"
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
  - "_writecr8"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_writecr8 組み込み"
ms.assetid: 6f8bd632-dddb-4335-971e-1acee24aa2b9
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __writecr8
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 CR8 レジスタに値 `Data` を書き込みます。  
  
## 構文  
  
```  
void writecr8(   
   unsigned __int64 Data   
);  
```  
  
#### パラメーター  
 \[入力\] `Data`  
 CR8 登録に書き込む値。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__writecr8`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 解説  
 この組み込みではカーネル モードでのみ使用できルーチンは組み込みとしてのみ使用できます。  
  
## Microsoft 固有の仕様→を終了  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)