---
title: "__rdtscp | Microsoft Docs"
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
  - "__rdtscp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rdtscp 組み込み"
  - "__rdtscp 組み込み"
  - "rdtscp 命令"
ms.assetid: f17d9a9c-88bb-44e0-b69d-d516bc1c93ee
caps.latest.revision: 13
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __rdtscp
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 `rdtscp` 命令を生成してメモリに `TSC_AUX[31:0`\] 書き込み64 ビットのタイム スタンプ カウンター \(`TSC)` の結果を返します。  
  
## 構文  
  
```  
unsigned __int64 __rdtscp(  
   unsigned int * Aux  
);  
```  
  
#### パラメーター  
 \[出力\] `Aux`  
 マシン固有の登録 `TSC_AUX[31:0]` の内容を格納する場所へのポインター。  
  
## 戻り値  
 64 ビット符号なし整数がティック数。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__rdtscp`|AMD NPT ファミリ 0Fh 以降のバージョン|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 解説  
 この組み込みでは `rdtscp` 命令を生成します。  この命令に対するハードウェア サポートを確認するには`InfoType=0x80000001` の `__cpuid` 組み込みを呼び出し`CPUInfo[3] (EDX)` のビット 27 をチェックします。  このビットは命令がサポートされている場合は 0 になりは 1。  `rdtscp` 命令をサポートするハードウェアのこの組み込みを使用するコードを実行すると結果は予測できません。  
  
> [!CAUTION]
>  `rdtsc` とは異なり`rdtscp` はシリアル化の命令。; いずれにしてもコンパイラはこの組み込みの周囲にコードを移動できます。  
  
 ハードウェアのこのジェネレーションの TSC の値の解釈は [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] の以前のバージョンの場合とは異なります。  詳細についてはハードウェアの手動を参照してください。  
  
 `TSC_AUX[31:0]` の値の意味はオペレーティング システムによって異なります。  
  
## 使用例  
  
```  
#include <intrin.h>   
#include <stdio.h>  
int main()   
{  
 unsigned __int64 i;  
 unsigned int ui;  
 i = __rdtscp(&ui);  
 printf_s("%I64d ticks\n", i);  
 printf_s("TSC_AUX was %x\n", ui);  
}  
```  
  
  **3363423610155519 匹のタイマー刻み**  
**TSC\_AUX は 0。**   
## 終了 Microsoft 固有の仕様→  
 アドバンストのマイクロアーキテクチャのデバイセズ Inc の著作の著作権2007 年\)   All rights reserved.  アドバンストのマイクロアーキテクチャのデバイセズのアクセス許可と再生されInc  
  
## 参照  
 [\_\_rdtsc](../intrinsics/rdtsc.md)   
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)