---
title: "abort | Microsoft Docs"
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
  - "abort"
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
  - "Abort"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "abort 関数"
  - "中止 (現在のプロセスを)"
  - "プロセス, 中止"
ms.assetid: a797783b-40ed-4bdb-a2cd-14ffede39e8a
caps.latest.revision: 24
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# abort
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

現在のプロセスを中止し、エラー コードを返します。  
  
> [!NOTE]
>  テスト シナリオまたはデバッグ シナリオの場合を除き、この方法を使用して [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリをシャットダウンしないでください。  プログラムや UI によって [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリを終了する方法は、「[Windows 8 アプリの認定の要件](http://go.microsoft.com/fwlink/?LinkId=262889)」により禁止されています。  詳細については、「[アプリケーションのライフサイクル \(Windows ストア アプリ\)](http://go.microsoft.com/fwlink/?LinkId=262853)」を参照してください。  
  
## 構文  
  
```  
void abort( void );  
```  
  
## 戻り値  
 `abort` は、呼び出し元のプロセスに制御を返しません。  既定では、中止シグナル ハンドラーが確認され、それが設定されている場合は `SIGABRT` が発生します。  その後 `abort` は、現在のプロセスを終了し、親プロセスに終了コードを返します。  
  
## 解説  
 **Microsoft 固有の仕様 →**  
  
 既定では、デバッグ ランタイム ライブラリを使用してアプリをビルドしている場合、`abort` ルーチンによってエラー メッセージが表示された後、`SIGABRT` が発生します。  コンソール モードで動作しているコンソール アプリの場合は、`STDERR` にメッセージが送信されます。  ウィンドウ モードで動作している Windows デスクトップ アプリとコンソール アプリでは、メッセージ ボックスにメッセージが表示されます。  メッセージを抑制するには、[\_set\_abort\_behavior](../../c-runtime-library/reference/set-abort-behavior.md) を使用して `_WRITE_ABORT_MSG` フラグをクリアします。  表示されるメッセージは、使用しているランタイム環境のバージョンによって異なります。  Visual C\+\+ の最新バージョンを使用してビルドされたアプリケーションでは、次のようなメッセージが表示されます。  
  
 `R6010`  
  
 `- abort() has been called`  
  
 C ランタイム ライブラリの以前のバージョンでは、次のメッセージが表示されました。  
  
 "`This application has requested the Runtime to terminate it in an unusual way. Please contact the application's support team for more information.`"  
  
 プログラムをデバッグ モードでコンパイルしている場合、メッセージ ボックスに **\[中止\]**、**\[再試行\]**、または **\[無視\]** のオプションが表示されます。  ユーザーが **\[中止\]** をクリックすると、プログラムが即座に終了し、終了コード "3" が返されます。  ユーザーが **\[再試行\]** をクリックすると、just\-in\-time デバッグが有効な場合はデバッガーが起動してデバッグが開始します。  ユーザーが **\[無視\]** をクリックすると、`abort` によって通常の処理が続けられます。  
  
 リテール ビルドとデバッグ ビルドのどちらの場合も、`abort` は次に、中止シグナル ハンドラーが設定されているかどうかを確認します。  既定以外のシグナル ハンドラーが設定されている場合、`abort` は `raise(SIGABRT)` を呼び出します。  `SIGABRT` シグナルに中止シグナル ハンドラー関数を関連付けるには、[signal](../../c-runtime-library/reference/signal.md) 関数を使用します。  ハンドラー関数では、カスタム動作 \(リソースのクリーンアップや情報のログ記録など\) を実行し、独自のエラー コードを発行してアプリを修了できます。  カスタムのシグナル ハンドラーが定義されていない場合、`abort` で `SIGABRT` 通知が発生しません。  
  
 既定では、デスクトップ アプリやコンソール アプリの非デバッグ ビルドで、`abort` は次に、Windows のエラー レポート機構 \(  ワトソン博士\) を起動してエラーを Microsoft に報告します。  この動作は、`_set_abort_behavior` を呼び出し、`_CALL_REPORTFAULT` フラグを設定するかマスクして、有効または無効にすることができます。  フラグが設定されていると、Windows でメッセージ ボックスが開き、「問題が発生したため、プログラムが正しく動作しなくなりました」などのテキストが表示されます。ユーザーは **\[デバッグ\]** をクリックしてデバッガーを開始するか、**\[プログラムの終了\]** をクリックすることでオペレーティング システムで定義されているエラー コードを発行してアプリを終了できます。  
  
 Windows のエラー レポート ハンドラーが起動しない場合、`abort` は [\_exit](../../c-runtime-library/reference/exit-exit-exit.md) を呼び出し、終了コード "3" を発行してプロセスを終了した後、親プロセスまたはオペレーティング システムに制御を戻します。  `_exit` は、ストリーム バッファーをフラッシュせず、`atexit`\/`_onexit` 処理を行いません。  
  
 CRT デバッグの詳細については、「[CRT のデバッグ技術](../Topic/CRT%20Debugging%20Techniques.md)」を参照してください。  
  
 **End Microsoft 固有**  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`abort`|\<process.h\> または \<stdlib.h\>|  
  
## 使用例  
 次のプログラムはファイルを開こうとしますが、試みに失敗すると中止されます。  
  
```c  
// crt_abort.c  
// compile with: /TC  
// This program demonstrates the use of  
// the abort function by attempting to open a file  
// and aborts if the attempt fails.  
  
#include  <stdio.h>  
#include  <stdlib.h>  
  
int main( void )  
{  
    FILE    *stream = NULL;  
    errno_t err = 0;  
  
    err = fopen_s(&stream, "NOSUCHF.ILE", "r" );  
    if ((err != 0) || (stream == NULL))  
    {  
        perror( "File could not be opened" );  
        abort();  
    }  
    else  
    {  
        fclose( stream );  
    }  
}  
```  
  
  **ファイルを開けませんでした: 該当するファイルまたはディレクトリがありません**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [abort の使用](../../cpp/using-abort.md)   
 [abort 関数](../../c-language/abort-function-c.md)   
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [\_exec、\_wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)   
 [終了、\_Exit、\_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [raise](../../c-runtime-library/reference/raise.md)   
 [signal](../../c-runtime-library/reference/signal.md)   
 [\_spawn 系関数と \_wspawn 系関数](../Topic/_spawn,%20_wspawn%20Functions.md)   
 [\_DEBUG](../Topic/_DEBUG.md)   
 [\_set\_abort\_behavior](../../c-runtime-library/reference/set-abort-behavior.md)