---
title: "コンパイラ エラー C3550 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3550
dev_langs:
- C++
helpviewer_keywords:
- C3550
ms.assetid: 9f2d5ffc-e429-41a1-89e3-7acc4fd47e14
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 408856c3ebabfdddef34a306d18193d88efcddcb
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3550"></a>コンパイラ エラー C3550
このコンテキストでは単純な 'decltype(auto)' のみが許可されます  
  
 `decltype(auto)` を関数の戻り値の型のプレースホルダーとして使用する場合は、単独で使用する必要があります。 ポインターの宣言 (`decltype(auto*)`)、参照の宣言 (`decltype(auto&)`)、またはその他の修飾の一部として使用することはできません。  
  
## <a name="see-also"></a>関連項目  
 [自動](../../cpp/auto-cpp.md)
