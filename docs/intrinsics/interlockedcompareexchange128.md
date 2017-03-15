---
title: "_InterlockedCompareExchange128 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedCompareExchange128_cpp"
  - "_InterlockedCompareExchange128"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cmpxchg16b 命令"
  - "_InterlockedCompareExchange128 組み込み"
ms.assetid: f05918fc-716a-4f6d-b746-1456d6b96c56
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _InterlockedCompareExchange128
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 かみ合うビットを比較し交換実行します。  
  
## 構文  
  
```  
unsigned char _InterlockedCompareExchange128(  
   __int64 volatile * Destination,  
   __int64 ExchangeHigh,  
   __int64 ExchangeLow,  
   __int64 * ComparandResult  
);  
```  
  
#### パラメーター  
 \[入力、出力\] `Destination`  
 ビット フィールドと見なされる 2 個の 64 ビット整数の配列であるターゲットへのポインター。  前のデータは一般保護違反を防ぐために配置されるバイトである必要があります。  
  
 \[入力\] `ExchangeHigh`  
 コピー先の高い部分を交換できる 64 ビット整数。  
  
 \[入力\] `ExchangeLow`  
 コピー先の下位部分を交換できる 64 ビット整数。  
  
 \[入力、出力\] `ComparandResult`  
 ターゲットと比較する 2 個の 64 ビット整数の配列へのポインター \(ビットのフィールドと見なされる\)。  出力では配置先の元の値で上書きされます。  
  
## 戻り値  
 ビットの値は比較先の元の値と等しい場合は 1。  `ExchangeHigh` と `ExchangeLow` はビットのターゲットをオーバーライドします。  
  
 比較先の値は元の値と等しくない場合は 0。  コピー先の値は変更されず比較は値がターゲットの値で上書きされます。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`_InterlockedCompareExchange128`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 解説  
 この組み込みでは `cmpxchg16b` 命令 \(`lock` のプレフィックス\) ロックされているビットを実行する比較し交換します。生成されます。  AMD 64 ビット ハードウェアの以前のバージョンでこの命令がサポートされません。  `cmpxchg16b` 命令のハードウェア サポートを確認するには`InfoType=0x00000001 (standard function 1)` の `__cpuid` の組み込みを呼び出します。  命令がサポートされている場合 `CPUInfo[2]`\(ECX\) のビット 13 は 1 です。  
  
> [!NOTE]
>  `ComparandResult` の値は常に上書きされます。  `lock` 命令とこの組み込みでは `ComparandResult` にすばやく `Destination` の初期値をコピーします。  したがって`ComparandResult` と `Destination`予期しない動作を回避するメモリ位置を分離するためによって指し示します。  
  
 低水準のスレッド同期用に `_InterlockedCompareExchange128` を使用できますが必要な同期関数 \(`_InterlockedCompareExchange` の他の組み込みなど\) を使用して 128 ビットに同期する必要はありません。  メモリのビットの値へのアトミック アクセスする場合は`_InterlockedCompareExchange128` を使用します。  
  
 `cmpxchg16b` 命令をサポートするハードウェアのこの組み込みを使用するコードを実行すると結果は予測できません。  
  
 このルーチンは組み込みとしてのみ使用できます。  
  
## 使用例  
 この例では2 個の 64 ビット整数の配列の上位ワードを上位および下位のワードの合計に置き換え下位ワードをインクリメントする場合に `_InterlockedCompareExchange128` を使用します。  BigInt.Int の配列へのアクセスはアトミックこの例ではシングル スレッドは無視されやすくするためにロックは異なります。  
  
```  
// cmpxchg16b.c  
// processor: x64  
// compile with: /EHsc /O2  
#include <stdio.h>  
#include <intrin.h>  
  
typedef struct _LARGE_INTEGER_128 {  
    __int64 Int[2];  
} LARGE_INTEGER_128, *PLARGE_INTEGER_128;  
  
volatile LARGE_INTEGER_128 BigInt;  
  
// This AtomicOp() function atomically performs:  
//   BigInt.Int[1] += BigInt.Int[0]  
//   BigInt.Int[0] += 1  
void AtomicOp ()  
{  
    LARGE_INTEGER_128 Comparand;  
    Comparand.Int[0] = BigInt.Int[0];  
    Comparand.Int[1] = BigInt.Int[1];  
    do {  
        ; // nothing  
    } while (_InterlockedCompareExchange128(BigInt.Int,  
                                            Comparand.Int[0] + Comparand.Int[1],  
                                            Comparand.Int[0] + 1,  
                                            Comparand.Int) == 0);  
}  
  
// In a real application, several threads contend for the value  
// of BigInt.  
// Here we focus on the compare and exchange for simplicity.  
int main(void)  
{  
   BigInt.Int[1] = 23;  
   BigInt.Int[0] = 11;  
   AtomicOp();  
   printf("BigInt.Int[1] = %d, BigInt.Int[0] = %d\n",  
      BigInt.Int[1],BigInt.Int[0]);  
}  
```  
  
  **BigInt.Int \[1\] \= 34BigInt.Int \[0\] \= 12**    
## 終了 Microsoft 固有の仕様→  
 アドバンストのマイクロアーキテクチャのデバイセズ Inc の著作の著作権2007 年\)   All rights reserved.  アドバンストのマイクロアーキテクチャのデバイセズのアクセス許可と再生されInc  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)   
 [\_InterlockedCompareExchange Intrinsic Functions](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)   
 [x86 コンパイラとの競合](../Topic/Conflicts%20with%20the%20x86%20Compiler.md)