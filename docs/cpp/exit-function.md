---
title: "exit 関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Exit
dev_langs: C++
helpviewer_keywords: exit function
ms.assetid: 26ce439f-81e2-431c-9ff8-a09a96f32127
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ee6a34a70465904e6725f42e68eb4a00c03a1661
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2018
---
# <a name="exit-function"></a>exit 関数
**終了**標準インクルード ファイルで宣言された関数\<stdlib.h >、C++ プログラムを終了します。  
  
 引数として指定された値**終了**プログラムのリターン コードまたは終了コードとしてオペレーティング システムに返されます。 慣例により、ゼロのリターン コードは、プログラムが正常に完了したことを意味します。  
  
> [!NOTE]
>  定数を使用することができます`EXIT_FAILURE`と`EXIT_SUCCESS`で定義されている\<stdlib.h >、プログラムの成功または失敗を示すためにします。  
  
 発行、`return`ステートメントから、**メイン**関数が呼び出すことと同じ、**終了**引数として戻り値を持つ関数です。  
  
 詳細については、次を参照してください。[終了](../c-runtime-library/reference/exit-exit-exit.md)で、*ランタイム ライブラリ リファレンス*です。  
  
## <a name="see-also"></a>参照  
 [プログラムの終了](../cpp/program-termination.md)