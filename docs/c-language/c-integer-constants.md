---
title: "C 整数定数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: integer constants
ms.assetid: fcf6b83c-2038-49ec-91ca-3d5ca1f83037
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8f851fe628b7ac69fe3d327c290881561219a011
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="c-integer-constants"></a>C 整数定数
"整数定数" は、整数値を表す 10 進数 (基数 10)、8 進数 (基数 8)、または 16 進数 (基数 16) です。 変更できない整数値を表すには、整数定数を使用します。  
  
## <a name="syntax"></a>構文  
 *integer-constant*:  
 *decimal-constant integer-suffix* opt  
  
 *octal-constant integer-suffix* opt  
  
 *hexadecimal-constant integer-suffix* opt  
  
 *decimal-constant*:  
 *nonzero-digit*  
  
 *decimal-constant digit*  
  
 *octal-constant*:  
 **0**  
  
 *octal-constant octal-digit*  
  
 *hexadecimal-constant*:  
 **0x**  *hexadecimal-digit*  
  
 **0X**  *hexadecimal-digit*  
  
 *hexadecimal-constant hexadecimal-digit*  
  
 *nonzero-digit*: 次のいずれか  
 **1 2 3 4 5 6 7 8 9**  
  
 *octal-digit*: 次のいずれか  
 **0 1 2 3 4 5 6 7**  
  
 *hexadecimal-digit*: 次のいずれか  
 **0 1 2 3 4 5 6 7 8 9**  
  
 **a b c d e f**  
  
 **A B C D E F**  
  
 *integer-suffix*:  
 *unsigned-suffix long-suffix* opt  
  
 *long-suffix unsigned-suffix* opt  
  
 *unsigned-suffix*: 次のいずれか  
 **u U**  
  
 *long-suffix*: 次のいずれか  
 **l L**  
  
 *64-bit integer-suffix*:  
 **i64**  
  
 整数定数は負符号 (**-**) が前にない場合、正数になります。 負符号は単項算術否定演算子として解釈されます  (この演算子については、「[単項算術演算子](../c-language/unary-arithmetic-operators.md)」を参照してください)。  
  
 整数定数が **0x** または **0X** で始まる場合は、16 進数です。 数字 **0** で始まる場合は 8 進数です。 それ以外の場合は、10 進数であると想定されます。  
  
 次の行は等価です。  
  
```  
0x1C   /* = Hexadecimal representation for decimal 28 */  
034    /* = Octal representation for decimal 28 */  
```  
  
 空白文字で整数定数の数字を分離することはできません。 これらの例は、有効な 10 進、8 進、および 16 進定数を示します。  
  
```  
/* Decimal Constants */  
10  
132  
32179  
  
/* Octal Constants */  
012  
0204  
076663  
  
/* Hexadecimal Constants */  
0xa or 0xA  
0x84  
0x7dB3 or 0X7DB3  
```  
  
## <a name="see-also"></a>参照  
 [C 定数](../c-language/c-constants.md)