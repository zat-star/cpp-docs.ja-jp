---
title: "数値演算エラー M6111 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- M6111
dev_langs:
- C++
helpviewer_keywords:
- M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
caps.latest.revision: 6
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 906072bdd8fe674d69604ddc6f8ddd66ebad712d
ms.lasthandoff: 02/24/2017

---
# <a name="math-error-m6111"></a>数値演算エラー M6111
スタックのアンダー フロー  
  
 浮動小数点演算 8087/287/387 コプロセッサまたはエミュレーターでのスタック アンダー フローが発生しました。  
  
 呼び出しでこのエラーが原因となった多くの場合、`long double`値を返さない関数です。 たとえば、次のこのエラーが生成コンパイルして実行時に。  
  
```  
long double ld() {};  
main ()  
{  
  ld();  
}  
```  
  
 プログラムは、終了コード 139 で終了します。
