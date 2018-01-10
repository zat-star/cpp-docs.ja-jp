---
title: "例外 (C + + CX) |Microsoft ドキュメント"
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6cbdc1f1-e4d7-4707-a670-86365146432f
caps.latest.revision: "22"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f578271823b0253dfa3defcb126bec251749a2dc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="exceptions-ccx"></a>例外 (C++/CX)

エラー処理に C + + CX は例外に基づいてです。 最も基本的なレベルでは、Windows ランタイム コンポーネントは、HRESULT 値としてエラーを報告します。 C + + CX、これらの値は HRESULT 値とプログラムでアクセスできる文字列による説明を含む厳密に型指定の例外に変換されます。  例外は、 `ref class` から派生した `Platform::Exception`として実装されます。  `Platform` 名前空間は、ほとんどの共通 HRESULT 値のために異なる例外クラスを定義します。それ以外のすべての値は、 `Platform::COMException` クラスで報告されます。 すべての例外クラスには、元の HRESULT を取得するために使用できる [Exception::HResult](platform-exception-class.md#hresult) フィールドがあります。 また、C++ 以外の言語で記述されたコードで、生成された場合でも、例外の元のソースの特定に役立つことができます、デバッガーでのユーザー コードに関するコール スタック情報を確認することもできます。  
  
## <a name="exceptions"></a>例外  
 C++ プログラムでスローおよびキャッチできます Windows ランタイム操作から派生した例外から派生した例外、 `std::exception`、またはユーザー定義型です。 など、例外をキャッチするコードが JavaScript で記述されたときに、アプリケーション バイナリ インターフェイス (ABI) の境界を越えることが場合にのみ、Windows ランタイムの例外をスローする必要があります。 非 Windows ランタイム C++ 例外には、ABI の境界に達すると、例外に変換されます、 `Platform::FailureException` E_FAIL HRESULT を表す例外。 ABI の詳細については、「 [Creating Windows Runtime Components in C++](/MicrosoftDocs/windows-uwp/blob/docs/windows-apps-src/winrt-components/creating-windows-runtime-components-in-cpp.md)」を参照してください。  
  
 1 つの HRESULT パラメーターを受け取るコンストラクター、または 1 つの HRESULT パラメーターと、処理を行う Windows ストア アプリに ABI を通じて渡すことができる 1 つの [Platform::String](platform-exception-class.md) ^ パラメーターを受け取るコンストラクターのいずれかを使用して、 [Platform::Exception](platform-string-class.md)を宣言することができます。 または、1 つの HRESULT パラメーター、または 1 つの HRESULT パラメーターと [パラメーターのいずれかを受け取る 2 つの](platform-exception-class.md#createexception) Exception::CreateException メソッド `Platform::String^` オーバーロードの 1 つを使用して、例外を宣言できます。  
  
## <a name="standard-exceptions"></a>標準の例外  
 C + + CX を一般的な HRESULT エラーを表す標準の例外のセットをサポートしています。 この標準例外は [Platform::COMException](platform-comexception-class.md)から派生し、その例外は `Platform::Exception`から派生します。 ABI の境界を越えて例外をスローするときは、標準の例外の 1 つをスローする必要があります。  

 `Platform::Exception`から独自の例外の種類を派生させることはできません。 カスタム例外をスローするには、ユーザー定義の HRESULT を使用して `COMException` オブジェクトを構築します。  
  
 次の表は、標準の例外の一覧を示しています。  
  
|name|基になる HRESULT|説明|  
|----------|------------------------|-----------------|  
|COMException|*ユーザー定義の hresult*|COM メソッドの呼び出しから認識されない HRESULT が返されるとスローされます。|  
|AccessDeniedException|E_ACCESSDENIED|リソースや機能へのアクセスが拒否されるとスローされます。|  
|ChangedStateException|E_CHANGED_STATE|コレクション反復子またはコレクション ビューのメソッドが、親コレクションの変更後に呼び出さたときにスローされます。これにより、メソッドの結果は無効になります。|  
|ClassNotRegisteredException|REGDB_E_CLASSNOTREG|COM クラスが登録されていないときにスローされます。|  
|DisconnectedException|RPC_E_DISCONNECTED|オブジェクトがクライアントから接続を切断されるとスローされます。|  
|FailureException|E_FAIL|操作が失敗したときにスローされます。|  
|InvalidArgumentException|E_INVALIDARG|メソッドに提供された引数のいずれかが有効でない場合にスローされます。|  
|InvalidCastException|E_NOINTERFACE|型が別の型にキャストできないときにスローされます。|  
|NotImplementedException|E_NOTIMPL|インターフェイス メソッドがクラスに実装されていないときにスローされます。|  
|NullReferenceException|E_POINTER|null オブジェクト参照を逆参照しようするとスローされます。|  
|ObjectDisposedException|RO_E_CLOSED|破棄されたオブジェクトで操作が実行されるとスローされます。|  
|OperationCanceledException|E_ABORT|操作が中止されるとスローされます。|  
|OutOfBoundsException|E_BOUNDS|操作が有効範囲外のデータにアクセスを試みるとスローされます。|  
|OutOfMemoryException|E_OUTOFMEMORY|メモリが不足して操作を完了できないときにスローされます。|  
|WrongThreadException|RPC_E_WRONG_THREAD|スレッドが、スレッドのアパートメントに属さないプロキシ オブジェクト用のインターフェイス ポインターを通じて呼び出すときにスローされます。|  
  
## <a name="hresult-and-message-properties"></a>HResult および Message プロパティ  
 すべての例外に、 [HResult](platform-comexception-class.md#hresult) プロパティと [Message](platform-comexception-class.md#message) プロパティがあります。 [Exception::HResult](platform-exception-class.md#hresult) プロパティは、例外の基になる数値 HRESULT 値を取得します。 [Exception::Message](platform-exception-class.md#message) プロパティは、例外を記述するシステム指定文字列を取得します。 Windows 8 のメッセージはデバッガーでのみ使用でき、読み取り専用です。 これは、例外を再スローするときに、例外を変更できないことを意味します。 Windows 8.1 では、例外を再スローする場合に、プログラムでメッセージの文字列にアクセスし、新しいメッセージを提供することができます。 非同期メソッド呼び出しに関する呼び出し履歴を含め、より詳細な呼び出し履歴情報もデバッガーで使用できます。  
  
### <a name="examples"></a>使用例  
 この例では、同期操作の Windows ランタイムの例外をスローする方法を示します。  
  
 [!code-cpp[cx_exceptions#01](codesnippet/CPP/exceptiontest/class1.cpp#01)]  
  
 次の例は、例外をキャッチする方法を示しています。  
  
 [!code-cpp[cx_exceptions#02](codesnippet/CPP/exceptiontest/class1.cpp#02)]  
  
 非同期操作中にスローされた例外をキャッチするには、タスク クラスを使用し、エラー処理の継続を追加します。 エラー処理コードの継続は、他のスレッドでスローされる例外を呼び出し元のスレッドにマーシャリングして、発生する可能性があるすべての例外をコード中の 1 つのポイントで処理できるようにします。 詳しくは、「 [C++ での非同期プログラミング](http://msdn.microsoft.com/library/windows/apps/Hh780559.aspx)」を参照してください。  
  
## <a name="unhandlederrordetected-event"></a>UnhandledErrorDetected イベント  
 Windows 8.1 にサブスクライブできます、 [:unhandlederrordetected](http://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.core.coreapplication.unhandlederrordetected.aspx)静的イベントは、プロセスを停止しようとしている未処理のエラーへのアクセスを提供します。 エラーがどこで発生したかにかかわりなく、イベントの引数によって渡される [Windows::ApplicationModel::Core::UnhandledError](http://msdnstage.redmond.corp.microsoft.com/library/windows/apps/windows.applicationmodel.core.unhandlederror.aspx) オブジェクトという形で、このハンドラーに到達します。 オブジェクトに対して `Propagate` を呼び出した場合、エラー コードに対応する型の `Platform::*Exception` が生成され、スローされます。 catch ブロックで、必要に応じて、ユーザー状態を保存することができ、その後、プロセスが `throw`を呼び出して終了すること、またはプログラムを既知の状態に戻すために他の作業を実行することを許可できます。 次の例に、基本的なパターンを示します。  
  
```  
  
// In app.xaml.h:  
void OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e);  
  
// In app.xaml.cpp  
  
// Subscribe to the event, for example in the app class constructor:  
Windows::ApplicationModel::Core::CoreApplication::UnhandledErrorDetected += ref new EventHandler<UnhandledErrorDetectedEventArgs^>(this, &App::OnUnhandledException);  
  
// Event handler implementation:  
void App::OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e)  
{  
    auto err = e->UnhandledError;  
  
    if (!err->Handled) //Propagate has not been called on it yet.  
{  
     try  
    {  
        err->Propagate();  
    }  
    // Catch any specific exception types if you know how to handle them  
    catch (AccessDeniedException^ ex)  
    {  
        // TODO: Log error and either take action to recover  
        // or else re-throw exception to continue fail-fast  
    }  
  
}  
  
```  
  
### <a name="remarks"></a>コメント  
 C + + CX は使用しない、`finally`句。  
  
## <a name="see-also"></a>参照  
 [Visual C 言語リファレンス](visual-c-language-reference-c-cx.md)   
 [名前空間参照](namespaces-reference-c-cx.md)