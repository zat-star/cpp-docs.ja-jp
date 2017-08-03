---
title: "Null ステートメント (C) | Microsoft Docs"
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
- semicolon, C null statement
- expressions [C++], null
- null statement
- null values, expressions
ms.assetid: 72576ce6-26d0-4379-be65-fee522088790
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
ms.openlocfilehash: 4a03d50c5c2a80bccd864f7e4d51df4d33169277
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="null-statement-c"></a>Null ステートメント (C)
"null ステートメント" はセミコロンのみを含むステートメントで、ステートメントが使用できるあらゆる場所に配置できます。 null ステートメントが実行されても、何も処理されません。 null ステートメントのコーディング方法は次のとおりです。  
  
## <a name="syntax"></a>構文  
  
```  
  
;  
  
```  
  
## <a name="remarks"></a>コメント  
 **do**、**for**、**if**、`while` などのステートメントでは、ステートメント本体に実行可能なステートメントを記述する必要があります。 null ステートメントは、実質的なステートメント本体が不要な場合にこの構文の要件を満たします。  
  
 null ステートメントは、他の C ステートメントと同様、前にラベルを付けることができます。 ステートメントではない項目 (複合ステートメントの右中かっこ (}) など) にラベルを付けるには、null ステートメントにラベルを付け、それを項目の直前に挿入して同じ効果を得ることができます。  
  
 null ステートメントの例を次に示します。  
  
```  
for ( i = 0; i < 10; line[i++] = 0 )  
     ;  
```  
  
 この例では、**for** ステートメントのループ式 `line[i++] = 0` によって、`line` の最初の 10 要素を 0 に初期化します。 それ以上のステートメントが不要であるため、ステートメント本体には null ステートメントを使用します。  
  
## <a name="see-also"></a>関連項目  
 [ステートメント](../c-language/statements-c.md)
