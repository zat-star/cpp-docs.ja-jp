---
title: "_cexit、_c_exit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_c_exit"
  - "_cexit"
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
  - "_cexit"
  - "c_exit"
  - "_c_exit"
  - "cexit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_c_exit 関数"
  - "_cexit 関数"
  - "c_exit 関数"
  - "cexit 関数"
  - "クリーンアップ操作 (処理時の)"
ms.assetid: f3072045-9924-4b1a-9fef-b0dcd6d12663
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _cexit、_c_exit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロセスを終えないでクリーンアップ アクションと制御を実行します。  
  
## 構文  
  
```  
void _cexit( void );  
void _c_exit( void );  
```  
  
## 解説  
 `_cexit` 関数呼び出し、最後の \(LIFO\)、最初の順序、`atexit` で登録する関数と `_onexit`。  次 `_cexit` はすべての I\/O バッファーをフラッシュし、戻る前にすべてのオープン ストリームを閉じます。  `_c_exit` は `_exit` が呼び出しプロセスに戻ると `atexit` または `_onexit` を処理するか、ストリーム バッファーをフラッシュせずに同じです。  `exit`、`_exit`、`_cexit`と `_c_exit` の動作を次の表に示します。  
  
|関数|動作|  
|--------|--------|  
|`exit`|完全な C ライブラリの完了ステップを実行し、プロセスが終了し、指定されたステータス コードが表示されます。|  
|`_exit`|高速 C ライブラリの完了ステップを実行し、プロセスが終了し、指定されたステータス コードが表示されます。|  
|`_cexit`|呼び出し元に C ライブラリの終了手順および戻り値が実行され、プロセスが終了することはありません。|  
|`_c_exit`|呼び出し元に対するすばやい C ライブラリの終了手順および戻り値が実行され、プロセスが終了することはありません。|  
  
 呼び出すと呼び出し時のある一時または自動オブジェクトの `_cexit` または `_c_exit` 関数、デストラクターは呼び出されません。  自動オブジェクトは静的で宣言されていない関数で定義されているオブジェクトです。  一時オブジェクトはコンパイラによって作成されるオブジェクトです。  `_cexit` または `_c_exit`を呼び出す前に、オブジェクトを破棄するには、次のように、明示的にオブジェクトのデストラクターを呼び出します。:  
  
```  
myObject.myClass::~myClass( );  
```  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_cexit`|\<process.h\>|  
|`_c_exit`|\<process.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 [System::Diagnostics::Process::CloseMainWindow](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.closemainwindow.aspx)  
  
## 参照  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [\_exec、\_wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)   
 [終了、\_Exit、\_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_onexit、\_onexit\_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [\_spawn 系関数と \_wspawn 系関数](../Topic/_spawn,%20_wspawn%20Functions.md)   
 [system、\_wsystem](../../c-runtime-library/reference/system-wsystem.md)