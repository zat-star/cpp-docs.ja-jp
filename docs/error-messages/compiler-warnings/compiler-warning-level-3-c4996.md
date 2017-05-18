---
title: "コンパイラの警告 (レベル 3) C4996 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 9a0c25772fadec86a893b8c7c4af09072eb0476f
ms.contentlocale: ja-jp
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-warning-level-3-c4996"></a>コンパイラの警告 (レベル 3) C4996
使用されていない宣言をコンパイラが検出しました。  
  
この警告またはエラーは、コンテキストに応じて、いくつかの可能な意味を持っています。  
  
C4996 は、関数または変数としてマークされている、コンパイラが検出したときに発生[廃止](../../cpp/deprecated-cpp.md)を使用して、`__declspec(deprecated)`修飾子です。 この警告は、関数、クラス メンバーまたは c++ 14 のある typedef にアクセスしようとしたときにも発行される`[[deprecated]]`属性。 詳細については、次を参照してください。 [C++ の標準属性](../../cpp/attributes2.md)です。 ことができますこの属性を使用して自分で、ライブラリで推奨されない関数、メンバー、または typedef は、クライアントに警告する。  
  
Visual Studio のライブラリには、使用されていないというマークが付いた関数、メンバー関数、テンプレート関数、グローバル変数がいくつかあります。 そのような関数としては、別の優先名があるもの、セキュリティで保護されていないかより安全なバリアントがあるもの、または古いものがあります。 多くのエラー メッセージには、非推奨の関数やグローバル変数の代わりに候補が含まれます。  
  
この問題を修正するには、通常お勧め、推奨される安全なまたは更新された関数とグローバル変数の代わりに使用するコードを変更します。 移植性上の理由から、既存の関数または変数を使用する必要がある場合、警告はオフにすることができます。  
  
使用してコードの特定の行に対する警告を無効にすることができます、[警告](../../preprocessor/warning.md)プラグマ`#pragma warning(suppress : 4996)`です。 オフにできますが、ファイル内で warning プラグマを使用して、`#pragma warning(disable : 4996)`です。 オフにできますがグローバルにコマンド ライン ビルドを使用して、 **/wd4996**コマンド ライン オプションです。 Visual Studio IDE でプロジェクトの警告をオフに開く、**プロパティ ページ**ダイアログで、選択、**構成プロパティ**、 **C/C++**、 **[詳細設定]**ページおよび編集、**特定の警告を無効にする**プロパティを追加する`4996`です。  ライブラリの使用廃止警告の特定の特定のクラスをオフにプリプロセッサ マクロを使用することもできます。 これらのマクロは次のとおりです。  
  
C4996 のライブラリのソースのいくつか示します。  
  
## <a name="posix-function-names"></a>POSIX 関数名  
  
**このアイテムの POSIX 名は使用されなくなりました。代わりに、ISO C および C++ に準拠する名前を使用:** *new_name*です。 **詳細については、オンライン ヘルプを参照してください。**  
  
Microsoft は C99 と c++ 03 の規則をグローバル関数の実装定義の名前に準拠するよう CRT の一部の POSIX 関数の名前を変更します。 元の POSIX 名のみが推奨されず、関数自体ではありません。 ほとんどの場合、標準準拠の名前を作成するため POSIX 関数名の先頭にアンダースコアが追加されています。 コンパイラは、元の関数名の廃止警告を発行し、優先の名前を示します。  
  
この問題を修正するには、通常お勧めに推奨される関数名の代わりに使用するコードを変更します。 ただし、更新された名前は、Microsoft 固有の仕様です。 移植性のための既存の関数名を使用する必要がある場合は、これらの警告を無効にすることができます。 POSIX 関数は、元の名前の下にあるライブラリで引き続き使用できます。  
  
これらの関数が使用されなくなったとの警告をオフにするには、プリプロセッサ マクロ **_CRT_NONSTDC_NO_WARNINGS**を定義します。 コマンド ラインでオプション `/D_CRT_NONSTDC_NO_WARNINGS`を含めれば、これを定義できます。 Visual Studio でこのマクロを定義するには、プロジェクトの **[プロパティ ページ]** ダイアログを開きます。 **[構成プロパティ]**、 **[C/C++]**、 **[プリプロセッサ]**を順に展開します。 **[プリプロセッサの定義]**で、 `_CRT_NONSTDC_NO_WARNINGS`を追加します。 **[OK]** を選んで保存し、プロジェクトをリビルドします。 特定のソース ファイルでのみこのマクロを定義するには、ヘッダー ファイルをインクルードするすべての行の前に行 `#define _CRT_NONSTDC_NO_WARNINGS` を追加します。  
  
