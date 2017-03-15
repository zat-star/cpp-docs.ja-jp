---
title: "リンカ ツール エラー LNK2019 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2019
dev_langs:
- C++
helpviewer_keywords:
- nochkclr.obj
- LNK2019
- _check_commonlanguageruntime_version
ms.assetid: 4392be92-195c-4eb2-bd4d-49cfac3ca291
caps.latest.revision: 39
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
ms.sourcegitcommit: 6cad5222fb0d97594d5b13b5cf8903eb2934ee88
ms.openlocfilehash: 86b43f2688b6e1dbfb39dfec681ca9adafd2c093
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk2019"></a>リンカ ツール エラー LNK2019
未解決の外部シンボル 'symbol' が関数 'function' で参照されました。  
  
 関数 "`symbol`" で使用されている外部シンボル "`function`" の定義をリンカーが見つけることができませんでした。  
  
 このエラーを引き起こす可能性のある問題は多数あります。 このトピックは、原因を特定し、解決策を見つけるために役立ちます。  
  
 A*シンボル*コンパイラを使用して関数やグローバル変数の名前を指定します。 *外部シンボル*別のソースまたはオブジェクト ファイルで定義されているシンボルへの参照に使用される名前を指定します。 リンカーでする必要があります*解決*、またはすべてのアプリケーションまたは DLL にリンクされている場合は、コンパイルされる各ファイルで使用されるグローバル変数または関数の外部シンボルの定義を検索します。 リンカーは、リンクするどのファイルからも外部シンボルに対応する定義を見つけられない場合に、LNK2019 を生成します。  
  
 このエラーは、シンボルの定義を持つオブジェクトまたはライブラリ ファイルがビルドに含まれていない場合に発生することができます。 また、リンカーが検索シンボル名がシンボルを定義しているライブラリまたはオブジェクトのファイルでの名前と一致しない場合にも発生することができます。 これは、呼び出し元のコード内の名前が正しくない、さまざまな大文字と小文字を使用して、別の呼び出し規約を使用または異なるパラメーターを指定する場合に発生することができます。  
  
 C++ リンケージを使用するコードを使用して[名前の装飾](../../error-messages/tool-errors/name-decoration.md)とも呼ばれる、*名前マングル*、変数または関数の型と、シンボル名では呼び出し元の規則に関する追加情報をエンコードします。 *装飾名* は、外部シンボルを解決するためにリンカーが検索する名前です。 型情報では、シンボルの装飾名の一部になる、ためにが使用されている外部シンボルの宣言が定義されているシンボルの宣言と一致しない場合は、LNK2019 が発生します。 エラーの原因を確認するために、エラー メッセージが両方"フレンドリ名が表示、"でソース コード、および未解決の外部シンボルの装飾名をかっこで使用する名前。 その他の装飾名と比較することができる、装飾名を変換する方法を理解する必要はありません。  
  
 **一般的な問題**  
  
 LNK2019 エラーが発生する一般的な問題には次のものがあります。  
  
-   **オブジェクト ファイルまたはシンボルの定義を含むライブラリがリンクされていません。** Visual Studio で、定義を含むソース ファイルがビルドし、プロジェクトの一部としてリンクされたことを確認します。 コマンド ラインで、定義を含むソース ファイルがコンパイルされていると、リンクするファイルの一覧で、生成されたオブジェクト ファイルが含まれていることを確認します。  
  
-   **シンボルの宣言では、シンボルの定義と同じスペルはありません。** 正しいスペルおよび大文字と小文字が、宣言と定義の両方で使用され、シンボルの使用方法またはと呼ばれる任意の場所を確認します。  
  
-   **関数を使用しますが、型またはパラメーターの数は、関数定義と一致しません。** 関数の宣言は、定義と一致している必要があります。 関数の呼び出しが宣言と一致することと、宣言が定義と一致することを確認します。 また、テンプレート関数を呼び出すコードでも、テンプレート関数の宣言を一致させ、定義と同じテンプレート パラメーターを組み込む必要があります。 テンプレート宣言の不一致の例は、サンプルの例で LNK2019e.cpp を参照してください。  
  
-   **関数または変数が宣言されてが定義されていません。** これは通常、ヘッダー ファイルで、宣言が存在しますが、対応する定義を実装していないことを意味します。 メンバー関数または静的データ メンバーの場合、実装にはクラス スコープ セレクターを含める必要があります。 例については、次を参照してください。[見つからない関数本体または変数](../../error-messages/tool-errors/missing-function-body-or-variable.md)します。  
  
-   **呼び出し元の規則が関数宣言と関数定義で異なるです。** 呼び出し規約 ([_ _cdecl](../../cpp/cdecl.md)、 [_ _stdcall](../../cpp/stdcall.md)、 [_ _fastcall](../../cpp/fastcall.md)、または[_ _vectorcall](../../cpp/vectorcall.md)) は、装飾名の一部としてエンコードします。 呼び出し規則が同じであることを確認します。  
  
