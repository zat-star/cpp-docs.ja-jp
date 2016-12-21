---
title: "ストレージ クラス (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "thread_local_cpp"
  - "external_cpp"
  - "static_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ストレージ クラス, 基本的な概念"
ms.assetid: f10e1c56-6249-4eb6-b08f-09ab1eef1992
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ストレージ クラス (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ の変数宣言のコンテキストにおいて、*ストレージ クラス* は、オブジェクトの有効期間、リンケージ、およびメモリの場所を制御する型指定子です。  特定のオブジェクトはストレージ クラスを 1 つのみ持つことができます。  ブロック内で定義された変数は、`extern`、`static`、または `thread_local` 指定子によって指定されていない限り、自動ストレージを持ちます。  自動オブジェクトおよび変数にはリンケージがないため、ブロックの外側のコードには不可視です。  
  
 **ノート**  
  
1.  [mutable](../cpp/mutable-data-members-cpp.md) キーワードは、ストレージ クラス指定子と見なされることがあります。  ただし、クラス定義のメンバー一覧でのみ使用できます。  
  
2.  [!INCLUDE[cpp_dev10_long](../Token/cpp_dev10_long_md.md)] 以降、`auto` キーワードは C\+\+ のストレージ クラス指定子ではなくなりました。また、`register` キーワードは使用されていません。  
  
-   [静的](#static)  
  
-   [extern](#extern)  
  
-   [thread\_local](#thread_local)  
  
## 静的  
 `static` キーワードを使用すると、変数と関数をグローバル スコープ、名前空間スコープ、およびクラス スコープで宣言することができます。  静的変数は、ローカル スコープでも宣言できます。  
  
 静的存続期間は、オブジェクトまたは変数がプログラム起動時に割り当てられ、プログラムの終了時に解放されることを意味します。  外部リンケージは、変数が宣言されたファイルの外部から変数名が参照できることを意味します。  逆に、内部リンケージは、変数が宣言されたファイルの外部でその名前を参照できないことを意味します。  既定では、グローバル名前空間で定義されたオブジェクトまたは変数には静的存続期間と外部リンケージがあります。  キーワード `static` は次の状況で使用できます。  
  
1.  ファイル スコープ \(グローバル スコープまたは名前空間スコープ、あるいはその両方\) で変数または関数を宣言する場合、`static` キーワードは、変数または関数に内部リンケージがあることを指定します。  変数を宣言すると、変数は静的存続期間が設定され、コンパイラによって 0 に初期化されます \(別の値を指定していない場合\)。  
  
2.  関数で変数を宣言する場合、`static` キーワードは、その関数の呼び出しと呼び出しの間に変数がその状態を保持することを指定します。  
  
3.  クラス宣言でデータ メンバーを宣言する場合、`static` キーワードは、メンバーの 1 つのコピーがクラスのすべてのインスタンスで共有されることを指定します。  静的データ メンバーはファイル スコープで定義する必要があります。  `const` `static` として宣言した整数データ メンバーには、初期化子を定義できます。  
  
4.  クラス宣言でメンバー関数を宣言する場合、`static` キーワードは、関数がクラスのすべてのインスタンスで共有されることを指定します。  静的メンバー関数は、関数に暗黙の `this` ポインターがないため、インスタンス メンバーにアクセスできません。  インスタンス メンバーにアクセスするには、インスタンスのポインターまたは参照であるパラメーターを受け取る関数を宣言します。  
  
5.  共用体のメンバーを static として宣言することはできません。  ただし、グローバルに宣言された匿名共用体は、明示的に `static` として宣言する必要があります。  
  
 次の例では、関数内で `static` として宣言された変数が、その関数の呼び出しと呼び出しの間、どのようにその状態を保持するかを示します。  
  
```  
// static1.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
void showstat( int curr ) {  
   static int nStatic;    // Value of nStatic is retained  
                          // between each function call  
   nStatic += curr;  
   cout << "nStatic is " << nStatic << endl;  
}  
  
int main() {  
   for ( int i = 0; i < 5; i++ )  
      showstat( i );  
}  
```  
  
  **nStatic is 0**  
**nStatic is 1**  
**nStatic is 3**  
**nStatic is 6**  
**nStatic is 10** クラスでの `static` の使用例を次に示します。  
  
```  
// static2.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class CMyClass {  
public:  
   static int m_i;  
};  
  
int CMyClass::m_i = 0;  
CMyClass myObject1;  
CMyClass myObject2;  
  
int main() {  
   cout << myObject1.m_i << endl;  
   cout << myObject2.m_i << endl;  
  
   myObject1.m_i = 1;  
   cout << myObject1.m_i << endl;  
   cout << myObject2.m_i << endl;  
  
   myObject2.m_i = 2;  
   cout << myObject1.m_i << endl;  
   cout << myObject2.m_i << endl;  
  
   CMyClass::m_i = 3;  
   cout << myObject1.m_i << endl;  
   cout << myObject2.m_i << endl;  
}  
```  
  
  **0**  
**0**  
**1**  
**1**  
**2**  
**2**  
**3**  
**3** 次の例では、メンバー関数内で `static` として宣言されたローカル変数を示します。  静的変数は、プログラム全体で使用できます。型のすべてのインスタンスは、静的変数の同じコピーを共有します。  
  
```  
// static3.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
struct C {  
   void Test(int value) {  
      static int var = 0;  
      if (var == value)   
         cout << "var == value" << endl;  
      else  
         cout << "var != value" << endl;  
  
      var = value;  
   }  
};   
  
int main() {  
   C c1;  
   C c2;  
   c1.Test(100);  
   c2.Test(100);  
}  
```  
  
  **var \!\= value**  
**var \=\= value** C\+\+11 以降では、静的ローカル変数の初期化はスレッド セーフであることが保証されています。  この機能は、*静的マジック*と呼ばれることがあります。  ただし、マルチスレッド アプリケーションでは、後続の割り当てはすべて同期する必要があります。  CRT の依存関係を避けるには、\/Zc:threadSafeInit\-フラグを使用してスレッド セーフな静的変数の機能を無効にできます。  
  
## extern  
 `extern` として宣言されたオブジェクトと変数は、別の翻訳単位または外側のスコープで定義されているオブジェクトを、外部リンケージを持つものとして宣言します。  
  
 **const** 変数を `extern` ストレージ クラスと共に宣言すると、変数は強制的に外部リンケージを持つことになります。  **extern const** 変数の初期化は、定義の翻訳単位で許可されます。  定義している翻訳単位以外の翻訳単位の初期化は未定義の結果になります。  詳細については、「[extern を使用したリンケージの指定](../cpp/using-extern-to-specify-linkage.md)」を参照してください。  
  
 次のコードは、2 つの `extern` 宣言、`DefinedElsewhere` \(別の翻訳単位で定義された名前を参照する\) と `DefinedHere` \(外側のスコープで定義された名前を参照する\) を示しています。  
  
```  
// external.cpp  
// defined in another translation unit  
extern int DefinedElsewhere;     
int main() {  
   int DefinedHere;   
   {  
      // refers to DefinedHere in the enclosing scope  
      extern int DefinedHere;  
    }  
}  
```  
  
## thread\_local \(C\+\+11\)  
 `thread_local` 指定子で宣言された変数は、それが作成されたスレッドでのみアクセスできます。  変数は、スレッドが作成されるときに作成され、スレッドが破棄されるときに破棄されます。  各スレッドには、それ自体の変数のコピーがあります。  Windows では、`thread_local` は Microsoft 固有の [\_\_declspec\( thread \)](../cpp/thread.md) 属性と機能的に同等です。  
  
```  
thread_local float f = 42.0; //global namespace  
  
struct C // cannot be applied to type definition  
{  
thread_local int i; //local  
thread_local static char buf[10]; // local and static  
};  
  
void DoSomething()  
{  
thread_local C my_struct; // Apply  thread_local to a variable  
}  
```  
  
1.  thread\_local 指定子は、`static` または `extern` と組み合わせることができます。  
  
2.  `thread_local` は、データの宣言と定義にのみ適用できます。**thread\_local** は、関数の宣言または定義では使用できません。  
  
3.  `thread_local` を使用すると、DLL のインポートの[遅延読み込み](../build/reference/linker-support-for-delay-loaded-dlls.md)と干渉することがあります**。**  
  
4.  XP システムでは、DLL が `thread_local` のデータを使用して、データが LoadLibrary 経由で動的に読み込まれる場合、`thread_local` は正常に機能しないことがあります。  
  
5.  `thread_local` は、静的ストレージ存続期間のあるデータ項目にのみ指定できます。  これには、グローバルなデータ オブジェクト \(**static** と `extern` の両方\)、ローカルな静的オブジェクト、クラスの静的データ メンバーなどが含まれます。  **thread\_local** を使用して自動データ オブジェクトを宣言することはできません。  
  
6.  宣言と定義が同じファイルと別々のファイルのどちらで発生する場合でも、スレッド ローカル オブジェクトの宣言と定義には `thread_local` を使用する必要があります。  
  
 Windows では、`thread_local` は [\_\_declspec\(thread\)](../cpp/thread.md) と機能的に同等です。ただし、\_\_declspec\(thread\) が型定義に適用できる点および C コードで有効である点は除きます。  `thread_local` は C\+\+ 標準の一部であり、移植性がより高いため、できるだけ常にこれを使用してください。  
  
 詳細については、「[スレッド ローカル ストレージ \(TLS: Thread Local Storage\)](../parallel/thread-local-storage-tls.md)」を参照してください。  
  
## register  
 C\+\+11 では、**register** キーワードは使用されていません。  可能であれば、変数をコンピューターのレジスタに格納するように指定します。  レジスタ ストレージ クラスで宣言できるのは、関数の引数とローカル変数だけです。  
  
```  
register int num;  
```  
  
 自動変数と同様、レジスタ変数は、それが宣言されたブロックの終わりまで保持されます。  
  
 コンパイラは、レジスタ変数に対するユーザーの要求を考慮しません。代わりに、グローバル最適化が有効な場合は独自にレジスタを選択します。  ただし、[register](http://msdn.microsoft.com/ja-jp/5b66905a-2f7f-4918-bb55-5e66d4bc50f9) キーワードに関連付けられた他のすべてのセマンティクスはコンパイラによって実行されます。  
  
 register を使用して宣言されたオブジェクトでアドレス演算子 \(**&**\) を使用する場合、コンパイラは、レジスタではなく、メモリにオブジェクトを配置する必要があります。  
  
## 例: 自動的な初期化と静的な初期化  
 ローカル自動オブジェクトまたは変数が、制御フローが定義に到達するたびに初期化されます。  ローカル静的オブジェクトまたは変数が、最初に制御フローが定義に到達すると初期化されます。  
  
 オブジェクトの初期化と破棄をログに記録するクラスを定義し、`I1`、`I2`、および `I3` の 3 つのオブジェクトを定義する、次の例を考えます。  
  
```  
// initialization_of_objects.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string.h>  
using namespace std;  
  
// Define a class that logs initializations and destructions.  
class InitDemo {  
public:  
   InitDemo( const char *szWhat );  
   ~InitDemo();  
  
private:  
   char *szObjName;  
   size_t sizeofObjName;  
};  
  
// Constructor for class InitDemo  
InitDemo::InitDemo( const char *szWhat ) :  
   szObjName(NULL), sizeofObjName(0) {  
   if( szWhat != 0 && strlen( szWhat ) > 0 ) {  
      // Allocate storage for szObjName, then copy  
      // initializer szWhat into szObjName, using  
      // secured CRT functions.  
      sizeofObjName = strlen( szWhat ) + 1;  
  
      szObjName = new char[ sizeofObjName ];  
      strcpy_s( szObjName, sizeofObjName, szWhat );  
  
      cout << "Initializing: " << szObjName << "\n";  
   }  
   else  
      szObjName = 0;  
}  
  
// Destructor for InitDemo  
InitDemo::~InitDemo() {  
   if( szObjName != 0 ) {  
      cout << "Destroying: " << szObjName << "\n";  
      delete szObjName;  
   }  
}  
  
// Enter main function  
int main() {  
   InitDemo I1( "Auto I1" ); {  
      cout << "In block.\n";  
      InitDemo I2( "Auto I2" );  
      static InitDemo I3( "Static I3" );  
   }  
   cout << "Exited block.\n";  
}  
```  
  
  **初期化: Auto I1**   
**In ブロック。  初期化: Auto I2**   
**初期化: Static I3**   
**破棄: Auto I2**   
**Exited ブロック。  破棄: Auto I1**   
**破棄: 静的 I3**  前のコードは、オブジェクト `I1`、`I2`、および `I3` がいつどのように初期化および破棄されるかを示します。  
  
 プログラムについていくつか注意点があります。  
  
 最初に、制御フローが `I1` と `I2` を定義しているブロックを終了すると、これらは自動的に破棄されます。  
  
 次に、C\+\+ では、ブロックの先頭でオブジェクトや変数を宣言する必要はありません。  さらに、これらのオブジェクトは、制御フローが定義に到達した場合にのみ初期化されます   \(このような定義には、`I2` や `I3` などがあります\)。 出力は、これらがいつ初期化されるかを正確に示します。  
  
 最後に、`I3` などの静的ローカル変数は、プログラム実行中は値が保持されますが、プログラムが終了すると破棄されます。  
  
## 参照  
 [宣言と定義](../cpp/declarations-and-definitions-cpp.md)