---
title: "_mm_extract_si64、_mm_extracti_si64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_mm_extracti_si64"
  - "_mm_extract_si64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "extrq 命令"
  - "_mm_extracti_si64 組み込み"
  - "_mm_extract_si64 組み込み"
ms.assetid: 459fdd72-cc54-4ee5-bbd5-d2c6067a88e7
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _mm_extract_si64、_mm_extracti_si64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 最初の引数の下位 64 ビットで指定のビットを抽出します `extrq` 命令を生成します。  
  
## 構文  
  
```  
__m128i _mm_extract_si64(  
   __m128i Source,  
   __m128i Descriptor  
);  
__m128i _mm_extracti_si64(  
   __m128i Source,  
   int Length,  
   int Index  
);  
```  
  
#### パラメーター  
 \[入力\]`Source`  
 下位 64 ビットの入力データのビット フィールドを指定します。  
  
 \[入力\] `Descriptor`  
 抽出するためにビット フィールドを記述するビットのフィールド。  
  
 \[入力\] `Length`  
 抽出するにはフィールドのサイズを指定する整数。  
  
 \[入力\] `Index`  
 抽出するにはフィールドのインデックスを指定する整数  
  
## 戻り値  
 最下位のビットを抽出するフィールドを持つビットのフィールド。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`_mm_extract_si64`|SSE4a|  
|`_mm_extracti_si64`|SSE4a|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 解説  
 この組み込みでは `Source` のビットを抽出 `extrq` 命令を生成します。この組み込みの 2 種類のバージョンがあります : `_mm_extracti_si64` は直接のバージョンであり`_mm_extract_si64` は直接のとおりです。  各バージョンがビット フィールドは最下位ビットの長さとインデックスによって定義された `Source` から抽出します。  長さとインデックスの値はmod 64 の一部であるため\-1 と 127 は 63 として解釈されます。  \(CSS\) とインデックス \(CSS\) フィールドの長さの合計が 64 の場合結果は未定義です。  64 としてフィールドの長さがゼロの値は解釈されます。  フィールドの長さとビット インデックスがどちらもゼロの場合`Source` 63:0 ビットを抽出します。  フィールドの長さがゼロの場合はビットのインデックスがゼロ以外の場合結果は未定義になります。  
  
 \_mm\_extract\_si64 の呼び出しが 5:0 ビットで抽出するデータ フィールドおよび 13:8 ビット長で`Descriptor` インデックスが含まれています。  
  
 を呼び出すとコンパイラは整数定数にコンパイルできない引数との `_mm_extracti_si64` は値を `Descriptor`XMM レジスタ \(\) を空けないようにパックし`_mm_extract_si64` を呼び出すコードを生成します。  
  
 `extrq` の命令に対するハードウェア サポートを確認するには`InfoType=0x80000001` の `__cpuid` 組み込みを呼び出し`CPUInfo[2] (ECX)` のビット 6 をチェックします。  このビットは命令がサポートされている場合は 0 になりは 1。  `extrq` 命令をサポートしないこの基本的なハードウェアを使用するコードを実行すると結果は予測できません。  
  
## 使用例  
  
```  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
union {  
    __m128i m;  
    unsigned __int64 ui64[2];  
} source, descriptor, result1, result2, result3;  
  
int  
main()  
{  
    source.ui64[0] =     0xfedcba9876543210ll;  
    descriptor.ui64[0] = 0x0000000000000b1bll;  
  
    result1.m = _mm_extract_si64 (source.m, descriptor.m);  
    result2.m = _mm_extracti_si64(source.m, 27, 11);  
    result3.ui64[0] = (source.ui64[0] >> 11) & 0x7ffffff;  
  
    cout << hex << "result1 = 0x" << result1.ui64[0] << endl;  
    cout << "result2 = 0x" << result2.ui64[0] << endl;  
    cout << "result3 = 0x" << result3.ui64[0] << endl;  
}  
```  
  
  **result1 \= 0x30eca86**  
**result2 \= 0x30eca86**  
**result3 \= 0x30eca86**   
## 終了 Microsoft 固有の仕様→  
 アドバンストのマイクロアーキテクチャのデバイセズ Inc の著作の著作権2007 年\)   All rights reserved.  アドバンストのマイクロアーキテクチャのデバイセズのアクセス許可と再生されInc  
  
## 参照  
 [\_mm\_insert\_si64、\_mm\_inserti\_si64](../Topic/_mm_insert_si64,%20_mm_inserti_si64.md)   
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)