## <a name="unsafe-crt-library-functions"></a>安全でない CRT ライブラリ関数  
  
 **この関数または変数が安全でない可能性があります。使用を検討して***safe_version* **代わりにします。  使用されなくなったことの警告を無効にするには、_CRT_SECURE_NO_WARNINGS を使用します。詳しくは、オンライン ヘルプをご覧ください。**  
  
 Microsoft では、いくつかの CRT および C++ 標準ライブラリ関数とより安全なバージョンを優先するためのグローバル使用は推奨します。 ほとんどの場合では、非推奨の関数は、未チェックの読み取りまたは重大なセキュリティの問題につながることが、バッファーへの書き込みアクセスを許可します。 コンパイラは、これらの関数は使用されなくなったとの警告を発し、優先関数を提案します。  
  
 この問題を解決することをお勧め関数または変数を使用する*safe_version*代わりにします。 バッファーが上書きのことはできませんまたは、コードで発生する overread はの移植性の理由からコードを変更できないことを確認した場合は、警告オフにすることができます。  
   
 CRT のこれらの関数が使用されなくなったとの警告をオフにするには、 **_CRT_SECURE_NO_WARNINGS**を定義します。 使用されていないグローバル変数に関する警告をオフにするには、 **_CRT_SECURE_NO_WARNINGS_GLOBALS**を定義します。 これらの非推奨の関数とグローバル変数の詳細については、次を参照してください。 [CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)と[安全なライブラリ: C++ 標準ライブラリ](../../standard-library/safe-libraries-cpp-standard-library.md)です。  
  
## <a name="unsafe-standard-library-functions"></a>安全でない標準ライブラリ関数  
  
 **' std::** *function_name* **::\_未チェック\_反復子::\_Deprecate' std への呼び出し::** *function_name* **安全でない可能性がありますパラメーターを使用して、この呼び出しが渡された値が正しいことを確認する呼び出し元に依存します。この警告を無効にするには、-D_SCL_SECURE_NO_WARNINGS を使用します。Visual C '反復子のチェック' を使用する方法のドキュメントを参照してください。**  
  
特定の C++ 標準ライブラリ テンプレート関数はパラメーターが正しいことを確認しないために、デバッグ ビルドでこの警告が表示されます。 ほとんどの場合、これは反復子がありません正しく関数と共に使用する、または十分な情報がある関数で、コンテナーの境界をチェックするためです。 セキュリティ ホール、プログラム内のソースがありますので、この警告はこれらの関数の使用を識別するのに役立ちます。 詳細については、「 [Checked Iterators](../../standard-library/checked-iterators.md)」を参照してください。  
  
要素ポインターを渡す場合など、この警告がデバッグ モードで表示されます`std::copy`プレーンな配列の代わりにします。 この問題を解決するには、ライブラリが配列の範囲を確認し、範囲チェックを実行できるよう、適切に宣言された配列を使用します。  
  
```cpp  
// C4996_copyarray.cpp
// compile with: cl /c /W4 /D_DEBUG C4996_copyarray.cpp
#include <algorithm>
 
void example(char const * const src) { 
    char dest[1234]; 
    char * pdest3 = dest + 3;
    std::copy(src, src + 42, pdest3); // C4996 
    std::copy(src, src + 42, dest);   // OK, copy can tell that dest is 1234 elements 
} 
```  
  
標準ライブラリのいくつかのアルゴリズムは、c++ 14 で「デュアル範囲」バージョンに更新されました。 デュアル範囲のバージョンを使用する場合、2 番目の範囲は、必要な範囲のチェックを提供します。  
  
```cpp  
// C4996_containers.cpp
// compile with: cl /c /W4 /D_DEBUG C4996_containers.cpp
#include <algorithm>
 
bool example(
    char const * const left, 
    const size_t leftSize, 
    char const * const right, 
    const size_t rightSize) 
{ 
    bool result = false;
    result = std::equal(left, left + leftSize, right); // C4996
    // To fix, try this form instead: 
    // result = std::equal(left, left + leftSize, right, right + rightSize); // OK 
    return result;
}
```  
  
この例は、標準ライブラリが反復子の使用率を確認するいくつかの他の方法を示します。 ときにオンになっていない使用法が危険な可能性があります。  
  
```cpp  
// C4996_standard.cpp
// compile with: cl /EHsc /W4 /MDd C4996_standard.cpp
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
    // (i.e. an overrun triggers a debug assertion)  
    vector<int> v2(16);  
    transform(v.begin(), v.end(), v2.begin(), [](int n) { return n * 2; });  
    print("v2: ", v2);  
  
    // OK: back_insert_iterator is marked as checked in debug mode  
    // (i.e. an overrun is impossible)  
    vector<int> v3;  
    transform(v.begin(), v.end(), back_inserter(v3), [](int n) { return n * 3; });  
    print("v3: ", v3);  
  
    // OK: array::iterator is checked in debug mode  
    // (i.e. an overrun triggers a debug assertion)  
    array<int, 16> a4;  
    transform(v.begin(), v.end(), a4.begin(), [](int n) { return n * 4; });  
    print("a4: ", a4);  
  
    // OK: Raw arrays are checked in debug mode  
    // (i.e. an overrun triggers a debug assertion)  
    // NOTE: This applies only when raw arrays are 
    // given to C++ Standard Library algorithms!  
    int a5[16];  
    transform(v.begin(), v.end(), a5, [](int n) { return n * 5; });  
    print("a5: ", a5);  
  
    // WARNING C4996: Pointers cannot be checked in debug mode  
    // (i.e. an overrun triggers undefined behavior)  
    int a6[16];  
    int * p6 = a6;  
    transform(v.begin(), v.end(), p6, [](int n) { return n * 6; });  
    print("a6: ", a6);  
  
    // OK: stdext::checked_array_iterator is checked in debug mode  
    // (i.e. an overrun triggers a debug assertion)  
    int a7[16];  
    int * p7 = a7;  
    transform(v.begin(), v.end(), 
        stdext::make_checked_array_iterator(p7, 16), 
        [](int n) { return n * 7; });  
    print("a7: ", a7);  
  
    // WARNING SILENCED: stdext::unchecked_array_iterator 
    // is marked as checked in debug mode, but it performs no checking, 
    // so an overrun triggers undefined behavior  
    int a8[16];  
    int * p8 = a8;  
    transform( v.begin(), v.end(), 
        stdext::make_unchecked_array_iterator(p8), 
        [](int n) { return n * 8; });  
    print("a8: ", a8);  
}  
```  
  
