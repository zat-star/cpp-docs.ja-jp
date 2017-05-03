---
title: "例外 (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6cbdc1f1-e4d7-4707-a670-86365146432f
caps.latest.revision: 22
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 22
---
# 例外 (C++/CX)
[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) のエラー処理は、例外に基づいています。 上位の基本 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] コンポーネントは、HRESULT 値としてエラーを報告します。[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]では、これらの値は HRESULT 値を含む厳密に型指定された例外に変換され、[!INCLUDE[win81](../cppcx/includes/win81-md.md)] ではプログラムでアクセスできる文字列による説明に変換されます。  例外は、`ref class` から派生した `Platform::Exception` として実装されます。`Platform` 名前空間は、ほとんどの共通 HRESULT 値のために異なる例外クラスを定義します。それ以外のすべての値は、`Platform::COMException` クラスで報告されます。 すべての例外クラスには、元の HRESULT を取得するために使用できる [Exception::HResult Property](../cppcx/exception-hresult-property.md) フィールドがあります。[!INCLUDE[win81](../cppcx/includes/win81-md.md)]では、C\+\+ 以外の言語で作成されたコードで例外が発生した場合でも、例外の元の発生場所を正確に突き止めるのに役立つ、ユーザー コードに関するコール スタック情報をデバッガー内で確認することもできます。  
  
