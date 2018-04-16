---
title: _purecall | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _purecall
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ntoskrnl.exe
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- purecall
- _purecall
dev_langs:
- C++
helpviewer_keywords:
- _purecall function
- purecall function
ms.assetid: 56135d9b-3403-4e22-822d-e714523801cc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c19324cde907f31ab18a312f3039c2da7a3a40c7
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="purecall"></a>_purecall
純粋仮想関数が呼び出された場合の、既定のエラー ハンドラーです。 純粋仮想メンバー関数が呼び出されると、コンパイラによってこの関数を呼び出すコードが生成されます。  
  
## <a name="syntax"></a>構文  
  
```  
extern "C" int __cdecl _purecall();  
```  
  
## <a name="remarks"></a>コメント  
 `_purecall` 関数は、Microsoft Visual C++ コンパイラに含まれる、Microsoft 固有の実装の詳細です。 この関数はコードで直接呼び出されるものではなく、パブリック ヘッダー宣言がありません。 C ランタイム ライブラリのパブリック エクスポートであるため、ここで説明しています。  
  
 純粋仮想関数には実装がないため、この関数への呼び出しはエラーになります。 純粋仮想関数が呼び出されると、コンパイラによって `_purecall` のエラー ハンドラー関数を呼び出すコードが生成されます。 既定では、`_purecall` によりプログラムが終了します。 `_purecall_handler` 関数がプロセスに設定されている場合は、`_purecall` 関数によってプログラムの終了前に呼び出されます。 純粋仮想関数の呼び出し用に独自のエラー ハンドラーの関数をインストールして呼び出しをキャッチし、デバッグまたはレポート作成に使用することができます。 独自のエラー ハンドラーを使用するには、`_purecall_handler` シグネチャのある関数を作成し、[_set_purecall_handler](../../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md) を使って作成した関数を現在のハンドラーにします。  
  
## <a name="requirements"></a>必要条件  
 `_purecall` 関数にはヘッダー宣言がありません。 `_purecall_handler` typedef は \<stdlib.h> で定義されています。  
  
## <a name="see-also"></a>参照  
 [関数リファレンス (アルファベット順)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [_get_purecall_handler、_set_purecall_handler](../../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)