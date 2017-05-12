---
title: "スレッドとマーシャリング (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4451"
helpviewer_keywords: 
  - "スレッド処理の問題、C++/CX"
  - "アジリティ、C++/CX"
  - "C++/CX、スレッド処理の問題"
ms.assetid: 83e9ca1d-5107-4194-ae6f-e01bd928c614
caps.latest.revision: 17
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 17
---
# スレッドとマーシャリング (C++/CX)
ほとんどの場合、標準 C\+\+ オブジェクトと同様に、[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] クラスのインスタンスにはどのスレッドからでもアクセスできます。 このようなクラスを "アジャイル" と呼びます。 ただし、Windows に付属する一部の [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] クラスは非アジャイルであり、標準 C\+\+ オブジェクトではなく、COM オブジェクトと同様に使用する必要があります。 非アジャイル クラスを使用するために COM の専門家になる必要はありませんが、クラスのスレッド モデルとマーシャリング動作を考慮する必要があります。 この技術情報では、非アジャイル クラスのインスタンスを使用する必要があるまれなシナリオの背景について説明し、ガイダンスを示します。  
  
## スレッド モデルとマーシャリング動作  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] クラスは、適用される 2 つの属性が示すとおり、さまざまな方法で同時実行スレッド アクセスをサポートできます。  
  
-   `ThreadingModel` 属性には、`ThreadingModel` 列挙体によって定義された STA、MTA、Both のいずれかの値を指定できます。  
  
-   `MarshallingBehavior` 属性には、`MarshallingType` 列挙体によって定義された Agile、None、Standard のいずれかの値を指定できます。  
  
 `ThreadingModel` 属性では、クラスをアクティブにしたときに読み込む場所を指定します。クラスの読み込み先として、ユーザー インターフェイス スレッド \(STA\) コンテキストのみ、バックグラウンド スレッド \(MTA\) コンテキストのみ、またはオブジェクトを作成するスレッドのコンテキスト \(Both\) を指定できます。`MarshallingBehavior` 属性値は、さまざまなスレッド コンテキストにおけるオブジェクトの動作を指しますが、ほとんどの場合、これらの値を詳しく理解する必要はありません。  Windows API が提供するクラスの約 90 % には、`ThreadingModel`\=Both と `MarshallingType`Agile があります。 これは、低レベルのスレッドの詳細を透過的および効率的に処理できることを意味します。`ref new` を使用して "agile" クラスを作成する場合、メイン アプリケーションのスレッドまたは 1 つ以上のワーカー スレッドから、そのクラスのメソッドを呼び出せます。  つまり、Windows から提供されたかサード パーティから提供されたかに関係なく、コード内の任意の場所でアジャイル クラスを使用できます。 クラスのスレッド モデルやマーシャリング動作について考慮する必要はありません。  
  
## [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] コンポーネントの使用  
 [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] アプリを作成するときに、アジャイル コンポーネントと非アジャイル コンポーネントの両方とやり取りする場合があります。 非アジャイル コンポーネントとやり取りすると、次の警告が表示されることがあります。  
  
### 非アジャイル クラス \(C4451\) 使用時のコンパイラの警告  
 さまざまな理由で、一部のクラスはアジャイルにすることができません。 ユーザー インターフェイス スレッドとバックグラウンド スレッドの両方から非アジャイル クラスのインスタンスにアクセスする場合は、実行時の動作が正しいことを注意深く確認する必要があります。 アプリケーション内のグローバル スコープで非アジャイルのランタイム クラスをインスタンス化する場合、またはそれ自体がアジャイルとマーク付けされている ref クラスのクラス メンバーとして非アジャイル型を宣言する場合、Visual C\+\+ コンパイラは警告を発します。  
  
 非アジャイル クラスで扱いが最も簡単なのは、`ThreadingModel`\=Bothおよび `MarshallingType`\=Standard が指定されているものです。  これらのクラスをアジャイルにするには、単に `Agile<T>` ヘルパー クラスを使用します。   次の例は、`Windows::Security::Credentials::UI::CredentialPickerOptions^` 型の非アジャイル オブジェクトの宣言、および結果として生成されるコンパイラの警告を示しています。  
  
```  
  
ref class MyOptions  
    {  
    public:  
        property Windows::Security::Credentials::UI::CredentialPickerOptions^ Options  
  
        {  
            Windows::Security::Credentials::UI::CredentialPickerOptions^ get()   
            {  
                return _myOptions;  
            }  
        }  
    private:  
        Windows::Security::Credentials::UI::CredentialPickerOptions^ _myOptions;  
    };  
```  
  
 次の警告が出されます。  
  
> `Warning 1 warning C4451: 'Platform::Agile<T>::_object' : Usage of ref class 'Windows::Security::Credentials::UI::CredentialPickerOptions' inside this context can lead to invalid marshaling of object across contexts. Consider using 'Platform::Agile<Windows::Security::Credentials::UI::CredentialPickerOptions>' instead`  
  
 マーシャリング動作が「標準」のオブジェクトへの参照を \(メンバー スコープまたはグローバル スコープで\) 追加する場合、コンパイラは、`Platform::Agile<T>` で型をラップするように勧める警告を発行します。`Consider using 'Platform::Agile<Windows::Security::Credentials::UI::CredentialPickerOptions>' instead``Agile<T>` を使用すると、他のすべてのアジャイル クラスと同じようにクラスを使用できます。 次のような状況では、`Platform::Agile<T>` を使用します。  
  