-   **シンボルは C ファイルで定義されているが、C++ ファイルで extern"C"を使用せずに宣言されました。** C としてコンパイルされたファイルで定義されているシンボルがある別の装飾名を使用する C++ ファイルで宣言されたシンボル、 [extern"C"](../../cpp/using-extern-to-specify-linkage.md)修飾子です。 シンボルごとに宣言がコンパイル リンケージと一致することを確認してください。  
  
     同様に、C++ ファイルで定義されているシンボルを C プログラムで使用する場合にも、定義の中で `extern "C"` を使用します。  
  
-   **シンボルは static として定義されているし、後で、ファイルの外部から参照します。** C++ では、C とは異なり[グローバル定数](../../error-messages/tool-errors/global-constants-in-cpp.md)が`static`リンケージ。 この制限を回避するには、 `const` 初期化をヘッダー ファイルに組み込み、そのヘッダーを .cpp ファイルにインクルードします。あるいは、変数を非定数にし、定数参照を使用してそれにアクセスすることもできます。  
  
-   **クラスの静的メンバーが定義されていません。** 静的クラス メンバーは一意に定義する必要があります。そうしないと、単一定義規則に違反します。 インラインで定義できない静的クラス メンバーは、完全修飾名を使用して&1; つのソース ファイル内で定義する必要があります。 それがまったく定義されていない場合、リンカーは LNK2019 を生成します。  
  
-   **ビルドの依存関係は、ソリューションにプロジェクトの依存関係としてのみ定義されます。** 前のバージョンの [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] では、このレベルの依存関係で十分でした。 ただし、Visual Studio 2010 以降で、[!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]必要があります、[プロジェクト間参照](/visualstudio/ide/managing-references-in-a-project)します。 プロジェクトにプロジェクト間の参照がない場合は、このリンカー エラーが発生することがあります。 この問題を修正するには、プロジェクト間参照を追加します。  
  
-   **Windows アプリケーション用の設定を使用してコンソール アプリケーションをビルドしている。** エラー メッセージは次のような場合**WinMain が関数で参照されている未解決の外部シンボル**`function_name`を使用してリンク**/subsystem:console」と入力**の代わりに**/SUBSYSTEM:WINDOWS**します。 この設定の詳細については、および Visual Studio でこのプロパティを設定する方法については、「 [/SUBSYSTEM (サブシステムの指定)](../../build/reference/subsystem-specify-subsystem.md)します。  
  
-   **関数のインライン化別のソース ファイル内の別のコンパイラ オプションを使用するとします。** .cpp ファイルで定義されている関数のインライン展開を使用している場合に、異なるソース ファイルで関数のインライン展開のコンパイラ オプションが混在していると、LNK2019 が発生することがあります。 詳細については、次を参照してください。[関数インライン展開の問題](../../error-messages/tool-errors/function-inlining-problems.md)します。  
  
-   **自動変数を使用して、そのスコープ外です。** 自動変数 (関数スコープ) は、その関数のスコープ内でのみ使用できます。 これらの変数を `extern` として宣言して他のソース ファイルで使用することはできません。 例については、次を参照してください。 [(関数スコープ) の自動変数](../../error-messages/tool-errors/automatic-function-scope-variables.md)します。  
  
-   **呼び出しているかをターゲット アーキテクチャでサポートされていない組み込み関数に引数の型を渡します。** など、AVX2 を使用しても、指定しない場合、 [/ARCH:AVX2](../../build/reference/arch-x86.md)コンパイラ オプションの組み込みを外部関数に、コンパイラと見なします。 コンパイラは、インライン命令を生成するのではなく、組み込みと同じ名前で外部シンボルへの呼び出しを生成します。 リンカーは、欠落しているこの関数の定義を検索しようとして、LNK2019 を生成します。 ターゲット アーキテクチャでサポートされている組み込み関数と型のみを使用していることを確認してください。  
  
