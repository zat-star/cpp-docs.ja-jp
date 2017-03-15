---
title: "方法: WRL コンポーネントを直接インスタンス化する | Microsoft Docs"
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
ms.assetid: 1a9fa011-0cee-4abf-bf83-49adf53ff906
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 方法: WRL コンポーネントを直接インスタンス化する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\) [Microsoft::WRL::Make](../windows/make-function.md) と [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md) 関数を使用して、コンポーネントを定義するモジュールからそのコンポーネントをインスタンス化する方法について説明します。  
  
 コンポーネントを直接インスタンス化することにより、クラス ファクトリやその他の機構が必要ない場合にオーバーヘッドを低減できます。  [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリとデスクトップ アプリの両方で、コンポーネントを直接インスタンス化できます。  
  
 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] を使用して [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] の基本コンポーネントを作成し、外部の [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリからインスタンス化する方法については、「[チュートリアル: 基本的な Windows ランタイム コンポーネントの作成](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md)」を参照してください。  [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] を使用してクラシック COM コンポーネントを作成し、外部のデスクトップ アプリからインスタンス化する方法については、「[方法: 従来の COM コンポーネントを作成する](../windows/how-to-create-a-classic-com-component-using-wrl.md)」を参照してください。  
  
 このドキュメントでは、2 つの例を示します。  最初の例では、`Make` 関数を使用してコンポーネントをインスタンス化します。  2 番目の例では、`MakeAndInitialize` 関数を使用して構築中に失敗する場合があるコンポーネントをインスタンス化します \(COM では通常、例外ではなく `HRESULT` の値を使用してエラーを示すため、COM 型は通常、コンストラクターからスローされません。  `MakeAndInitialize` を使用すると、コンポーネントで `RuntimeClassInitialize` メソッドを使用して構築引数を検証できます\)。どちらの例も、基本的なロガー インターフェイスを定義し、コンソールにメッセージを記述するクラスを定義することでそのインターフェイスを実装します。  
  
> [!IMPORTANT]
>  `new` 演算子を使用して [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] コンポーネントをインスタンス化することはできません。  そのため、コンポーネントを直接インスタンス化するには、常に `Make` または `MakeAndInitialize` を使用することをお勧めします。  
  
### 基本的なロガー コンポーネントを作成してインスタンス化するには  
  
1.  Visual Studio で、**\[Win32 コンソール アプリケーション\]** プロジェクトを作成します。  プロジェクトに "`WRLLogger`" などの名前を付けます。  
  
2.  プロジェクトに **\[Midl ファイル \(.idl\)\]** を追加してファイルに "`ILogger.idl`" という名前を付け、次のコードを追加します。  
  
     [!code-cpp[wrl-logger-make#1](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_1.idl)]  
  
3.  次のコードを使用して WRLLogger.cpp の内容を置き換えます。  
  
     [!code-cpp[wrl-logger-make#2](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_2.cpp)]  
  
### 基本的なロガー コンポーネントの構造エラーを処理するには  
  
1.  次のコードを使用して `CConsoleWriter` クラスの定義を置き換えます。  このバージョンは、プライベート文字列のメンバー変数を保持し、`RuntimeClass::RuntimeClassInitialize` メソッドをオーバーライドします。  `RuntimeClassInitialize` は `SHStrDup` の呼び出しに失敗すると失敗します。  
  
     [!code-cpp[wrl-logger-makeandinitialize#1](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_3.cpp)]  
  
2.  次のコードを使用して `wmain` の定義を置き換えます。  このバージョンは `MakeAndInitialize` を使用して `CConsoleWriter` オブジェクトをインスタンス化し、`HRESULT` の結果を確認します。  
  
     [!code-cpp[wrl-logger-makeandinitialize#2](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_4.cpp)]  
  
## 参照  
 [Windows ランタイム C\+\+ テンプレート ライブラリ \(WRL\)](../Topic/Windows%20Runtime%20C++%20Template%20Library%20\(WRL\).md)   
 [Microsoft::WRL::Make](../windows/make-function.md)   
 [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md)