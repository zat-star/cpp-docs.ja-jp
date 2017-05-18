---
title: "コンパイラの警告 (レベル 1) C4910 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
caps.latest.revision: 3
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: b8416e456a7d985eb7a3c40addb716ba5c30bf96
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4910"></a>コンパイラの警告 (レベル 1) C4910
'\<識別子 >': '関数' と 'extern' 明示的なインスタンス化に互換性がありません  
  
 という名前の明示的なテンプレート インスタンス化*\<識別子 >*両方によって変更、`__declspec(dllexport)`と`extern`キーワード。 ただし、これらのキーワードは、相互に排他的です。 `__declspec(dllexport)` キーワードは、テンプレート クラスのインスタンス化を意味しますが、 `extern` キーワードは、テンプレート クラスを自動的にインスタンス化しないことを意味します。  
  
## <a name="see-also"></a>関連項目  
 [明示的なインスタンス化](../../cpp/explicit-instantiation.md)   
 [dllexport、dllimport](../../cpp/dllexport-dllimport.md)   
 [一般的な規則と制約](../../cpp/general-rules-and-limitations.md)
