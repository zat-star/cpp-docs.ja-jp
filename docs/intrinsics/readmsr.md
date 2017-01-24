---
title: "__readmsr | Microsoft Docs"
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
  - "__readmsr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "モデル専用レジスタの読み取り"
  - "rdmsr 命令"
  - "__readmsr 組み込み"
ms.assetid: 7ab1f8e8-72cb-4ce4-817d-3e728a3c9716
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __readmsr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 `register` で指定されたモデル固有の登録を読み取り値を返す `rdmsr` 命令を生成します。  
  
## 構文  
  
```  
__int64 __readmsr(   
   int register   
);  
```  
  
#### パラメーター  
 \[入力\] `register`  
 読み取るモデル固有の登録。  
  
## 戻り値  
 指定されたレジスタの値。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__readmsr`|x86[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 解説  
 この関数はカーネル モードでのみ使用できルーチンは組み込みとしてのみ使用できます。  
  
 詳細についてはAMD のドキュメントを参照してください。  
  
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)