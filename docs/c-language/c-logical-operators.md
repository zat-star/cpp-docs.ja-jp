---
title: "C 論理演算子 | Microsoft Docs"
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
- logical operators, expression sequence points
- logical operators, C
- logical AND operator
- '|| operator'
- operators [C], logical
- short-circuit evaluation
- '&& operator'
- logical OR operator
ms.assetid: c0a4e766-ad56-4300-bf76-b28dc0e19b43
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 91df7af4322fc3fd8022542ffeb0c6b7b2d2e087
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="c-logical-operators"></a>C 論理演算子
論理演算子は、論理 AND (**&&**) 演算と論理 OR ( `||` ) 演算を実行します。  
  
 **構文**  
  
 *logical-AND-expression*:  
 *inclusive-OR-expression*  
  
 *logical-AND-expression*  **&&**  *inclusive-OR-expression*  
  
 *logical-OR-expression*:  
 *logical-AND-expression*  
  
 *logical-OR-expression*  **&#124;&#124;**  *logical-AND-expression*  
  
 論理演算子は通常の算術変換を実行しません。 代わりに、0 との等価性において各オペランドを評価します。 論理演算の結果は 0 または 1 になります。 結果の型は `int` です。  
  
 C の論理演算子について、以下に説明します。  
  
|演算子|説明|  
|--------------|-----------------|  
|**&&**|両方のオペランドが 0 以外の値の場合、論理 AND 演算子は値 1 を生成します。 どちらかのオペランドが 0 の場合、結果も 0 となります。 論理 AND 演算の 1 つ目のオペランドが 0 となる場合、2 つ目のオペランドは評価されません。|  
|`&#124;&#124;`|論理 OR 演算子は、そのオペランドに対して包括 OR 演算を実行します。 両方のオペランドの値が 0 の場合、結果は 0 です。 どちらかのオペランドの値が 0 以外の場合、結果は 1 になります。 論理 OR 演算の 1 つ目のオペランドにゼロ以外の値が含まれる場合、2 つ目のオペランドは評価されません。|  
  
 論理 AND 式と論理 OR 式のオペランドは左から右に評価されます。 1 つ目のオペランドの値で演算の結果を確認できる場合、2 つ目のオペランドは評価されません。 これは、"ショートサーキット評価" と呼ばれます。 1 つ目のオペランドの後にシーケンス ポイントがあります。 詳細については、「[シーケンス ポイント](../c-language/c-sequence-points.md)」を参照してください。  
  
## <a name="examples"></a>例  
 論理演算子の例を次に示します。  
  
```  
int w, x, y, z;  
  
if ( x < y && y < z )  
    printf( "x is less than z\n" );  
```  
  
 この例では、`printf` が `x` 未満で、`y` が `y` 未満である場合に、`z` 関数が呼び出され、メッセージが出力されます。 `x` が `y` より大きい場合、2 つ目のオペランド (`y < z`) は評価されず、何も出力されません。 このことは、2 つ目のオペランドが他の理由で依存される副作用をもたらす場合、問題となる可能性があることに注意してください。  
  
```  
printf( "%d" , (x == w || x == y || x == z) );  
```  
  
 この例では、`x` が `w`、`y`、または `z` と等しい場合、`printf` 関数の 2 番目の引数が true に評価され、値 1 が出力されます。 それ以外の場合は、false と評価され、値 0 が出力されます。 条件の 1 つが true と評価されると、直ちに評価が終了します。  
  
## <a name="see-also"></a>関連項目  
 [論理 AND 演算子: &&](../cpp/logical-and-operator-amp-amp.md)   
 [論理 OR 演算子: &#124;&#124;](../cpp/logical-or-operator-pipe-pipe.md)
