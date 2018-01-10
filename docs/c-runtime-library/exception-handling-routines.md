---
title: "例外処理ルーチン | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.exceptions
dev_langs: C++
helpviewer_keywords: exception handling, routines
ms.assetid: f60548c6-850a-4e1e-a79b-a2a6a541ab62
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 95ecbc69dd9cbd86bd7891c79f115442f659ff94
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="exception-handling-routines"></a>例外処理ルーチン
C++ 例外処理関数を利用し、プログラム実行中の予想外のイベントから復旧します。  
  
### <a name="exception-handling-functions"></a>例外処理関数  
  
|関数|使用|  
|--------------|---------|  
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Win32 例外 (C 構造化例外) を C++ 型指定例外として処理する|  
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|`terminate` によって呼び出される独自の終了ルーチンをインストールする|  
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|`unexpected` によって呼び出される独自の終了関数をインストールする|  
|[terminate](../c-runtime-library/reference/terminate-crt.md)|例外がスローされた後、特定の状況下で自動的に呼び出されます。 `terminate` 関数は、`abort` または `set_terminate` で指定した関数を呼び出します|  
|[unexpected](../c-runtime-library/reference/unexpected-crt.md)|`terminate`、または `set_unexpected` を使用して指定した関数を呼び出します。 `unexpected` 関数は現在の Microsoft C++ 例外処理の実装では使用されません|  
  
## <a name="see-also"></a>参照  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)