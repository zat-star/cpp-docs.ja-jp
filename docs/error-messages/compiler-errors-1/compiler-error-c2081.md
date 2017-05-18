---
title: "コンパイラ エラー C2081 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2081
dev_langs:
- C++
helpviewer_keywords:
- C2081
ms.assetid: 7db9892d-364d-4178-a49d-f8398ece09a0
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
ms.openlocfilehash: e8d652dcd44772653ea1b09397a2fff0f7a36ac3
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2081"></a>コンパイラ エラー C2081
'identifier': 名前仮パラメーター リストが不正です。  
  
 識別子には、構文エラーが発生しました。  
  
 このエラーは、正式なパラメーター リストの従来のスタイルを使用して、発生することができます。 正式なパラメーター リストでは、仮パラメーターの種類を指定する必要があります。  
  
 次の例では、c2081 エラーが生成されます。  
  
```  
// C2081.c  
void func( int i, j ) {}  // C2081, no type specified for j  
```  
  
 考えられる解決策:  
  
```  
// C2081b.c  
// compile with: /c  
void func( int i, int j ) {}  
```
