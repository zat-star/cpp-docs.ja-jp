---
title: "event  (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "event"
  - "event_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "event keyword [C++]"
ms.assetid: c4998e42-883c-4419-bbf4-36cdc979dd27
caps.latest.revision: 34
caps.handback.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# event  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`event` キーワードを使用して、*イベント*を宣言します。イベントとは、登録済みのサブスクライバー \(*イベント ハンドラー*\) に重要な事態が発生したことを伝える通知です。  
  
## すべてのランタイム  
 C\+\+\/CX は、*イベント メンバー*または*イベント ブロック*の宣言をサポートします。  イベント メンバーは、イベント ブロックを宣言する簡単な表記法です。  既定ではイベント メンバーは、イベント ブロックで明示的に宣言される、`add()` 関数、`remove()` 関数、および `raise()` 関数を宣言します。  イベント メンバーの関数をカスタマイズするには、イベント ブロックを宣言した後で必要な関数をオーバーライドします。  
  
 **構文**  
  
```  
  
// event data member  
modifier event delegate^ event_name;     
  
// event block  
modifier event delegate^ event_name   
{  
   modifier return_value add(delegate^ name);  
   modifier void remove(delegate^ name);  
   modifier void raise(parameters);  
}  
```  
  
 **パラメーター**  
  
 *modifier*  
 イベントの宣言またはイベントのアクセサー メソッドで使用できる修飾子。  有効な値は、`static` と `virtual` です。  
  
 *delegate*  
 [デリゲート](../windows/delegate-cpp-component-extensions.md)。このデリゲートのシグネチャがイベント ハンドラーと一致する必要があります。  
  
 *event\_name*  
 イベントの名前です。  
  
 *return\_value*  
 イベントのアクセサー メソッドの戻り値。  検証可能にするために、戻り値の型は `void` である必要があります。  
  
 *parameters*  
 \(省略可能\) *delegate* パラメーターのシグネチャと一致する、`raise` メソッドのパラメーター。  
  
 **コメント**  
  
 イベントとは、イベントのトリガーに応答する、デリゲートとメンバー関数 \(イベント ハンドラー\) の間の関連付けです。イベントによって、任意のクラスのクライアントが、基になるデリゲートのシグネチャおよび戻り値の型に準拠したメソッドを登録できます。  
  
 イベントの宣言には 2 つの種類があります。  
  
 *イベント データ メンバー*  
 コンパイラが自動的にデリゲート型のメンバーの形でイベント用のストレージを作成し、内部の `add()`、`remove()`、および `raise()` の各メンバー関数を作成します。  イベント データ メンバーはクラス内で宣言する必要があります。  デリゲートの戻り値の型と、イベント ハンドラーの戻り値の型が一致する必要があります。  
  
 *イベント ブロック*  
 イベント ブロックを使用して、`add()`、`remove()`、および `raise()` の各メソッドの動作を明示的に宣言し、カスタマイズすることができます。  
  
 `operators+=` および `operator-=` を使用して、イベント ハンドラーの追加と削除を行うことも、`add()` メソッドおよび `remove()` メソッドを明示的に呼び出すこともできます。  
  
 `event` は状況依存のキーワードです。詳細については、「[状況依存のキーワード](../windows/context-sensitive-keywords-cpp-component-extensions.md)」を参照してください。  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
  
