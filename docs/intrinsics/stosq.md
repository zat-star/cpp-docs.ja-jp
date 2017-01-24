---
title: "__stosq | Microsoft Docs"
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
  - "__stosq"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rep stosq 命令"
  - "stosq 命令"
  - "__stosq 組み込み"
ms.assetid: 3ea28297-4369-4c2d-bf0c-91fa539ce209
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __stosq
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 ストアの文字列 \(`rep stosq`\) 命令を生成します。  
  
## 構文  
  
```  
void __stosb(   
   unsigned __int64* Dest,   
   unsigned __int64 Data,   
   size_t Count   
);  
```  
  
#### パラメーター  
 \[出力\] `Dest`  
 操作のコピー先。  
  
 \[入力\] `Data`  
 格納するデータ。  
  
 \[入力\] `Count`  
 書き込む各ブロックの長さ。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__stosq`|AMD64|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 解説  
 結果はクワドワード `Data` が `Dest` の文字列の `Count` の各ブロックに記述する必要があります。  
  
 このルーチンは組み込みとしてのみ使用できます。  
  
## 使用例  
  
```  
// stosq.c  
// processor: x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__stosq)  
  
int main()  
{  
   unsigned __int64 val = 0xFFFFFFFFFFFFI64;  
   unsigned __int64 a[10];  
   memset(a, 0, sizeof(a));  
   __stosq(a+1, val, 2);  
   printf("%I64x %I64x %I64x %I64x", a[0], a[1], a[2], a[3]);   
}  
```  
  
## 出力  
  
```  
0 ffffffffffff ffffffffffff 0  
```  
  
### 終了 Microsoft 固有の仕様→  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)