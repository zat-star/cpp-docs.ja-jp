---
title: "基本型の格納 | Microsoft Docs"
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
- specifiers [C++], type
- integral types, storage
- storage [C++], types
- floating-point numbers, storage
- type specifiers [C++], sizes
- arithmetic operations [C++], types
- int data type
- short data type
- signed types [C++], storage
- long double keyword [C], storage
- long keyword [C]
- double data type, storage
- types [C], arithmetic
- integral types
- data types [C], specifiers
- storing types [C++]
- unsigned types [C++], storage
- data types [C], storage
ms.assetid: bd1f33c1-c6b9-4558-8a72-afb21aef3318
caps.latest.revision: 6
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
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 5a42f5c0e4592fc397ac51d610ed6ca1495c4504
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="storage-of-basic-types"></a>基本型の格納
次の表は、各基本型に関連付けられたストレージをまとめたものです。  
  
### <a name="sizes-of-fundamental-types"></a>基本型のサイズ  
  
|型|記憶域|  
|----------|-------------|  
|`char`, `unsigned char`, **signed char**|1 バイト|  
|**short**, **unsigned short**|2 バイト|  
|`int`, `unsigned int`|4 バイト|  
|**long**, `unsigned long`|4 バイト|  
|**float**|4 バイト|  
|**double**|8 バイト|  
|`long double`|8 バイト|  
  
 C のデータ型は一般カテゴリに分類されます。 "整数型" には、`char`、`int`、**short**、**long**、**signed**、`unsigned`、および `enum` が含まれます。 "浮動小数点型" には、**float**、**double**、および `long double` が含まれます。 "数値型" には、すべての浮動小数点型と整数型が含まれます。  
  
## <a name="see-also"></a>関連項目  
 [宣言と型](../c-language/declarations-and-types.md)
