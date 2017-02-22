---
title: "set_unexpected (CRT) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "set_unexpected"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "set_unexpected"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "例外処理, 終了"
  - "set_unexpected 関数"
  - "unexpected 関数"
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# set_unexpected (CRT)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`unexpected`が呼び出される独自の終了関数をインストールします。  
  
## 構文  
  
```  
unexpected_function set_unexpected(  
   unexpected_function unexpFunction   
);  
```  
  
#### パラメーター  
 `unexpFunction`  
 `unexpected` 関数を置き換えるために作成する関数へのポインター。  
  
## 戻り値  
 前の関数が後で復元できるように `_set_unexpected` に登録される前の終了関数へのポインターを返します。  前の関数が設定されていない場合の既定の動作を復元するには、戻り値が使用されることがあります。; この値は null になることがあります。  
  
## 解説  
 `set_unexpected` 関数は `unexpected`で呼び出される関数として `unexpFunction` をインストールします。  `unexpected` は 現在の C\+\+ 例外処理の実装では使用されません。  `unexpected_function` の型はユーザー定義の予期しない関数へのポインターと EH.H、その戻り `void``unexpFunction` で定義されます。  `unexpFunction` のカスタム関数が呼び出し元に返される必要があります。  
  
```  
typedef void ( *unexpected_function )( );  
```  
  
 既定で、`unexpected` の呼び出し `terminate`。  独自の終了関数を記述し、引数として関数の名前 `set_unexpected` を呼び出して、この既定の動作を変更できます。  `unexpected` は 最後の関数を `set_unexpected`に引数としてから呼び出します。  
  
 `set_terminate`呼び出しによってインストールされるカスタムの終了関数とは異なり、例外が `unexpFunction`内からスローすることができます。  
  
 マルチスレッド環境では、予期しない関数は、スレッドごとに別々に保持されます。  それぞれの独自の予期しない関数をインストールする新しいスレッドで行う必要があります。  したがって、各スレッドには、独自の予期しない処理があります。  
  
 C\+\+ 例外処理 \(Microsoft の現在の実装では、`unexpected` は `terminate` を既定で呼び出し、例外処理のランタイム ライブラリでも呼び出されません。  特定の利点は `terminate`ではなく `unexpected` を呼び出すことはありません。  
  
 すべての動的にリンクされたな EXE の `set_unexpected` 単一のハンドラーがあり、; `set_unexpected` を呼び出して、ハンドラーは別の置換されるかは、別の DLL または EXE によって設定されたハンドラーを置き換えます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`set_unexpected`|\<eh.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [例外処理ルーチン](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [\_get\_unexpected](../Topic/_get_unexpected.md)   
 [set\_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../Topic/unexpected%20\(CRT\).md)