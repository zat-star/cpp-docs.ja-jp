---
title: "signal のアクション定数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SIG_IGN
- SIG_DFL
dev_langs:
- C++
helpviewer_keywords:
- signal action constants
- SIG_IGN constant
- SIG_DFL constant
ms.assetid: c3cb4f15-d39e-4d9d-84f9-0d33e3eb5993
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: f316218673d83187f29934ebd75a838b31005912
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="signal-action-constants"></a>signal のアクション定数
割り込みシグナルを受信したときに実行されるアクションは、`func` の値によって異なります。  
  
## <a name="syntax"></a>構文  
  
```  
#include <signal.h>  
```  
  
## <a name="remarks"></a>コメント  
 `func` 引数は、関数のアドレス、または SIGNAL.H に定義されている以下のマニフェスト定数のいずれかにする必要があります。  
  
 `SIG_DFL`  
 システム既定の応答を使用します。 呼び出し元のプログラムがストリーム I/O を使用している場合、ランタイム ライブラリによって作成されるバッファーはフラッシュされません。  
  
 `SIG_IGN`  
 割り込みシグナルを無視します。 プロセスの浮動小数点状態が未定義のままになるため、この値を `SIGFPE` に指定しないでください。  
  
 `SIG_SGE`  
 シグナルでエラーが発生したことを示します。  
  
 `SIG_ACK`  
 受信確認を受け取ったことを示します。  
  
 `SIG_ERR`  
 エラーが発生したことを示すシグナルからの戻り値の型。  
  
## <a name="see-also"></a>関連項目  
 [signal](../c-runtime-library/reference/signal.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)
