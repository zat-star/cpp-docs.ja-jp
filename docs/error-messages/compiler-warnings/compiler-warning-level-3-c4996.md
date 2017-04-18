---
title: "コンパイラの警告 (レベル 3) C4996 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4996
dev_langs:
- C++
helpviewer_keywords:
- C4996
ms.assetid: 926c7cc2-921d-43ed-ae75-634f560dd317
caps.latest.revision: 34
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
translationtype: Machine Translation
ms.sourcegitcommit: bb94e24657d16b2a3eda3a770c2b6ae734c6006f
ms.openlocfilehash: 4a82bbdd3b28ae0150ab8366d3ecbe849e7ac8a1
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-3-c4996"></a>コンパイラの警告 (レベル 3) C4996
使用されていない宣言をコンパイラが検出しました。  
  
 この警告またはエラーには、いくつかの意味が考えられます。  
  
 `C4996`関数または変数としてマークされている、コンパイラが検出すると発生[廃止](../../cpp/deprecated-cpp.md)です。 Visual Studio のライブラリには、使用されていないというマークが付いた関数、メンバー関数、テンプレート関数、グローバル変数がいくつかあります。 そのような関数としては、別の優先名があるもの、セキュリティで保護されていないかより安全なバリアントがあるもの、または古いものがあります。 使用されていない関数またはグローバル変数に代えて使用できる修正候補がエラー メッセージに示される可能性があります。 この警告をオフにできます、[警告](../../preprocessor/warning.md)プラグマ、または**/wd4996**コマンド ライン オプションです。 使用されなくなったものに関する警告の特定のクラスをオフにするために、プリプロセッサ マクロを使用することもできます。 

