---
title: "エラー処理 (CRT) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.errors"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "エラー処理, C ルーチン"
  - "エラー処理, ライブラリ ルーチン"
  - "論理エラー"
  - "テスト, プログラム エラーの"
ms.assetid: 125ac697-9eb0-4152-a440-b7842f23d97f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# エラー処理 (CRT)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プログラム エラーを処理するには、次のルーチンを使用します。  
  
### エラー処理ルーチン  
  
|ルーチン|使用方法|同等の .NET Framework 関数|  
|----------|----------|---------------------------|  
|[アサートします。](../c-runtime-library/reference/assert-macro-assert-wassert.md) マクロ|プログラミング ロジックのエラーをテストします。; ランタイム ライブラリのリリース バージョンとデバッグ バージョンの両方で使用できます。|[\<caps:sentence id\="tgt8" sentenceid\="14fd9bf776829d73028df00162f7533f" class\="tgtSentence"\>System::Diagnostics::Debug::Assert\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[\_ASSERT、\_ASSERTE](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md) マクロ|`assert`に似ていますが、デバッグ バージョンのランタイム ライブラリだけで使用できます。|[\<caps:sentence id\="tgt11" sentenceid\="14fd9bf776829d73028df00162f7533f" class\="tgtSentence"\>System::Diagnostics::Debug::Assert\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[clearerr](../c-runtime-library/reference/clearerr.md)|エラー インジケーターをリセットします。  `rewind` または完了を呼び出してストリームもエラー インジケーターがリセットされます。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_eof](../c-runtime-library/reference/eof.md)|低水準 I\/O の終端ファイルをチェックします。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[feof](../c-runtime-library/reference/feof.md)|ファイルの終端のかどうかをテストします。  ファイルの終端に達した場合は、時 `_read`は 0 を示します。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[ferror](../c-runtime-library/reference/ferror.md)|ストリームの I\/O エラーをテストします。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_RPT、\_RPTF](../Topic/_RPT,%20_RPTF,%20_RPTW,%20_RPTFW%20Macros.md) マクロ|`printf`に似た、ランタイム ライブラリのデバッグ バージョンでのみ使用可能なレポートを生成します。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_set\_error\_mode](../c-runtime-library/reference/set-error-mode.md)|`__error_mode` を C の実行時が、プログラムを終了するエラーのエラー メッセージを書き込む既定以外の位置を確認するように変更します。||  
|[\_set\_purecall\_handler](../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)|純粋仮想関数呼び出しのハンドラーを設定します。||  
  
## 参照  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)