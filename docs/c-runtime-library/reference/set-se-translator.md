---
title: _set_se_translator | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _set_se_translator
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _set_se_translator
- set_se_translator
dev_langs:
- C++
helpviewer_keywords:
- set_se_translator function
- exception handling, changing
- _set_se_translator function
ms.assetid: 280842bc-d72a-468b-a565-2d3db893ae0f
caps.latest.revision: 21
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
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: d8d43b39c9f71807d68f20cb4873abf96d3f91e8
ms.lasthandoff: 02/24/2017

---
# <a name="setsetranslator"></a>_set_se_translator
Win32 例外 (C 構造化例外) を C++ 型指定例外として処理します。  
  
## <a name="syntax"></a>構文  
  
```  
_se_translator_function _set_se_translator(  
   _se_translator_function seTransFunction  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `seTransFunction`  
 ユーザーが作成した C 構造化例外の変換関数へのポインター。  
  
## <a name="return-value"></a>戻り値  
 `_set_se_translator` によって登録された前の変換関数へのポインターを返し、前の関数を後で復元できるようにします。 前の関数が設定されていない場合には、戻り値を使用して既定の動作を復元することができます。この値は NULL になります。  
  
## <a name="remarks"></a>コメント  
 `_set_se_translator` 関数は、Win32 例外 (C 構造化例外) を C++ 型指定例外として処理する方法を提供します。 それぞれの C 例外が C++ `catch` ハンドラーによって処理されるようにするには、まず、特定のクラスの種類を C 例外に起因すると見なすために利用したり派生させたりできる、C 例外のラッパー クラスを定義します。 このクラスを使用するには、C 例外が発生するたびに内部例外処理メカニズムによって呼び出されるカスタム C 例外変換関数をインストールします。 変換関数内では、一致する C++ `catch` ハンドラーでキャッチできる任意の型例外をスローすることができます。  
  
 `_set_se_translator` を使用するときには、[/EHa](../../build/reference/eh-exception-handling-model.md) を使用する必要があります。  
  
 カスタム変換関数を指定する場合は、変換関数の名前を引数として指定して `_set_se_translator` を呼び出します。 作成した変換関数は、`try` ブロックを持つスタックの関数呼び出しごとに&1; 回呼び出されます。 既定の変換関数はありません。  
  
 変換関数は、C++ 型の例外をスローする以外のことは何もすべきではありません。 スローに加えて何かを行う場合 (たとえば、ログ ファイルへの書き込みなど)、プログラムが期待どおりに動作しない可能性があります。それは、変換関数が呼び出される回数がプラットフォームに依存するためです。  
  
 マルチスレッド環境では、変換関数は各スレッドとは別に管理されます。 新しい各スレッドは、それぞれの変換関数をインストールする必要があります。 したがって、各スレッドが、それぞれの変換処理を担当します。 `_set_se_translator` は&1; つのスレッドに対して固有であり、他の DLL は別の変換関数をインストールできます。  
  
 ユーザーが作成する `seTransFunction` 関数は、ネイティブにコンパイルされた関数である (/clr を使ってコンパイルしない) 必要があります。 それは引数として、符号なし整数と、Win32 `_EXCEPTION_POINTERS` 構造体へのポインターを取る必要があります。 引数はそれぞれ、Win32 API の `GetExceptionCode` 関数と `GetExceptionInformation` 関数の呼び出しの戻り値です。  
  
```  
typedef void (*_se_translator_function)(unsigned int, struct _EXCEPTION_POINTERS* );  
```  
  
 `_set_se_translator` の場合、CRT に動的にリンクするときに影響があります。プロセス内の別の DLL は `_set_se_translator` を呼び出す可能性があり、ハンドラーを独自のものに置換します。  
  
 `_set_se_translator` をマネージ コード (/clr でコンパイルされたコード) から使用する場合や、ネイティブ コードとマネージ コードが混在している状態で使用する場合、変換プログラムはネイティブ コードで生成される例外のみに影響することにご注意ください。 マネージ コードで生成されるマネージ例外 (`System::Exception` の発生時のものなど) はいずれも、変換関数経由ではルーティングされません。 Win32 関数 `RaiseException` を使用してマネージ コードで発生した例外や、ゼロ除算例外などのシステム例外が原因の例外は、変換プログラム経由でルーティングされます。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_set_se_translator`|\<eh.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
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
  
```Output  
In trans_func.  
In finally  
Caught a __try exception with SE_Exception.  
```  
  
## <a name="example"></a>例  
 `_set_se_translator` によって提供される機能がマネージ コードでは使用できなくても、このマッピングをネイティブ コードで使用することは可能です。そのネイティブ コードが `/clr` スイッチのもとでコンパイルされている場合でも、ネイティブ コードで `#pragma unmanaged` を使用していることが示されている限り、それは可能です。 マップされることになっているマネージ コード内で構造化例外がスローされる場合、例外を生成および処理するコードは `pragma` でマークする必要があります。 次のコードは考えられる使用法を示しています。 詳細については、「[プラグマ ディレクティブと __Pragma キーワード](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)」を参照してください。  
  
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
  
```Output  
Translating the structured exception to a C++ exception.  
Caught CMyException.  
```  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [例外処理ルーチン](../../c-runtime-library/exception-handling-routines.md)   
 [set_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)
