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
ms.openlocfilehash: b9e0d6a7f903d4af39698b2d98c005cbf64515eb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="exit-function"></a>exit 関数
**終了**STDLIB 標準インクルード ファイルで宣言された関数。H は、C++ プログラムを終了します。  
  
 引数として指定された値**終了**プログラムのリターン コードまたは終了コードとしてオペレーティング システムに返されます。 慣例により、ゼロのリターン コードは、プログラムが正常に完了したことを意味します。  
  
> [!NOTE]
>  STDLIB.H で定義された定数 `EXIT_FAILURE` および `EXIT_SUCCESS` を使用して、プログラムの成功または失敗を示すことができます。  
  
 発行、`return`ステートメントから、**メイン**関数が呼び出すことと同じ、**終了**引数として戻り値を持つ関数です。  
  
 詳細については、次を参照してください。[終了](../c-runtime-library/reference/exit-exit-exit.md)で、*ランタイム ライブラリ リファレンス*です。  
  
## <a name="see-also"></a>参照  
 [プログラムの終了](../cpp/program-termination.md)