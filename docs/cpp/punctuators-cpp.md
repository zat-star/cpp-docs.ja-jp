---
title: "区切り記号 (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ;
- ','
- '{'
- '}'
- (
- )
- '['
- ']'
- '!'
- '%'
- '&#94;'
- '&#42;'
- '&#34;'
dev_langs:
- C++
helpviewer_keywords:
- punctuators [C++]
ms.assetid: 1521564c-a977-488a-9490-068079897592
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: a747b74f20d0c427883b8b7deba748b9de793d7a
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="punctuators-c"></a>区切り記号 (C++)
C++ の区切り記号はコンパイラに対する構文上およびセマンティック上の意味を持ちますが、それ自体は値を生成する演算を指定しません。 一部の区切り記号 (単独または組み合わせ) は、C++ の演算子としても使用できたり、プリプロセッサで意味を持つことがあります。  

 次の文字が区切り記号と見なされます。  

```  
! % ^ & * ( ) - + = { } | ~  
[ ] \ ; ' : " < > ? , . / #  
```  

 区切り記号****、**に関するページ ()**、および**{}**後に、ペアで使用する必要があります[変換フェーズ](../preprocessor/phases-of-translation.md)4 です。  

## <a name="see-also"></a>関連項目  
 [構文規則](../cpp/lexical-conventions.md)

