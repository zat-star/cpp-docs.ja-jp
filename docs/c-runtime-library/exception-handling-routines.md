---
title: "例外処理ルーチン | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.exceptions
dev_langs:
- C++
helpviewer_keywords:
- exception handling, routines
ms.assetid: f60548c6-850a-4e1e-a79b-a2a6a541ab62
caps.latest.revision: 8
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: fe4946a8d3785c6295cb7537de0a11e06cd7a1cc
ms.lasthandoff: 02/24/2017

---
# <a name="exception-handling-routines"></a>例外処理ルーチン
C++ 例外処理関数を利用し、プログラム実行中の予想外のイベントから復旧します。  
  
### <a name="exception-handling-functions"></a>例外処理関数  
  
|関数|用途|同等の .NET Framework 関数|  
|--------------|---------|-------------------------------|  
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Win32 例外 (C 構造化例外) を C++ 型指定例外として処理する|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|`terminate` によって呼び出される独自の終了ルーチンをインストールする|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|`unexpected` によって呼び出される独自の終了関数をインストールする|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[terminate](../c-runtime-library/reference/terminate-crt.md)|例外がスローされた後、特定の状況下で自動的に呼び出されます。 `terminate` 関数は、`abort` または `set_terminate` で指定した関数を呼び出します|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[unexpected](../c-runtime-library/reference/unexpected-crt.md)|`terminate`、または `set_unexpected` を使用して指定した関数を呼び出します。 `unexpected` 関数は現在の Microsoft C++ 例外処理の実装では使用されません|[System::Exception クラス](https://msdn.microsoft.com/en-us/library/system.exception.aspx)|  
  
## <a name="see-also"></a>関連項目  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)
