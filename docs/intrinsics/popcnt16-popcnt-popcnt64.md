---
title: "__popcnt16、__popcnt、__popcnt64 | Microsoft Docs"
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
  - "__popcnt64"
  - "__popcnt"
  - "__popcnt16"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "popcnt 命令"
  - "__popcnt16"
  - "__popcnt64"
  - "__popcnt"
ms.assetid: e525b236-adc8-42df-9b9b-8b7d8c245d3b
caps.latest.revision: 15
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __popcnt16、__popcnt、__popcnt64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 16 \- 32\-またはバイトの符号なし整数の 1 ビット数 \(数値\) を作成します。  
  
## 構文  
  
```  
unsigned short __popcnt16(  
   unsigned short value  
);  
unsigned int __popcnt(  
   unsigned int value  
);  
unsigned __int64 __popcnt64(  
   unsigned __int64 value  
);  
```  
  
#### パラメーター  
 \[入力\] `value`  
 16 ビットまたは 64 ビット符号なし整数は作成する数値が 32 ~。  
  
## 戻り値  
 `value` パラメーターの 1 ビット数。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__popcnt16`|高度なビット操作|  
|`__popcnt`|高度なビット操作|  
|`__popcnt64`|64 ビット モードの高度なビット操作。|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 解説  
 これらの組み込みは `popcnt` 命令を生成します。  `popcnt` 命令の戻り値は引数のサイズと同じになります。値。  32 ビット モードでは64 ビットの汎用レジスタしたがって64 ビット `popcnt` はありません。  
  
 `popcnt` の命令に対するハードウェア サポートを確認するには`InfoType=0x00000001` の `__cpuid` 組み込みを呼び出し`CPUInfo[2] (ECX)` のビット 23 をチェックします。  このビットは命令がサポートされている場合は 0 になりは 1。  `popcnt` 命令をサポートするハードウェアのこの組み込みを使用するコードを実行すると結果は予測できません。  
  
## 使用例  
  
```  
#include <iostream>   
#include <intrin.h>   
using namespace std;   
  
int main()   
{  
  unsigned short us[3] = {0, 0xFF, 0xFFFF};  
  unsigned short usr;  
  unsigned int   ui[4] = {0, 0xFF, 0xFFFF, 0xFFFFFFFF};  
  unsigned int   uir;  
  
  for (int i=0; i<3; i++) {  
    usr = __popcnt16(us[i]);  
    cout << "__popcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;  
  }  
  
  for (int i=0; i<4; i++) {  
    uir = __popcnt(ui[i]);  
    cout << "__popcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;  
  }  
}  
  
```  
  
  **\_\_popcnt16 \(0x0\) \= 0**  
 **\_\_popcnt16 \(0xff\) \= 8**  
 **\_\_popcnt16 \(0xffff\) \= 16**  
 **\_\_popcnt \(0x0\) \= 0**  
 **\_\_popcnt \(0xff\) \= 8**  
 **\_\_oopcnt \(0xffff\) \= 16**  
 **\_\_popcnt \(32\) \= 0xffffffff**   
## Microsoft 固有の仕様→を終了  
 アドバンストのマイクロアーキテクチャのデバイセズ Inc の著作の著作権2007 年\)   All rights reserved.  アドバンストのマイクロアーキテクチャのデバイセズのアクセス許可と再生されInc  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)