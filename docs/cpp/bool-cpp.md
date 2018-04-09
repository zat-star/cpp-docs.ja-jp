---
title: bool (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- bool_cpp
- __BOOL_DEFINED
dev_langs:
- C++
helpviewer_keywords:
- bool keyword [C++]
- __BOOL_DEFINED macro
ms.assetid: 9abed3f2-d21c-4eb4-97c5-716342e613d8
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2d5a8a86cfcc64b70e4910079461513c34fc7d0d
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2018
---
# <a name="bool-c"></a>bool (C++)

このキーワードは組み込みの型です。 この型の変数に値を持つことができます[true](../cpp/true-cpp.md)と[false](../cpp/false-cpp.md)です。 条件式の型は `bool` であるため、その値は `bool` 型になります。 たとえば、`i!=0`ようになりました**true**または**false**の値に応じて`i`です。  

**Visual Studio 2017 15.3 およびそれ以降のバージョン**(で利用可能な[/std:c + + 17](../build/reference/std-specify-language-standard-version.md))。 オペランドの後置または前置インクリメントまたはデクリメント演算子できない可能性があります型の**bool**です。 つまり、変数がある**b**型の**bool**、これらの式はもう行えません。

```cpp
    b++;
    ++b;
    b--;
    --b;
```
  
値**true**と**false**次の関係があります。  
  
```cpp  
!false == true  
!true == false  
```  
  
次のステートメントがあるとします。  
  
```cpp  
if (condexpr1) statement1;   
```  
  
場合`condexpr1`は**true**、`statement1`は常に実行します。 場合`condexpr1`は**false**、`statement1`は実行されません。  
  
後置または前置と**++**演算子は型の変数に適用**bool**、変数に設定されている**true**です。 
**Visual Studio 2017 15.3 およびそれ以降のバージョン**: 演算子 + + の**bool**は言語から削除され、現在サポートされていません。

後置または前置**--**演算子は、この型の変数に適用することはできません。  
  
 **Bool**型は整数の上位変換に関与します。 型の右辺**bool**型の右辺値に変換できる**int**で**false**ゼロになると**true**は 1 です。 別個の型として**bool**オーバー ロードの解決に関与します。  
  
## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)<br/>
[基本的な型](../cpp/fundamental-types-cpp.md)<br/>
