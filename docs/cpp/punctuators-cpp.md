---
title: "区切り記号 (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: punctuators [C++]
ms.assetid: 1521564c-a977-488a-9490-068079897592
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 46ebf6e98b9c9d6521174cd35c9754cff7d9d609
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="punctuators-c"></a>区切り記号 (C++)
C++ の区切り記号はコンパイラに対する構文上およびセマンティック上の意味を持ちますが、それ自体は値を生成する演算を指定しません。 一部の区切り記号 (単独または組み合わせ) は、C++ の演算子としても使用できたり、プリプロセッサで意味を持つことがあります。  

 次の文字が区切り記号と見なされます。  

```  
! % ^ & * ( ) - + = { } | ~  
[ ] \ ; ' : " < > ? , . / #  
```  

 区切り記号**[]**、**に関するページ ()**、および**{}**後に、ペアで使用する必要があります[変換フェーズ](../preprocessor/phases-of-translation.md)4 です。  

## <a name="see-also"></a>参照  
 [構文規則](../cpp/lexical-conventions.md)
