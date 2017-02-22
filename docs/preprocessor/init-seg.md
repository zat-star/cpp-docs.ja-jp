---
title: "init_seg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.init_seg"
  - "init_seg_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "データ セグメントの初期化 [C++]"
  - "init_seg プラグマ"
  - "プラグマ, init_seg"
ms.assetid: 40a5898a-5c85-4aa9-8d73-3d967eb13610
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# init_seg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 固有の仕様**  
  
 スタートアップ コードが実行される順序に影響を与えるキーワードまたコード セクションを指定します。  
  
## 構文  
  
```  
  
#pragma init_seg({ compiler | lib | user | "section-name" [, func-name]} )  
```  
  
## 解説  
 このトピックでは、*セグメント*と*セクション*は同義の用語です。  
  
 グローバルな静的オブジェクトの初期化にはコードの実行を含めることができるため、オブジェクトを構築する時期を定義するキーワードを指定する必要があります。  初期化を必要とするダイナミック リンク ライブラリ \(DLL\) またはライブラリでは、**init\_seg** プラグマの使用は特に重要です。  
  
 **init\_seg** プラグマへのオプションは次のとおりです。  
  
 **compiler**  
 Microsoft C ランタイム ライブラリの初期化のために予約されています。  このグループ内のオブジェクトが最初に構築されます。  
  
 **lib**  
 サード パーティの開発元のクラス ライブラリの初期化に使用できます。  このグループのオブジェクトは、**compiler** としてマークされているオブジェクトの後で、それ以外のすべてのオブジェクトより先に構築されます。  
  
 **ユーザー**  
 ユーザーが使用できます。  このグループ内のオブジェクトが最後に構築されます。  
  
 *section\-name*  
 初期化セクションの明示的な指定を許可します。  ユーザーが指定した *section\-name* のオブジェクトは暗黙的に構築されません。ただし、アドレスは *section\-name* で指定されるセクション内に配置されます。  
  
 指定したセクション名には、プラグマの後のそのモジュール内で宣言されたグローバル オブジェクトを構築するヘルパー関数へのポインターが格納されます。  
  
 セクションを作成する場合に使用しない名前のリストについては、「[\/SECTION](../build/reference/section-specify-section-attributes.md)」を参照してください。  
  
 *func\-name*  
 プログラムの終了時に `atexit` の代わりに呼び出される関数を指定します。  このヘルパー関数は、[atexit](../c-runtime-library/reference/atexit.md) も呼び出して、グローバル オブジェクトのデストラクターへのポインターを渡します。  次の形式のプラグマで関数の識別子を指定した場合、  
  
```  
int __cdecl myexit (void (__cdecl *pf)(void))  
```  
  
 指定した関数が C ランタイム ライブラリの `atexit` の代わりに呼び出されます。  これにより、オブジェクトを破棄する準備ができたときに呼び出す必要のあるデストラクターの一覧を構築できます。  
  
 初期化を遅延する必要がある場合 \(たとえば、DLL 内で\) セクション名を明示的に指定することもできます。  その後、各静的オブジェクトのコンストラクターを呼び出す必要があります。  
  
 `atexit` の代わりとなる関数は引用符で囲みません。  
  
 それでも、オブジェクトは他の XXX\_seg プラグマで定義されたセクションに配置されます。  
  
 モジュール内で宣言されたオブジェクトは C ランタイムで自動的には初期化されません。  これは、自分で行う必要があります。  
  
 既定では、`init_seg` セクションは読み取り専用です。  セクション名が .CRT の場合、属性が読み取り\/書き込み可能としてマークされている場合でも、属性はコンパイラによって通知なしで読み取り専用に変更されます。  
  
 1 つの翻訳単位で **init\_seg** を複数回指定することはできません。  
  
 オブジェクトにユーザー定義のコンストラクター、つまりコードで明示的に定義されていないコンストラクターがない場合でも、\(たとえば v\-table ポインターをバインドするために\) コンパイラによってコンストラクターが生成される場合があります。  したがって、コードはコンパイラによって生成されたコンストラクターを呼び出す必要があります。  
  
## 使用例  
  
```  
// pragma_directive_init_seg.cpp  
#include <stdio.h>  
#pragma warning(disable : 4075)  
  
typedef void (__cdecl *PF)(void);  
int cxpf = 0;   // number of destructors we need to call  
PF pfx[200];    // pointers to destructors.  
  
int myexit (PF pf) {  
   pfx[cxpf++] = pf;  
   return 0;  
}  
  
struct A {  
   A() { puts("A()"); }  
   ~A() { puts("~A()"); }  
};  
  
// ctor & dtor called by CRT startup code   
// because this is before the pragma init_seg  
A aaaa;   
  
// The order here is important.  
// Section names must be 8 characters or less.  
// The sections with the same name before the $  
// are merged into one section. The order that  
// they are merged is determined by sorting  
// the characters after the $.  
// InitSegStart and InitSegEnd are used to set  
// boundaries so we can find the real functions  
// that we need to call for initialization.  
  
#pragma section(".mine$a", read)  
__declspec(allocate(".mine$a")) const PF InitSegStart = (PF)1;  
  
#pragma section(".mine$z",read)  
__declspec(allocate(".mine$z")) const PF InitSegEnd = (PF)1;  
  
// The comparison for 0 is important.  
// For now, each section is 256 bytes. When they  
// are merged, they are padded with zeros. You  
// can't depend on the section being 256 bytes, but  
// you can depend on it being padded with zeros.  
  
void InitializeObjects () {  
   const PF *x = &InitSegStart;  
   for (++x ; x < &InitSegEnd ; ++x)  
      if (*x) (*x)();  
}  
  
void DestroyObjects () {  
   while (cxpf>0) {  
      --cxpf;  
      (pfx[cxpf])();  
   }  
}  
  
// by default, goes into a read only section  
#pragma init_seg(".mine$m", myexit)  
  
A bbbb;   
A cccc;  
  
int main () {  
   InitializeObjects();  
   DestroyObjects();  
}  
```  
  
  **A\(\)**  
**A\(\)**  
**A\(\)**  
**~A\(\)**  
**~A\(\)**  
**~A\(\)**   
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)