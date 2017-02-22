---
title: "例外処理の相違点 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++ 例外処理, 構造化例外処理との比較"
  - "例外, ラッパー クラス"
  - "構造化例外処理, C++ 例外処理との比較"
  - "構造化例外処理, および非構造化"
  - "ラッパー クラス, C の例外"
ms.assetid: f21d1944-4810-468e-b02a-9f77da4138c9
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 例外処理の相違点
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

構造化例外処理と C\+\+ 例外処理との主な相違点は、C\+\+ 例外処理モデルが複数の型を取り扱うのに対し、C の構造化例外処理モデルは 1 つの型 \(特に、`unsigned int`\) を取り扱うことです。  つまり、C 例外は符号なし整数値で識別されますが、C\+\+ 例外はデータ型で識別されます。  例外が C で発生すると、可能な各ハンドラーは、C 例外コンテキストをチェックするフィルターを実行して、例外を受け入れるか、他のハンドラーに渡すか、または無視するかを決定します。  C\+\+ でスローされる例外は、どのような型でもかまいません。  
  
 2 番目の相違点は、例外がコントロールの標準フローに従属的に発生すると C の構造化例外処理モデルが "非同期" と呼ばれることです。  C\+\+ の例外処理機構は、完全な "同期処理" を提供します。つまり、例外は、スローされたときにのみ発生します。  
  
 C の例外が C \+\+ プログラムで発生した場合、その例外は、関連のフィルターを持つ構造化例外ハンドラーまたは C \+\+ **catch** ハンドラーのどちらか例外コンテキストに動的に近い方で処理できます。  たとえば、次の C\+\+ プログラムでは、C\+\+ **try** コンテキスト内で C 例外が発生します。  
  
## 使用例  
  
```  
// exceptions_Exception_Handling_Differences.cpp  
// compile with: /EHa  
#include <iostream>  
  
using namespace std;  
void SEHFunc( void );  
  
int main() {  
   try {  
      SEHFunc();  
   }  
   catch( ... ) {  
      cout << "Caught a C exception."<< endl;  
   }  
}  
  
void SEHFunc() {  
   __try {  
      int x, y = 0;  
      x = 5 / y;  
   }  
   __finally {  
      cout << "In finally." << endl;  
   }  
}  
```  
  
  **In finally.**  
**Caught a C exception.**   
##  <a name="_core_c_exception_wrapper_class"></a> C 例外のラッパー クラス  
 上のような単純な例では、C 例外は省略記号 \(**...**\) **catch** ハンドラーによってのみキャッチされます。  ハンドラーに伝達される例外の種類または特性に関する情報はありません。  このメソッドは動作しますが、場合によっては、それぞれの C 例外が特定のクラスに関連付けられるように、2 つの例外処理モデル間の変換を定義する必要があります。  これを行うために、特定のクラスの種類を C 例外に起因すると見なすために利用したり派生させたりできる、C 例外の "wrapper" クラスを定義できます。  それにより、C の各例外は、C\+\+ の **catch** ハンドラーによって前の例よりも個別に処理できます。  
  
 ラッパー クラスには、例外の値を決定して、C 例外モデルが提供する拡張例外コンテキスト情報にアクセスするメンバー関数で構成されるインターフェイスが含まれることがあります。  また、既定のコンストラクター、`unsigned int` 引数を受け入れるコンストラクター \(基になる C の例外の表現を提供するため\)、およびビット単位のコピー コンストラクターを定義した方がよい場合もあります。  次は、C 例外のラッパー クラスの実装の例です。  
  
```  
// exceptions_Exception_Handling_Differences2.cpp  
// compile with: /c  
class SE_Exception {  
private:  
   SE_Exception() {}  
   SE_Exception( SE_Exception& ) {}  
   unsigned int nSE;  
public:  
   SE_Exception( unsigned int n ) : nSE( n ) {}  
   ~SE_Exception() {}  
   unsigned int getSeNumber() {  
      return nSE;  
   }  
};  
  
```  
  
 このクラスを使用するには、C 例外がスローされるたびに内部例外処理メカニズムによって呼び出されるカスタム C 例外変換関数をインストールします。  変換関数内で、適切な一致する C\+\+ **catch** ハンドラーでキャッチできる、任意の型指定例外 \(通常は `SE_Exception` 型、または `SE_Exception` から派生したクラス型\) をスローできます。  変換関数は、単純に制御を返すことができます。これは、例外を処理しなかったことを示します。  変換関数自体で C 例外が発生した場合は、[terminate](../c-runtime-library/reference/terminate-crt.md) が呼び出されます。  
  
 カスタム変換関数を指定する場合は、変換関数の名前を単一の引数として指定して [\_set\_se\_translator](../c-runtime-library/reference/set-se-translator.md) 関数を呼び出します。  作成した変換関数は、**try** ブロックを持つスタックの関数呼び出しごとに 1 回呼び出されます。  既定の変換関数はありません。`_set_se_translator` を呼び出してそれを指定しない場合、C の例外は省略記号 **catch** ハンドラーでしかキャッチできません。  
  
## 使用例  
 たとえば、次のコードでは、カスタム変換関数がインストールされた後に、`SE_Exception` クラスでラップされた C 例外が発生します。  
  
```  
// exceptions_Exception_Handling_Differences3.cpp  
// compile with: /EHa  
#include <stdio.h>  
#include <eh.h>  
#include <windows.h>  
  
class SE_Exception {  
private:  
   SE_Exception() {}  
   unsigned int nSE;  
  
public:  
   SE_Exception( SE_Exception& e) : nSE(e.nSE) {}  
   SE_Exception(unsigned int n) : nSE(n) {}  
   ~SE_Exception() {}  
   unsigned int getSeNumber() { return nSE; }  
};  
  
void SEFunc() {  
   __try {  
      int x, y = 0;  
      x = 5 / y;  
    }  
    __finally {  
      printf_s( "In finally\n" );  
   }  
}  
  
void trans_func( unsigned int u, _EXCEPTION_POINTERS* pExp ) {  
   printf_s( "In trans_func.\n" );  
   throw SE_Exception( u );  
}  
  
int main() {  
   _set_se_translator( trans_func );  
    try {  
      SEFunc();  
    }  
    catch( SE_Exception e ) {  
      printf_s( "Caught a __try exception with SE_Exception.\n" );  
      printf_s( "nSE = 0x%x\n", e.getSeNumber() );  
    }  
}  
```  
  
  **In trans\_func.**  
**In finally**  
**Caught a \_\_try exception with SE\_Exception.**  
**nSE \= 0xc0000094**   
## 参照  
 [C \(構造化\) と C\+\+ の混合例外](../Topic/Mixing%20C%20\(Structured\)%20and%20C++%20Exceptions.md)