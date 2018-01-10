---
title: "bool (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- bool_cpp
- __BOOL_DEFINED
dev_langs: C++
helpviewer_keywords:
- bool keyword [C++]
- __BOOL_DEFINED macro
ms.assetid: 9abed3f2-d21c-4eb4-97c5-716342e613d8
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 564d2f4849d1725d46d92562e2ce75b2ea2e2d44
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="bool-c"></a>bool (C++)
このキーワードは組み込みの型です。 この型の変数に値を持つことができます[true](../cpp/true-cpp.md)と[false](../cpp/false-cpp.md)です。 条件式の型は `bool` であるため、その値は `bool` 型になります。 たとえば、`i!=0`ようになりました**true**または**false**の値に応じて`i`です。  

**Visual Studio 2017 15.3 およびそれ以降のバージョン**(で利用可能な[/std:c + + 17](../build/reference/std-specify-language-standard-version.md))。 オペランドの後置または前置インクリメントまたはデクリメント演算子できない可能性があります型の`bool`します。 
  
 値**true**と**false**次の関係があります。  
  
```  
!false == true  
!true == false  
```  
  
 次のステートメントがあるとします。  
  
```  
if (condexpr1) statement1;   
```  
  
 場合`condexpr1`は**true**、`statement1`は常に実行します。 場合`condexpr1`は**false**、`statement1`は実行されません。  
  
 後置または前置と`++`演算子は型の変数に適用`bool`、変数に設定されている**true**です。 
**Visual Studio 2017 15.3 およびそれ以降のバージョン**: operator++ bool の言語からは削除され、現在サポートされていません。

後置または前置 `--` 演算子は、この型の変数には適用できません。  
  
 `bool` 型は整数の上位変換に使用されます。 型の右辺`bool`型の右辺値に変換できる`int`で**false**ゼロになると**true**は 1 です。 別個の型として、`bool` はオーバーロードの解決に使用されます。  
  
## <a name="see-also"></a>参照  
 [キーワード](../cpp/keywords-cpp.md)   
 [基本型](../cpp/fundamental-types-cpp.md)