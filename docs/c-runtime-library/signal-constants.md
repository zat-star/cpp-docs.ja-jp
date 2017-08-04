---
title: "signal 定数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SIGTERM
- SIGFPE
- SIGABRT
- SIGILL
- SIGINT
- SIGSEGV
dev_langs:
- C++
helpviewer_keywords:
- SIGTERM constant
- SIGABRT constant
- SIGSEGV constant
- SIGFPE constant
- SIGINT constant
- signal constants
- SIGILL constant
ms.assetid: a3b39281-dae7-4e44-8d68-e6a610c669dd
caps.latest.revision: 11
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
ms.openlocfilehash: 511d700aa5eaa47c59648160e152cfc14c4c1177
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="signal-constants"></a>signal 定数
## <a name="syntax"></a>構文  
  
```  
#include <signal.h>  
```  
  
## <a name="remarks"></a>コメント  
 `sig` 引数は、SIGNAL.H に定義されている以下のマニフェスト定数のいずれかにする必要があります。  
  
 `SIGABRT`  
 異常終了。 既定のアクションでは、終了コード 3 で呼び出し元のプログラムを終了します。  
  
 `SIGABRT_COMPAT`  
 SIGABRT と同じ。 その他のプラットフォームとの互換性を維持します。  
  
 `SIGFPE`  
 オーバーフロー、0 除算、無効な操作などの浮動小数点エラー。 既定のアクションでは、呼び出し元のプログラムを終了します。  
  
 `SIGILL`  
 無効な命令。 既定のアクションでは、呼び出し元のプログラムを終了します。  
  
 `SIGINT`  
 Ctrl + C 割り込み。 既定のアクションでは、終了コード 3 で呼び出し元のプログラムを終了します。  
  
 `SIGSEGV`  
 ストレージへの無効なアクセス。 既定のアクションでは、呼び出し元のプログラムを終了します。  
  
 `SIGTERM`  
 プログラムに送信される終了要求。 既定のアクションでは、終了コード 3 で呼び出し元のプログラムを終了します。  
  
 `SIG_ERR`  
 エラーが発生したことを示すシグナルからの戻り値の型。  
  
## <a name="see-also"></a>関連項目  
 [signal](../c-runtime-library/reference/signal.md)   
 [raise](../c-runtime-library/reference/raise.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)
