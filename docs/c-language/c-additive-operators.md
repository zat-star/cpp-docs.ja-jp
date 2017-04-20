---
title: "C 加法演算子 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- usual arithmetic conversions
- operators [C], addition
- + operator, additive operators
- additive operators
- arithmetic operators [C++], additive operators
ms.assetid: bb8ac205-b061-41fc-8dd4-dab87c8b900c
caps.latest.revision: 8
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
translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 885967baa9a7e3651dde02bb5cfb1d6b9783f42b
ms.lasthandoff: 04/01/2017

---
# <a name="c-additive-operators"></a>C 加法演算子
加法演算子は加算 (**+**) と減算 (**-**) を実行します。  
  
## <a name="syntax"></a>構文  
 *additive-expression*:  
 *multiplicative-expression*  
  
 *additive-expression*  **+**  *multiplicative-expression*  
  
 *additive-expression*  **-**  *multiplicative-expression*  
  
> [!NOTE]
>  *additive-expression* の構文に *multiplicative-expression* が含まれてますが、乗算を使用する式が必要なわけではありません。 「[C 言語の構文概要](../c-language/c-language-syntax-summary.md)」で、*multiplicative-expression*、*cast-expression*、および *unary-expression* の構文を参照してください。  
  
 オペランドは整数値または浮動小数点値になります。 各演算子の説明に記載されているように、一部の加算演算はポインター値に対しても実行できます。  
  
 加算演算子は、整数および浮動小数点のオペランドに対して通常の算術変換を実行します。 結果の型は、変換後のオペランドの型です。 加算演算子によって実行される変換にはオーバーフロー条件やアンダーフロー条件が用意されていないため、加算演算の結果を変換後のオペランドの型で表すことができない場合、情報が失われる可能性があります。  
  
## <a name="see-also"></a>関連項目  
 [加法演算子: + および -](../cpp/additive-operators-plus-and.md)
