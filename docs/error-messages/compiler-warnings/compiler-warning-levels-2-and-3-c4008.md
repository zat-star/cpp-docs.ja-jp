---
title: "コンパイラの警告 (レベル 2 および 3) C4008 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4008
dev_langs:
- C++
helpviewer_keywords:
- C4008
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
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
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 0539a36dddf5bed1d7474f6456eb710bb0506ae4
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-levels-2-and-3-c4008"></a>コンパイラの警告 (レベル 2 および 3) C4008
'identifier': 'attribute' 属性は無視されました  
  
 コンパイラは、関数 (レベル 3 警告) またはデータ (レベル 2 警告) の `__fastcall`、 **静的**、または **インライン** 属性を無視しました。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  `__fastcall`データを持つ属性。  
  
2.  **メイン** 関数の **静的** または **インライン** 属性。
