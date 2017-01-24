---
title: "__lzcnt16、__lzcnt、__lzcnt64 | Microsoft Docs"
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
  - "__lzcnt64"
  - "__lzcnt16"
  - "__lzcnt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__lzcnt 組み込み"
  - "lzcnt 命令"
  - "lzcnt16 組み込み"
  - "lzcnt 組み込み"
  - "__lzcnt16 組み込み"
  - "lzcnt64 組み込み"
  - "__lzcnt64 組み込み"
ms.assetid: 412113e7-052e-46e5-8bfa-d5ad72abc10e
caps.latest.revision: 14
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __lzcnt16、__lzcnt、__lzcnt64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 先行するゼロの数を 16 ビット32 ビットまたはバイトの整数します。  
  
## 構文  
  
```  
unsigned short __lzcnt16(  
   unsigned short value  
);  
unsigned int __lzcnt(  
   unsigned int value  
);  
unsigned __int64 __lzcnt64(  
   unsigned __int64 value  
);  
```  
  
#### パラメーター  
 \[入力\] `value`  
 先行ゼロを確認する 16 ビット32 ビットまたは 64 ビット符号なし整数。  
  
## 戻り値  
 `value` のパラメーターに先行するゼロのビット数。  `value` がゼロの場合戻り値は入力のオペランド \(1632または 64\) のサイズです。  `value` の最上位ビットが 1 の場合戻り値はになります。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__lzcnt16`|高度なビット操作|  
|`__lzcnt`|高度なビット操作|  
|`__lzcnt64`|64 ビット モードの高度なビット操作。|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 解説  
 これらの組み込みは `lzcnt` 命令を生成します。  `lzcnt` 命令の戻り値は引数のサイズと同じになります。値。  32 ビット モードでは64 ビットの汎用レジスタしたがって64 ビット `lzcnt` はありません。  
  
 `lzcnt` の命令に対するハードウェア サポートを確認するには `InfoType=0x80000001` の `__cpuid` 組み込みを呼び出し`CPUInfo[2] (ECX)` のビット 5 をチェックします。  このビットは命令がサポートされている場合は 0 になりは 1。  `lzcnt` 命令をサポートするハードウェアのこの組み込みを使用するコードを実行すると結果は予測できません。  
  
## 使用例  
  
```  
// Compile this test with: /EHsc  
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
    usr = __lzcnt16(us[i]);  
    cout << "__lzcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;  
  }  
  
  for (int i=0; i<4; i++) {  
    uir = __lzcnt(ui[i]);  
    cout << "__lzcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;  
  }  
}  
  
```  
  
  **\_\_lzcnt16 \(0x0\) \= 16**  
 **\_\_lzcnt16 \(0xff\) \= 8**  
 **\_\_lzcnt16 \(0xffff\) \= 0**  
 **\_\_lzcnt \(0x0\) \= 32**  
 **\_\_lzcnt \(0xff\) \= 24**  
 **\_\_lzcnt \(0xffff\) \= 16**  
 **\_\_lzcnt \(0\) \= 0xffffffff**   
## 終了 Microsoft 固有の仕様→  
 アドバンストのマイクロアーキテクチャのデバイセズ Inc の著作の著作権2007 年\)   All rights reserved.  アドバンストのマイクロアーキテクチャのデバイセズのアクセス許可と再生されInc  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)