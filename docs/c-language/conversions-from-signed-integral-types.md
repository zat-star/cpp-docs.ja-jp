---
title: "符号付き整数型からの変換 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- integral conversions, from signed
- integers, converting
- conversions [C++], integral
- data type conversion [C++], signed and unsigned integers
- type conversion [C++], signed and unsigned integers
ms.assetid: 5eea32f8-8b14-413d-acac-c063b3d118d7
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: d7ed58066cecc42492f3b163b130ff8a4ef53ed0
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="conversions-from-signed-integral-types"></a>Conversions from Signed Integral Types (符号付き整数型からの変換)
符号付き整数が、それ以上のサイズの符号なし整数に変換される場合、符号付き整数の値が負でないときは、値は変更されません。 変換は、符号付き整数を符号拡張することによって行われます。 符号付き整数は、上位ビットを切り捨てることにより、短い符号付き整数に変換されます。 結果は、この例に示すように、符号なしの値として解釈されます。  
  
```  
int i = -3;  
unsigned short u;  
  
u = i;   
printf_s( "%hu\n", u );  // Prints 65533  
  
```  
  
 符号付き整数が浮動小数点値に変換されるとき、基本的に失われる情報はありませんが、**long int** または **unsigned long int** 値が **float** 値に変換される場合のみ、一部精度が失われる場合があります。  
  
 次の表は、符号付き整数型からの変換をまとめたものです。 この表では、**char** 型が既定で符号付きであると想定しています。 コンパイル時オプションを使用して **char** 型の既定を unsigned に変更すると、次の「符号付き整数型からの変換」表にある変換の代わりに、「[符号なし整数型からの変換](../c-language/conversions-from-unsigned-integral-types.md)」表に示す **unsigned char** 型の変換が適用されます。  
  
### <a name="conversions-from-signed-integral-types"></a>Conversions from Signed Integral Types (符号付き整数型からの変換)  
  
|変換前|目的|メソッド|  
|----------|--------|------------|  
|**char**1|**short**|符号拡張。|  
|**char**|**long**|符号拡張。|  
|**char**|**unsigned char**|パターンを維持、上位ビットは符号ビットとしての機能を失う。|  
|**char**|**unsigned short**|**short** への符号拡張、**short** から **unsigned short** への変換|  
|**char**|**unsigned long**|**long** への符号拡張、**long** から **unsigned long** への変換|  
|**char**|**float**|**long** への符号拡張、**long** から **float** への変換|  
|**char**|**double**|**long** への符号拡張、**long** から **double** への変換|  
|**char**|**long double**|**long** への符号拡張、**long** から **double** への変換|  
|**short**|**char**|下位バイトを維持。|  
|**short**|**long**|符号拡張。|  
|**short**|**unsigned char**|下位バイトを維持。|  
|**short**|**unsigned short**|ビット パターンを維持、上位ビットは符号ビットとしての機能を失う。|  
|**short**|**unsigned long**|**long** への符号拡張、**long** から **unsigned long** への変換|  
|**short**|**float**|**long** への符号拡張、**long** から **float** への変換|  
|**short**|**double**|**long** への符号拡張、**long** から **double** への変換|  
|**short**|**long double**|**long** への符号拡張、**long** から **double** への変換|  
|**long**|**char**|下位バイトを維持。|  
|**long**|**short**|下位ワードを維持。|  
|**long**|**unsigned char**|下位バイトを維持。|  
|**long**|**unsigned short**|下位ワードを維持。|  
|**long**|**unsigned long**|ビット パターンを維持、上位ビットは符号ビットとしての機能を失う。|  
|**long**|**float**|**float** として表される。 **long** を正確に表すことができない場合、精度が低下する場合がある。|  
|**long**|**double**|**double** として表される。 **long** を **double** として正確に表すことができない場合、精度が低下する場合がある。|  
|**long**|**long double**|**double** として表される。 **long** を **double** として正確に表すことができない場合、精度が低下する場合がある。|  
  
 1. すべての **char** エントリでは、**char** 型が既定で符号付きであると仮定しています。  
  
 **Microsoft 固有の仕様**  
  
 Microsoft の 32 ビット C コンパイラでは、整数は **long** と等価です。 **int** 値の変換は、**long** の場合と同様に実行されます。  
  
 **END Microsoft 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 [代入の変換](../c-language/assignment-conversions.md)
