---
title: "単項プラス演算子と否定演算子: +、- |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- +
- '-'
dev_langs:
- C++
helpviewer_keywords:
- unary operators, plus
- '- operator'
- negation operator
- + operator, unary operators
- + operator
ms.assetid: 2c58c4f4-0d92-4ae3-9d0c-1a6157875cc1
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 9c664cd382685693da7ab12ba85891bc2ab0d7e8
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="unary-plus-and-negation-operators--and--"></a>単項加算演算子と否定演算子: + および -
## <a name="syntax"></a>構文  
  
```  
  
+ cast-expression  
```  
  
```  
  
- cast-expression  
```  
  
## <a name="-operator"></a>+ 演算子  
 単項プラス演算子の結果 (**+**)、オペランドの値です。 単項プラス演算子のオペランドは数値型である必要があります。  
  
 整数の上位変換が整数オペランドに対して実行されます。 結果の型は、オペランドの上位変換先の型です。 したがって、式 `+ch` (`ch` が `char` 型) は、結果が `int` 型になります。値は変更されません。 参照してください[標準変換](standard-conversions.md)昇格を実行する方法の詳細についてはします。  
  
## <a name="--operator"></a>- 演算子  
 単項否定演算子 (**-**)、オペランドの負数を生成します。 単項否定演算子のオペランドには数値型を指定する必要があります。  
  
 整数の上位変換は、整数オペランドに対して実行され、結果の型は、そのオペランドが昇格される型になります。 参照してください[標準変換](standard-conversions.md)昇格を実行する方法の詳細についてはします。  
  
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 符号なし数値の単項否定演算は、2^n からオペランドの値を減算することによって実行されます。この n は、指定した符号なし型のオブジェクトのビット数です  (Microsoft C++ は、2 の補数演算を利用するプロセッサで実行されます。 他のプロセッサでは否定のアルゴリズムが異なる場合があります)。  
  
## <a name="see-also"></a>関連項目  
 [単項演算子を含む式](../cpp/expressions-with-unary-operators.md)   
 [C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
