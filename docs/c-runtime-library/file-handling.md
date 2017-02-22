---
title: "ファイル処理 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.files"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ファイル [C++], 処理"
  - "ファイル [C++], 操作"
  - "ファイル [C++], 開く"
ms.assetid: 48119e2e-e94f-4602-b08b-b72440f731d8
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# ファイル処理
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ファイル処理ルーチンは、ファイルの作成、削除、操作、およびファイル アクセス許可の設定、チェックに使用します。  
  
 C ランタイム ライブラリには、同時に開くことのできるファイル数の上限が 512 に設定されています。 上限を超える数のファイル記述子またはファイル ストリームを開こうとすると、プログラム エラーが発生します。 上限のファイル数を変更するには、[\_setmaxstdio](../c-runtime-library/reference/setmaxstdio.md) を使用します。  
  
 ファイル記述子で指定されたファイルを操作するには、次のルーチンを使用します。  
  
### ファイル処理ルーチン \(ファイル記述子\)  
  
|ルーチン|用途|同等の .NET Framework 関数|  
|----------|--------|---------------------------|  
|[\_chsize](../c-runtime-library/reference/chsize.md)、[\_chsize\_s](../c-runtime-library/reference/chsize-s.md)|ファイル サイズを変更します。|[System::IO::Stream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.stream.setlength.aspx)、[System::IO::FileStream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.filestream.setlength.aspx)|  
|[\_filelength、\_filelengthi64](../c-runtime-library/reference/filelength-filelengthi64.md)|ファイル長を取得します。|[System::IO::Stream::Length](https://msdn.microsoft.com/en-us/library/system.io.stream.length.aspx)、[System::IO::FileStream::Length](https://msdn.microsoft.com/en-us/library/system.io.filestream.length.aspx)|  
|[\_fstat、\_fstat32、\_fstat64、\_fstati64、\_fstat32i64、\_fstat64i32](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)|記述子のファイル ステータス情報を取得します。|該当なし。 標準の C 関数を呼び出すには、`PInvoke` を使用します。 詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_get\_osfhandle](../c-runtime-library/reference/get-osfhandle.md)|C ランタイムの既存のファイル記述子に関連付けられたオペレーティング システムのファイル ハンドルを返します。|該当なし。 標準の C 関数を呼び出すには、`PInvoke` を使用します。 詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_isatty](../c-runtime-library/reference/isatty.md)|キャラクター デバイスをチェックします。|[System::IO::Stream::CanWrite](https://msdn.microsoft.com/en-us/library/system.io.filestream.canwrite.aspx)、[System::IO::FileStream::CanWrite](https://msdn.microsoft.com/en-us/library/system.io.stream.canwrite.aspx)|  
|[\_locking](../Topic/_locking.md)|ファイル領域をロックします。|[System::IO::FileStream::Lock](https://msdn.microsoft.com/en-us/library/system.io.filestream.lock.aspx)|  
|[\_open\_osfhandle](../c-runtime-library/reference/open-osfhandle.md)|C ランタイムのファイル記述子を既存のオペレーティング システムのファイル ハンドルに関連付けます。|[System::IO::FileStream::Handle](https://msdn.microsoft.com/en-us/library/system.io.filestream.handle.aspx)|  
|[\_setmode](../c-runtime-library/reference/setmode.md)|ファイルの変換モードを設定します。|[System::IO::BinaryReader Class](https://msdn.microsoft.com/en-us/library/system.io.binaryreader.aspx)、[System::IO::TextReader Class](https://msdn.microsoft.com/en-us/library/system.io.textreader.aspx)|  
  
 パスまたはファイル名で指定されたファイルを操作するには、次のルーチンを使用します。  
  
### ファイル処理ルーチン \(パスまたはファイル名\)  
  
|ルーチン|用途|同等の .NET Framework 関数|  
|----------|--------|---------------------------|  
|[\_access、\_waccess](../c-runtime-library/reference/access-waccess.md), [\_access\_s、\_waccess\_s](../c-runtime-library/reference/access-s-waccess-s.md)|ファイルのアクセス許可の設定をチェックします。|[System::IO::FileAccess Enumeration](https://msdn.microsoft.com/en-us/library/4z36sx0f.aspx)|  
|[\_chmod、\_wchmod](../c-runtime-library/reference/chmod-wchmod.md)|ファイルのアクセス許可の設定を変更します。|[System::IO::File::SetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.setattributes.aspx)、[System::Security::Permissions::FileIOPermission](https://msdn.microsoft.com/en-us/library/system.security.permissions.fileiopermission.aspx)|  
|[\_fullpath、\_wfullpath](../c-runtime-library/reference/fullpath-wfullpath.md)|相対パス名を絶対パス名に展開します。|[System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)|  
|[\_makepath、\_wmakepath](../c-runtime-library/reference/makepath-wmakepath.md), [\_makepath\_s、\_wmakepath\_s](../c-runtime-library/reference/makepath-s-wmakepath-s.md)|パス コンポーネントを単一の完全パスにマージします。|[System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)|  
|[\_mktemp、\_wmktemp](../c-runtime-library/reference/mktemp-wmktemp.md)、[\_mktemp\_s、\_wmktemp\_s](../c-runtime-library/reference/mktemp-s-wmktemp-s.md)|一意のファイル名を作成します。|該当なし。 標準の C 関数を呼び出すには、`PInvoke` を使用します。 詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[remove、\_wremove](../c-runtime-library/reference/remove-wremove.md)|ファイルの削除|[System::IO::File::Delete](https://msdn.microsoft.com/en-us/library/system.io.file.delete.aspx)|  
|[rename、\_wrename](../c-runtime-library/reference/rename-wrename.md)|ファイル名の変更|[System::IO::File::Move](https://msdn.microsoft.com/en-us/library/system.io.file.move.aspx)|  
|[\_splitpath、\_wsplitpath](../Topic/_splitpath,%20_wsplitpath.md)、[\_splitpath\_s、\_wsplitpath\_s](../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)|コンポーネントのパスを解析します。|該当なし。 標準の C 関数を呼び出すには、`PInvoke` を使用します。 詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_stat、\_stat64、\_stati64、\_wstat、\_wstat64、\_wstati64](../c-runtime-library/reference/stat-functions.md)|名前付きファイルのファイル ステータス情報を取得します。|[System::IO::File::GetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.getattributes.aspx)、[System::IO::File::GetCreationTime](https://msdn.microsoft.com/en-us/library/system.io.file.getcreationtime.aspx)、[System::IO::File::GetLastAccessTime](https://msdn.microsoft.com/en-us/library/system.io.file.getlastaccesstime.aspx)、[System::IO::File::GetLastWriteTime](https://msdn.microsoft.com/en-us/library/system.io.file.getlastwritetime.aspx)|  
|[\_umask](../c-runtime-library/reference/umask.md), [\_umask\_s](../Topic/_umask_s.md)|プログラムが新しく作成したファイルに、既定のアクセス許可マスクを設定します。|[System::IO::File::SetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.setattributes.aspx)|  
|[\_unlink、\_wunlink](../Topic/_unlink,%20_wunlink.md)|ファイルの削除|[System::IO::File::Delete](https://msdn.microsoft.com/en-us/library/system.io.file.delete.aspx)|  
  
 ファイルを開くには、次のルーチンを使用します。  
  
### ファイル処理ルーチン \(開いているファイル\)  
  
|ルーチン|用途|同等の .NET Framework 関数|  
|----------|--------|---------------------------|  
|[fopen、\_wfopen](../c-runtime-library/reference/fopen-wfopen.md), [fopen\_s、\_wfopen\_s](../c-runtime-library/reference/fopen-s-wfopen-s.md)|ファイルを開き、開いているファイルへのポインターを返します。|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx)、<xref:System.IO.FileStream.%23ctor%2A>|  
|[\_fsopen、\_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)|ファイル共有でストリームを開き、開いているファイルへのポインターを返します。|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx)、<xref:System.IO.FileStream.%23ctor%2A>|  
|[\_open、\_wopen](../c-runtime-library/reference/open-wopen.md)|ファイルを開き、開いているファイルへのファイル記述子を返します。|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx)、<xref:System.IO.FileStream.%23ctor%2A>|  
|[\_sopen、\_wsopen](../c-runtime-library/reference/sopen-wsopen.md), [\_sopen\_s、\_wsopen\_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|ファイル共有でファイルを開き、開いているファイルへのファイル記述子を返します。||  
|[\_pipe](../c-runtime-library/reference/pipe.md)|読み取りおよび書き込み用のパイプを作成します。|該当なし。 標準の C 関数を呼び出すには、`PInvoke` を使用します。 詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[freopen、\_wfreopen](../c-runtime-library/reference/freopen-wfreopen.md), [freopen\_s、\_wfreopen\_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md)|ファイル ポインターを再度割り当てます。|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx)、<xref:System.IO.FileStream.%23ctor%2A>|  
  
 次の関数を使用すると、`FILE` 構造体、ファイル記述子、および Win32 ファイル ハンドル間でファイルの表示を変更できます。  
  
||||  
|-|-|-|  
|[\_fdopen、\_wfdopen](../Topic/_fdopen,%20_wfdopen.md)|ストリームを前回下位入出力で開いたファイルに関連付け、オープン ストリームへのポインターを返します。|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.filestream.aspx)|  
|[\_fileno](../Topic/_fileno.md)|ストリームに関連付けられているファイル記述子を取得します。|[System::IO::FileStream::Handle](https://msdn.microsoft.com/en-us/library/system.io.filestream.handle.aspx)|  
|[\_get\_osfhandle](../c-runtime-library/reference/get-osfhandle.md)|C ランタイムの既存のファイル記述子に関連付けられたオペレーティング システムのファイル ハンドルを返します。|該当なし。 標準の C 関数を呼び出すには、`PInvoke` を使用します。 詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_open\_osfhandle](../c-runtime-library/reference/open-osfhandle.md)|C ランタイム ファイル記述子を既存のオペレーティング システムのファイル ハンドルに関連付けます。|[System::IO::FileStream::Handle](https://msdn.microsoft.com/en-us/library/system.io.filestream.handle.aspx)|  
  
 ファイルおよびパイプは、次の Win32 関数でも開くことができます。  
  
-   [CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858.aspx)  
  
-   [CreatePipe](http://msdn.microsoft.com/library/windows/desktop/aa365152.aspx)  
  
-   [CreateNamedPipe](http://msdn.microsoft.com/library/windows/desktop/aa365150.aspx)  
  
## 参照  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)   
 [ディレクトリ制御](../c-runtime-library/directory-control.md)   
 [システム コール](../Topic/System%20Calls.md)