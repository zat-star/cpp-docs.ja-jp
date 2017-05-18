---
title: "コンパイラ エラー C2008 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2008
dev_langs:
- C++
helpviewer_keywords:
- C2008
ms.assetid: e748ccbe-ffd4-4008-aca7-e53c25225209
caps.latest.revision: 7
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: fc0efbbb942c689831dae73b14f2fa113bec997a
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2008"></a>コンパイラ エラー C2008
'character' : マクロ定義内で指定された文字の使い方が間違っています。  
  
 マクロ名の直後の文字が表示されます。 エラーを解決するには、必要がありますスペース マクロ名の後。  
  
 次の例では、C2008 が生成されます。  
  
```  
// C2008.cpp  
#define TEST1"mytest1"    // C2008  
```  
  
 考えられる解決策:  
  
```  
// C2008b.cpp  
// compile with: /c  
#define TEST2 "mytest2"  
```
