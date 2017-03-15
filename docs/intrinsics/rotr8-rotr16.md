---
title: "_rotr8, _rotr16 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_rotr16"
  - "_rotr8"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_rotr16 intrinsic"
  - "_rotr8 intrinsic"
ms.assetid: dfbd2c82-82b4-427a-ad52-51609027ebff
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _rotr8, _rotr16
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 指定したビット位置の数だけ、最下位ビット \(LSB\) に向かって入力値を右に回転します。  
  
## 構文  
  
```  
unsigned char _rotr8(     unsigned char value,     unsigned char shift  ); unsigned short _rotr16(     unsigned short value,     unsigned char shift  );  
```  
  
#### パラメーター  
 \[入力\] `value`  
 回転する値。  
  
 \[入力\] `shift`  
 回転するビット数。  
  
## 戻り値  
 回転後の値。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`_rotr8`|x86、ARM、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`_rotr16`|x86、ARM、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 解説  
 右シフト演算とは異なり、右回転を実行すると、下端からあふれた下位ビットは最上位ビット位置に移動します。  
  
## 使用例  
  
```  
// rotr.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_rotr8, _rotr16)  
  
int main()  
{  
    unsigned char c = 'A', c1, c2;  
  
    for (int i = 0; i < 8; i++)  
    {  
       printf_s("Rotating 0x%x right by %d bits gives 0x%x\n", c,  
                i, _rotr8(c, i));  
    }  
  
    unsigned short s = 0x12;  
    int nBit = 10;  
  
    printf_s("Rotating unsigned short 0x%x right by %d bits "  
             "gives 0x%x\n",  
            s, nBit, _rotr16(s, nBit));  
}  
```  
  
  **Rotating 0x41 right by 0 bits gives 0x41**  
**Rotating 0x41 right by 1 bits gives 0xa0**  
**Rotating 0x41 right by 2 bits gives 0x50**  
**Rotating 0x41 right by 3 bits gives 0x28**  
**Rotating 0x41 right by 4 bits gives 0x14**  
**Rotating 0x41 right by 5 bits gives 0xa**  
**Rotating 0x41 right by 6 bits gives 0x5**  
**Rotating 0x41 right by 7 bits gives 0x82**  
**Rotating unsigned short 0x12 right by 10 bits gives 0x480**   
## END Microsoft 固有の仕様  
  
## 参照  
 [\_rotl8, \_rotl16](../intrinsics/rotl8-rotl16.md)   
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)