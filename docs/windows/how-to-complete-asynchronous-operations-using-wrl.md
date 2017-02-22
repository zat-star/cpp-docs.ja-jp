---
title: "方法: WRL を使用して非同期操作を完了する | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 02173eae-731b-49bc-b412-f1f69388b99d
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# 方法: WRL を使用して非同期操作を完了する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このドキュメントでは、[!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\) を使用して非同期操作を開始し、その操作が完了した時点で他の作業を実行する方法を示します。  
  
 このドキュメントでは、2 つの例を示します。  最初の例では、非同期タイマーを開始し、そのタイマーが期限切れになるのを待機します。  この例では、タイマー オブジェクトを作成するときに、非同期アクションを指定します。  2 番目の例では、バックグラウンド ワーカー スレッドを実行します。  この例では、`IAsyncInfo` インターフェイスを返す [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] メソッドの作業を実行する方法を示します。  ["Callback \(コールバック\)"](../windows/callback-function-windows-runtime-cpp-template-library.md) 関数は、非同期操作の結果を処理するイベント ハンドラーを指定するため、どちらの例でも重要です。  
  
 コンポーネントのインスタンスを作成してプロパティ値を取得する基本的な例については、"[方法: Windows ランタイム コンポーネントをアクティブ化し使用する](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md) \(Windows ランタイム コンポーネント \(WRL\) の読み込みと使用の方法\)" を参照してください。  
  
> [!TIP]
>  これらの例では、コールバックを定義するためにラムダ式を使用します。  関数オブジェクト \(ファンクター\)、関数ポインター、または [std::function](../standard-library/function-class.md) オブジェクトを使用することもできます。  C\+\+ のラムダ式の詳細については、"[ラムダ式](../cpp/lambda-expressions-in-cpp.md) \(C\+\+ でのラムダ式\)" を参照してください。  
  
## 例: タイマーを使用した作業  
 以下の手順では、非同期タイマーを開始し、そのタイマーが期限切れになるのを待機します。  完全な例を次に示します。  
  