-   非アジャイル変数は、グローバル スコープで宣言されます。  
  
-   非アジャイル変数はクラス スコープで宣言されます。使用コードが、ポインターを忍び込ませる、つまり、正しいマーシャリングなしで別のアパートメントで使用する可能性があります。  
  
 このどちらの状況にも該当しない場合は、含んでいるクラスを非アジャイルとしてマークできます。 つまり、非アジャイル クラスでは非アジャイル オブジェクトだけを直接保持し、アジャイル クラスでは Platform::Agile\<T\> を使用して非アジャイル オブジェクトを保持します。  
  
 次の例は、警告を安全に無視できるように、`Agile<T>` を使用する方法を示しています。  
  
```  
  
#include <agile.h>  
ref class MyOptions  
    {  
    public:  
        property Windows::Security::Credentials::UI::CredentialPickerOptions^ Options  
  
        {  
            Windows::Security::Credentials::UI::CredentialPickerOptions^ get()   
            {  
                return m_myOptions.Get();  
            }  
        }  
    private:  
        Platform::Agile<Windows::Security::Credentials::UI::CredentialPickerOptions^> m_myOptions;  
  
    };  
  
```  
  
 `Agile` を ref クラスの戻り値またはパラメーターとして渡すことはできません。`Agile<T>::Get()` メソッドは、パブリック メソッドまたはプロパティでアプリケーション バイナリ インターフェイス \(ABI\) 間で渡せるオブジェクトへのハンドル \(^\) を返します。  
  
 Visual C\+\+ では、マーシャリング動作が「None」に指定されている内部プロシージャ [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] クラスへの参照を作成すると、コンパイラは警告 C4451 を発行しますが、`Platform::Agile<T>` の使用を検討することは勧めません。  コンパイラは、この警告を超えるヘルプを提供できます。従って、クラスを正しく使用して、コードがユーザー インターフェイス スレッドからのみ STA コンポーネントを呼び出すこと、およびバックグラウンド スレッドからのみ MTA コンポーネントを呼び出すことを確認するのはユーザーの責任になります。  
  
## [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] アジャイル コンポーネントの作成  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] で ref クラスを定義する場合、そのクラスは既定でアジャイルです。つまり、`ThreadingModel`\=Both と `MarshallingType`\=Agile が指定されています。[!INCLUDE[cppwrl](../cppcx/includes/cppwrl-md.md)] を使用する場合は、`FtmBase` を使用する `FreeThreadedMarshaller` から派生することで、クラスをアジャイルにできます。`ThreadingModel`\=Both または `ThreadingModel`\=MTA が指定されたクラスを作成する場合、クラスがスレッドセーフであることを確認します。 詳細については、「[オブジェクト \(WRL\) の作成と利用](http://msdn.microsoft.com/ja-jp/d5e42216-e888-4f1f-865a-b5ccd0def73e)」を参照してください。  
  
 ref クラスのスレッド モデルとマーシャリングの動作を変更できます。 ただし、クラスを非アジャイルにする変更を加えた場合は、その変更に関連付けられた影響を理解する必要があります。  
  
 次の例は、`MarshalingBehavior` クラス ライブラリのランタイム クラスに、`ThreadingModel` 属性と [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 属性を適用する方法を示しています。 アプリケーションが DLL を使用し、`ref new` キーワードを使用して `MySTAClass` クラス オブジェクトをアクティベートする場合、オブジェクトはシングル スレッド アパートメントでアクティベートされ、マーシャリングをサポートしません。  
  
```  
using namespace Windows::Foundation::Metadata;  
using namespace Platform;  
  
[Threading(ThreadingModel::STA)]  
[MarshalingBehavior(MarshalingType::None)]   
public ref class MySTAClass  
{  
};  
  
```  
  
 シールされていないクラスでは、マーシャリング属性とスレッド属性が設定されている必要があります。これにより、コンパイラは派生クラスでこれらの属性の値が同じであることを検証できます。 クラスでこれらの属性が明示的に設定されていない場合、コンパイラはエラーを生成し、コンパイルは失敗します。 次のいずれかの場合、シールされていないクラスから派生したクラスでコンパイラ エラーが生成されます。  
  
-   `ThreadingModel` および `MarshallingBehavior` 属性が派生クラスで定義されていない。  
  
-   派生クラスの `ThreadingModel` と `MarshallingBehavior` 属性の値が基底クラスの値と一致しない。  
  
 サードパーティの [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] コンポーネントで必要なスレッド情報とマーシャリング情報は、コンポーネントのアプリケーション マニフェスト登録情報で指定します。 すべての [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] コンポーネントをアジャイルにすることをお勧めします。 これにより、クライアント コードはアプリケーション内の任意のスレッドからコンポーネントを呼び出すことができます。また、それらの呼び出しは、マーシャリングがない直接呼び出しであるため、呼び出しのパフォーマンスが向上します。 この方法でクラスを作成する場合、クラスを使用するために、クライアント コードで `Platform::Agile<T>` を使用する必要はありません。  
  
## 参照  
 [\(NOTINBUILD\) 高度なトピック](http://msdn.microsoft.com/ja-jp/1ccff0cf-a6cc-47ef-a05f-eba6307b3ced)   
 [ThreadingModel](http://msdn.microsoft.com/library/windows/apps/xaml/windows.foundation.metadata.threadingmodel.aspx)   
 [MarshallingBehavior](http://msdn.microsoft.com/library/windows/apps/xaml/windows.foundation.metadata.marshalingbehaviorattribute.aspx)