コードがバッファー オーバーランこの警告をトリガーする、標準ライブラリ関数のエラーを持たないことを確認場合は、この警告をオフにします。 これらの関数の警告をオフにするには、 **_SCL_SECURE_NO_WARNINGS**を定義します。   
  
## <a name="example-checked-iterators-enabled"></a>例: 有効になっている Checked 反復子  
  
コンパイルすると、反復子を使用しない場合にも C4996 `_ITERATOR_DEBUG_LEVEL` 1 または 2 として定義します。 デバッグ モードのビルド、既定では 2 に、製品版ビルドでは 0 に設定されます。 詳細については、「 [Checked Iterators](../../standard-library/checked-iterators.md) 」を参照してください。  
  
```cpp  
// C4996_checked.cpp  
// compile with: /EHsc /W4 /MDd C4996_checked.cpp  
#define _ITERATOR_DEBUG_LEVEL 2  
  
#include <algorithm>  
#include <iterator>  
  
using namespace std;  
using namespace stdext;  
  
int main() {  
    int a[] = { 1, 2, 3 };  
    int b[] = { 10, 11, 12 };  
    copy(a, a + 3, b + 1);   // C4996  
    // try the following line instead:  
    // copy(a, a + 3, checked_array_iterator<int *>(b, 3));   // OK  
}  
```  
  
## <a name="unsafe-mfc-or-atl-code"></a>安全でない MFC または ATL コード  
  
C4996 は、セキュリティ上の理由から使用されなくなった MFC または ATL 関数を使用する場合にも発生することができます。  
  
この問題を解決するには、強くお勧めの更新された関数を代わりに使用するコードを変更します。  
  
これらの警告を抑制する方法については、次を参照してください。[無効](../../mfc/reference/diagnostic-services.md#afx_secure_no_warnings)と[無効](http://msdn.microsoft.com/Library/587d29d8-a75a-44a3-bec8-f724087e5e73)です。  
  
## <a name="obsolete-crt-functions-and-variables"></a>古い CRT 関数および変数  
  
**この関数または変数は、新しいライブラリまたはオペレーティング システムの機能が提供されています。使用を検討して** *new_item* **代わりにします。詳しくは、オンライン ヘルプをご覧ください。**  
  
一部のライブラリ関数およびグローバル変数は古いため使用されていません。 これらの関数および変数は、将来のバージョンのライブラリでは削除される可能性があります。 コンパイラは、これらの項目は使用されなくなったとの警告を発行し、優先すべき代替項目を提案します。  
  
この問題を解決するには、推奨される関数または変数を使用するコードを変更するをお勧めします。  
  
これらの項目が使用されなくなったとの警告をオフにするには、 **_CRT_OBSOLETE_NO_WARNINGS**を定義します。 詳しくは、使用されていない関数または変数のドキュメントをご覧ください。  
  
## <a name="example-marshalling-errors-in-clr-code"></a>例: CLR コード内のエラーをマーシャ リング  
  
C4996 は、CLR のマーシャ リング ライブラリを使用する場合にも発生することができます。 この場合、C4996 はエラーであり、警告ではありません。 使用すると、このエラーが発生[marshal_as](../../dotnet/marshal-as.md)を必要とする 2 つのデータ型の間で変換する、 [marshal_context クラス](../../dotnet/marshal-context-class.md)です。 マーシャ リング ライブラリが変換をサポートしていない場合にも、このエラーを受信できます。 マーシャリング ライブラリについて詳しくは、「 [Overview of Marshaling in C++](../../dotnet/overview-of-marshaling-in-cpp.md)」をご覧ください。  
  
この例では、マーシャ リング ライブラリに変換するときにコンテキストが必要であるため C4996 が生成されます、`System::String`を`const char *`です。  
  
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
  
## <a name="example-user-defined-deprecated-function"></a>例: ユーザー定義の非推奨機能  
  
独自のコードで非推奨属性を使用すると、不要になったの特定の関数の使用を推奨するときに、呼び出し元を警告します。 この例では、非推奨の関数が宣言されている行と関数が使用されている行は、C4996 が生成されます。  
  
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
   func1(1);    // C4996  
}  
```  
  

