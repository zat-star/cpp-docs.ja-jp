---
title: "プロセス制御と環境制御 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.programs
dev_langs:
- C++
helpviewer_keywords:
- processes, stopping
- processes, administrative tasks
- parent process
- processes, starting
- environment control routines
- process control routines
ms.assetid: 7fde74c3-c2a6-4d15-84b8-092160d60c3e
caps.latest.revision: 9
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: d5198dcef7d24d2755c21b90802b19e809c5b8da
ms.lasthandoff: 02/24/2017

---
# <a name="process-and-environment-control"></a>プロセス制御と環境制御
プログラム内からプロセスを開始、停止、および管理するには、プロセス制御ルーチンを使用します。 オペレーティング システム環境に関する情報を取得および変更するには、環境制御ルーチンを使用します。  
  
### <a name="process-and-environment-control-functions"></a>プロセス制御と環境制御の関数  
  
|ルーチン|用途|同等の .NET Framework 関数|  
|-------------|---------|-------------------------------|  
|[abort](../c-runtime-library/reference/abort.md)|バッファーをフラッシュしたり、`atexit` および `_onexit` によって登録された関数を呼び出したりせずにプロセスを中止する|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[assert](../c-runtime-library/reference/assert-macro-assert-wassert.md)|論理エラーのテスト|[System::Diagnostics::Debug::Assert](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[_ASSERT マクロ、_ASSERTE マクロ](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|`assert` に類似。ただしランタイム ライブラリのデバッグ バージョンでのみ使用できる|[System::Diagnostics::Debug::Assert](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[atexit](../c-runtime-library/reference/atexit.md)|プログラムの終了時に実行されるルーチンをスケジュールする|[System::Diagnostics::Process::Exited](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)|  
|[_beginthread、_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)|Windows オペレーティング システムのプロセスで新しいスレッドを作成する|[System::Threading::Thread::Start](https://msdn.microsoft.com/en-us/library/system.threading.thread.start.aspx)|  
|[_cexit](../c-runtime-library/reference/cexit-c-exit.md)|`exit` の終了処理 (バッファーのフラッシュなど) を実行し、プロセスを終了せずに呼び出し元のプログラムに制御を戻す|[System::Diagnostics::Process::CloseMainWindow](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.closemainwindow.aspx)|  
|[_c_exit](../c-runtime-library/reference/cexit-c-exit.md)|`_exit` の終了処理を実行し、プロセスを終了せずに呼び出し元のプログラムに制御を戻す|[System::Diagnostics::Process::CloseMainWindow](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.closemainwindow.aspx)|  
|[_cwait](../c-runtime-library/reference/cwait.md)|他のプロセスが終了するまで待機する|[System::Diagnostics::Process::WaitForExit](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.waitforexit.aspx)|  
|[_endthread、_endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)|Windows オペレーティング システムのスレッドを終了する|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[_execl、_wexecl](../c-runtime-library/reference/execl-wexecl.md)|引数リストを含む新しいプロセスを実行する|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execle、_wexecle](../c-runtime-library/reference/execle-wexecle.md)|引数リストおよび指定された環境を含む新しいプロセスを実行する|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execlp、_wexeclp](../c-runtime-library/reference/execlp-wexeclp.md)|`PATH` 変数および引数リストを使用して新しいプロセスを実行する|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execlpe、_wexeclpe](../c-runtime-library/reference/execlpe-wexeclpe.md)|`PATH` 変数、指定された環境、および引数リストを使用して新しいプロセスを実行する|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execv、_wexecv](../c-runtime-library/reference/execv-wexecv.md)|引数配列を含む新しいプロセスを実行する|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execve、_wexecve](../c-runtime-library/reference/execve-wexecve.md)|引数配列および指定された環境を含む新しいプロセスを実行する|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execvp、_wexecvp](../c-runtime-library/reference/execvp-wexecvp.md)|`PATH` 変数および引数配列を使用して新しいプロセスを実行する|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execvpe、_wexecvpe](../c-runtime-library/reference/execvpe-wexecvpe.md)|`PATH` 変数、指定された環境、および引数配列を使用して新しいプロセスを実行する|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[exit](../c-runtime-library/reference/exit-exit-exit.md)|`atexit` および `_onexit` によって登録された関数の呼び出し、すべてのバッファーのフラッシュ、開いているすべてのファイルを閉じ、プロセスの終了を行う|[System::Diagnostics::Process::Kill](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.kill.aspx)|  
|[_exit](../c-runtime-library/reference/exit-exit-exit.md)|`atexit` または `_onexit` の呼び出し、またはバッファーのフラッシュを行わずに直ちにプロセスを終了する|[System::Diagnostics::Process::Kill](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.kill.aspx)|  
|[getenv、_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)、[getenv_s、_wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)|環境変数の値を取得する|[System::Environment::GetEnvironmentVariable](https://msdn.microsoft.com/en-us/library/system.environment.getenvironmentvariable.aspx)|  
|[_getpid](../c-runtime-library/reference/getpid.md)|プロセス ID 番号を取得する|[System::Diagnostics::Process::Id](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.id.aspx)|  
|[longjmp](../c-runtime-library/reference/longjmp.md)|保存したスタック環境を復元し、これを非ローカルの `goto` の実行に使用する|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[_onexit](../c-runtime-library/reference/onexit-onexit-m.md)|プログラムの終了時に実行されるルーチンをスケジュールする (Microsoft C/C++ version 7.0 以前のバージョンとの互換性のために使用)|[System::Diagnostics::Process::Exited](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)|  
|[_pclose](../c-runtime-library/reference/pclose.md)|新しいコマンド プロセッサを待機し、関連するパイプのストリームを閉じる|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[perror、_wperror](../c-runtime-library/reference/perror-wperror.md)|エラー メッセージを出力する|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[_pipe](../c-runtime-library/reference/pipe.md)|読み取りおよび書き込み用のパイプを作成する|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[_popen、_wpopen](../c-runtime-library/reference/popen-wpopen.md)|パイプを作成し、コマンドを実行する|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[_putenv、_wputenv](../c-runtime-library/reference/putenv-wputenv.md)、[_putenv_s、_wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)|環境変数の値を追加または変更する|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[raise](../c-runtime-library/reference/raise.md)|呼び出し元のプロセスにシグナルを送る|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[setjmp](../c-runtime-library/reference/setjmp.md)|スタック環境を保存し、非ローカルの `goto` の実行に使用する|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[signal](../c-runtime-library/reference/signal.md)|割り込みシグナルを処理する|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[_spawnl、_wspawnl](../c-runtime-library/reference/spawnl-wspawnl.md)|指定した引数リストを含む新しいプロセスを作成して実行する|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnle、_wspawnle](../c-runtime-library/reference/spawnle-wspawnle.md)|指定した引数リストおよび環境を含む新しいプロセスを作成して実行する|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnlp、_wspawnlp](../c-runtime-library/reference/spawnlp-wspawnlp.md)|`PATH` 変数および指定した引数リストを含む新しいプロセスを作成して実行する|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnlpe、_wspawnlpe](../c-runtime-library/reference/spawnlpe-wspawnlpe.md)|`PATH` 変数、指定した環境および引数リストを含む新しいプロセスを作成して実行する|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnv、_wspawnv](../c-runtime-library/reference/spawnv-wspawnv.md)|指定した引数配列を含む新しいプロセスを作成して実行する|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnve、_wspawnve](../c-runtime-library/reference/spawnve-wspawnve.md)|指定した環境および引数配列を含む新しいプロセスを作成して実行する|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnvp、_wspawnvp](../c-runtime-library/reference/spawnvp-wspawnvp.md)|`PATH` 変数および指定した引数配列を含む新しいプロセスを作成して実行する|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnvpe、_wspawnvpe](../c-runtime-library/reference/spawnvpe-wspawnvpe.md)|`PATH` 変数、指定した環境および引数配列を含む新しいプロセスを作成して実行する|[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)、[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[system、_wsystem](../c-runtime-library/reference/system-wsystem.md)|オペレーティング システム コマンドを実行する|[System::Diagnostics::ProcessStartInfo クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)、[System::Diagnostics::Process クラス](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)|  
  
 Windows オペレーティング システムでは、起動されたプロセスは、起動元のプロセスと同じです。 どのプロセスでも、`_cwait` を使用してプロセス ID がわかっている、他のすべてのプロセスを待機することができます。  
  
 `_exec` ファミリと `_spawn` ファミリの違いは、`_spawn` 関数の場合、新しいプロセスから呼び出し元のプロセスにコントロールを戻すことができることです。 `_spawn` 関数では、`_P_OVERLAY` が指定されていなければ、呼び出し元のプロセスも新しいプロセスもメモリに存在します。 `_exec` 関数では、新しいプロセスによって呼び出し元のプロセスがオーバーレイされるため、新しいプロセスの実行の開始時にエラーが発生しても、呼び出し元のプロセスに制御が戻りません。  
  
 `_exec` ファミリのそれぞれの関数は、`_spawn` ファミリの場合と同様、下記の表に示すように、新しいプロセスとして実行されるファイルの検索方法、引数を新しいプロセスに渡す際の形式、そして環境の設定方法などが異なります。 引数の数が定数の場合、またはコンパイル時に認識される場合は、引数リストを渡す関数を使用します。 引数の数が実行時に決定される場合は、引数が含まれる配列にポインターを渡す関数を使用します。 次の表の情報は、`_spawn` および `_exec` 関数のワイド文字バージョンにも適用されます。  
  
### <a name="spawn-and-exec-function-families"></a>_spawn と _exec の関数ファミリ  
  
|関数|PATH 変数を使用してファイルを検索する|引数渡し規約|環境設定|  
|---------------|--------------------------------------|----------------------------------|--------------------------|  
|`_execl, _spawnl`|いいえ|リスト|呼び出し元プロセスから継承|  
|`_execle, _spawnle`|いいえ|リスト|最後の引数として渡された新しいプロセスの環境のテーブルへのポインター|  
|`_execlp, _spawnlp`|はい|リスト|呼び出し元プロセスから継承|  
|`_execlpe, _spawnlpe`|はい|リスト|最後の引数として渡された新しいプロセスの環境のテーブルへのポインター|  
|`_execv, _spawnv`|いいえ|配列|呼び出し元プロセスから継承|  
|`_execve, _spawnve`|いいえ|配列|最後の引数として渡された新しいプロセスの環境のテーブルへのポインター|  
|`_execvp, _spawnvp`|はい|配列|呼び出し元プロセスから継承|  
|`_execvpe, _spawnvpe`|はい|配列|最後の引数として渡された新しいプロセスの環境のテーブルへのポインター|  
  
## <a name="see-also"></a>関連項目  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)
