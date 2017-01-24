---
title: "_get_purecall_handler _set_purecall_handler | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_purecall_handler"
  - "_set_purecall_handler_m"
  - "_get_purecall_handler"
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
  - "_set_purecall_handler"
  - "_set_purecall_handler_m"
  - "set_purecall_handler_m"
  - "set_purecall_handler"
  - "stdlib/_set_purecall_handler"
  - "stdlib/_get_purecall_handler"
  - "_get_purecall_handler"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_set_purecall_handler 関数"
  - "set_purecall_handler 関数"
  - "purecall_handler"
  - "set_purecall_handler_m 関数"
  - "_purecall_handler"
  - "_set_purecall_handler_m 関数"
  - "_get_purecall_handler 関数"
ms.assetid: 2759b878-8afa-4129-86e7-72afc2153d9c
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _get_purecall_handler _set_purecall_handler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

取得または純粋仮想関数呼び出しのエラー ハンドラーを設定します。  
  
## 構文  
  
```  
typedef void (__cdecl* _purecall_handler)(void);  
  
_purecall_handler __cdecl _get_purecall_handler(void);  
  
_purecall_handler __cdecl _set_purecall_handler(   
   _purecall_handler function  
);  
```  
  
#### パラメーター  
 `function`  
 純粋仮想関数が呼び出されたときに呼び出される関数。`_purecall_handler` 関数の戻り値は void 型である必要があります。  
  
## 戻り値  
 以前の `_purecall_handler`。 以前のハンドラーがなかった場合は、`nullptr` を返します。  
  
## 解説  
 `_get_purecall_handler` と `_set_purecall_handler` 関数は Microsoft 固有で、C\+\+ コードにのみ適用されます。  
  
 純粋仮想関数への呼び出しは、実装があるないために、エラーをされます。 既定は、コンパイラは、プログラムを終了しますが、純粋仮想関数が呼び出されると、エラー ハンドラー関数を呼び出すコードを生成します。 デバッグまたはレポート用の例外をキャッチする純粋仮想関数呼び出しのため、独自のエラー ハンドラー関数をインストールすることができます。 エラー ハンドラーを使用するを持つ関数を作成、 `_purecall_handler` 署名を使用して `_set_purecall_handler` に現在のハンドラーを作成します。  
  
 1 つだけあるため `_purecall_handler` を呼び出すと、各プロセスの `_set_purecall_handler` すべてのスレッドをすぐに影響します。 ハンドラーは、すべてのスレッドでの最後の呼び出し元によって設定されます。  
  
 既定の動作を復元するには、呼び出す `_set_purecall_handler` を使用して、 `nullptr` 引数。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_get_purecall_handler`, `_set_purecall_handler`|\< cstdlib \> または \< stdlib.h \>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// _set_purecall_handler.cpp  
// compile with: /W1  
#include <tchar.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
class CDerived;  
class CBase  
{  
public:  
   CBase(CDerived *derived): m_pDerived(derived) {};  
   ~CBase();  
   virtual void function(void) = 0;  
  
   CDerived * m_pDerived;  
};  
  
class CDerived : public CBase  
{  
public:  
   CDerived() : CBase(this) {};   // C4355  
   virtual void function(void) {};  
};  
  
CBase::~CBase()  
{  
   m_pDerived -> function();  
}  
  
void myPurecallHandler(void)  
{  
   printf("In _purecall_handler.");  
   exit(0);  
}  
  
int _tmain(int argc, _TCHAR* argv[])  
{  
   _set_purecall_handler(myPurecallHandler);  
   CDerived myDerived;  
}  
```  
  
```Output  
In _purecall_handler.  
```  
  
## 参照  
 [エラー処理](../../c-runtime-library/error-handling-crt.md)   
 [\_purecall](../Topic/_purecall.md)