> [!WARNING]
>  通常は [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] を [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリケーション内で使用しますが、この例では説明の目的でコンソール アプリケーションを使用します。  `wprintf_s` のような関数、[!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリケーションから使用することはできません。  [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリケーション内で使用できる関数と型の詳細については、["CRT functions not supported by \/ZW \(\/ZW でサポートされていない CRT 関数\)"](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx) と、["Win32 and COM for Windows Store apps \(Windows ストア アプリ用の Win32 と COM\)"](http://msdn.microsoft.com/library/windows/apps/br205757.aspx) を参照してください。  
  
1.  必要な [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]、[!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]、または標準 C\+\+ ライブラリのヘッダーをインクルードします \(`#include`\)。  
  
     [!code-cpp[wrl-consume-async#2](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_1.cpp)]  
  
     Windows.System.Threading.h は、非同期タイマーを使用するために必要な型を宣言します。  
  
     コードを読みやすくするために、.cpp ファイルでは `using namespace` ディレクティブを使用することをお勧めします。  
  
2.  [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] を初期化します。  
  
     [!code-cpp[wrl-consume-async#3](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_2.cpp)]  
  
3.  `ABI::Windows::System::Threading::IThreadPoolTimer` インターフェイスに対応するアクティベーション ファクトリを作成します。  
  
     [!code-cpp[wrl-consume-async#4](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_3.cpp)]  
  
     [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] は、型を識別するための完全修飾名を使用します。  `RuntimeClass_Windows_System_Threading_ThreadPoolTimer` パラメーターは [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] によって提供される文字列であり、必須のランタイム クラス名が含まれています。  
  
4.  タイマーからのコールバックをメイン アプリケーションに同期させる ["Event \(イベント\)"](../windows/event-class-windows-runtime-cpp-template-library.md) オブジェクトを作成します。  
  
     [!code-cpp[wrl-consume-async#5](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_4.cpp)]  
  
    > [!NOTE]
    >  このイベントは、コンソール アプリケーションの一部としてデモのみを目的としています。  この例では、アプリケーションが終了する前に非同期操作が完了したことを確認するために、イベントを使用します。  ほとんどのアプリケーションでは、通常は非同期操作の完了を待機しません。  
  
5.  2 秒後に期限切れになる `IThreadPoolTimer` オブジェクトを作成します。  `Callback` 関数を使用して、イベント ハンドラー \(`ABI::Windows::System::Threading::ITimerElapsedHandler` オブジェクト\) を作成します。  
  
     [!code-cpp[wrl-consume-async#6](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_5.cpp)]  
  
6.  メッセージをコンソールに出力し、タイマーからのコールバックが完了するのを待機します。  すべての `ComPtr` オブジェクトと RAII オブジェクトは自動的にスコープから外れて解放されます。  
  
     [!code-cpp[wrl-consume-async#7](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_6.cpp)]  
  
 完全な例を次に示します。  
  
 [!code-cpp[wrl-consume-async#1](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_7.cpp)]  
  
### コードのコンパイル  
 このコードをコンパイルするには、コードをコピーし、Visual Studio プロジェクトに貼り付けるか、`wrl-consume-async.cpp` という名前のファイルに貼り付けてから、Visual Studio のコマンド プロンプト ウィンドウで次のコマンドを実行します。  
  
 **cl.exe wrl\-consume\-async.cpp runtimeobject.lib**  
  
## 例: バックグラウンド スレッドを使用した作業  
 以下の手順では、ワーカー スレッドを開始し、そのスレッドによって実行されるアクションを定義します。  完全な例を次に示します。  
  
> [!TIP]
>  この例では、`ABI::Windows::Foundation::IAsyncAction` インターフェイスを使用して作業する方法を示します。  `IAsyncInfo`、`IAsyncAction`、`IAsyncActionWithProgress`、`IAsyncOperation`、および `IAsyncOperationWithProgress` を実装するすべてのインターフェイスに、このパターンを追加できます。  
  
1.  必要な [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]、[!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]、または標準 C\+\+ ライブラリのヘッダーをインクルードします \(`#include`\)。  
  
     [!code-cpp[wrl-consume-asyncOp#2](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_8.cpp)]  
  
     Windows.System.Threading.h は、ワーカー スレッドを使用するために必要な型を宣言します。  
  
     コードを読みやすくするために、.cpp ファイルでは `using namespace` ディレクティブを使用することをお勧めします。  
  
2.  [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] を初期化します。  
  
     [!code-cpp[wrl-consume-asyncOp#3](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_9.cpp)]  
  
3.  `ABI::Windows::System::Threading::IThreadPoolStatics` インターフェイスに対応するアクティベーション ファクトリを作成します。  
  
     [!code-cpp[wrl-consume-asyncOp#4](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_10.cpp)]  
  
4.  ワーカー スレッドの完了をメイン アプリケーションに同期させる ["Event \(イベント\)"](../windows/event-class-windows-runtime-cpp-template-library.md) オブジェクトを作成します。  
  
     [!code-cpp[wrl-consume-asyncOp#5](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_11.cpp)]  
  
    > [!NOTE]
    >  このイベントは、コンソール アプリケーションの一部としてデモのみを目的としています。  この例では、アプリケーションが終了する前に非同期操作が完了したことを確認するために、イベントを使用します。  ほとんどのアプリケーションでは、通常は非同期操作の完了を待機しません。  
  
5.  ワーカー スレッドを作成するには、`IThreadPoolStatics::RunAsync` メソッドを呼び出します。  アクションを定義するには、`Callback` 関数を使用します。  
  
     [!code-cpp[wrl-consume-asyncOp#6](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_12.cpp)]  
  
     `IsPrime` 関数は、この後に続く完全な例で定義します。  
  
6.  メッセージをコンソールに出力し、スレッドが完了するのを待機します。  すべての `ComPtr` オブジェクトと RAII オブジェクトは自動的にスコープから外れて解放されます。  
  
     [!code-cpp[wrl-consume-asyncOp#7](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_13.cpp)]  
  
 完全な例を次に示します。  
  
 [!code-cpp[wrl-consume-asyncOp#1](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_14.cpp)]  
  
### コードのコンパイル  
 このコードをコンパイルするには、コードをコピーし、Visual Studio プロジェクトに貼り付けるか、`wrl-consume-asyncOp.cpp` という名前のファイルに貼り付けてから、Visual Studio のコマンド プロンプト ウィンドウで次のコマンドを実行します。  
  
 **cl.exe wrl\-consume\-asyncOp.cpp runtimeobject.lib**  
  
## 参照  
 [Windows ランタイム C\+\+ テンプレート ライブラリ \(WRL\)](../Topic/Windows%20Runtime%20C++%20Template%20Library%20\(WRL\).md)