---
title: "呼び出しの例: 関数プロトタイプと呼び出し |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- calling conventions, examples [C++]
- examples [C++], calling conventions
ms.assetid: e4275d1f-df2e-4bfc-a162-eb43ec69554a
caps.latest.revision: 7
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
ms.openlocfilehash: 897771dbe2d769744bd5dc119083c9db243d56c0
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="calling-example-function-prototype-and-call"></a>呼び出しの例: 関数プロトタイプと呼び出し
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 次の例では、さまざまな呼び出し規約を使用して関数呼び出しを行った結果を示しています。  
  
 この例は、次の関数スケルトンに基づいています。 `calltype` は適切な呼び出し規約に置き換えます。  
  
```  
void    calltype MyFunc( char c, short s, int i, double f );  
.  
.  
.  
void    MyFunc( char c, short s, int i, double f )  
    {  
    .  
    .  
    .  
    }  
.  
.  
.  
MyFunc ('x', 12, 8192, 2.7183);  
```  
  
 詳細については、次を参照してください。[呼び出し結果の例](../cpp/results-of-calling-example.md)です。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [呼び出し規約](../cpp/calling-conventions.md)
