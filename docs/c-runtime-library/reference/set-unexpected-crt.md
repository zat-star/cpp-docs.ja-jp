---
title: set_unexpected (CRT) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: set_unexpected
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
- ucrtbase.dll
apitype: DLLExport
f1_keywords: set_unexpected
dev_langs: C++
helpviewer_keywords:
- set_unexpected function
- unexpected function
- exception handling, termination
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2798fff46d40ed6100f101cbc8839ad2fd166f4b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="setunexpected-crt"></a>set_unexpected (CRT)
`unexpected`.によって呼び出される独自の終了関数をインストールします。  
  
## <a name="syntax"></a>構文  
  
```  
unexpected_function set_unexpected(  
   unexpected_function unexpFunction   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `unexpFunction`  
 `unexpected` 関数を置き換えるために作成する関数へのポインター。  
  
## <a name="return-value"></a>戻り値  
 `_set_unexpected` によって登録された前の終了関数へのポインターを返し、前の関数を後で復元できるようにします。 前の関数が設定されていない場合には、戻り値を使用して既定の動作を復元することができます。この値は NULL になります。  
  
## <a name="remarks"></a>コメント  
 `set_unexpected` 関数は `unexpected` によって呼び出される関数として `unexpFunction` をインストールします。 `unexpected` は現在の C++ 例外処理の実装では使用されません。 `unexpected_function` 型は EH.H に、ユーザー定義の予期しない関数、つまり `void` を返す `unexpFunction` へのポインターとして定義されます。 カスタムの `unexpFunction` 関数は、呼び出し元に返ることはできません。  
  
```  
typedef void ( *unexpected_function )( );  
```  
  
 既定では `unexpected` は `terminate`を呼び出します。 この既定の設定を変更するには、独自の終了関数を作成し、その関数の名前を引数として `set_unexpected` を呼び出します。 `unexpected` は、`set_unexpected` への引数として渡された最後の関数を呼び出します。  
  
 `set_terminate` への呼び出しによってインストールされたカスタムの終了関数とは異なり、例外は `unexpFunction` 内からスローすることができます。  
  
 マルチ スレッド環境では、予期しない関数はスレッドごとに別々に管理されます。 新しいスレッドは各々、それぞれの予期しない関数をインストールする必要があります。 したがって、各スレッドがそれぞれの予期しない処理を担当します。  
  
 C++ 例外処理の Microsoft での現在の実装では、`unexpected` は既定で `terminate` を呼び出し、例外処理のランタイム ライブラリによって呼び出されることはありません。 `terminate` ではなく `unexpected` を呼び出すことに、特に利点はありません。  
  
 動的にリンクされるすべての DLL または EXE ファイルに対して、`set_unexpected` ハンドラーは単一です。自分で `set_unexpected` を呼び出しても別のハンドラーに置き換えられます。あるいはハンドラーを別の DLL または EXE ファイルに自分で置き換えることもできます。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`set_unexpected`|\<eh.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="see-also"></a>参照  
 [例外処理ルーチン](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [_get_unexpected](../../c-runtime-library/reference/get-unexpected.md)   
 [set_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)