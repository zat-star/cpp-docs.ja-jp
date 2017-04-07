---
title: "エラー処理 (CRT) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.errors
dev_langs:
- C++
helpviewer_keywords:
- error handling, C routines for
- logic errors
- error handling, library routines
- testing, for program errors
ms.assetid: 125ac697-9eb0-4152-a440-b7842f23d97f
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: ad3844e5d57081b1a9638e197231479b7a03a337
ms.lasthandoff: 03/29/2017

---
# <a name="error-handling-crt"></a>エラー処理 (CRT)
これらのルーチンを使用し、プログラム エラーを処理します。  
  
### <a name="error-handling-routines"></a>エラー処理ルーチン  
  
|ルーチン|用途|  
|-------------|---------|  
|[assert](../c-runtime-library/reference/assert-macro-assert-wassert.md) マクロ|プログラミング論理エラーのテストであり、ランタイム ライブラリのリリース バージョンとデバッグ バージョンの両方で利用できます。|  
|[_ASSERT マクロ、_ASSERTE マクロ](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|`assert` に類似していますが、ランタイム ライブラリのデバッグ バージョンでのみ使用できます。|  
|[clearerr](../c-runtime-library/reference/clearerr.md)|エラー インジケーターをリセットします。 `rewind` を呼び出すか、ストリームを閉じると、エラー インジケーターもリセットされます。|  
|[_eof](../c-runtime-library/reference/eof.md)|下位入出力のファイルの終わりを確認します。|  
|[feof](../c-runtime-library/reference/feof.md)|ファイルの終わりをテストします。 ファイルの終わりは、`_read` が 0 を返したときにも指示されます。|  
|[ferror](../c-runtime-library/reference/ferror.md)|ストリーム入出力エラーをテストします。|  
|[_RPT マクロ、_RPTF](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) マクロ|`printf` に似たレポートを生成しますが、ランタイム ライブラリのデバッグ バージョンでのみ使用できます。|  
|[_set_error_mode](../c-runtime-library/reference/set-error-mode.md)|プログラムを終了させる可能性があるエラーに対して C ランタイムがエラー メッセージを書き込む、既定以外の位置を `__error_mode` を変更して決定します。|  
|[_set_purecall_handler](../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)|純粋仮想関数呼び出しのハンドラーを設定します。|  
  
## <a name="see-also"></a>関連項目  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)
