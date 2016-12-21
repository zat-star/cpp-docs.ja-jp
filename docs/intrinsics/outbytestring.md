---
title: "__outbytestring | Microsoft Docs"
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
  - "__outbytestring"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rep outsb 命令"
  - "__outbytestring 組み込み"
  - "outsb 命令"
ms.assetid: c9150661-9c18-427f-bae8-710bba6ed78c
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __outbytestring
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 `Port` で指定されたポートに `Buffer` が指すデータの `Count` の先頭バイトを送信 `rep outsb` 命令を生成します。  
  
## 構文  
  
```  
void __outbytestring(   
   unsigned short Port,   
   unsigned char* Buffer,   
   unsigned long Count   
);  
```  
  
#### パラメーター  
 \[入力\] `Port`  
 データを送信する。  
  
 \[入力\] `Buffer`  
 指定したポート送信するデータ。  
  
 \[入力\] `Count`  
 送信されるデータのバイト数。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__outbytestring`|x86[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 解説  
 このルーチンは組み込みとしてのみ使用できます。  
  
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)