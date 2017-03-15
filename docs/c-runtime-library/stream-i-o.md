---
title: "ストリーム入出力 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.io
dev_langs:
- C++
helpviewer_keywords:
- I/O routines, stream I/O
- I/O [CRT], stream
- stream I/O
ms.assetid: dc7874d3-a91b-456a-9015-4748bb358217
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: a112925692e175005b3ff2885192298c73c0e433
ms.lasthandoff: 02/24/2017

---
# <a name="stream-io"></a>ストリーム入出力
これらの関数は、1 文字から大きなデータ構造に至るまで、さまざまなサイズと形式のデータを処理します。 バッファリングも提供しており、パフォーマンスを向上させることができます。 ストリーム バッファーの既定のサイズは 4K です。 これらのルーチンは、ランタイム ライブラリ ルーチンによって作成されるバッファーにのみ影響し、オペレーティング システムによって作成されるバッファーには影響しません。  
  
### <a name="stream-io-routines"></a>ストリーム入出力ルーチン  
  
|ルーチン|用途|同等の .NET Framework 関数|  
|-------------|---------|-------------------------------|  
|[clearerr](../c-runtime-library/reference/clearerr.md)、[clearerr_s](../c-runtime-library/reference/clearerr-s.md)|ストリームのクリア エラー インジケーター|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[fclose](../c-runtime-library/reference/fclose-fcloseall.md)|ストリームを閉じる|[System::IO::Stream::Close](https://msdn.microsoft.com/en-us/library/system.io.stream.close.aspx)、 [System::IO::BinaryReader::Close](https://msdn.microsoft.com/en-us/library/system.io.binaryreader.close.aspx)、 [System::IO::BinaryWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.binarywriter.close.aspx)、 [System::IO::TextReader::Close](https://msdn.microsoft.com/en-us/library/system.io.textreader.close.aspx)、 [System::IO::TextWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.textwriter.close.aspx)、 [System::IO::StringReader::Close](https://msdn.microsoft.com/en-us/library/system.io.stringreader.close.aspx)、 [System::IO::StringWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.stringwriter.close.aspx)、 [System::IO::StreamReader::Close](https://msdn.microsoft.com/en-us/library/system.io.streamreader.close.aspx)、 [System::IO::StreamWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.close.aspx)|  
|[_fcloseall](../c-runtime-library/reference/fclose-fcloseall.md)|`stdin`、`stdout`、および `stderr` を除く、開いているすべてのストリームを閉じる|[System::IO::Stream::Close](https://msdn.microsoft.com/en-us/library/system.io.stream.close.aspx)、 [System::IO::BinaryReader::Close](https://msdn.microsoft.com/en-us/library/system.io.binaryreader.close.aspx)、 [System::IO::BinaryWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.binarywriter.close.aspx)、 [System::IO::TextReader::Close](https://msdn.microsoft.com/en-us/library/system.io.textreader.close.aspx)、 [System::IO::TextWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.textwriter.close.aspx)、 [System::IO::StringReader::Close](https://msdn.microsoft.com/en-us/library/system.io.stringreader.close.aspx)、 [System::IO::StringWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.stringwriter.close.aspx)、 [System::IO::StreamReader::Close](https://msdn.microsoft.com/en-us/library/system.io.streamreader.close.aspx)、 [System::IO::StreamWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.close.aspx)|  
|[_fdopen、wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)|開いているファイルのファイル記述子にストリームを関連付ける|<xref:System.IO.FileStream.%23ctor%2A>|  
|[feof](../c-runtime-library/reference/feof.md)|ストリームのファイルの終わりをテストする|[System::IO::FileStream::Read](https://msdn.microsoft.com/en-us/library/system.io.filestream.read.aspx)|  
|[ferror](../c-runtime-library/reference/ferror.md)|ストリームのエラーをテストする|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[fflush](../c-runtime-library/reference/fflush.md)|ストリームをバッファーまたはストレージ デバイスにフラッシュする|[System::IO::FileStream::Flush](https://msdn.microsoft.com/en-us/library/2bw4h516.aspx)|  
|[fgetc、fgetwc](../c-runtime-library/reference/fgetc-fgetwc.md)|ストリームから文字を読み取る ( `getc` および `getwc`の関数バージョン)|[System::IO::StreamReader::Read](https://msdn.microsoft.com/en-us/library/system.io.streamreader.read.aspx)|  
|[_fgetchar、_fgetwchar](../c-runtime-library/reference/fgetc-fgetwc.md)|`stdin` から文字を読み取る ( `getchar` および `getwchar`の関数バージョン)|[System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)|  
|[fgetpos](../c-runtime-library/reference/fgetpos.md)|ストリームの位置インジケーターを取得する|[System::IO::FileStream::Position](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)|  
|[fgets、fgetws](../c-runtime-library/reference/fgets-fgetws.md)|文字列をストリームから読み取る|[System::IO::StreamReader::ReadLine](https://msdn.microsoft.com/en-us/library/system.io.streamreader.readline.aspx)、 [System::IO::TextReader::ReadBlock](https://msdn.microsoft.com/en-us/library/system.io.textreader.readblock.aspx)|  
|[_fileno](../c-runtime-library/reference/fileno.md)|ストリームに関連付けられているファイル記述子を取得する|[System::IO::FileStream::Handle](https://msdn.microsoft.com/en-us/library/system.io.filestream.handle.aspx)|  
|[_flushall](../c-runtime-library/reference/flushall.md)|すべてのストリームをバッファーまたはストレージ デバイスにフラッシュする|[System::IO::FileStream::Flush](https://msdn.microsoft.com/en-us/library/2bw4h516.aspx)、 [System::IO::StreamWriter::Flush](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.flush.aspx)、 [System::IO::TextWriter::Flush](https://msdn.microsoft.com/en-us/library/system.io.textwriter.flush.aspx)、 [System::IO::BinaryWriter::Flush](https://msdn.microsoft.com/en-us/library/system.io.binarywriter.flush.aspx)|  
|[fopen、_wfopen](../c-runtime-library/reference/fopen-wfopen.md)、[fopen_s、_wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md)|ストリームを開く|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx)|  
|[fprintf、_fprintf_l、fwprintf、_fwprintf_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)、[fprintf_s、_fprintf_s_l、fwprintf_s、_fwprintf_s_l](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|ストリームに書式付きデータを書き込む|[System::IO::StreamWriter::Write](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.write.aspx)|  
|[fputc、fputwc](../c-runtime-library/reference/fputc-fputwc.md)|ストリームに文字を書き込む ( `putc` および `putwc`の関数バージョン)|[System::IO::StreamWriter::Write](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.write.aspx)|  
|[_fputchar、_fputwchar](../c-runtime-library/reference/fputc-fputwc.md)|`stdout` に文字を書き込む ( `putchar` および `putwchar`の関数バージョン)|[System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)|  
|[fputs、fputws](../c-runtime-library/reference/fputs-fputws.md)|文字列をストリームに書き込む|[System::IO::StreamWriter::Write](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.write.aspx)|  
|[fread](../c-runtime-library/reference/fread.md)|書式設定されていないデータをストリームから読み取る|[System::IO::FileStream::Read](https://msdn.microsoft.com/en-us/library/system.io.filestream.read.aspx)|  
|[freopen、_wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)、[freopen_s、_wfreopen_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md)|`FILE` ストリーム ポインターを新しいファイルまたはデバイスに再割り当てする|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx)|  
|[fscanf、fwscanf](../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)、[fscanf_s、_fscanf_s_l、fwscanf_s、_fwscanf_s_l](../c-runtime-library/reference/fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)|書式付きデータをストリームから読み取る|[System::IO::StreamReader::ReadLine](https://msdn.microsoft.com/en-us/library/system.io.streamreader.readline.aspx)。 `Parse` System::Double::Parse [などの](https://msdn.microsoft.com/en-us/library/system.double.parse.aspx)メソッドも参照してください。|  
|[fseek、_fseeki64](../c-runtime-library/reference/fseek-fseeki64.md)|ファイルの位置を指定の場所に移動する|[System::IO::FileStream::Position](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)、 [System::IO::FileStream::Seek](https://msdn.microsoft.com/en-us/library/system.io.filestream.seek.aspx)|  
|[fsetpos](../c-runtime-library/reference/fsetpos.md)|ストリームの位置インジケーターを設定する|[System::IO::FileStream::Position](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)|  
|[_fsopen、_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)|ファイル共有付きでストリームを開く|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[ftell、_ftelli64](../c-runtime-library/reference/ftell-ftelli64.md)|現在のファイルの位置を取得する|[System::IO::FileStream::Position](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)|  
|[fwrite](../c-runtime-library/reference/fwrite.md)|書式設定されていないデータの項目をストリームに書き込む|[System::IO::FileStream::Write](https://msdn.microsoft.com/en-us/library/system.io.filestream.write.aspx)|  
|[getc、getwc](../c-runtime-library/reference/getc-getwc.md)|ストリームから文字を読み取る ( `fgetc` および `fgetwc`のマクロ バージョン)|[System::IO::StreamReader::Read](https://msdn.microsoft.com/en-us/library/system.io.streamreader.read.aspx)|  
|[getchar、getwchar](../c-runtime-library/reference/getc-getwc.md)|`stdin` から文字を読み取る ( `fgetchar` および `fgetwchar`のマクロ バージョン)|[System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)|  
|[_getmaxstdio](../c-runtime-library/reference/getmaxstdio.md)|ストリーム入出力のレベルで許可されている、同時に開かれたファイルの数を返します。|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[gets_s、_getws_s](../c-runtime-library/reference/gets-s-getws-s.md)|`stdin` から行を読み取る|[System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)|  
|[_getw](../c-runtime-library/reference/getw.md)|ストリームからバイナリ `int` を読み取る|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[printf、_printf_l、wprintf、_wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)、[printf_s、_printf_s_l、wprintf_s、_wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|`stdout` に書式付きデータを書き込む|[System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)|  
|[putc、putwc](../c-runtime-library/reference/putc-putwc.md)|ストリームに文字を書き込む ( `fputc` および `fputwc`のマクロ バージョン)|[System::IO::StreamWriter::Write](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.write.aspx)|  
|[putchar、putwchar](../c-runtime-library/reference/putc-putwc.md)|`stdout` に文字を書き込む ( `fputchar` および `fputwchar`のマクロ バージョン)|[System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)|  
|[puts、_putws](../c-runtime-library/reference/puts-putws.md)|ストリームに行を書き込む|[System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)|  
|[_putw](../c-runtime-library/reference/putw.md)|ストリームにバイナリ `int` を書き込む|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[rewind](../c-runtime-library/reference/rewind.md)|ファイルの位置をストリームの先頭に移動する|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[_rmtmp](../c-runtime-library/reference/rmtmp.md)|`tmpfile` によって作成された一時ファイルを削除する|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[scanf、_scanf_l、wscanf、_wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)、[scanf_s、_scanf_s_l、wscanf_s、_wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)|`stdin` から書式付きデータを読み取る|[System::Console::ReadLine](https://msdn.microsoft.com/en-us/library/system.console.readline.aspx)。 `Parse` System::Double::Parse [などの](https://msdn.microsoft.com/en-us/library/system.double.parse.aspx)メソッドも参照してください。|  
|[setbuf](../c-runtime-library/reference/setbuf.md)|ストリーム バッファリングを制御する|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[_setmaxstdio](../c-runtime-library/reference/setmaxstdio.md)|ストリーム入出力のレベルで同時に開かれるファイルの数の最大値を設定する。|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[setvbuf](../c-runtime-library/reference/setvbuf.md)|ストリーム バッファリングとバッファー サイズを制御する|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[_snprintf、_snwprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)、[_snprintf_s、_snprintf_s_l、_snwprintf_s、_snwprintf_s_l](../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)|指定された長さの書式付きデータを文字列に書き込む|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[_snscanf、_snwscanf](../c-runtime-library/reference/snscanf-snscanf-l-snwscanf-snwscanf-l.md)、[_snscanf_s、_snscanf_s_l、_snwscanf_s、_snwscanf_s_l](../c-runtime-library/reference/snscanf-s-snscanf-s-l-snwscanf-s-snwscanf-s-l.md)|指定した長さの書式付きデータを標準入力ストリームから読み取ります。|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[sprintf、swprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)、[sprintf_s、_sprintf_s_l、swprintf_s、_swprintf_s_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|文字列に書式付きデータを書き込む|[System::String::Format](https://msdn.microsoft.com/en-us/library/system.string.format.aspx)|  
|[sscanf、swscanf](../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)、[sscanf_s、_sscanf_s_l、swscanf_s、_swscanf_s_l](../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)|文字列から書式付きデータを読み取る|`Parse` などの [などの](https://msdn.microsoft.com/en-us/library/system.double.parse.aspx)メソッドを参照してください。|  
|[_tempnam、_wtempnam](../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|指定されたディレクトリに一時ファイル名を生成する|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[tmpfile](../c-runtime-library/reference/tmpfile.md)、[tmpfile_s](../c-runtime-library/reference/tmpfile-s.md)|一時ファイルを作成する|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[tmpnam、_wtmpnam](../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)、[tmpnam_s、_wtmpnam_s](../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md)|一時ファイル名を生成する|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[ungetc、ungetwc](../c-runtime-library/reference/ungetc-ungetwc.md)|文字をストリームにプッシュし直す|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[_vcprintf、_vcwprintf](../c-runtime-library/reference/vcprintf-vcprintf-l-vcwprintf-vcwprintf-l.md)、[_vcprintf_s、_vcprintf_s_l、_vcwprintf_s、_vcwprintf_s_l](../c-runtime-library/reference/vcprintf-s-vcprintf-s-l-vcwprintf-s-vcwprintf-s-l.md)|コンソールに書式付きデータを書き込む。|[System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)|  
|[vfprintf、vfwprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)、[vfprintf_s、_vfprintf_s_l、vfwprintf_s、_vfwprintf_s_l](../c-runtime-library/reference/vfprintf-s-vfprintf-s-l-vfwprintf-s-vfwprintf-s-l.md)|ストリームに書式付きデータを書き込む|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[vprintf、vwprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)、[vprintf_s、_vprintf_s_l、vwprintf_s、_vwprintf_s_l](../c-runtime-library/reference/vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md)|`stdout` に書式付きデータを書き込む|[System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)|  
|[_vsnprintf、_vsnwprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md)、[vsnprintf_s、_vsnprintf_s、_vsnprintf_s_l、_vsnwprintf_s、_vsnwprintf_s_l](../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)|指定された長さの書式付きデータをバッファーに書き込む|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[vsprintf、vswprintf](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)、[vsprintf_s、_vsprintf_s_l、vswprintf_s、_vswprintf_s_l](../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)|バッファーに書式付きデータを書き込む|[System::String::Format](https://msdn.microsoft.com/en-us/library/system.string.format.aspx)|  
  
 プログラムの実行を開始すると、スタートアップ コードは自動的に複数のストリームを開きます。すなわち、標準入力 ( `stdin`が指す)、標準出力 ( `stdout`が指す)、および標準エラー ( `stderr`が指す) です。 これらのストリームは既定でコンソール (キーボードと画面) に送られます。 ディスク ファイルまたはデバイスに `freopen` 、 `stdin`、または `stdout`をリダイレクトするには `stderr` を使用します。  
  
 ストリーム ルーチンを使用して開くファイルは、既定でバッファリングされます。 いっぱいになった場合、またはキャラクター デバイスに書き込みを行う場合、各ライブラリ呼び出しの後に `stdout` および `stderr` の関数はフラッシュされます。 プログラムが異常に終了した場合、出力バッファーがフラッシュされず、データが失われる可能性があります。 `fflush` または `_flushall` を使用して、特定のファイルに関連付けられているバッファー、または開いているすべてのバッファーが必ずオペレーティング システムにフラッシュされるようにします。データをディスクに書き込む前に、オペレーティング システムはデータをキャッシュすることができます。 ディスクへのコミットの機能により、フラッシュされるバッファーの内容がシステム障害時に失われないようにすることができます。  
  
 バッファーの内容をディスクにコミットする&2; つの方法があります。  
  
-   ファイル COMMODE.OBJ とリンクして、グローバル コミット フラグを設定します。 グローバル フラグの既定の設定は、 `n`("コミットなし") です。  
  
-   モード フラグを `c` または `fopen` で `_fdopen`に設定します。  
  
 `c` または `n` フラグで開かれるファイルは、グローバル コミット/コミットなしのフラグの状態にかかわらず、フラグに従って動作します。  
  
 プログラムが明示的にストリームを閉じない場合、ストリームはプログラムが終了するときに自動的に閉じます。 ただし、一度に開くことのできるストリームの数は限られているため、プログラムがストリームの作業を終了したら、そのストリームを閉じる必要があります。 この制限については、「[_setmaxstdio](../c-runtime-library/reference/setmaxstdio.md)」を参照してください。  
  
 出力の直後に入力を行うには、 `fflush` またはファイル ポジショニング関数 (`fseek`、 `fsetpos`、または `rewind`) の呼び出しを間に挟まなければなりません。 入力操作がファイルの末尾に達した場合、ファイル ポジショニング関数の呼び出しを間に挟まなくても、入力の直後に出力を行うことができます。  
  
## <a name="see-also"></a>関連項目  
 [入出力](../c-runtime-library/input-and-output.md)   
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)
