---
title: "コンパイラの警告 (レベル 4) C4718 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4718
dev_langs:
- C++
helpviewer_keywords:
- C4718
ms.assetid: 29507f8a-b024-42c1-a3b8-f35d1f2641f3
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
ms.openlocfilehash: 48a1144d19f760760f40b5bd9fd1cb43e00e11d8
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-4-c4718"></a>コンパイラの警告 (レベル 4) C4718
'function call': 再帰呼び出しには副作用がありません、削除しています  
  
 関数に再帰呼び出しが含まれていますが、それ以外の副作用はありません。 この関数に対する呼び出しを削除しています。 プログラムの正確性に影響しませんが、動作には影響します。 呼び出しをそのままにした場合、ランタイム スタック オーバーフロー例外が発生する可能性がありますが、呼び出しを削除するとその可能性はなくなります。
