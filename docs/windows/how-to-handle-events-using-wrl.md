---
title: "方法: WRL を使用してイベントを処理する | Microsoft Docs"
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
ms.assetid: 1c77543f-7b0c-4a94-93bf-e3225885ed76
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# 方法: WRL を使用してイベントを処理する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このドキュメントは、[!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\) を使用して [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] オブジェクトのイベントをサブスクライブし、そのイベントを処理する方法について説明します。  
  
 コンポーネントのインスタンスを作成してプロパティ値を取得する基本的な例については、"[方法: Windows ランタイム コンポーネントをアクティブ化し使用する](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md) \(Windows ランタイム コンポーネント \(WRL\) の読み込みと使用の方法\)" を参照してください。  
  
## イベントのサブスクライブと処理  
 次の手順では `ABI::Windows::System::Threading::IDeviceWatcher` オブジェクトを開始し、イベント ハンドラーを使用して進行状況を監視します。  `IDeviceWatcher` インターフェイスを使用すると、デバイスを非同期的にまたはバックグラウンドで列挙でき、デバイスが追加、削除、または変更された場合に通知を受け取ることができます。  [コールバック](../windows/callback-function-windows-runtime-cpp-template-library.md)関数は、バックグラウンド操作の結果を処理するイベント ハンドラーを指定できるため、この例において重要です。  完全な例を次に示します。  
  
> [!WARNING]
>  通常は [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] を [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリケーション内で使用しますが、この例では説明の目的でコンソール アプリケーションを使用します。  `wprintf_s` のような関数、[!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリケーションから使用することはできません。  [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリ内で使用できる型と関数の詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」と、「[Win32 and COM for Windows Store apps \(Windows ストア アプリ用の Win32 と COM\)](http://msdn.microsoft.com/library/windows/apps/br205757.aspx)」を参照してください。  
  
1.  必要な [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]、[!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]、または標準 C\+\+ ライブラリのヘッダーをインクルードします \(`#include`\)。  
  
     [!code-cpp[wrl-consume-event#2](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_1.cpp)]  
  
     Windows.Devices.Enumeration.h では、デバイスを列挙するために必要な型を宣言します。  
  
     コードを読みやすくするために、.cpp ファイルでは `using namespace` ディレクティブを使用することをお勧めします。  
  
2.  アプリ用のローカル変数を宣言します。  この例では、後でイベント サブスクリプションを解除できるようにするために、列挙されたデバイスと登録トークンの数を保持します。  
  
     [!code-cpp[wrl-consume-event#7](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_2.cpp)]  
  
3.  [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] を初期化します。  
  
     [!code-cpp[wrl-consume-event#3](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_3.cpp)]  
  
4.  列挙プロセスの完了をメイン アプリと同期する [Event](../windows/event-class-windows-runtime-cpp-template-library.md) オブジェクトを作成します。  
  
     [!code-cpp[wrl-consume-event#4](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_4.cpp)]  
  
    > [!NOTE]
    >  このイベントは、コンソール アプリケーションの一部としてデモのみを目的としています。  この例では、アプリケーションが終了する前に非同期操作が完了したことを確認するために、イベントを使用します。  ほとんどのアプリケーションでは、通常は非同期操作の完了を待機しません。  
  
5.  `IDeviceWatcher` インターフェイスに対応するアクティベーション ファクトリを作成します。  
  
     [!code-cpp[wrl-consume-event#5](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_5.cpp)]  
  
     [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] は、型を識別するための完全修飾名を使用します。  `RuntimeClass_Windows_Devices_Enumeration_DeviceInformation` パラメーターは [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]によって提供される文字列であり、必須のランタイム クラス名が含まれています。  
  
6.  `IDeviceWatcher` オブジェクトを作成します。  
  
     [!code-cpp[wrl-consume-event#6](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_6.cpp)]  
  
7.  `Callback` 関数を使用して `Added`、`EnumerationCompleted`、および `Stopped` の各イベントをサブスクライブします。  
  
     [!code-cpp[wrl-consume-event#8](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_7.cpp)]  
  
     `Added` イベント ハンドラーは、列挙されたデバイス数をインクリメントします。  デバイスが10 個検出されると、列挙プロセスが停止します。  
  
     `Stopped` イベント ハンドラーは、イベント ハンドラーを削除し、完了イベントを設定します。  
  
     `EnumerationCompleted` イベント ハンドラーは、列挙プロセスを停止します。  このイベントはデバイスの数が 10 未満である場合に処理されます。  
  
    > [!TIP]
    >  この例では、ラムダ式を使用してコールバックを定義します。  関数オブジェクト \(ファンクター\)、関数ポインター、または [std::function](../standard-library/function-class.md) オブジェクトを使用することもできます。  ラムダ式の詳細については、「[ラムダ式](../cpp/lambda-expressions-in-cpp.md)」を参照してください。  
  
8.  列挙プロセスを開始します。  
  
     [!code-cpp[wrl-consume-event#9](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_8.cpp)]  
  
9. 列挙プロセスが完了するのを待機し、メッセージを出力します。  すべての `ComPtr` オブジェクトと RAII オブジェクトは自動的にスコープから外れて解放されます。  
  
     [!code-cpp[wrl-consume-event#10](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_9.cpp)]  
  
 完全な例を次に示します。  
  
 [!code-cpp[wrl-consume-event#1](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_10.cpp)]  
  
## コードのコンパイル  
 このコードをコンパイルするには、コードをコピーし、Visual Studio プロジェクトに貼り付けるか、"`wrl-consume-events.cpp`" という名前のファイルに貼り付けてから、Visual Studio のコマンド プロンプト ウィンドウで次のコマンドを実行します。  
  
 **cl.exe wrl\-consume\-events.cpp runtimeobject.lib**  
  
## 参照  
 [Windows ランタイム C\+\+ テンプレート ライブラリ \(WRL\)](../Topic/Windows%20Runtime%20C++%20Template%20Library%20\(WRL\).md)