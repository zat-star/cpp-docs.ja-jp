---
title: "_BitScanForward, _BitScanForward64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_BitScanForward"
  - "_BitScanForward_cpp"
  - "_BitScanForward64_cpp"
  - "_BitScanForward64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_BitScanForward intrinsic"
  - "BitScanForward intrinsic"
  - "bsf instruction"
ms.assetid: 405e60fb-0815-42a7-9b02-6fc035122203
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _BitScanForward, _BitScanForward64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 マスク データの最下位ビット \(LSB\) から最上位ビット \(MSB\) に向かって設定済みビット \(1\) を検索します。  
  
## 構文  
  
```  
unsigned char _BitScanForward(    unsigned long * Index,    unsigned long Mask ); unsigned char _BitScanForward64(    unsigned long * Index,    unsigned __int64 Mask );  
```  
  
#### パラメーター  
 \[出力\] `Index`  
 最初に見つかった設定済みビット \(1\) のビット位置が読み込まれます。  
  
 \[入力\] `Mask`  
 検索する 32 ビットまたは 64 ビットの値。  
  
## 戻り値  
 マスクが 0 の場合は 0。それ以外の場合は 0 以外。  
  
## 解説  
 設定済みビットが見つかった場合は、最初に見つかった設定済みビットのビット位置が最初のパラメーターで返されます。  設定済みビットが見つからない場合は 0 が返されます。それ以外の場合は 1 が返されます。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`_BitScanForward`|x86、ARM、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`_BitScanForward64`|ARM、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 使用例  
  
```  
// BitScanForward.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(_BitScanForward)  
  
int main()  
{  
   unsigned long mask = 0x1000;  
   unsigned long index;  
   unsigned char isNonzero;  
  
   cout << "Enter a positive integer as the mask: " << flush;  
   cin >> mask;  
   isNonzero = _BitScanForward(&index, mask);  
   if (isNonzero)  
   {  
      cout << "Mask: " << mask << " Index: " << index << endl;  
   }  
   else  
   {  
      cout << "No set bits found.  Mask is zero." << endl;  
   }  
}  
```  
  
## 入力  
  
```  
12  
```  
  
## 出力例  
  
```  
Enter a positive integer as the mask:   
Mask: 12 Index: 2  
```  
  
### END Microsoft 固有の仕様  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)