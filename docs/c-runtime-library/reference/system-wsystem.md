---
title: "system、_wsystem | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "system"
  - "_wsystem"
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
  - "_tsystem"
  - "_wsystem"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tsystem 関数"
  - "_wsystem 関数"
  - "コマンド インタープリター"
  - "コマンド, 実行"
  - "system 関数"
  - "tsystem 関数"
  - "wsystem 関数"
ms.assetid: 7d3df2b6-f742-49ce-bf52-012b0aee3df5
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# system、_wsystem
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コマンドを実行します。  
  
> [!IMPORTANT]
>  この API は、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
int system(  
   const char *command   
);  
int _wsystem(  
   const wchar_t *command   
);  
```  
  
#### パラメーター  
 `command`  
 実行するコマンド。  
  
## 戻り値  
 `command` が `NULL` の場合に、コマンド インタープリターが見つかると、0 以外の値を返します。  コマンド インタープリターが見つからない場合は、0 を返し、`errno` を `ENOENT` に設定します。  `command` が `NULL` でない場合、`system` は、コマンド インタープリターから返された値を返します。  コマンド インタープリターから値 0 が返された場合にのみ、値 0 を返します。  戻り値 \-1 はエラーを示します。その場合、`errno` は次のいずれかの値に設定されます。  
  
 `E2BIG`  
 引数リスト \(システムに依存する\) が大きすぎます。  
  
 `ENOENT`  
 コマンド インタープリターが見つかりません。  
  
 `ENOEXEC`  
 形式が無効なため、コマンド インタープリター ファイルを実行できません。  
  
 `ENOMEM`  
 コマンドを実行するために十分なメモリがないか、使用できるメモリが破損しているか、または無効なブロックが存在します \(これは、呼び出しを実行しているプロセスが正しく割り当てられなかったことを示します\)。  
  
 これらのリターン コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `system` 関数は `command` をコマンド インタープリターに渡し、その文字列がオペレーティング システム コマンドとして実行されます。  `system` は、`COMSPEC` および `PATH` の各環境変数を使用して、コマンド インタープリター ファイル CMD.exe を見つけます。  `command` が `NULL` の場合、この関数はコマンド インタープリターの存在を確認するだけです。  
  
 `system` 関数を呼び出す前に、`fflush` または `_flushall` を使用してストリームを明示的にフラッシュするか、ストリームを閉じる必要があります。  
  
 `_wsystem` 関数は、`system` 関数のワイド文字バージョンです。`command` 関数の引数 `_wsystem` は、ワイド文字列です。  それ以外では、これらの関数の動作は同じです。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tsystem`|`system`|`system`|`_wsystem`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`system`|\<process.h\> または \<stdlib.h\>|  
|`_wsystem`|\<process.h\> または \<stdlib.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 この例では、`system` を使用してテキスト ファイルをタイプします。  
  
```  
// crt_system.c  
  
#include <process.h>  
  
int main( void )  
{  
   system( "type crt_system.txt" );  
}  
```  
  
## 入力: crt\_system.txt  
  
```  
Line one.  
Line two.  
```  
  
### 出力  
  
```  
Line one.  
Line two.  
```  
  
## 同等の .NET Framework 関数  
  
-   [System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)  
  
-   [System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)  
  
## 参照  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [\_exec、\_wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)   
 [終了、\_Exit、\_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_flushall](../../c-runtime-library/reference/flushall.md)   
 [\_spawn 系関数と \_wspawn 系関数](../Topic/_spawn,%20_wspawn%20Functions.md)