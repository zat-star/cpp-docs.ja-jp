---
title: "プロセス制御と環境制御 | Microsoft Docs"
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
  - "c.programs"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "環境制御ルーチン"
  - "親プロセス"
  - "プロセス制御ルーチン"
  - "プロセス, 管理タスク"
  - "プロセス, 開始"
  - "プロセス, 停止"
ms.assetid: 7fde74c3-c2a6-4d15-84b8-092160d60c3e
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# プロセス制御と環境制御
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

開始、停止、内部の管理にプロセス制御ルーチンをプログラムからプロセスを使用します。  オペレーティング システムの環境に関する情報を取得したり、変更に環境コントロール ルーチンを使用します。  
  
### プロセスと環境で機能  
  
|ルーチン|使用方法|同等の .NET Framework 関数|  
|----------|----------|---------------------------|  
|[中止](../c-runtime-library/reference/abort.md)|`atexit` と `_onexit`に登録されているフラッシュ バッファーまたは呼び出し元の関数がないプロセスを中止します。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[assert](../c-runtime-library/reference/assert-macro-assert-wassert.md)|論理エラーをテストします。|[\<caps:sentence id\="tgt14" sentenceid\="14fd9bf776829d73028df00162f7533f" class\="tgtSentence"\>System::Diagnostics::Debug::Assert\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[\_ASSERT、\_ASSERTE](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md) マクロ|`assert`に似ていますが、デバッグ バージョンのランタイム ライブラリだけで使用できます。|[\<caps:sentence id\="tgt17" sentenceid\="14fd9bf776829d73028df00162f7533f" class\="tgtSentence"\>System::Diagnostics::Debug::Assert\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[atexit](../c-runtime-library/reference/atexit.md)|プログラムの終了のスケジュール ルーチン|[\<caps:sentence id\="tgt20" sentenceid\="db022fa9aa2a12937c3610e3eb32e80f" class\="tgtSentence"\>System::Diagnostics::Process::Exited\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)|  
|[\_beginthread、\_beginthreadex](../Topic/_beginthread,%20_beginthreadex.md)|Windows オペレーティング システム プロセスの新しいスレッドを作成します。|[\<caps:sentence id\="tgt23" sentenceid\="221e38ecc6535bce91af4e1a19f464d1" class\="tgtSentence"\>System::Threading::Thread::Start\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.threading.thread.start.aspx)|  
|[\_cexit](../c-runtime-library/reference/cexit-c-exit.md)|`exit` の終了手順 \(バッファーをフラッシュなど\) で実行され、呼び出し元のプログラムにプロセスを終えないでコントロールを返します。|[\<caps:sentence id\="tgt26" sentenceid\="46302f19d05c09c5875a795cb64800f9" class\="tgtSentence"\>System::Diagnostics::Process::CloseMainWindow\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.closemainwindow.aspx)|  
|[\_c\_exit](../c-runtime-library/reference/cexit-c-exit.md)|`_exit` の終了手順を実行した後、呼び出し元のプログラムにプロセスを終えないでコントロールを返します。|[\<caps:sentence id\="tgt29" sentenceid\="46302f19d05c09c5875a795cb64800f9" class\="tgtSentence"\>System::Diagnostics::Process::CloseMainWindow\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.closemainwindow.aspx)|  
|[\_cwait](../c-runtime-library/reference/cwait.md)|別のプロセスが終了するまで待機します。|[\<caps:sentence id\="tgt32" sentenceid\="d9c88c429eaacaa9f37d91d29bc6504e" class\="tgtSentence"\>System::Diagnostics::Process::WaitForExit\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.waitforexit.aspx)|  
|[\_endthread と\_endthreadex](../Topic/_endthread,%20_endthreadex.md)|Windows オペレーティング システムのスレッドを終了します。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_execl、\_wexecl](../Topic/_execl,%20_wexecl.md)|引数リストで新しいプロセスを実行します。|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execle、\_wexecle](../c-runtime-library/reference/execle-wexecle.md)|引数リストと特定の環境で新しいプロセスを実行します。|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execlp、\_wexeclp](../c-runtime-library/reference/execlp-wexeclp.md)|`PATH` の変数と引数リストを使用して新しいプロセスを実行します。|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execlpe、\_wexeclpe](../c-runtime-library/reference/execlpe-wexeclpe.md)|、環境変数 `PATH` を使用して新しいプロセスおよび引数リストが指定された実行します。|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execv、\_wexecv](../c-runtime-library/reference/execv-wexecv.md)|引数配列を持つ新しいプロセスを実行します。|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execve、\_wexecve](../c-runtime-library/reference/execve-wexecve.md)|引数配列および特定の環境に対する新しいプロセスを実行します。|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execvp、\_wexecvp](../c-runtime-library/reference/execvp-wexecvp.md)|`PATH` の変数と引数配列を使用して新しいプロセスを実行します。|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execvpe、\_wexecvpe](../Topic/_execvpe,%20_wexecvpe.md)|、環境変数 `PATH` を使用して新しいプロセスおよび引数配列に用意されている実行します。|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[exit](../c-runtime-library/reference/exit-exit-exit.md)|関数を `atexit` と `_onexit`に登録されている呼び出し、すべてのバッファーをフラッシュし、すべてのファイルを閉じ、プロセスを終了します。|[\<caps:sentence id\="tgt64" sentenceid\="811a70e90f150f212690505b37a46c0f" class\="tgtSentence"\>System::Diagnostics::Process::Kill\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.kill.aspx)|  
|[\_exit](../c-runtime-library/reference/exit-exit-exit.md)|`atexit` または `_onexit` を呼び出すか、バッファーがフラッシュしないでプロセスを直ちに終了します。|[\<caps:sentence id\="tgt67" sentenceid\="811a70e90f150f212690505b37a46c0f" class\="tgtSentence"\>System::Diagnostics::Process::Kill\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.kill.aspx)|  
|[getenv、バージョン](../c-runtime-library/reference/getenv-wgetenv.md)、[getenv\_s、\_wgetenv\_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)|環境変数の値を取得します。|[\<caps:sentence id\="tgt70" sentenceid\="795988b9277d74ea3b722ecd42dcb29d" class\="tgtSentence"\>System::Environment::GetEnvironmentVariable\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.getenvironmentvariable.aspx)|  
|[\_getpid](../Topic/_getpid.md)|プロセス ID 番号を取得します。|[\<caps:sentence id\="tgt73" sentenceid\="745b82c461dc74b15540e9622f7cd7bd" class\="tgtSentence"\>System::Diagnostics::Process::Id\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.id.aspx)|  
|[longjmp](../c-runtime-library/reference/longjmp.md)|保存されたスタック環境を復元してください; 非ローカルの `goto`を実行するために使用します。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_onexit](../c-runtime-library/reference/onexit-onexit-m.md)|プログラムの終了のスケジュール;ルーチン Microsoft C\/C\+\+ Version 7.0 の互換性の以前の使用|[\<caps:sentence id\="tgt81" sentenceid\="db022fa9aa2a12937c3610e3eb32e80f" class\="tgtSentence"\>System::Diagnostics::Process::Exited\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)|  
|[\_pclose](../Topic/_pclose.md)|関連するパイプの新しいコマンド プロセッサと終了ストリームを待機します。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[perror、\_wperror](../c-runtime-library/reference/perror-wperror.md)|出力エラー メッセージ|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_pipe](../c-runtime-library/reference/pipe.md)|読み取りおよび書き込み用のパイプを作成します。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_popen、\_wpopen](../c-runtime-library/reference/popen-wpopen.md)|パイプを作成し、コマンドを実行します。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_putenv、\_wputenv](../c-runtime-library/reference/putenv-wputenv.md)、[\_putenv\_s、\_wputenv\_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)|環境変数の値を追加するか、変更します。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[raise](../c-runtime-library/reference/raise.md)|呼び出しプロセスにシグナルを送信します。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[setjmp](../c-runtime-library/reference/setjmp.md)|スタック環境を格納します。; 非ローカル `goto`を実行するために使用します。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[とき](../c-runtime-library/reference/signal.md)|ハンドル割り込み場合|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_spawnl、\_wspawnl](../Topic/_spawnl,%20_wspawnl.md)|指定した引数リストで新しいプロセスを作成して実行します。|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnle、\_wspawnle](../c-runtime-library/reference/spawnle-wspawnle.md)|指定された引数の引数リストと環境で新しいプロセスを作成して実行します。|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnlp、\_wspawnlp](../c-runtime-library/reference/spawnlp-wspawnlp.md)|`PATH` の変数と指定した引数リストを使用して新しいプロセスを作成して実行します。|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnlpe、\_wspawnlpe](../Topic/_spawnlpe,%20_wspawnlpe.md)|`PATH` の変数、指定した環境と引数リストを使用して新しいプロセスを作成して実行します。|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnv、\_wspawnv](../c-runtime-library/reference/spawnv-wspawnv.md)|指定された引数の配列を持つ新しいプロセスを作成して実行します。|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnve、\_wspawnve](../c-runtime-library/reference/spawnve-wspawnve.md)|指定された環境と引数配列を持つ新しいプロセスを作成して実行します。|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnvp、\_wspawnvp](../c-runtime-library/reference/spawnvp-wspawnvp.md)|`PATH` の変数と指定された引数の配列を使用して新しいプロセスを作成して実行します。|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnvpe、\_wspawnvpe](../Topic/_spawnvpe,%20_wspawnvpe.md)|`PATH` の変数、指定した環境と引数配列を使用して新しいプロセスを作成して実行します。|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[System、\_wsystem](../c-runtime-library/reference/system-wsystem.md)|オペレーティング システム コマンドを実行します。|[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)、[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)|  
  
 Windows オペレーティング システムでは、起動されたプロセスは起動されたプロセスと同じです。  どのプロセスがプロセス ID がわかっている他のプロセスを待機するために `_cwait` を使用できます。  
  
 `_spawn` の `_exec` とファミリの違いは `_spawn` 関数が新しいプロセスから呼び出しプロセスにコントロールを返すことができます。  `_spawn` 関数では、`_P_OVERLAY` 呼び出しプロセスが指定されていない場合、新しいプロセスは、メモリにあります。  `_exec` 関数では、新しいプロセスが呼び出しプロセスに重なって表示されるため、エラーが新しいプロセスの実行を開始する試みで発生しないコントロールが呼び出しプロセスに戻ることはできません。  
  
 `_exec` ファミリの関数ごとに、`_spawn` ファミリの中の違いは、引数が新しいプロセスに渡すと、次の表に示すように環境を設定するメソッドの新しいプロセス、フォームとして実行するファイルを検索メソッドを示します。  引数の数が一定にまたはコンパイル時に判明しているときに引数リストを渡す関数を使用します。  引数の数が実行時に決定されるときに含める配列へのポインターに引数を渡す関数を使用します。  次の表の情報は、`_spawn` と `_exec` 関数のワイド文字の対応するコントロールに適用されます。  
  
### " \_spawn と\_exec 関数ファミリ  
  
|関数|ファイルは、PATH 変数を使用します。|引数渡し規約|環境設定|  
|--------|--------------------------|------------|----------|  
|`_execl, _spawnl`|No|リスト|呼び出しプロセスから継承される|  
|`_execle, _spawnle`|No|リスト|最後に、新しいプロセスの環境テーブルへのポインター引数として|  
|`_execlp, _spawnlp`|Yes|リスト|呼び出しプロセスから継承される|  
|`_execlpe, _spawnlpe`|Yes|リスト|最後に、新しいプロセスの環境テーブルへのポインター引数として|  
|`_execv, _spawnv`|No|Array|呼び出しプロセスから継承される|  
|`_execve, _spawnve`|No|Array|最後に、新しいプロセスの環境テーブルへのポインター引数として|  
|`_execvp, _spawnvp`|Yes|Array|呼び出しプロセスから継承される|  
|`_execvpe, _spawnvpe`|Yes|Array|最後に、新しいプロセスの環境テーブルへのポインター引数として|  
  
## 参照  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)