-   **しないコードにネイティブの wchar_t を使用するコードを混在させること。** Visual C++ 2005 で行われた C++ 言語への準拠作業により、 `wchar_t` は既定でネイティブ型になりました。 使用する必要があります、 [/Zc:wchar_t-](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md)コンパイラ オプションを Visual C の以前のバージョンを使用してコンパイルされたライブラリとオブジェクトのファイルと互換性のあるコードを生成します。 すべてのファイルで同じ **/Zc:wchar_t** 設定を使用してコンパイルされていない場合は、型の参照が互換性のある型に解決されないことがあります。 すべてのライブラリ ファイルとオブジェクト ファイル内の `wchar_t` の型に互換性があることを検証し、使用する型を更新するか、コンパイル時に使用する **/Zc:wchar_t** の設定を一貫させるようにしてください。  
  
 LNK2019 に関する考えられる原因と解決策の詳細については、「スタック オーバーフロー」の質問「 [未定義の参照/未解決の外部シンボルというエラーの意味と解決方法を教えてください](http://stackoverflow.com/q/12573816/2002113)」を参照してください。  
  
 **診断ツール**  
  
 リンカーが特定のシンボル定義を見つけられない理由を調べるのは難しい問題になることがあります。 多くの場合、問題は、ビルドにコードを含めていなかったことか、ビルド オプションの違いによって外部シンボルに対して異なる装飾名が作成されたことです。 LNK2019 エラーを診断するために役立ついくつかのツールとオプションを紹介します。  
  
-   [/Verbose](../../build/reference/verbose-print-progress-messages.md)リンカー オプションを使用して、どのファイルをリンカーの参照を判断できます。 これは、シンボルの定義の入ったファイルがビルドに含まれているかどうかを確認するために役立ちます。  
  
-   [/Exports](../../build/reference/dash-exports.md)と[/symbols](../../build/reference/symbols.md) DUMPBIN ユーティリティのオプションを使用して、どのシンボルが、.dll、オブジェクトまたはライブラリ ファイルで定義を発見できます。 エクスポートされた装飾名が、リンカーが検索する装飾名と一致することを確認してください。  
  
-   UNDNAME ユーティリティを使用すると、装飾名に対応する、装飾されていない外部シンボルを表示できます。  
  
 **例**  
  
 ここでは、LNK2019 エラーが発生するコードの例を、そのエラーを修正する方法に関する情報と一緒に紹介します。  
  
 **シンボルが宣言されているが、定義されていません**  
  
 次の例では、外部シンボルを宣言していますが、定義していないため、LNK2019 が発生します。  
  
```cpp  
// LNK2019.cpp  
// Compile by using: cl /EHsc LNK2019.cpp  
// LNK2019 expected  
extern char B[100];   // B is not available to the linker  
int main() {  
   B[0] = ' ';   // LNK2019  
}  
```  
  
 別の例を示します。  
  
```cpp  
// LNK2019c.cpp  
// Compile by using: cl /EHsc LNK2019c.cpp  
// LNK2019 expected  
extern int i;  
extern void g();  
void f() {  
   i++;  
   g();  
}  
int main() {}  
```  
  
 `i` と `g` がビルド内のどのファイルでも定義されていない場合、リンカーは LNK2019 を生成します。 このエラーを修正するには、定義を含むソース コード ファイルをコンパイルの一部に組み込みます。 または、定義を含む .obj ファイルまたは .lib ファイルをリンカーに渡すこともできます。  
  
 **静的データ メンバーが宣言されているが定義されていません**  
  
 LNK2019 は、静的データ メンバーが宣言されているものの定義がなされていない場合に発生することもあります。 次の例は LNK2019 を生成します。その修正方法も示しています。  
  
```cpp  
// LNK2019b.cpp  
// Compile by using: cl /EHsc LNK2019b.cpp  
// LNK2019 expected  
struct C {  
   static int s;  
};  
  
// Uncomment the following line to fix the error.  
// int C::s;  
  
int main() {  
   C c;  
   C::s = 1;  
}  
```  
  
 **パラメーターの宣言は定義と一致しません**  
  
 テンプレート関数を呼び出すコードには、対応するテンプレート関数宣言が必要です。 宣言には、定義と同じテンプレート パラメーターを含める必要があります。 次の例では、ユーザー定義の演算子で LNK2019 が発生します。その修正方法も示しています。  
  
```cpp  
// LNK2019e.cpp  
// compile by using: cl /EHsc LNK2019e.cpp  
// LNK2019 expected  
#include <iostream>  
using namespace std;  
  
template<class T> class   
Test {  
   // The operator<< declaration does not match the definition below:  
   friend ostream& operator<<(ostream&, Test&);  
   // To fix, replace the line above with the following:  
   // template<typename T> friend ostream& operator<<(ostream&, Test<T>&);  
};  
  
template<typename T>  
ostream& operator<<(ostream& os, Test<T>& tt) {  
   return os;  
}  
  
int main() {  
   Test<int> t;  
   cout << "Test: " << t << endl;   // LNK2019 unresolved external  
}  
```  
  
 **一貫性のない wchar_t 型の定義**  
  
 次の例から作成する DLL には、 `WCHAR`を使用しており、それが `wchar_t`に解決されるエクスポートが含まれます。  
  
```cpp  
// LNK2019g.cpp  
// compile with: cl /EHsc /LD LNK2019g.cpp  
#include "windows.h"  
// WCHAR resolves to wchar_t  
__declspec(dllexport) void func(WCHAR*) {}  
```  
  
 次の例は、前の例で、DLL を使用し、short * と WCHAR 型が署名されていないために、lnk2019\*が一致しません。  
  
```cpp  
// LNK2019h.cpp  
// compile by using: cl /EHsc LNK2019h LNK2019g.lib  
// LNK2019 expected  
__declspec(dllimport) void func(unsigned short*);  
  
int main() {  
   func(0);  
}  
```  
  
 このエラーを解決するには、次のように変更します。`unsigned short`に`wchar_t`または`WCHAR`、を使用して、LNK2019g.cpp をコンパイルまたは**/Zc:wchar_t-**します。
