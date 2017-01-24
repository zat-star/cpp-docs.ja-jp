---
title: "コンパイラの警告 (レベル 3) C4996 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4996"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4996"
ms.assetid: 926c7cc2-921d-43ed-ae75-634f560dd317
caps.latest.revision: 34
caps.handback.revision: 34
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 3) C4996
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

使用されていない宣言をコンパイラが検出しました。  
  
 この警告またはエラーには、いくつかの意味が考えられます。  
  
 [使用されていない](../../cpp/deprecated-cpp.md)というマークが付いた関数または変数をコンパイラが検出すると、`C4996` が発生します。 Visual Studio のライブラリには、使用されていないというマークが付いた関数、メンバー関数、テンプレート関数、グローバル変数がいくつかあります。 そのような関数としては、別の優先名があるもの、セキュリティで保護されていないかより安全なバリアントがあるもの、または古いものがあります。 使用されていない関数またはグローバル変数に代えて使用できる修正候補がエラー メッセージに示される可能性があります。 この警告は、[warning](../../preprocessor/warning.md) プラグマまたは **\/wd4996** コマンド ライン オプションを使用するとオフにできます。 使用されなくなったものに関する警告の特定のクラスをオフにするために、プリプロセッサ マクロを使用することもできます。  
  
 **このアイテムの POSIX 名は使用されていません。代わりに、ISO C および C\+\+ に準拠する次の名前を使用します。**new\_name**。詳しくは、オンライン ヘルプをご覧ください。**  
  
 CRT の一部の POSIX 関数は、実装定義のグローバル関数名に関する C99 と C\+\+03 の規則に合わせて名前が変更されました。 ほとんどの場合、標準準拠の名前を作成するため POSIX 関数名の先頭にアンダースコアが追加されています。 コンパイラは、元の関数名は使用されなくなったとの警告を発し、優先名を提案します。 使用されていないのは元の名前だけであり、関数自体ではありません。 これらの関数が使用されなくなったとの警告をオフにするには、プリプロセッサ マクロ **\_CRT\_NONSTDC\_NO\_WARNINGS** を定義します。 コマンド ラインでオプション  `/D_CRT_NONSTDC_NO_WARNINGS` を含めれば、これを定義できます。 Visual Studio でこのマクロを定義するには、プロジェクトの **\[プロパティ ページ\]** ダイアログを開きます。**\[構成プロパティ\]**、**\[C\/C\+\+\]**、**\[プリプロセッサ\]** を順に展開します。**\[プリプロセッサの定義\]** で、`_CRT_NONSTDC_NO_WARNINGS` を追加します。**\[OK\]** を選んで保存し、プロジェクトをリビルドします。 特定のソース ファイルでのみこのマクロを定義するには、ヘッダー ファイルをインクルードするすべての行の前に行 `#define _CRT_NONSTDC_NO_WARNINGS` を追加します。  
  
 **この関数または変数は安全でない可能性があります。 代わりに** safe\_version **を使用することをご検討ください。使用されなくなったことの警告を無効にするには、\_CRT\_SECURE\_NO\_WARNINGS を使用します。詳しくは、オンライン ヘルプをご覧ください。**  
  
 セキュリティが強化された新しい関数が優先されるので、一部の CRT 関数と標準 C\+\+ ライブラリ関数およびグローバルは使用されなくなっています。 コンパイラは、これらの関数は使用されなくなったとの警告を発し、優先関数を提案します。 CRT のこれらの関数が使用されなくなったとの警告をオフにするには、**\_CRT\_SECURE\_NO\_WARNINGS** を定義します。 使用されていないグローバル変数に関する警告をオフにするには、**\_CRT\_SECURE\_NO\_WARNINGS\_GLOBALS** を定義します。 これらの使用されていない関数とグローバルについて詳しくは、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」および「[安全なライブラリ: C\+\+ 標準ライブラリ](../../standard-library/safe-libraries-cpp-standard-library.md)」をご覧ください。  
  
 **パラメーターが指定されている関数呼び出しが安全でない可能性があります。この呼び出しは、呼び出し元を使用して、渡された値が正しいかどうかを確認します。 この警告を無効にするには、\-D\_SCL\_SECURE\_NO\_WARNINGS を使用します。 Visual C\+\+ の "チェックを行う反復子" の使用方法に関するドキュメントを参照してください。**  
  
 C\+\+ 標準ライブラリの一部のテンプレート関数は、パラメーターが正しいかどうかをチェックしません。 そのような関数が使用されていることをこの警告で識別できます。 これらの関数の警告をオフにするには、**\_SCL\_SECURE\_NO\_WARNINGS** を定義します。 詳細については、「[チェックを行う反復子](../../standard-library/checked-iterators.md)」を参照してください。  
  
 **この関数または変数は、新しいライブラリまたはオペレーティング システムの機能で置き換えられました。 代わりに** new\_item **を使用することをご検討ください。詳しくは、オンライン ヘルプをご覧ください。**  
  
 一部のライブラリ関数およびグローバル変数は古いため使用されていません。 これらの関数および変数は、将来のバージョンのライブラリでは削除される可能性があります。 コンパイラは、これらの項目は使用されなくなったとの警告を発行し、優先すべき代替項目を提案します。 これらの項目が使用されなくなったとの警告をオフにするには、**\_CRT\_OBSOLETE\_NO\_WARNINGS** を定義します。 詳しくは、使用されていない関数または変数のドキュメントをご覧ください。  
  
 **MFC コードまたは ATL コードのさまざまなメッセージ**  
  
 `C4996` は、セキュリティ上の理由から使用されなくなった MFC 関数または ATL 関数を使用している場合にも発生することがあります。 これらの警告が表示されないようにするには、「[\_AFX\_SECURE\_NO\_WARNINGS](../Topic/_AFX_SECURE_NO_WARNINGS.md)」および「[\_ATL\_SECURE\_NO\_WARNINGS](../Topic/_ATL_SECURE_NO_WARNINGS.md)」をご覧ください。  
  
 **CLR コードのマーシャリング エラー**  
  
 `C4996` は、マーシャリング ライブラリを使用しているときも発生します。 この場合、C4996 はエラーであり、警告ではありません。 このエラーは、[marshal\_as](../../dotnet/marshal-as.md) を使用して [marshal\_context クラス](../../dotnet/marshal-context-class.md) を必要とする 2 つのデータ型間で変換を行うときに発生します。 マーシャリング ライブラリが変換をサポートしていないときにもこのエラーが発生します。 マーシャリング ライブラリについて詳しくは、「[C\+\+ におけるマーシャリングの概要](../../dotnet/overview-of-marshaling-in-cpp.md)」をご覧ください。  
  
 **C4996 が生成される例**  
  
 最初の例では、関数が宣言されている行と関数が使用されている行に対して `C4996` が生成されます。  
  
