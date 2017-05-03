---
title: "キャスト (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5247f6c7-6a0a-4021-97c9-21c868bd9455
caps.latest.revision: 15
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 15
---
# キャスト (C++/CX)
4 つの異なるキャスト演算子が [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 型に適用されます。[static\_cast Operator](../cpp/static-cast-operator.md)、[dynamic\_cast Operator](../cpp/dynamic-cast-operator.md)、[safe\_cast Operator](~/windows/safe-cast-cpp-component-extensions.md)、[reinterpret\_cast Operator](../cpp/reinterpret-cast-operator.md) です。`safe_cast` と `static_cast` は、変換を実行できない場合に例外をスローします。[static\_cast 演算子](../cpp/static-cast-operator.md) は、コンパイル時の型チェックも実行します。`dynamic_cast` は、型を変換できない場合 `nullptr` を返します。`reinterpret_cast` は NULL 以外の値を返しますが、その値が無効な場合があります。 この理由で、キャストが成功することがわかっている場合を除き、`reinterpret_cast` を使用しないことをお勧めします。 また、C スタイル キャストは [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] と同じであるため、[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] \(`reinterpret_cast`\) コード内では使用しないことをお勧めします。  
  
 コンパイラとランタイムは、暗黙的なキャストも実行します。たとえば、ボックス化操作で、パラメーターの型が `Object^` であるメソッドに値型または組み込み型が引数として渡される場合です。 理論的には、暗黙的なキャストは実行時に例外を引き起こしません。コンパイラが暗黙的な変換を実行できない場合は、コンパイル時にエラーが発生します。  
  
 [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)]は COM を抽象化したものであり、例外の代わりに HRESULT エラー コードを使用します。 一般に、[Platform::InvalidCastException](../cppcx/platform-invalidcastexception-class.md) は E\_NOINTERFACE の低レベルの COM エラーを表します。  
  
## static\_cast  
 コンパイル時に `static_cast` をチェックすることで、2 つの型の間に継承関係が存在するかどうかを判断します。 2 つの型に継承関係がない場合は、キャストによってコンパイラ エラーが発生します。  
  
 ref クラスの `static_cast` は、ランタイムのチェックも実行します。 ref クラスに対する `static_cast` はコンパイル時の検証でエラーになりませんが、実行時にはエラーになります。この場合、`Platform::InvalidCastException` がスローされます。 一般的に、このような例外を処理する必要はありません。ほとんどの例外は常に、開発時およびテスト時に解決できるプログラミング エラーを示しているためです。  
  
 2 つの型の間の関係をコードが明示的に宣言し、したがってキャストが機能することを確信している場合は、`static_cast` を使用します。  
  
```  
interface class A{}; public ref class Class1 sealed : A { }; ... A^ obj = ref new Class1(); // Class1 is an A // You know obj is a Class1. The compiler verifies that this is possible, and in C++/CX a run-time check is also performed. Class1^ c = static_cast<Class1^>(obj);  
  
```  
  
## safe\_cast  
 `safe_cast` 演算子は [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)]の一部です。 変換が失敗すると、実行時の型チェックを実行して `Platform::InvalidCastException` をスローします。 ランタイム エラーが例外条件を示している場合は `safe_cast` を使用します。`safe_cast` の主な目的は、開発フェーズおよびテスト フェーズにおけるプログラミング エラーを発生時点で識別しやすくすることです。 ハンドルされていない例外自体がエラーの位置を示しているため、例外を処理する必要はありません。  
  
 コードが関係を宣言していないが、キャストが機能することを確信している場合は、safe\_cast を使用します。  
  
```  
  
// A and B are not related interface class A{}; interface class B{}; public ref class Class1 sealed : A, B { }; ... A^ obj = ref new Class1(); // You know that obj’s backing type implements A and B, but // the compiler can’t tell this by comparing A and B. The run-time type check succeeds. B^ obj2 = safe_cast<B^>(obj);  
  
```  
  
## dynamic\_cast  
 `dynamic_cast` を使用するのは、オブジェクト \(具体的にはハット "^"\) をより強い派生型にキャストするときに、ターゲット オブジェクトが `nullptr` になる可能性があるか、キャストが失敗する可能性があり、その状況を例外ではなく標準のコード パスとして処理する必要がある場合です。 たとえば、**\[Windows Store Blank App\] \(Windows ストアの空のアプリケーション\)** プロジェクト テンプレートの場合、`OnLaunched` の `app.xamp.cpp` メソッドによって `dynamic_cast` を使用してアプリ ウィンドウにコンテンツが含まれているかどうかをテストします。 コンテンツが含まれていなくても、エラーではありません。これは予期された状態です。`Windows::Current::Content` は `Windows::UI::XAML::UIElement` であり、継承階層内のより強い派生型である `Windows::UI.XAML::Controls::Frame` への変換が実行されます。  
  
