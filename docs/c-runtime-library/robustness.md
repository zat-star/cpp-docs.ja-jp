---
title: "保全性 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.runtime
dev_langs:
- C++
helpviewer_keywords:
- robustness [CRT]
ms.assetid: 7f1a87f8-eff9-4b76-ae9b-d133d3de6adf
caps.latest.revision: 13
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
ms.translationtype: Human Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 84b4144744d896f008d42c3d535eed6d2abd3138
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="robustness"></a>保全性
プログラムの信頼性を向上させるには、次の C ランタイム ライブラリ関数を使用します。  
  
### <a name="run-time-robustness-functions"></a>ランタイムの信頼性関数  
  
|関数|用途|  
|--------------|---------|  
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|`new` 演算子がメモリの割り当てに失敗した場合は、独自のエラー処理機構に制御を移します。|  
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Win32 例外 (C 構造化例外) を C++ 型指定例外として処理します。|  
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|[terminate](../c-runtime-library/reference/terminate-crt.md) によって呼び出される独自の終了関数をインストールします。|  
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|[unexpected](../c-runtime-library/reference/unexpected-crt.md) によって呼び出される独自の終了関数をインストールします。|  
  
## <a name="see-also"></a>関連項目  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)   
 [SetUnhandledExceptionFilter](http://msdn.microsoft.com/library/windows/desktop/ms680634.aspx)
