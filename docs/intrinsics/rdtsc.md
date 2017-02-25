---
title: "__rdtsc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__rdtsc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__rdtsc 組み込み"
  - "rdtsc 命令"
  - "タイム スタンプ カウンターの読み取り命令"
ms.assetid: e31d0e51-c9bb-42ca-bbe9-a81ffe662387
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# __rdtsc
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 プロセッサ タイム スタンプを返す `rdtsc` 命令を生成します。  プロセッサ タイム スタンプは最後のリセットはクロック サイクル数を記録します。  
  
## 構文  
  
```  
unsigned __int64 __rdtsc();  
```  
  
## 戻り値  
 ティック数を表す 64 ビット符号なし整数。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__rdtsc`|x86[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 解説  
 このルーチンは組み込みとしてのみ使用できます。  
  
 ハードウェアのこのジェネレーションの TSC の値の解釈は [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] の以前のバージョンの場合とは異なります。  詳細についてはハードウェアの手動を参照してください。  
  
## 使用例  
  
```  
// rdtsc.cpp  
// processor: x86, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__rdtsc)  
  
int main()  
{  
    unsigned __int64 i;  
    i = __rdtsc();  
    printf_s("%I64d ticks\n", i);  
}  
```  
  
  **3363423610155519 匹のタイマー刻み**   
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)