```  
void App::OnLaunched(Windows::ApplicationModel::Activation::LaunchActivatedEventArgs^ args) { auto rootFrame = dynamic_cast<Frame^>(Window::Current->Content); // Do not repeat app initialization when the window already has content, // just ensure that the window is active if (rootFrame == nullptr) { // Create a Frame to act as the navigation context and associate it with // a SuspensionManager key rootFrame = ref new Frame(); ...  
```  
  
 `dynamic_cast` のもう 1 つの用途は、ボックス化された値型を持つかどうかを判断するために `Object^` を調べることです。 この場合、`dynamic_cast<Platform::Box>` または `dynamic_cast<Platform::IBox>` を試行します。  
  
 **dynamic\_cast と追跡参照 \(%\)**  
  
 `dynamic_cast` を追跡参照に適用することもできますが、この場合キャストは `safe_cast` と同様に動作します。 追跡参照は `Platform::InvalidCastException` の値を持つことができないため、エラーが発生した場合は `nullptr` をスローします。  
  
## reinterpret\_cast  
 [reinterpret\_cast](../cpp/reinterpret-cast-operator.md) を使用しないことをお勧めします。コンパイル時のチェックと、ランタイム チェックのどちらも実行されないためです。 最悪の状況では、`reinterpret_cast` を使用すると開発時にプログラミング エラーが検出されず、プログラムの動作に軽度または致命的なエラーが発生するおそれがあります。 したがって、関係のない型の間でキャストを実行する必要があり、そのキャストが正常に実行される確証があるという非常にまれな状況でのみ、`reinterpret_cast` を使用することをお勧めします。 まれな使用例の 1 つは、[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)]を基になる ABI の型に変換する場合です。この場合は、オブジェクトに対する参照カウントが管理されています。 この作業を行うには、[ComPtr クラス](../windows/comptr-class.md) のスマート ポインターを使用することをお勧めします。 それ以外の場合、特にインターフェイスに対して Release を呼び出す必要があります。 次の例では、ref クラスを `IInspectable*` にキャストする方法を示します。  
  
```  
  
#include <wrl.h> using namespace Microsoft::WRL; auto winRtObject = ref new SomeWinRTType(); ComPtr<IInspectable> inspectable = reinterpret_cast<IInspectable*>(obj2); ...  
  
```  
  
 `reinterpret_cast` を使用して [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)]のインターフェイスを別のインターフェイスに変換すると、オブジェクトを 2 回解放することになります。 したがって、[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)]以外のインターフェイスを変換する場合にのみ、このキャストを使用します。  
  
 **ABI の型**  
  
-   ABI の型は、Windows SDK のヘッダーに置かれます。 判別しやすいように、ヘッダーは名前空間にちなんだ名前が付けられています \(`windows.storage.h` など\)。  
  
-   ABI の型は、`ABI::Windows::Storage::Streams::IBuffer*` のような特殊な ABI 名前空間に置かれます。  
  
-   [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)]のインターフェイス型と、それに対応する ABI の型との変換は常に安全です \(たとえば `IBuffer^` から `ABI::IBuffer*`\)。  
  
-   [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)]のランタイム クラスは、常に `IInspectable*` または既定のインターフェイス \(わかっている場合\) に変換する必要があります。  
  
-   ABI の型への変換後は、その型の有効期間を管理し、COM 規則に従う必要があります。 ABI のポインターの有効期間管理を容易にするために、`WRL::ComPtr` を使用することをお勧めします。  
  
 次の表に、`reinterpret_cast`を使用しても安全な状況の概要を示します。 どの状況でも、キャストは両方向とも安全です。  
  
|||  
|-|-|  
|HSTRING|String^|  
|HSTRING\*|String^\*|  
|IInspectable\*|Object^|  
|IInspectable\*\*|Object^\*|  
|IInspectable\-derived\-type\*|same\-interface\-from\-winmd^|  
|IInspectable\-derived\-type\*\*|same\-interface\-from\-winmd^\*|  
|IDefault\-interface\-of\-RuntimeClass\*|same\-RefClass\-from\-winmd^|  
|IDefault\-interface\-of\-RuntimeClass\*\*|same\-RefClass\-from\-winmd^\*|  
  
## 参照  
 [型システム](../cppcx/type-system-c-cx.md)   
 [Visual C\+\+ の言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)   
 [名前空間参照](../cppcx/namespaces-reference-c-cx.md)