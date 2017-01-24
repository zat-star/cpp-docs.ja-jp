---
title: "_set_se_translator | Microsoft Docs"
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
  - "_set_se_translator"
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
apitype: "DLLExport"
f1_keywords: 
  - "_set_se_translator"
  - "set_se_translator"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_set_se_translator 関数"
  - "例外処理, 変更"
  - "set_se_translator 関数"
ms.assetid: 280842bc-d72a-468b-a565-2d3db893ae0f
caps.latest.revision: 21
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _set_se_translator
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Win32 例外 \(C 構造化例外\) を C\+\+ 型指定例外として処理します。  
  
## 構文  
  
```  
_se_translator_function _set_se_translator(  
   _se_translator_function seTransFunction  
);  
```  
  
#### パラメーター  
 `seTransFunction`  
 作成する C\+\+.の構造化例外変換関数へのポインター。  
  
## 戻り値  
 前の関数が後で復元できるように `_set_se_translator`に登録される前の変換関数へのポインターを返します。  前の関数が設定されていない場合の既定の動作を復元するには、戻り値を使用できます。; この値は、NULL の場合もあります。  
  
## 解説  
 `_set_se_translator` 関数が C\+\+ に入力された例外として Win32 例外 \(C の構造化例外\) を処理する方法を示します。  それぞれに C の例外が C \+\+. `catch` ハンドラーによって処理されるようにように C.の例外にクラス型を設定するように使用されるか、派生することができる C\+\+.の例外のラッパー クラスを定義します。  このクラスを使用するには、内部の例外処理機構に C.の例外によって発生させる呼び出されるカスタム C の例外の変換関数をインストールします。  変換関数内で、一致 C\+\+ `catch` ハンドラーでキャッチできる型の例外をスローすることができます。  
  
 `_set_se_translator`を使用する場合 [\/EHa](../../build/reference/eh-exception-handling-model.md) を使用する必要があります。  
  
 カスタム変換関数を指定するには、引数として変換関数名の `_set_se_translator`を呼び出します。  作成する変換関数は `try`ブロックがある履歴の各関数の呼び出しを一度呼び出されます。  既定の変換関数はありません。  
  
 変換関数よりスローします. "のように入力された例外は大幅にしないでください。  これがスローするだけでなく、任意の場合 \(ログ ファイルへの書き込みなど\) は、プログラム変換関数が呼び出された回数は、プラットフォームに依存するため、期待どおりに動作しないことがあります。  
  
 マルチスレッド環境では、変換関数は、スレッドごとに別々に保持されます。  それぞれの独自の変換関数をインストールする新しいスレッドで行う必要があります。  したがって、各スレッドには、独自の変換処理があります。  `_set_se_translator`に" 1 個のスレッドに固有です; 別の DLL は異なる変換関数をインストールできます。  
  
 作成する `seTransFunction` 関数はネイティブ コンパイルされた関数である必要があります \(\/clr でコンパイルされていません\)。  これは、引数として Win32 `_EXCEPTION_POINTERS` 構造体に符号なし整数とポインターを持って行かなければ必要があります。  引数は、Win32 API `GetExceptionCode` と `GetExceptionInformation` の関数呼び出しの戻り値、それぞれです。  
  
```  
typedef void (*_se_translator_function)(unsigned int, struct _EXCEPTION_POINTERS* );  
```  
  
 `_set_se_translator`では、CRT に動的にリンクするときに影響がある; プロセス内の別の DLL は `_set_se_translator` を呼び出し、独自にハンドラーを置き換えることがあります。  
  
 マネージ コード \(\/clr でコンパイルしたコード\) の `_set_se_translator` またはネイティブ コードとマネージ コードの混合を使用する場合は、変換がネイティブ コードの生成された例外に影響を与えることに注意してください。  `System::Exception`を発生させるとマネージ コードで生成されるマネージ例外は、変換関数で \(など\) ルーティングされません。  マネージ コードでの Win32 関数を使用して `RaiseException` 発生させるまたは例外ゼロによる除算などのシステム例外による例外は変換を通じてルーティングされます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_set_se_translator`|\<eh.h\>|  
  
 `_set_se_translator` で提供される機能は [\/clr: 純粋](../../build/reference/clr-common-language-runtime-compilation.md) のコンパイラ オプションを使用してコンパイルされたコードでは使用できません。  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_settrans.cpp  
// compile with: /EHa  
#include <stdio.h>  
#include <windows.h>  
#include <eh.h>  
  
void SEFunc();  
void trans_func( unsigned int, EXCEPTION_POINTERS* );  
  
class SE_Exception  
{  
private:  
    unsigned int nSE;  
public:  
    SE_Exception() {}  
    SE_Exception( unsigned int n ) : nSE( n ) {}  
    ~SE_Exception() {}  
    unsigned int getSeNumber() { return nSE; }  
};  
int main( void )  
{  
    try  
    {  
        _set_se_translator( trans_func );  
        SEFunc();  
    }  
    catch( SE_Exception e )  
    {  
        printf( "Caught a __try exception with SE_Exception.\n" );  
    }  
}  
void SEFunc()  
{  
    __try  
    {  
        int x, y=0;  
        x = 5 / y;  
    }  
    __finally  
    {  
        printf( "In finally\n" );  
    }  
}  
void trans_func( unsigned int u, EXCEPTION_POINTERS* pExp )  
{  
    printf( "In trans_func.\n" );  
    throw SE_Exception();  
}  
```  
  
  **In trans\_func.**  
**最終的に**  
**SE\_Exception の\_\_try 例外をつかまえました。**   
## 使用例  
 `_set_se_translator` で提供される機能はマネージ コードで使用することはできませんが、ネイティブ コードが `#pragma unmanaged`を使用して表示される限り、ネイティブ コードが `/clr` スイッチの下にコンパイルであってもネイティブ コードでこのマッピングを使用する可能性があります。  構造化例外が割り当てられているマネージ コードでスローされれば作成とハンドルは `pragma`例外コードとマークする必要があります。  次のコードは、可能な使用方法を示します。  詳細については、「[プラグマ ディレクティブと \_\_Pragma キーワード](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)」を参照してください。  
  
```  
// crt_set_se_translator_clr.cpp  
// compile with: /clr  
#include <windows.h>  
#include <eh.h>  
#include <assert.h>  
#include <stdio.h>  
  
int thrower_func(int i) {  
   int j = i/0;  
  return 0;  
}  
  
class CMyException{  
};  
  
#pragma unmanaged  
void my_trans_func(unsigned int u, PEXCEPTION_POINTERS pExp )  
{  
printf("Translating the structured exception to a C++"  
             " exception.\n");  
throw CMyException();  
}  
  
void DoTest()  
{  
    try  
    {  
      thrower_func(10);  
    }   
  
    catch(CMyException e)  
    {  
printf("Caught CMyException.\n");  
    }  
    catch(...)  
    {  
      printf("Caught unexpected SEH exception.\n");  
    }  
}  
#pragma managed  
  
int main(int argc, char** argv) {  
    _set_se_translator(my_trans_func);  
    DoTest();  
    return 0;  
}  
```  
  
  **C\+\+. C\+\+ 例外への構造化例外に変換します。**  
**CMyException キャッチされます。**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [例外処理ルーチン](../../c-runtime-library/exception-handling-routines.md)   
 [set\_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set\_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../Topic/unexpected%20\(CRT\).md)