### コメント  
 詳細については、「[イベント \(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh755799.aspx)」を参照してください。  
  
 イベント ハンドラーを追加した後で削除する場合は、追加操作で返される EventRegistrationToken 構造体を保存する必要があります。  その後の削除操作で、削除するイベント ハンドラーを識別するために、保存しておいた EventRegistrationToken 構造体を使用します。  
  
### 必要条件  
 コンパイラ オプション: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 `event` キーワードを使用して、イベントを宣言できます。  イベントは、何か重要なことが起きたときにクラスで通知するための手段です。  
  
 **構文**  
  
```  
  
// event data member  
modifier event delegate^ event_name;   
  
// event block  
modifier event delegate^ event_name   
{  
   modifier return_value add(delegate^ name);  
   modifier void remove(delegate^ name);  
   modifier void raise(parameters);  
}  
```  
  
 **パラメーター**  
  
 *modifier*  
 イベントの宣言またはイベントのアクセサー メソッドで使用できる修飾子。  有効な値は、`static` と `virtual` です。  
  
 *delegate*  
 [デリゲート](../windows/delegate-cpp-component-extensions.md)。このデリゲートのシグネチャがイベント ハンドラーと一致する必要があります。  
  
 *event\_name*  
 イベントの名前です。  
  
 *return\_value*  
 イベントのアクセサー メソッドの戻り値。  検証可能にするために、戻り値の型は `void` である必要があります。  
  
 *parameters*  
 \(省略可能\) *delegate* パラメーターのシグネチャと一致する、`raise` メソッドのパラメーター。  
  
 **コメント**  
  
 イベントとは、イベントのトリガーに応答する、デリゲートとメンバー関数 \(イベント ハンドラー\) の間の関連付けです。イベントによって、任意のクラスのクライアントが、基になるデリゲートのシグネチャおよび戻り値の型に準拠したメソッドを登録できます。  
  
 デリゲートには、イベントが発生したことをコードによって示すときに呼び出されるメソッドを 1 つ以上関連付けることができます。  プログラム内のイベントを、.NET Framework 共通言語ランタイムを対象とする他のプログラムで使用できるようにすることができます。  例については、「[別のアセンブリで定義されたイベントの発生](../misc/how-to-raise-events-defined-in-a-different-assembly.md)」を参照してください。  
  
 イベントの宣言には 2 つの種類があります。  
  
 *イベント データ メンバー*  
 データ メンバー イベントについては、コンパイラによってイベント用のストレージがデリゲート型のメンバーの形で作成されます。  イベント データ メンバーはクラス内で宣言する必要があります。  これは、単純なイベントとも呼ばれます \(下のコード サンプルを参照してください\)。  
  
 *イベント ブロック*  
 イベント ブロックを使用し、add、remove、および raise の各メソッドを実装することで、add、remove、および raise の各メソッドの動作をカスタマイズすることができます。  add、remove、および raise の各メソッドのシグネチャが、デリゲートのシグネチャと一致する必要があります。  イベント ブロック イベントはデータ メンバーではなく、データ メンバーとして使用した場合はコンパイル エラーが生成されます。  例については、「[イベント アクセサー メソッドの定義](../misc/how-to-define-event-accessor-methods.md)」を参照してください。  
  
 イベント ハンドラーの戻り値の型は、デリゲートの戻り値の型と一致する必要があります。  
  
 .NET Framework では、それ自身がメソッド \(つまり、対応するデリゲートの `Invoke` メソッド\) であるかのようにデータ メンバーを処理できます。  マネージ イベント データ メンバーを宣言するためのデリゲート型を事前に定義する必要があります。  これに対し、マネージ イベント メソッドは、まだ定義されていない場合、対応するマネージ デリゲートを暗黙的に定義します。  例については、このトピックの最後にあるコード サンプルを参照してください。  
  
 マネージ イベントを宣言するときは、演算子 \+\= および \-\= を使用してイベント ハンドラーを追加または削除したときに呼び出される追加アクセサーおよび削除アクセサーを指定できます。  add、remove、および raise の各メソッドを明示的に呼び出すことができます。  
  
 Visual C\+\+ でイベントを作成して使用するには、次の手順に従う必要があります。  
  
1.  デリゲートを作成または指定します。  独自のイベントを定義する場合は、`event` キーワードで使用するデリゲートが存在することも確認します。  イベントが .NET Framework などで事前に定義されている場合、そのイベントのコンシューマーにはデリゲートの名前を指定するだけでかまいません。  
  
2.  次のものを含むクラスを作成します。  
  
    -   デリゲートから作成されるイベント。  
  
    -   \(省略可能\) `event` キーワードで宣言されたデリゲートのインスタンスが存在することを検証するメソッド。  省略する場合、イベントを発生させるコード内にこのロジックを組み込む必要があります。  
  
    -   イベントを呼び出すメソッド。  このメソッドは一部の基本クラスの機能によってオーバーライドされる場合があります。  
  
     このクラスでイベントを定義します。  
  
3.  メソッドをイベントに接続するクラスを 1 つ以上定義します。  それぞれのクラスで、1 つ以上のメソッドを基本クラスのイベントと関連付けます。  
  
4.  イベントを使用します。  
  
    -   イベントの宣言を含むクラスのオブジェクトを作成します。  
  
    -   イベントの定義を含むクラスのオブジェクトを作成します。  
  
 [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] イベントの詳細については、次を参照してください。  
  
-   [インターフェイス内のイベント](../dotnet/how-to-use-events-in-cpp-cli.md)  
  
-   [add、remove、および raise の各メソッドの既定のアクセスのオーバーライド](../misc/how-to-override-default-access-of-add-remove-and-raise-methods.md)  
  
-   [イベントに対する複数のハンドラー](../misc/how-to-add-multiple-handlers-to-events.md)  
  
-   [マネージ仮想イベント](../misc/how-to-implement-managed-virtual-events.md)  
  
-   [イベントのアクセサー メソッド](../misc/how-to-define-event-accessor-methods.md)  
  
-   [静的イベント](../Topic/How%20to:%20Define%20and%20Use%20Static%20Events.md)  
  
-   [別のアセンブリで定義されたイベントの発生](../misc/how-to-raise-events-defined-in-a-different-assembly.md)  
  
-   [抽象イベント](../misc/how-to-implement-abstract-events.md)  
  
### 必要条件  
 コンパイラ オプション: **\/clr**  
  
### 使用例  
 **例**  
  
 次のコード例では、デリゲート、イベント、およびイベント ハンドラーのペアを宣言します。次に、イベント ハンドラーをサブスクライブ \(追加\) し、そのイベント ハンドラーを呼び出した後、サブスクライブ解除 \(削除\) します。  
  
```  
// mcppv2_events.cpp  
// compile with: /clr  
using namespace System;  
  
// declare delegates  
delegate void ClickEventHandler(int, double);  
delegate void DblClickEventHandler(String^);  
  
// class that defines events  
ref class EventSource {  
public:  
   event ClickEventHandler^ OnClick;   // declare the event OnClick  
   event DblClickEventHandler^ OnDblClick;   // declare OnDblClick  
  
   void FireEvents() {  
      // raises events  
      OnClick(7, 3.14159);  
      OnDblClick("Hello");  
   }  
};  
  
// class that defines methods that will called when event occurs  
ref class EventReceiver {  
public:  
   void OnMyClick(int i, double d) {  
      Console::WriteLine("OnClick: {0}, {1}", i, d);  
   }  
  
   void OnMyDblClick(String^ str) {  
      Console::WriteLine("OnDblClick: {0}", str);  
   }  
};  
  
int main() {  
   EventSource ^ MyEventSource = gcnew EventSource();  
   EventReceiver^ MyEventReceiver = gcnew EventReceiver();  
  
   // hook handler to event  
   MyEventSource->OnClick += gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);  
   MyEventSource->OnDblClick += gcnew DblClickEventHandler(MyEventReceiver, &EventReceiver::OnMyDblClick);  
  
   // invoke events  
   MyEventSource->FireEvents();  
  
   // unhook handler to event  
   MyEventSource->OnClick -= gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);  
   MyEventSource->OnDblClick -= gcnew DblClickEventHandler(MyEventReceiver, &EventReceiver::OnMyDblClick);  
}  
```  
  
 **出力**  
  
  **OnClick: 7, 3.14159**  
 **OnDblClick: Hello** **例**  
  
 次のコード例では、単純なイベントの `raise` メソッドを生成するために使用するロジックを示しています。イベントに 1 つ以上のサブスクライバーがある場合、`raise` メソッドを呼び出すと、暗黙的または明示的にデリゲートが呼び出されます。  デリゲートの戻り値の型が `void` ではなく、なおかつイベント サブスクライバーが存在しない場合は、`raise` メソッドはデリゲート型の既定値を返します。  イベント サブスクライバーが存在しない場合に `raise` メソッドを呼び出すと、単純に返されるだけで、例外は発生しません。  デリゲートの戻り値の型が `void` 以外の場合、デリゲート型が返されます。  
  
```  
// trivial_events.cpp  
// compile with: /clr /c  
using namespace System;  
public delegate int Del();  
public ref struct C {  
   int i;  
   event Del^ MyEvent;  
  
   void FireEvent() {  
      i = MyEvent();  
   }  
};  
  
ref struct EventReceiver {  
   int OnMyClick() { return 0; }  
};  
  
int main() {  
   C c;  
   c.i = 687;  
  
   c.FireEvent();  
   Console::WriteLine(c.i);  
   c.i = 688;  
  
   EventReceiver^ MyEventReceiver = gcnew EventReceiver();  
   c.MyEvent += gcnew Del(MyEventReceiver, &EventReceiver::OnMyClick);  
   Console::WriteLine(c.i);     
}  
```  
  
 **出力**  
  
  **0**  
 **688**   
## 参照  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)