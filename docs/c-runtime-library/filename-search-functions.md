---
title: "ファイル名検索関数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr100.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
apitype: "DLLExport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ファイル名 [C++]、検索"
  - "_find 関数"
  - "wfind 関数"
  - "find 関数"
  - "_wfind 関数"
ms.assetid: 2bc2f8ef-44e4-4271-b3e8-666d36fde828
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# ファイル名検索関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

これらの関数は指定されたファイル名を検索し、検索を閉じます:  
  
-   [\_findnext、\_wfindnext](../Topic/_findnext,%20_findnext32,%20_findnext32i64,%20_findnext64,%20_findnext64i32,%20_findnexti64,%20_wfindnext,%20_wfindnext32,%20_wfindnext32i64,%20_wfindnext64,%20_wfindnext64i32,%20_wfindnexti64.md)  
  
-   [\_findfirst、\_wfindfirst](../Topic/_findfirst,%20_findfirst32,%20_findfirst32i64,%20_findfirst64,%20_findfirst64i32,%20_findfirsti64,%20_wfindfirst,%20_wfindfirst32,%20_wfindfirst32i64,%20_wfindfirst64,%20_wfindfirst64i32,%20_wfindfirsti64.md)  
  
-   [\_findclose](../c-runtime-library/reference/findclose.md)  
  
## 解説  
 `_findfirst` 関数は `filespec` 引数で指定されたファイルと一致するファイル名の最初のインスタンスに関する情報を提供します。`filespec` では、ホスト オペレーティング システムでサポートされているいかなるワイルドカード文字の組み合わせも使用できます。  
  
 これらの関数は IO.h で定義されている \_`finddata_t` 構造体でファイル情報を返します。 ファミリーの様々な関数は多くのバリエーションを `_finddata_t` 構造体で使用します。 基本的な `_finddata_t` 構造体には、次の要素が含まれています:  
  
 `unsigned attrib`  
 ファイル属性。  
  
 `time_t time_create`  
 ファイルの作成時刻 \(FAT ファイル システムの場合は –1L\)。 この時刻は UTC 形式で保存されます。 現地時刻に変換する場合は [localtime\_s](../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md) を使用します。  
  
 `time_t time_access`  
 ファイルの最後のアクセス時刻 \(FAT ファイル システムの場合は –1L\)。 この時刻は UTC 形式で保存されます。 現地時刻に変換する場合は `localtime_s` を使用します。  
  
 `time_t time_write`  
 ファイルの最終書き込み時刻。 この時刻は UTC 形式で保存されます。 現地時刻に変換する場合は `localtime_s` を使用します。  
  
 `_fsize_t size`  
 ファイルの長さ \(バイト単位\)。  
  
 `char name`\[ `_MAX_PATH`\]  
 パスのない、一致するファイルの null で終わる名前またはディレクトリ。  
  
 FAT システムなど、ファイルの作成と最終アクセス時刻をサポートしていないファイル システムでは、`time_create`  と `time_access`  フィールドは常に –1L です。  
  
 `_MAX_PATH`  は Stdli.h で 260 バイトと定義されます。  
  
 ターゲットの属性 \(`_A_RDONLY` など\) を指定して検索操作を制限することはできません。 これらの属性は `_finddata_t`  構造の `attrib` のフィールドに返され、次の値 \(IO.h で定義されている\) を持つことができます。 ユーザーは `attrib` フィールドに可能な値がこれらだけであると想定すべきではありません。  
  
 `_A_ARCH`  
 アーカイブ。**BACKUP** コマンドによってファイルが変更またはクリアされる度に設定されます。 値: 0x20。  
  
 `_A_HIDDEN`  
 隠しファイル。 一般に **\/AH** オプションを使用しない限り、DIR コマンドで見ることはできません。 この属性を持つファイルと通常のファイルに関する情報を返します。 値: 0x02。  
  
 `_A_NORMAL`  
 標準。 ファイルにその他の属性は設定されておらず、制限なく読み取りや書き込みができます。 値: 0x00。  
  
 `_A_RDONLY`  
 読み取り専用です。 書き込み用にファイルを開くことや、同じ名前を持つファイルを作成することはできません。 値: 0x01。  
  
 `_A_SUBDIR`  
 サブディレクトリ。 値: 0x10。  
  
 `_A_SYSTEM`  
 システム ファイル。**\/A** または **\/A:S** オプションを使用しない限り、通常は **DIR** コマンドでは見られません。 値: 0x04。  
  
 `_findnext` は、前回の `_findfirst` への呼び出しで指定された `filespec` 引数に一致する次の名前を検索します。`fileinfo` 引数は、`_findfirst` への前の呼び出しによって初期化された構造体を指す必要があります。 一致が見つかった場合、`fileinfo` 構造体の内容が前述のように変更されます。 それ以外の場合は、変更されません。`_findclose` は指定した検索のハンドルを終了し、`_findfirst` と `_findnext` の両方に関連付けられているすべてのリソースを解放します。`_findfirst` または `_findnext` のどちらかによって返されたハンドルは、削除などの変更操作が渡されたパスを形成するディレクトリで実行できるようになる前に、最初に  `_findclose` に渡される必要があります。  
  
 `_find` 関数を入れ子にできます。 たとえば、`_findfirst` または `_findnext` への呼び出しでサブディレクトリのファイルを見つけた場合、`_findfirst` または `_findnext` への別の呼び出しで新しい検索を開始することができます。  
  
 `_wfindfirst` と `_wfindnext` は、`_findfirst` と `_findnext` のワイド文字バージョンです。 ワイド文字バージョンの構造体の引数は IO.h と Wchar.h で定義されている `_wfinddata_t` データ型です。 このデータ型のフィールドは、`_wfinddata_t` では名前フィールドが `char` 型ではなく `wchar_t` 型であることを除き、`_finddata_t` データ型と同じです。 それ以外では、`_wfindfirst` と `_wfindnext` の動作は `_findfirst` と `_findnext` と同じです。  
  
 `_findfirst` と `_findnext` は 64 ビット時刻型を使用します。 従来の 32 ビット時刻型を使用する場合は、`_USE_32BIT_TIME_T` を定義できます。 名前に `32` サフィックスを持つこれらの関数のバージョンは 32 ビット時刻型を使用し、`64` サフィックスを持つものは 64 ビットの時刻型を使用します。  
  
 関数 `_findfirst32i64`、`_findnext32i64`、`_wfindfirst32i64`、`_wfindnext32i64` も 32 ビットの時刻の種類のバージョンの関数と同様に動作しますが、64 ビット ファイルの長さを使用して返す点が異なります。 関数 `_findfirst64i32`、`_findnext64i32`、`_wfindfirst64i32`、`_wfindnext64i32`は 64 ビットの時刻型ですが 32 ビット ファイルの長さを使用します。 これらの関数は、時間とファイル サイズの異なる型を持つフィールドの `_finddata_t` 型の適切なバリエーションを使用します。  
  
 `_finddata_t` は実際には `_finddata64i32_t` \(`_USE_32BIT_TIME_T` が定義されている場合は `_finddata32_t`\) に評価されるマクロです。`_finddata_t` のバリエーションの概要を次の表に示します:  
  
