---
title: "方法: WRL を使用して Windows ランタイム コンポーネントをアクティブ化し使用する | Microsoft Docs"
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
ms.assetid: 54828f02-6af3-45d1-b965-d0104442f8d5
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# 方法: WRL を使用して Windows ランタイム コンポーネントをアクティブ化し使用する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このドキュメントでは、[!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\) を使用して [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]を初期化する方法と [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] コンポーネントをアクティブ化して使用する方法について示しています。  
  
> [!NOTE]
>  この例では、[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]の組み込みコンポーネントをアクティブ化します。  同様の方法でアクティブ化できる独自のコンポーネントを作成する方法については、「[チュートリアル: 基本的な Windows ランタイム コンポーネントの作成](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md)」を参照してください。  
  
 コンポーネントを使用するには、コンポーネントによって実装されている型へのインターフェイス ポインターを取得する必要があります。  [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]の基になるテクノロジがコンポーネント オブジェクト モデル \(COM: Component Object Model\) であるため、COM 規則に従って型のインスタンスを保持する必要があります。  たとえば、型がメモリから削除されるタイミングを決定する*参照カウント*を保持する必要があります。  
  
 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]の使用を簡略化するために、[!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] には参照カウントを自動的に実行するスマート ポインター テンプレートである [ComPtr\<T\>](../windows/comptr-class.md) が用意されています。  変数の宣言時に `ComPtr<`*interface\-name*`>` *identifier* を指定します。  インターフェイスのメンバーにアクセスするには、識別子に矢印のメンバー アクセス演算子 \(`->`\) を適用します。  
  
> [!IMPORTANT]
>  インターフェイス関数を呼び出す際は、`HRESULT` の戻り値を必ずテストしてください。  
  
## Windows ランタイム コンポーネントのアクティブ化と使用  
 次の手順では、`Windows::Foundation::IUriRuntimeClass` インターフェイスを使用して [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] コンポーネントのアクティベーション ファクトリを作成する方法、そのコンポーネントのインスタンスの作成方法、およびプロパティ値の取得方法を示します。  また、[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]を初期化する方法を示します。  完全な例を次に示します。  
  
> [!IMPORTANT]
>  通常は [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] を [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリケーション内で使用しますが、この例では説明の目的でコンソール アプリケーションを使用します。  `wprintf_s` のような関数、[!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリケーションから使用することはできません。  [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリ内で使用できる型と関数の詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」と、「[Win32 and COM for Windows Store apps \(Windows ストア アプリ用の Win32 と COM\)](http://msdn.microsoft.com/library/windows/apps/br205757.aspx)」を参照してください。  
  
#### Windows ランタイム コンポーネントをアクティブ化して使用するには  
  
1.  必要な [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]、[!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]、または標準 C\+\+ ライブラリのヘッダーをインクルードします \(`#include`\)。  
  
     [!code-cpp[wrl-consume-component#2](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_1.cpp)]  
  
     コードを読みやすくするために、.cpp ファイルでは `using namespace` ディレクティブを使用することをお勧めします。  
  
2.  アプリが実行されるスレッドを初期化します。  すべてのアプリケーションでスレッドとスレッド モデルを初期化する必要があります。  この例では、[Microsoft::WRL::Wrappers::RoInitializeWrapper](../Topic/RoInitializeWrapper%20Class.md) クラスを使用して [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]を初期化し、スレッド モデルとして [RO\_INIT\_MULTITHREADED](http://msdn.microsoft.com/library/windows/apps/br224661.aspx) を指定します。  `RoInitializeWrapper` クラスでは、構築時に `Windows::Foundation::Initialize` を呼び出し、破棄時に `Windows::Foundation::Uninitialize` を呼び出します。  
  
     [!code-cpp[wrl-consume-component#3](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_2.cpp)]  
  
     2 番目のステートメントでは、[RoInitializeWrapper::HRESULT](../windows/roinitializewrapper-hresult-parens-operator.md) 演算子によって、呼び出しから `Windows::Foundation::Initialize` に `HRESULT` が返されます。  
  
3.  `ABI::Windows::Foundation::IUriRuntimeClassFactory` インターフェイスに対応する*アクティベーション ファクトリ*を作成します。  
  
     [!code-cpp[wrl-consume-component#4](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_3.cpp)]  
  
     [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] は、型を識別するための完全修飾名を使用します。  `RuntimeClass_Windows_Foundation_Uri` パラメーターは [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]によって提供される文字列であり、必須のランタイム クラス名が含まれています。  
  
4.  URI `"http://www.microsoft.com"` を表す [Microsoft::WRL::Wrappers::HString](../windows/hstring-class.md) 変数を初期化します。  
  
     [!code-cpp[wrl-consume-component#6](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_4.cpp)]  
  
     [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]では、[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]で使用される文字列のメモリは割り当てません。  代わりに、[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]によって、操作用に保持および使用される文字列のコピーがバッファーに作成され、作成されたバッファーへのハンドルが返されます。  
  
5.  `IUriRuntimeClassFactory::CreateUri` ファクトリ メソッドを使用して、`ABI::Windows::Foundation::IUriRuntimeClass` オブジェクトを作成します。  
  
     [!code-cpp[wrl-consume-component#7](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_5.cpp)]  
  
6.  `IUriRuntimeClass::get_Domain` メソッドを呼び出し、`Domain` プロパティの値を取得します。  
  
     [!code-cpp[wrl-consume-component#8](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_6.cpp)]  
  
7.  ドメイン名をコンソールに出力して返ります。  すべての `ComPtr` オブジェクトと RAII オブジェクトは自動的にスコープから外れて解放されます。  
  
     [!code-cpp[wrl-consume-component#9](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_7.cpp)]  
  
     [WindowsGetStringRawBuffer](http://msdn.microsoft.com/library/windows/apps/br224636.aspx) 関数によって、URI 文字列の基になる Unicode 形式が取得されます。  
  
 完全な例を次に示します。  
  
 [!code-cpp[wrl-consume-component#1](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_8.cpp)]  
  
## コードのコンパイル  
 このコードをコンパイルするには、コードをコピーし、Visual Studio プロジェクトに貼り付けるか、"`wrl-consume-component.cpp`" という名前のファイルに貼り付けてから、Visual Studio のコマンド プロンプト ウィンドウで次のコマンドを実行します。  
  
 **cl.exe wrl\-consume\-component.cpp runtimeobject.lib**  
  
## 参照  
 [Windows ランタイム C\+\+ テンプレート ライブラリ \(WRL\)](../Topic/Windows%20Runtime%20C++%20Template%20Library%20\(WRL\).md)