---
title: "_mm_stream_sd | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_mm_stream_sd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mm_stream_sd 組み込み"
  - "movntsd 命令"
ms.assetid: 2b4bea5e-e64e-45fa-9afc-88a2e4b82cfc
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _mm_stream_sd
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 キャッシュを汚さないのメモリ位置に 64 ビットのデータを書き込みます。  
  
## 構文  
  
```  
void _mm_stream_sd(  
   double * Dest,  
   __m128d Source  
);  
```  
  
#### パラメーター  
 \[出力\] `Dest`  
 データ ソースが書き込まれる場所へのポインター。  
  
 \[入力\] `Source`  
 下位 64 ビットに記述する必要 `double` の値を含むビットの値。  
  
## 戻り値  
 なし。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`_mm_stream_sd`|SSE4a|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 解説  
 この組み込みでは `movntsd` 命令を生成します。  この命令に対するハードウェア サポートを確認するには`InfoType=0x80000001` の `__cpuid` 組み込みを呼び出し`CPUInfo[2] (ECX)` のビット 6 をチェックします。  このビットはハードウェアでこの命令がサポートされる場合は 0 になりは 1。  
  
 `movntsd` 命令をサポートするハードウェアの `_mm_stream_sd` 組み込みを使用するコードを実行すると結果は予測できません。  
  
## 使用例  
  
```  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
int main()  
{  
    __m128d vals;  
    double d[2];  
  
    d[0] = -1.;  
    d[1] = -2.;  
    vals.m128d_f64[0] = 0.;  
    vals.m128d_f64[1] = 1.;  
    _mm_stream_sd(&d[1], vals);  
    cout << "d[0] = " << d[0] << ", d[1] = " << d[1] << endl;  
}  
  
```  
  
  **d \[0\] \= \-1d \[1\] \= 1**    
## 終了 Microsoft 固有の仕様→  
 アドバンストのマイクロアーキテクチャのデバイセズ Inc の著作の著作権2007 年\)   All rights reserved.  アドバンストのマイクロアーキテクチャのデバイセズのアクセス許可と再生されInc  
  
## 参照  
 [\_mm\_stream\_ss](../Topic/_mm_stream_ss.md)   
 [\_mm\_store\_sd](http://msdn.microsoft.com/ja-jp/8e672d0d-0a96-45b9-a783-392a2457de42)   
 [\_mm\_sfence](http://msdn.microsoft.com/ja-jp/b6c0d18e-3628-4318-826b-45f66782e870)   
 [Streaming SIMD Extensions that Support the Cache](http://msdn.microsoft.com/ja-jp/8f03493a-d5f5-4457-892e-0b6540494872)   
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)