---
title: "C 代入演算子 | Microsoft Docs"
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
- remainder assignment operator (%=)
- '&= operator'
- bitwise-AND assignment operator
- operators [C], assignment
- operators [C], shift
- ^= operator, assignment operators
- += operator
- '>>= operator'
- '|= operator'
- division assignment operator
- subtraction operator
- right shift operators
- subtraction operator, C assignment operators
- = operator, assignment operators
- '*= operator'
- '>> operator'
- '%= operator'
- assignment operators, C
- = operator
- assignment operators
- assignment conversions
- -= operator
- multiplication assignment operator (*=)
- shift operators, right
- /= operator
- operator >>=, C assignment operators
- <<= operator
ms.assetid: 11688dcb-c941-44e7-a636-3fc98e7dac40
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c839538b94ff8f80eabed98dbaf16e4009d3e500
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="c-assignment-operators"></a>C 代入演算子
代入演算は、右オペランドの値を、左オペランドによって指定されたデータ格納場所に代入します。 したがって、代入演算の左オペランドは変更可能な左辺値である必要があります。 代入の後、代入式は左オペランドの値を持ちますが、代入式は左辺値ではありません。  
  
 **構文**  
  
 *assignment-expression*:  
 *conditional-expression*  
  
 *unary-expression assignment-operator assignment-expression*  
  
 *assignment-operator*: 次のいずれか  
 **= \*=** `/=` `%=` `+=` **-= <\<= >>= &=** `^=` `|=`  
  
 C の代入演算子は、1 回の演算で値の変換と値の代入の両方を実行することができます。 C には、次の代入演算子が用意されています。  
  
|演算子|実行される演算|  
|--------------|-------------------------|  
|**=**|単純代入|  
|**\*=**|乗算代入|  
|`/=`|除算代入|  
|`%=`|剰余代入|  
|`+=`|加算代入|  
|**-=**|減算代入|  
|**<\<=**|左シフト代入|  
|**>>=**|右シフト代入|  
|**&=**|ビットごとの AND 代入|  
|`^=`|ビットごとの排他的 OR 代入|  
|`&#124;=`|ビットごとの包括的 OR/代入|  
  
 代入では、右辺値の型は、左辺値の型に変換され、代入が行われた後、値が左オペランドに格納されます。 左オペランドを、配列、関数、または定数にすることはできません。 2 つの型に依存する特定の変換パスについては、「[型変換](../c-language/type-conversions-c.md)」で詳しく説明します。  
  
## <a name="see-also"></a>参照  
 [代入演算子](../cpp/assignment-operators.md)