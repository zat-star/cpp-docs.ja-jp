---
title: "set_terminate (CRT) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "set_terminate"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "set_terminate"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "例外処理, 終了"
  - "set_terminate 関数"
  - "terminate 関数"
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# set_terminate (CRT)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`terminate`が呼び出される独自の終端ルーチンをインストールします。  
  
## 構文  
  
```  
terminate_function set_terminate(  
   terminate_function termFunction  
);  
```  
  
#### パラメーター  
 `termFunction`  
 作成する終端の関数へのポインター。  
  
## 戻り値  
 前の関数が後で復元できるように `set_terminate` に登録されている以前の関数へのポインターを返します。  前の関数が設定されていない場合の既定の動作を復元するには、戻り値が使用されることがあります。; この値は null になることがあります。  
  
## 解説  
 `set_terminate` 関数は `terminate`で呼び出される関数として `termFunction` をインストールします。  `set_terminate` は C\+\+ 例外処理との例外がスローされる前に使用され、プログラム上の任意の場所で呼び出されることがあります。  `terminate` の 呼び出し `abort` 既定で。  独自の終了関数を記述し、引数として関数の名前 `set_terminate` を呼び出して、この既定を変更できます。  `terminate` は 最後の関数を `set_terminate`に引数としてから呼び出します。  必要なクリーンアップ タスクを実行した後、`termFunction` はプログラムを終了する必要があります。   \(呼び出し元に戻ると、それが表示されない場合は、`abort`\) が呼び出されます。  
  
 マルチスレッド環境では、関数を別々に保持され、スレッドごとに終了します。  それぞれの独自にインストールする新しいスレッドのニーズに応じて関数を終了します。  したがって、各スレッドには、独自の終了処理があります。  
  
 `terminate_function` の型はユーザー定義の終了関数へのポインターと EH.H、その戻り `void``termFunction` で定義されます。  カスタム関数 `termFunction` は、引数を受け取らないことができ、呼び出し元に戻る必要があります。  これは、`abort` が呼び出されます。  例外は `termFunction`内からスローされないことがあります。  
  
```  
typedef void ( *terminate_function )( );  
```  
  
> [!NOTE]
>  `set_terminate` 関数は、デバッガーの外部でのみ機能します。  
  
 すべての動的にリンクされたな EXE の `set_terminate` 単一のハンドラーがあり、; `set_terminate` を呼び出して、ハンドラーは別の置換したり、または別の DLL または EXE によって設定されたハンドラーを置き換えることがあります。  
  
 この関数は **\/clr:pure**でサポートされません。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`set_terminate`|\<eh.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 [完成します。](../../c-runtime-library/reference/terminate-crt.md)"の例を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [例外処理ルーチン](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [\_get\_terminate](../../c-runtime-library/reference/get-terminate.md)   
 [set\_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../Topic/unexpected%20\(CRT\).md)