## 使用例  
 次の例では C4996 が生成されます。  
  
```cpp  
// C4996.cpp // compile with: /W3 // C4996 warning expected #include <stdio.h> // #pragma warning(disable : 4996) void func1(void) { printf_s("\nIn func1"); } __declspec(deprecated) void func1(int) { printf_s("\nIn func2"); } int main() { func1(); func1(1); }  
```  
  
## 使用例  
 C4996 は、`_ITERATOR_DEBUG_LEVEL` を定義してコンパイルするときに、チェックを行う反復子を使用しない場合にも発生することがあります \(デバッグ モードのビルドでは既定で 1 に設定\)。  詳細については、「[チェックを行う反復子](../../standard-library/checked-iterators.md)」を参照してください。  
  
 次の STL コード例では、C4996 が生成されます。  
  
```cpp  
// C4996_b.cpp // compile with: /EHsc /W3 /c #define _ITERATOR_DEBUG_LEVEL 1 #include <algorithm> #include <iterator> using namespace std; using namespace stdext; int main() { int a[] = { 1, 2, 3 }; int b[] = { 10, 11, 12 }; copy(a, a + 3, b + 1);   // C4996 // try the following line instead //   copy(a, a + 3, b); copy(a, a + 3, checked_array_iterator<int *>(b, 3));   // OK }  
  
```  
  
## 使用例  
 次の STL コード例では、C4996 が警告として生成されます。 コメントはインラインです。  
  
```cpp  
#include <algorithm> #include <array> #include <iostream> #include <iterator> #include <numeric> #include <string> #include <vector> using namespace std; template <typename C> void print(const string& s, const C& c) { cout << s; for (const auto& e : c) { cout << e << " "; } cout << endl; } int main() { vector<int> v(16); iota(v.begin(), v.end(), 0); print("v: ", v); // OK: vector::iterator is checked in debug mode // (i.e. an overrun will trigger a debug assertion) vector<int> v2(16); transform(v.begin(), v.end(), v2.begin(), [](int n) { return n * 2; }); print("v2: ", v2); // OK: back_insert_iterator is marked as checked in debug mode // (i.e. an overrun is impossible) vector<int> v3; transform(v.begin(), v.end(), back_inserter(v3), [](int n) { return n * 3; }); print("v3: ", v3); // OK: array::iterator is checked in debug mode // (i.e. an overrun will trigger a debug assertion) array<int, 16> a4; transform(v.begin(), v.end(), a4.begin(), [](int n) { return n * 4; }); print("a4: ", a4); // OK: Raw arrays are checked in debug mode // (i.e. an overrun will trigger a debug assertion) // NOTE: This applies only when raw arrays are given to STL algorithms! int a5[16]; transform(v.begin(), v.end(), a5, [](int n) { return n * 5; }); print("a5: ", a5); // WARNING C4996: Pointers cannot be checked in debug mode // (i.e. an overrun will trigger undefined behavior) int a6[16]; int * p6 = a6; transform(v.begin(), v.end(), p6, [](int n) { return n * 6; }); print("a6: ", a6); // OK: stdext::checked_array_iterator is checked in debug mode // (i.e. an overrun will trigger a debug assertion) int a7[16]; int * p7 = a7; transform(v.begin(), v.end(), stdext::make_checked_array_iterator(p7, 16), [](int n) { return n * 7; }); print("a7: ", a7); // WARNING SILENCED: stdext::unchecked_array_iterator is marked as checked in debug mode // (i.e. it performs no checking, so an overrun will trigger undefined behavior) int a8[16]; int * p8 = a8; transform(v.begin(), v.end(), stdext::make_unchecked_array_iterator(p8), [](int n) { return n * 8; }); print("a8: ", a8); }  
  
```  
  
## 使用例  
 次の例では、マーシャリング ライブラリが `System::String` を `const char *` に変換するときにコンテキストを必要とするため、C4996 が生成されます。  
  
```cpp  
// C4996_Marshal.cpp // compile with: /clr // C4996 expected #include <stdlib.h> #include <string.h> #include <msclr\marshal.h> using namespace System; using namespace msclr::interop; int main() { String^ message = gcnew String("Test String to Marshal"); const char* result; result = marshal_as<const char*>( message ); return 0; }  
```