---
title: "exit 関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Exit
dev_langs:
- C++
helpviewer_keywords:
- exit function
ms.assetid: 26ce439f-81e2-431c-9ff8-a09a96f32127
caps.latest.revision: 6
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
ms.openlocfilehash: 240636bf7b6f10421c5d4ebd202a5fb3473a819d
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="exit-function"></a>exit 関数
**終了**STDLIB 標準インクルード ファイルで宣言された関数。H は、C++ プログラムを終了します。  
  
 引数として指定された値**終了**プログラムのリターン コードまたは終了コードとしてオペレーティング システムに返されます。 慣例により、ゼロのリターン コードは、プログラムが正常に完了したことを意味します。  
  
> [!NOTE]
>  STDLIB.H で定義された定数 `EXIT_FAILURE` および `EXIT_SUCCESS` を使用して、プログラムの成功または失敗を示すことができます。  
  
 発行、`return`ステートメントから、**メイン**関数が呼び出すことと同じ、**終了**引数として戻り値を持つ関数です。  
  
 詳細については、次を参照してください。[終了](../c-runtime-library/reference/exit-exit-exit.md)で、*ランタイム ライブラリ リファレンス*です。  
  
## <a name="see-also"></a>関連項目  
 [プログラムの終了](../cpp/program-termination.md)
