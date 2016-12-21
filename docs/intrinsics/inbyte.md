---
title: "__inbyte | Microsoft Docs"
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
  - "__inbyte"
  - "__inbyte_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "in 命令"
  - "__inbyte 組み込み"
ms.assetid: 03b61799-2a08-474d-adc4-2cbf7c81a4d5
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __inbyte
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 読み取り `Port` で指定されたポートから 1 バイトを返す `in` 命令を生成します。  
  
## 構文  
  
```  
unsigned char __inbyte(  
   unsigned short Port  
);  
```  
  
#### パラメーター  
 \[入力\] `Port`  
 から読み取るポート。  
  
## 戻り値  
 指定したポートから読み取られたバイト数。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__inbyte`|x86[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 終了 Microsoft 固有の仕様→  
  
## 解説  
 このルーチンは組み込みとしてのみ使用できます。  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)