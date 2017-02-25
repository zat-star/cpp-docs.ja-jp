---
title: "DLL の境界を越えて CRT オブジェクトを渡す場合に発生する可能性のあるエラー | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL 競合 [C++]"
ms.assetid: c217ffd2-5d9a-4678-a1df-62a637a96460
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# DLL の境界を越えて CRT オブジェクトを渡す場合に発生する可能性のあるエラー
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

成功すると C ランタイム \(\(CRT\)、ファイル ハンドル、ロケール、環境変数などに対応するまたは DLL \(DLL の境界を越えて関数呼び出し DLL、DLL を呼び出すファイルが CRT ライブラリの複数のコピーを使用している場合\)、予期しない動作が発生する可能性があります。  
  
 関連の問題はメモリ \(明示的に `new` または `malloc`または `strdup`、`strstreambuf::str`と暗黙的など\) 煮割り当て、解放する DLL の境界を越えてポインターを置いたときに発生します。  DLL とユーザーが CRT ライブラリの複数のコピーを使用する場合に、メモリ アクセス違反またはヒープが破損する可能性があります。  
  
 この問題の別の症状は、デバッグ中に出力ウィンドウのエラーなどがあります:  
  
 ヒープ\[\]: RtlValidateHeap に指定された無効なアドレス \(\#、\#\)  
  
## 原因  
 CRT ライブラリの各コピーに異なる、別の状態になります。  したがって、CRT、ファイル ハンドル、環境変数など、作成し、ロケールはこれらのオブジェクトを割り当てるか、設定した CRT のコピーに対してのみ有効です。  DLL とユーザーが CRT ライブラリの複数のコピーを使用すると、DLL の境界を越えてこれらの CRT オブジェクトを渡し、反対側に正しく実行されると想定することはできません。  
  
 また、CRT ライブラリの各コピーに 1 個の CRT ライブラリにメモリを割り当て、合格した独自のヒープ マネージャーがあるため、CRT ライブラリのコピーが解放 DLL の境界を越えてポインターはヒープ破損の考えられる原因です。  
  
 境界を越えて CRT オブジェクトを渡すか、メモリの割り当て、DLL の外部で解放されることが予期される場合は、DLL をデザインする場合、DLL と CRT ライブラリの同じコピーを使用する DLL のユーザーを制限します。  両方の CRT DLL と同じバージョンにリンクされている場合のみ、DLL とユーザーは CRT ライブラリの同じコピーを使用します。  これは、ビルドされた Visual C\+\+ 4.1 でまたは以前のビルドされたアプリケーションを DLL の Visual C\+\+ 5.0 が混在する問題になる可能性があります。  Visual C\+\+ 4.1 で使用されている CRT ライブラリの DLL バージョンが msvcrt40.dll であり、ビジュアル 5.0 で使用されている 1 つが msvcrt.dll であるため、これらの DLL に CRT ライブラリの同じコピーを使用するアプリケーションをビルドすることはできません。  
  
 ただし、例外もあります。  Windows 2000 の US English エディションと他のいくつかのローカライズ バージョンで、ドイツ語、フランス語とチェコなど、msvcrt40.dll \(Version 4.20\) フォワーダー バージョンが提供されます。  その結果、DLL が msvcrt40.dll とリンクしているユーザーが msvcrt.dll とリンクしますが、msvcrt40.dll へのすべての呼び出しが msvcrt.dll に転送されるので、CRT ライブラリの同じコピーを使用します。  
  
 ただし msvcrt40.dll フォワーダーのこのバージョンは、日本語、および韓国語繁体字中国語など、Windows 2000 のあるローカライズ版で使用できません。  したがって、アプリケーションが対象とするこれらのオペレーティング システムのいずれかが必要な場合は、msvcrt40.dll に依存しない get または CRT ライブラリの同じコピーの使用に依存しないようにアプリケーションを変更します。DLL のアップグレード バージョンを示します。  DLL を開発する場合、これは Visual C\+\+ 4.2 以降でリビルドすることを意味します。  これはサード パーティの DLL の場合、アップグレードの販売元に連絡する必要があります。  
  
 msvcrt40.dll \(Version 4.20\) でこのフォワーダー DLL バージョンで再配布できないことに注意してください。  
  
## 例  
  
### 説明  
 この例では、DLL の境界を越えてファイル ハンドルを渡します。  
  
 DLL や .exe ファイルが \/MD でビルドされるため、CRT の一つのコピーを共有します。  
  
 これらは CRT のコピーを使用する方法 \/MT で再ビルドした場合、生成される test1Main.exe を実行すると、アクセス違反が発生します。  
  
### コード  
  
```  
// test1Dll.cpp  
// compile with: /MD /LD  
#include <stdio.h>  
__declspec(dllexport) void writeFile(FILE *stream)  
{  
   char   s[] = "this is a string\n";  
   fprintf( stream, "%s", s );  
   fclose( stream );  
}  
```  
  
### コード  
  
```  
// test1Main.cpp  
// compile with: /MD test1dll.lib  
#include <stdio.h>  
#include <process.h>  
void writeFile(FILE *stream);  
  
int main(void)  
{  
   FILE  * stream;  
   errno_t err = fopen_s( &stream, "fprintf.out", "w" );  
   writeFile(stream);  
   system( "type fprintf.out" );  
}  
```  
  
### 出力  
  
```  
this is a string  
```  
  
## 例  
  
### 説明  
 この例では、DLL の境界を越えて環境変数を渡します。  
  
### コード  
  
```  
// test2Dll.cpp  
// compile with: /MT /LD  
#include <stdio.h>  
#include <stdlib.h>  
  
__declspec(dllexport) void readEnv()  
{  
   char *libvar;  
   size_t libvarsize;  
  
   /* Get the value of the MYLIB environment variable. */   
   _dupenv_s( &libvar, &libvarsize, "MYLIB" );  
  
   if( libvar != NULL )  
      printf( "New MYLIB variable is: %s\n", libvar);  
   else  
      printf( "MYLIB has not been set.\n");  
   free( libvar );  
}  
```  
  
### コード  
  
```  
// test2Main.cpp  
// compile with: /MT /link test2dll.lib  
#include <stdlib.h>  
#include <stdio.h>  
  
void readEnv();  
  
int main( void )  
{  
   _putenv( "MYLIB=c:\\mylib;c:\\yourlib" );  
   readEnv();  
}  
```  
  
### 出力  
  
```  
MYLIB has not been set.  
```  
  
 CRT のは 1 部のみ使用されることを .exe ファイルと DLL の両方が \/MD を指定してビルドされている場合、プログラムは正常に実行され、次の出力が生成されます。:  
  
```  
New MYLIB variable is: c:\mylib;c:\yourlib  
```  
  
## 参照  
 [CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)