|構造体|時刻型|ファイル サイズの型|  
|---------|---------|----------------|  
|`_finddata_t`, `_wfinddata_t`|`__time64_t`|`_fsize_t`|  
|`_finddata32_t`, `_wfinddata32_t`|`__time32_t`|`_fsize_t`|  
|`__finddata64_t`, `__wfinddata64_t`|`__time64_t`|`__int64`|  
|`_finddata32i64_t`, `_wfinddata32i64_t`|`__time32_t`|`__int64`|  
|`_finddata64i32_t`, `_wfinddata64i32_t`|`__time64_t`|`_fsize_t`|  
  
 `_fsize_t` は `unsigned long` \(32 ビット\) の `typedef` です。  
  
## 使用例  
  
```  
// crt_find.c // This program uses the 32-bit _find functions to print // a list of all files (and their attributes) with a .C extension // in the current directory. #include <stdio.h> #include <stdlib.h> #include <io.h> #include <time.h> int main( void ) { struct _finddata_t c_file; intptr_t hFile; // Find first .c file in current directory if( (hFile = _findfirst( "*.c", &c_file )) == -1L ) printf( "No *.c files in current directory!\n" ); else { printf( "Listing of .c files\n\n" ); printf( "RDO HID SYS ARC  FILE         DATE %25c SIZE\n", ' ' ); printf( "--- --- --- ---  ----         ---- %25c ----\n", ' ' ); do { char buffer[30]; printf( ( c_file.attrib & _A_RDONLY ) ? " Y  " : " N  " ); printf( ( c_file.attrib & _A_HIDDEN ) ? " Y  " : " N  " ); printf( ( c_file.attrib & _A_SYSTEM ) ? " Y  " : " N  " ); printf( ( c_file.attrib & _A_ARCH )   ? " Y  " : " N  " ); ctime_s( buffer, _countof(buffer), &c_file.time_write ); printf( " %-12s %.24s  %9ld\n", c_file.name, buffer, c_file.size ); } while( _findnext( hFile, &c_file ) == 0 ); _findclose( hFile ); } }  
```  
  
```Output  
.c ファイルの一覧 RDO HID SYS ARC  ファイル         日付                           サイズ --- --- --- ---  ----         ----                           ---- N   N   N   Y   blah.c       2002 年 2 月 13 日 (水) 09:21:42       1715 N   N   N   Y   test.c       2002 年 2 月 6 日 (水) 14:30:44        312  
```  
  
## 参照  
 [システム コール](../Topic/System%20Calls.md)