## 例外  
 C\+\+ プログラムでは、[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 操作から派生した例外、`std::exception` から派生した派生、またはユーザー定義型をスローおよびキャッチできます。[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 例外をスローする必要があるのは、例外をキャッチするコードが JavaScript で記述されている場合など、例外がアプリケーション バイナリ インターフェイス \(ABI\) の境界を越える場合のみです。[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] ではない C\+\+ 例外が ABI 境界に達すると、例外は、E\_FAIL HRESULT を表す `Platform::FailureException` 例外に変換されます。 ABI の詳細については、「[C\+\+ で Windows ランタイム コンポーネントを作成する](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf)」を参照してください。  
  
 1 つの HRESULT パラメーターを受け取るコンストラクター、または 1 つの HRESULT パラメーターと、処理を行う Windows ストア アプリに ABI を通じて渡すことができる 1 つの [Platform::String](../cppcx/platform-exception-class.md)^ パラメーターを受け取るコンストラクターのいずれかを使用して、[Platform::Exception](../cppcx/platform-string-class.md) を宣言することができます。 または、1 つの HRESULT パラメーター、または 1 つの HRESULT パラメーターと `Platform::String^` パラメーターのいずれかを受け取る 2 つの [Exception::CreateException メソッド](../cppcx/exception-createexception-method.md) オーバーロードの 1 つを使用して、例外を宣言できます。  
  
## 標準の例外  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] は、一般的な HRESULT エラーを表す標準の例外をサポートしています。 この標準例外は [Platform::COMException](../cppcx/platform-comexception-class.md) から派生し、その例外は `Platform::Exception` から派生します。 ABI の境界を越えて例外をスローするときは、標準の例外の 1 つをスローする必要があります。  
  
 `Platform::Exception` から独自の例外の種類を派生させることはできません。 カスタム例外をスローするには、ユーザー定義の HRESULT を使用して `COMException` オブジェクトを構築します。  
  
 次の表は、標準の例外の一覧を示しています。  
  
|名前|基になる HRESULT|説明|  
|--------|------------------|--------|  
|COMException|*ユーザー定義の hresult*|COM メソッドの呼び出しから認識されない HRESULT が返されるとスローされます。|  
|AccessDeniedException|E\_ACCESSDENIED|リソースや機能へのアクセスが拒否されるとスローされます。|  
|ChangedStateException|E\_CHANGED\_STATE|コレクション反復子またはコレクション ビューのメソッドが、親コレクションの変更後に呼び出さたときにスローされます。これにより、メソッドの結果は無効になります。|  
|ClassNotRegisteredException|REGDB\_E\_CLASSNOTREG|COM クラスが登録されていないときにスローされます。|  
|DisconnectedException|RPC\_E\_DISCONNECTED|オブジェクトがクライアントから接続を切断されるとスローされます。|  
|FailureException|E\_FAIL|操作が失敗したときにスローされます。|  
|InvalidArgumentException|E\_INVALIDARG|メソッドに提供された引数のいずれかが有効でない場合にスローされます。|  
|InvalidCastException|E\_NOINTERFACE|型が別の型にキャストできないときにスローされます。|  
|NotImplementedException|E\_NOTIMPL|インターフェイス メソッドがクラスに実装されていないときにスローされます。|  
|NullReferenceException|E\_POINTER|null オブジェクト参照を逆参照しようするとスローされます。|  
|ObjectDisposedException|RO\_E\_CLOSED|破棄されたオブジェクトで操作が実行されるとスローされます。|  
|OperationCanceledException|E\_ABORT|操作が中止されるとスローされます。|  
|OutOfBoundsException|E\_BOUNDS|操作が有効範囲外のデータにアクセスを試みるとスローされます。|  
|OutOfMemoryException|E\_OUTOFMEMORY|メモリが不足して操作を完了できないときにスローされます。|  
|WrongThreadException|RPC\_E\_WRONG\_THREAD|スレッドが、スレッドのアパートメントに属さないプロキシ オブジェクト用のインターフェイス ポインターを通じて呼び出すときにスローされます。|  
  
## HResult および Message プロパティ  
 すべての例外に、[HResult](../cppcx/comexception-hresult-property.md) プロパティと [Message](../cppcx/comexception-message-property.md) プロパティがあります。[Exception::HResult](../cppcx/exception-hresult-property.md) プロパティは、例外の基になる数値 HRESULT 値を取得します。[Exception::Message](../cppcx/exception-message-property.md) プロパティは、例外を記述するシステム指定文字列を取得します。[!INCLUDE[win8](../cppcx/includes/win8-md.md)]では、メッセージはデバッガーでのみ使用でき、また読み取り専用です。 これは、例外を再スローするときに、例外を変更できないことを意味します。[!INCLUDE[win81](../cppcx/includes/win81-md.md)]では、例外を再スローする場合に、プログラムでメッセージの文字列にアクセスし、新しいメッセージを提供することができます。 非同期メソッド呼び出しに関する呼び出し履歴を含め、より詳細な呼び出し履歴情報もデバッガーで使用できます。  
  
## 例  
 この例は、同期操作の [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 例外をスローする方法を示しています。  
  
 [!code-cpp[cx_exceptions#01](../snippets/cpp/VS_Snippets_Misc/cx_exceptions/cpp/class1.cpp#01)]  
  
 次の例は、例外をキャッチする方法を示しています。  
  
 [!code-cpp[cx_exceptions#02](../snippets/cpp/VS_Snippets_Misc/cx_exceptions/cpp/class1.cpp#02)]  
  
 非同期操作中にスローされた例外をキャッチするには、タスク クラスを使用し、エラー処理の継続を追加します。 エラー処理コードの継続は、他のスレッドでスローされる例外を呼び出し元のスレッドにマーシャリングして、発生する可能性があるすべての例外をコード中の 1 つのポイントで処理できるようにします。 詳しくは、「[C\+\+ での非同期プログラミング](http://msdn.microsoft.com/library/windows/apps/Hh780559.aspx)」を参照してください。  
  
## UnhandledErrorDetected イベント  
 [!INCLUDE[win81](../cppcx/includes/win81-md.md)] では、静的イベント [Windows::ApplicationModel::Core::CoreApplication::UnhandledErrorDetected](http://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.core.coreapplication.unhandlederrordetected.aspx) にサブスクライブできます。このイベントは、プロセスをダウンさせようとしている未処理のエラーへのアクセスを提供します。 エラーがどこで発生したかにかかわりなく、イベントの引数によって渡される [Windows::ApplicationModel::Core::UnhandledError](http://msdnstage.redmond.corp.microsoft.com/library/windows/apps/windows.applicationmodel.core.unhandlederror.aspx) オブジェクトという形で、このハンドラーに到達します。 オブジェクトに対して `Propagate` を呼び出した場合、エラー コードに対応する型の `Platform::*Exception` が生成され、スローされます。 catch ブロックで、必要に応じて、ユーザー状態を保存することができ、その後、プロセスが `throw`を呼び出して終了すること、またはプログラムを既知の状態に戻すために他の作業を実行することを許可できます。 次の例に、基本的なパターンを示します。  
  
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
  
## コメント  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] は、`finally` 句を使用しません。  
  
## 参照  
 [Visual C\+\+ の言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)   
 [名前空間参照](../cppcx/namespaces-reference-c-cx.md)