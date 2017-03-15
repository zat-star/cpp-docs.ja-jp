---
title: "チュートリアル: WRL を使用した基本的な Windows ランタイム コンポーネントの作成 | Microsoft Docs"
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
ms.assetid: 6e3f0986-7905-4f94-90e5-22c2ebfc8cd0
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# チュートリアル: WRL を使用した基本的な Windows ランタイム コンポーネントの作成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このドキュメントでは、使用する方法、 [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] ([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]) 基本的な [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] コンポーネントです。 コンポーネントは、2 つの数値を加算し、結果が素数である場合に、イベントを発生させます。 コンポーネントを使用する方法についても説明、 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] JavaScript を使用するアプリケーション。  
  
## <a name="prerequisites"></a>必要条件  
  
-   発生すると、 [Windows ランタイム](http://msdn.microsoft.com/library/windows/apps/br211377.aspx)します。  
  
-   COM の使用経験。  
  
### <a name="to-create-a-basic-includewrttokenwrtmdmd-component-that-adds-two-numbers"></a>基本的な [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 2 つの数値を追加するコンポーネント  
  
1.  Visual Studio で、Visual C の作成 `WRLClassLibrary` プロジェクトです。 ドキュメント [クラス ライブラリ プロジェクト テンプレート](../windows/wrl-class-library-project-template.md) このテンプレートをダウンロードする方法について説明します。 プロジェクトに `Contoso` という名前を付けます。  
  
2.  Contoso.cpp および Contoso.idl では、"Calculator"と"WinRTClass"のすべてのインスタンスを置き換えます。  
  
3.  Contoso.idl で追加、 `Add` メソッドを `ICalculator` インターフェイスです。  
  
     [!code-cpp[wrl-basic-component#1](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_1.idl)]  
  
4.  Contoso.cpp で追加、 `Add` メソッドを `public` のセクションで、 `Calculator` クラスです。  
  
     [!code-cpp[wrl-basic-component#2](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_2.cpp)]  
  
    > [!IMPORTANT]
    >  使用してください、COM コンポーネントを作成しているため、 `__stdcall` 呼び出し規約です。  
  
     使用することをお勧め `_Out_` とソース注釈言語 (SAL) の注釈に他の関数がそのパラメーターを使用する方法について説明します。 SAL 注釈は、戻り値の説明にも使用されます。 SAL 注釈の使用、 [、C/C++ コード分析ツール](../Topic/Code%20Analysis%20for%20C-C++%20Overview.md) をソース コードを C および C++ での障害を検出します。 ツールによって報告される一般的なコーディング エラーは、バッファー オーバーラン、初期化されていないメモリを含む、null ポインターの逆参照、およびメモリとリソースのリークが発生します。  
  
### <a name="to-use-the-component-from-a-includewin8appnamelongtokenwin8appnamelongmdmd-app-that-uses-javascript"></a>コンポーネントを使用して、 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] JavaScript を使用するアプリ  
  
1.  Visual Studio で、追加する新しい JavaScript `Blank App` プロジェクトを `Contoso` ソリューションです。 プロジェクトに `CalculatorJS` という名前を付けます。  
  
2.   `CalculatorJS` プロジェクトへの参照を追加、 `Contoso` プロジェクトです。  
  
3.  Default.html で置き換え、 `body` にこれらの UI 要素のセクション。  
  
     [!code-html[wrl-basic-component#3](../windows/codesnippet/Html/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_3.html)]  
  
4.  Default.js では、実装、 `OnClick` 関数です。  
  
     [!code-javascript[wrl-basic-component#4](../windows/codesnippet/JavaScript/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_4.js)]  
  
    > [!NOTE]
    >  JavaScript では、メソッド名の最初の文字を標準的な名前付け規則に一致するように小文字に変更されます。  
  
### <a name="to-add-an-event-that-fires-when-a-prime-number-is-calculated"></a>素数を計算するときに発生するイベントを追加するには  
  
1.  宣言の前に、Contoso.idl で `ICalculator`, 、デリゲート型を定義する `PrimeNumberEvent`, 、提供する、 `int` 引数。  
  
     [!code-cpp[wrl-basic-component#5](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_5.idl)]  
  
     使用すると、 `delegate` キーワード、MIDL コンパイラの作成を含むインターフェイス、 `Invoke` そのデリゲートのシグネチャと一致するメソッドです。 この例では、生成されたファイル Contoso_h.h を定義、 `IPrimeNumberEvent` 後の手順で使用されるインターフェイスです。  
  
     [!code-cpp[wrl-basic-component#13](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_6.cpp)]  
  
2.   `ICalculator` インターフェイスを定義、 `PrimeNumberFound` イベントです。  `eventadd` と `eventremove` 属性を指定するのコンシューマー、 `ICalculator` インターフェイスを購読しての両方がこのイベントの購読を解除します。  
  
     [!code-cpp[wrl-basic-component#6](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_7.idl)]  
  
3.  Contoso.cpp で追加、 `private` [Microsoft::WRL::EventSource](../windows/eventsource-class.md) メンバー変数をイベント サブスクライバーを管理し、イベント ハンドラーを呼び出します。  
  
     [!code-cpp[wrl-basic-component#7](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_8.cpp)]  
  
4.  Contoso.cpp、実装、 `add_PrimeNumberFound` と `remove_PrimeNumberFound` メソッドです。  
  
     [!code-cpp[wrl-basic-component#8](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_9.cpp)]  
  
### <a name="to-raise-the-event-when-a-prime-number-is-calculated"></a>素数を計算するときのイベントを生成するには  
  
1.  Contoso.cpp で追加、 `IsPrime` メソッドを `private` のセクションで、 `Calculator` クラスです。  
  
     [!code-cpp[wrl-basic-component#12](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_10.cpp)]  
  
2.  変更、 `Calculator`の `Add` メソッドを呼び出す、 [Microsoft::WRL::EventSource::InvokeAll](../windows/eventsource-invokeall-method.md) 素数を計算するときのメソッドです。  
  
     [!code-cpp[wrl-basic-component#11](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_11.cpp)]  
  
### <a name="to-handle-the-event-from-javascript"></a>JavaScript からイベントを処理するには  
  
1.  Default.html で変更、 `body` 素数を格納しているテキスト領域を記載します。  
  
     [!code-html[wrl-basic-component#9](../windows/codesnippet/Html/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_12.html)]  
  
2.  Default.js 内で変更、 `Add` を処理する関数、 `PrimeNumberFound` イベントです。 イベント ハンドラーは、素数の数を前の手順で定義されているテキスト領域に追加します。  
  
     [!code-javascript[wrl-basic-component#10](../windows/codesnippet/JavaScript/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_13.js)]  
  
    > [!NOTE]
    >  JavaScript だけでなく、イベント名は小文字に変更は、先頭の名前付け規則に一致するように"on"にします。  
  
 次の図は、基本的な電卓アプリケーションを示しています。  
  
 ![JavaScript を使用した基本的な電卓アプリケーション](../windows/media/wrl_basic_component.png "WRL_Basic_Component")  
  
## <a name="next-steps"></a>次の手順  
  
## <a name="see-also"></a>「  
 [Windows ランタイム C++ テンプレート ライブラリ (WRL)](../Topic/Windows%20Runtime%20C++%20Template%20Library%20\(WRL\).md)   
 [クラス ライブラリ プロジェクト テンプレート](../windows/wrl-class-library-project-template.md)   
 [C/C++ コード分析ツール](../Topic/Code%20Analysis%20for%20C-C++%20Overview.md)