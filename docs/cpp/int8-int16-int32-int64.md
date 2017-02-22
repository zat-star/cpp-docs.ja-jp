---
title: "__int8、__int16、__int32、__int64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__int8_cpp"
  - "__int64"
  - "__int8"
  - "__int16"
  - "__int16_cpp"
  - "__int64_cpp"
  - "__int32_cpp"
  - "__int32"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__int16 キーワード [C++]"
  - "__int32 キーワード [C++]"
  - "__int64 キーワード [C++]"
  - "__int8 キーワード [C++]"
  - "整数データ型, 整数型 (C++ 内)"
  - "整数型 [C++]"
ms.assetid: 8e384602-2578-4980-8cc8-da63842356b2
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# __int8、__int16、__int32、__int64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 Microsoft C\/C\+\+ の機能では、サイズ設定された整数型をサポートします。  **\_\_int***n* 型指定子を使用して、8、16、32、または 64 ビットの整数変数を宣言できます。ここで、*n* は 8、16、32、または 64 です。  
  
 次の例は、サイズ設定された整数のこれらの型のそれぞれに 1 つの変数を宣言しています。  
  
```  
__int8 nSmall;      // Declares 8-bit integer  
__int16 nMedium;    // Declares 16-bit integer  
__int32 nLarge;     // Declares 32-bit integer  
__int64 nHuge;      // Declares 64-bit integer  
```  
  
 型 `__int8`、`__int16`、および `__int32` は、同じサイズを持つ ANSI 型のシノニムであり、複数のプラットフォームで同じように動作する移植性のあるコードを作成する場合に便利です。  `__int8` データ型は、型 `char` と同じ意味です。`__int16` は、型 **short** と同じ意味です。`__int32` は、型 `int` と同じ意味です。  `__int64` 型に相当する ANSI 型はありません。  
  
## 使用例  
 次の例は、\_\_int*xx* パラメーターが `int` に昇格されることを示しています。  
  
```  
// sized_int_types.cpp  
  
#include <stdio.h>  
  
void func(int i) {  
    printf_s("%s\n", __FUNCTION__);  
}  
  
int main()  
{  
    __int8 i8 = 100;  
    func(i8);   // no void func(__int8 i8) function  
                // __int8 will be promoted to int  
}  
```  
  
  **func**   
## END Microsoft 固有の仕様  
  
## 参照  
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [基本型](../cpp/fundamental-types-cpp.md)   
 [データ型の範囲](../cpp/data-type-ranges.md)