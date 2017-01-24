---
title: "C 代入演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "%= 演算子"
  - "&= 演算子"
  - "*= 演算子"
  - "/= 演算子"
  - "^= 演算子, 代入演算子"
  - "|= 演算子"
  - "+= 演算子"
  - "<<= 演算子"
  - "= 演算子"
  - "-= 演算子"
  - "= 演算子, 代入演算子"
  - ">> 演算子"
  - ">>= 演算子"
  - "代入の変換"
  - "代入演算子"
  - "代入演算子, C"
  - "ビットごとの AND 代入演算子"
  - "除算代入演算子"
  - "乗算代入演算子 (*=)"
  - "演算子 >>=, C の代入演算子"
  - "演算子 [C], 割り当て"
  - "演算子 [C], シフト"
  - "剰余代入演算子 (%=)"
  - "右シフト演算子"
  - "シフト演算子, 右"
  - "減算演算子"
  - "減算演算子, C の代入演算子"
ms.assetid: 11688dcb-c941-44e7-a636-3fc98e7dac40
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C 代入演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

代入演算は、右オペランドの値を、左オペランドによって指定されたデータ格納場所に代入します。  したがって、代入演算の左オペランドは変更可能な左辺値である必要があります。  代入の後、代入式は左オペランドの値を持ちますが、代入式は左辺値ではありません。  
  
 **構文**  
  
 *assignment\-expression*:  
 *conditional\-expression*  
  
 *unary\-expression assignment\-operator assignment\-expression*  
  
 *assignment\-operator*: 次のいずれか  
 **\= \*\=** `/=` `%=` `+=` **–\= \<\<\= \>\>\= &\=** `^=` `|=`  
  
 C の代入演算子は、1 回の演算で値の変換と値の代入の両方を実行することができます。  C には、次の代入演算子が用意されています。  
  
|演算子|実行される演算|  
|---------|-------------|  
|**\=**|単純代入|  
|**\*\=**|乗算代入|  
|`/=`|除算代入|  
|`%=`|剰余代入|  
|`+=`|加算代入|  
|**–\=**|減算代入|  
|**\<\<\=**|左シフト代入|  
|**\>\>\=**|右シフト代入|  
|**&\=**|ビットごとの AND 代入|  
|`^=`|ビットごとの排他的 OR 代入|  
|`&#124;=`|ビットごとの包括的 OR\/代入|  
  
 代入では、右辺値の型は、左辺値の型に変換され、代入が行われた後、値が左オペランドに格納されます。  左オペランドを、配列、関数、または定数にすることはできません。  2 つの型に依存する特定の変換パスについては、「[型変換](../c-language/type-conversions-c.md)」で詳しく説明します。  
  
## 参照  
 [代入演算子](../cpp/assignment-operators.md)