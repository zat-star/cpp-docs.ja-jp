---
title: "コンパイラの警告 (レベル 4) C4057 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4057
dev_langs:
- C++
helpviewer_keywords:
- C4057
ms.assetid: e75d0645-84c9-4bef-a812-942ed9879aa3
caps.latest.revision: 6
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
ms.openlocfilehash: ad1013a90b2b3d6ad1f7148ea62c05ae505348d4
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-4-c4057"></a>コンパイラの警告 (レベル 4) C4057
'operator' : 'identifier1' と 'identifier2' で間接参照している基本型が微妙に異なっています
  
  
 2 つのポインター式が参照する基本型が異なります。 式は変換されずに使用されます。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  signed 型と unsigned 型が混在しています。  
  
2.  **short** 型と **long** 型が混在しています。