この警告は、関数、クラス メンバーまたは c++ 14 のある typedef にアクセスしようとしたときにも発行される`[[deprecated]]`属性。 詳細については、次を参照してください。 [C++ の標準属性](../../cpp/attributes2.md)です。 
  
 **このアイテムの POSIX 名は使用されなくなりました。代わりに、ISO C および C++ に準拠する名前を使用:** new_name**です。詳しくは、オンライン ヘルプをご覧ください。**  
  
 CRT の一部の POSIX 関数は、実装定義のグローバル関数名に関する C99 と C++03 の規則に合わせて名前が変更されました。 ほとんどの場合、標準準拠の名前を作成するため POSIX 関数名の先頭にアンダースコアが追加されています。 コンパイラは、元の関数名は使用されなくなったとの警告を発し、優先名を提案します。 使用されていないのは元の名前だけであり、関数自体ではありません。 これらの関数が使用されなくなったとの警告をオフにするには、プリプロセッサ マクロ **_CRT_NONSTDC_NO_WARNINGS**を定義します。 コマンド ラインでオプション `/D_CRT_NONSTDC_NO_WARNINGS`を含めれば、これを定義できます。 Visual Studio でこのマクロを定義するには、プロジェクトの **[プロパティ ページ]** ダイアログを開きます。 **[構成プロパティ]**、 **[C/C++]**、 **[プリプロセッサ]**を順に展開します。 **[プリプロセッサの定義]**で、 `_CRT_NONSTDC_NO_WARNINGS`を追加します。 **[OK]** を選んで保存し、プロジェクトをリビルドします。 特定のソース ファイルでのみこのマクロを定義するには、ヘッダー ファイルをインクルードするすべての行の前に行 `#define _CRT_NONSTDC_NO_WARNINGS` を追加します。  
  
 **この関数または変数が安全でない可能性があります。使用を検討して**safe_version**代わりにします。使用されなくなったことの警告を無効にするには、_CRT_SECURE_NO_WARNINGS を使用します。詳しくは、オンライン ヘルプをご覧ください。**  
  
 一部の CRT および C++ 標準ライブラリ関数およびグローバル変数は新しいより安全な関数を優先するため推奨されません。 コンパイラは、これらの関数は使用されなくなったとの警告を発し、優先関数を提案します。 CRT のこれらの関数が使用されなくなったとの警告をオフにするには、 **_CRT_SECURE_NO_WARNINGS**を定義します。 使用されていないグローバル変数に関する警告をオフにするには、 **_CRT_SECURE_NO_WARNINGS_GLOBALS**を定義します。 これらの非推奨の関数とグローバル変数の詳細については、次を参照してください。 [CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)と[安全なライブラリ: C++ 標準ライブラリ](../../standard-library/safe-libraries-cpp-standard-library.md)です。  
  
 **安全でない可能性がありますパラメーターを持つ関数呼び出しこの呼び出しは、渡された値が正しいことを確認する呼び出し元に依存します。この警告を無効にするには、-D_SCL_SECURE_NO_WARNINGS を使用します。Visual C '反復子のチェック' を使用する方法のドキュメントを参照してください。**  
  
 C++ 標準ライブラリの一部のテンプレート関数は、パラメーターが正しいかどうかをチェックしません。 そのような関数が使用されていることをこの警告で識別できます。 これらの関数の警告をオフにするには、 **_SCL_SECURE_NO_WARNINGS**を定義します。 詳細については、「[チェックを行う反復子](../../standard-library/checked-iterators.md)」を参照してください。  
  
 **この関数または変数は、新しいライブラリまたはオペレーティング システムの機能が提供されています。使用を検討して**new_item**代わりにします。詳しくは、オンライン ヘルプをご覧ください。**  
  
 一部のライブラリ関数およびグローバル変数は古いため使用されていません。 これらの関数および変数は、将来のバージョンのライブラリでは削除される可能性があります。 コンパイラは、これらの項目は使用されなくなったとの警告を発行し、優先すべき代替項目を提案します。 これらの項目が使用されなくなったとの警告をオフにするには、 **_CRT_OBSOLETE_NO_WARNINGS**を定義します。 詳しくは、使用されていない関数または変数のドキュメントをご覧ください。  
  
 **MFC または ATL コードでさまざまなメッセージ**  
  
 `C4996` は、セキュリティ上の理由から使用されなくなった MFC 関数または ATL 関数を使用している場合にも発生することがあります。 これらの警告を抑制するのを参照してください。[無効](../../mfc/reference/diagnostic-services.md#afx_secure_no_warnings)と[無効](http://msdn.microsoft.com/Library/587d29d8-a75a-44a3-bec8-f724087e5e73)です。  
  
 **CLR コードのマーシャ リング エラー**  
  
 `C4996` は、マーシャリング ライブラリを使用しているときも発生します。 この場合、C4996 はエラーであり、警告ではありません。 このエラーが発生するときに[marshal_as](../../dotnet/marshal-as.md)を必要とする 2 つのデータ型の間で変換する、 [marshal_context クラス](../../dotnet/marshal-context-class.md)です。 マーシャリング ライブラリが変換をサポートしていないときにもこのエラーが発生します。 詳細については、マーシャ リング ライブラリは、次を参照してください。[概要の C++ におけるマーシャ リング](../../dotnet/overview-of-marshaling-in-cpp.md)です。  
  
 **C4996 が生成される例**  
  
 最初の例では、関数が宣言されている行と関数が使用されている行に対して `C4996` が生成されます。  
  
## <a name="example"></a>例  
 次の例では C4996 が生成されます。  
  
```cpp  
// C4996.cpp  
// compile with: /W3  
// C4996 warning expected  
#include <stdio.h>  
  
// #pragma warning(disable : 4996)  
void func1(void) {  
   printf_s("\nIn func1");  
}  
  
__declspec(deprecated) void func1(int) {  
   printf_s("\nIn func2");  
}  
  
int main() {  
   func1();  
   func1(1);  
}  
```  
  
## <a name="example"></a>例  
 C4996 は、 `_ITERATOR_DEBUG_LEVEL` を定義してコンパイルするときに、チェックを行う反復子を使用しない場合にも発生することがあります (デバッグ モードのビルドでは既定で 1 に設定)。  詳細については、「[チェックを行う反復子](../../standard-library/checked-iterators.md)」をご覧ください。  
  
 C++ 標準ライブラリの次のコード例では、C4996 が生成されます。  
  
```cpp  
// C4996_b.cpp  
// compile with: /EHsc /W3 /c  
#define _ITERATOR_DEBUG_LEVEL 1  
  
#include <algorithm>  
#include <iterator>  
  
using namespace std;  
using namespace stdext;  
  
int main() {  
    int a[] = { 1, 2, 3 };  
    int b[] = { 10, 11, 12 };  
    copy(a, a + 3, b + 1);   // C4996  
    // try the following line instead  
    //   copy(a, a + 3, b);  
    copy(a, a + 3, checked_array_iterator<int *>(b, 3));   // OK  
}  
  
```  
  
## <a name="example"></a>例  
 C++ 標準ライブラリの次のコード例では、警告として C4996 が生成されます。 コメントはインラインです。  
  
```cpp  
#include <algorithm>  
#include <array>  
#include <iostream>  
#include <iterator>  
#include <numeric>  
#include <string>  
#include <vector>  
  
using namespace std;  
  
template <typename C> void print(const string& s, const C& c) {  
    cout << s;  
  
    for (const auto& e : c) {  
        cout << e << " ";  
    }  
  
    cout << endl;  
}  
  
int main()  
{  
    vector<int> v(16);  
    iota(v.begin(), v.end(), 0);  
    print("v: ", v);  
  
    // OK: vector::iterator is checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    vector<int> v2(16);  
    transform(v.begin(), v.end(), v2.begin(), [](int n) { return n * 2; });  
    print("v2: ", v2);  
  
    // OK: back_insert_iterator is marked as checked in debug mode  
    // (i.e. an overrun is impossible)  
    vector<int> v3;  
    transform(v.begin(), v.end(), back_inserter(v3), [](int n) { return n * 3; });  
    print("v3: ", v3);  
  
    // OK: array::iterator is checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    array<int, 16> a4;  
    transform(v.begin(), v.end(), a4.begin(), [](int n) { return n * 4; });  
    print("a4: ", a4);  
  
    // OK: Raw arrays are checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    // NOTE: This applies only when raw arrays are given to C++ Standard Library algorithms!  
    int a5[16];  
    transform(v.begin(), v.end(), a5, [](int n) { return n * 5; });  
    print("a5: ", a5);  
  
    // WARNING C4996: Pointers cannot be checked in debug mode  
    // (i.e. an overrun will trigger undefined behavior)  
    int a6[16];  
    int * p6 = a6;  
    transform(v.begin(), v.end(), p6, [](int n) { return n * 6; });  
    print("a6: ", a6);  
  
    // OK: stdext::checked_array_iterator is checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    int a7[16];  
    int * p7 = a7;  
    transform(v.begin(), v.end(), stdext::make_checked_array_iterator(p7, 16), [](int n) { return n * 7; });  
    print("a7: ", a7);  
  
    // WARNING SILENCED: stdext::unchecked_array_iterator is marked as checked in debug mode  
    // (i.e. it performs no checking, so an overrun will trigger undefined behavior)  
    int a8[16];  
    int * p8 = a8;  
    transform(v.begin(), v.end(), stdext::make_unchecked_array_iterator(p8), [](int n) { return n * 8; });  
    print("a8: ", a8);  
}  
  
```  
  
## <a name="example"></a>例  
 次の例では、マーシャリング ライブラリが `System::String` を `const char *`に変換するときにコンテキストを必要とするため、C4996 が生成されます。  
  
```cpp  
// C4996_Marshal.cpp  
// compile with: /clr   
// C4996 expected  
#include <stdlib.h>  
#include <string.h>  
#include <msclr\marshal.h>  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   String^ message = gcnew String("Test String to Marshal");  
   const char* result;  
   result = marshal_as<const char*>( message );  
   return 0;  
}  
```

