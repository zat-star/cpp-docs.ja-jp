---
title: "コンパイラ エラー C3292 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3292
dev_langs:
- C++
helpviewer_keywords:
- C3292
ms.assetid: ead485cc-5471-4e10-b361-300589ff5b70
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 873f0a2e57aff09435763a5091cc8a384294690a
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3292"></a>コンパイラ エラー C3292
cli 名前空間はを再度開くことはできません  
  
 コード内で cli 名前空間を宣言することはできません。  詳細については、次を参照してください。[プラットフォーム、既定では、および cli 名前空間](../../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md)します。  
  
## <a name="example"></a>例  
 次の例では C3292 が生成されます。  
  
```  
// C3292.cpp  
// compile with: /clr /c  
namespace cli {};   // C3292  
```
