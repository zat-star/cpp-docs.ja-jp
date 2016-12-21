---
title: "方法: WRL を使用して従来の COM コンポーネントを作成する | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 5efe7690-90d5-4c3c-9e53-11a14cefcb19
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: WRL を使用して従来の COM コンポーネントを作成する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] ([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]) を使用して、[!INCLUDE[win8_appstore_long](../build/reference/includes/win8_appstore_long_md.md)] アプリだけでなくデスクトップ アプリでも使用できる基本のクラシックな COM コンポーネントを作成できます。 COM コンポーネントの作成では、[!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] は ATL に比べて必要となるコードが少なく済む場合があります。 COM のについては、サブセットを [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] サポートされておりを参照してください [Windows ランタイム C++ テンプレート ライブラリ (WRL)](../Topic/Windows%20Runtime%20C++%20Template%20Library%20\(WRL\).md)します。  
  
 このドキュメントでは、[!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] を使用して基本の COM コンポーネントを作成する方法について説明します。 ニーズに最適な配置メカニズムを使用できますが、このドキュメントでは、デスクトップ アプリから COM コンポーネントを登録して使用する基本的な方法についても説明します。  
  
### <a name="to-use-the-includecppwrlshorttokencppwrlshortmdmd-to-create-a-basic-classic-com-component"></a>[!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] を使用して基本のクラシックな COM コンポーネントを作成するには  
  
1.  Visual Studio で作成、 **空のソリューション** プロジェクトです。 など、プロジェクトの名前 `WRLClassicCOM`します。  
  
2.  追加、 **Win32 プロジェクト** ソリューションにします。 など、プロジェクトの名前 `CalculatorComponent`します。  **アプリケーション設定** ] タブで [ **DLL**します。  
  
3.  追加、 **Midl ファイル (.idl)** 、プロジェクトへのファイルです。 など、ファイルの名前 `CalculatorComponent.idl`します。  
  
4.  CalculatorComponent.idl に次のコードを追加します。  
  
     [!code-cpp[wrl-classic-com-component#1](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_1.idl)]  
  
5.  CalculatorComponent.cpp で、`CalculatorComponent` クラスを定義します。  `CalculatorComponent` クラスから継承 [Microsoft::WRL::RuntimeClass](../windows/runtimeclass-class.md)します。 [Microsoft::WRL::RuntimeClassFlags \< ClassicCom>](../windows/runtimeclassflags-structure.md) クラスの派生元を指定 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509\(v=vs.85\).aspx) および not [IInspectable](http://msdn.microsoft.com/library/br205821\(v=vs.85\).aspx)します。 (`IInspectable` を使用する [!INCLUDE[win8_appstore_short](../windows/includes/win8_appstore_short_md.md)] アプリのコンポーネントです。) `CoCreatableClass` などの関数で使用できるクラスのファクトリを作成 [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615\(v=vs.85\).aspx)します。  
  
     [!code-cpp[wrl-classic-com-component#2](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_2.cpp)]  
  
6.  次のコードを使用して、dllmain.cpp のコードを置き換えます。 このファイルで DLL のエクスポート関数が定義されます。 これらの関数を使用して、 [Microsoft::WRL::Module](../windows/module-class.md) モジュールのクラス ファクトリを管理するクラス。  
  
     [!code-cpp[wrl-classic-com-component#3](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_3.cpp)]  
  
7.  追加、 **モジュール定義ファイル (.def)** 、プロジェクトへのファイルです。 など、ファイルの名前 `CalculatorComponent.def`します。 このファイルによって、エクスポートされる関数の名前がリンカーに設定されます。  
  
8.  CalculatorComponent.def に次のコードを追加します。  
  
     [!CODE [wrl-classic-com-component#4](../CodeSnippet/VS_Snippets_Misc/wrl-classic-com-component#4)]  
  
9. リンカー行に runtimeobject.lib を追加します。 については、参照する方法、 [です。リンカー入力として lib ファイル](../build/reference/dot-lib-files-as-linker-input.md)します。  
  
### <a name="to-consume-the-com-component-from-a-desktop-app"></a>デスクトップ アプリから COM コンポーネントを使用するには  
  
1.  Windows レジストリを使用して COM コンポーネントを登録します。 これを行うには、登録エントリのファイルを作成、名前を付けます `RegScript.reg`, 、し、次のテキストを追加します。 置換 *\< dll パス >* 、DLL のパスを持つ — たとえば、 `C:\\temp\\WRLClassicCOM\\Debug\\CalculatorComponent.dll`です。  
  
     [!CODE [wrl-classic-com-component#5](../CodeSnippet/VS_Snippets_Misc/wrl-classic-com-component#5)]  
  
2.  RegScript.reg を実行するか、プロジェクトに追加 **ビルド後イベント**です。 詳細については、次を参照してください。 [ビルド前のビルド後コマンド ライン] ダイアログ ボックス](../Topic/Pre-build%20Event-Post-build%20Event%20Command%20Line%20Dialog%20Box.md)します。  
  
3.  追加、 **Win32 コンソール アプリケーション** プロジェクトがソリューションにします。 など、プロジェクトの名前 `Calculator`します。  
  
4.  次のコードを使用して Calculator.cpp の内容を置き換えます。  
  
     [!code-cpp[wrl-classic-com-component#6](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_6.cpp)]  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  
 このドキュメントでは、[!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] を使用して COM コンポーネントを作成し、COM 対応テクノロジで利用可能にできることを、標準の COM 関数を用いて示します。 使用することも [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] などの型 [Microsoft::WRL::ComPtr](../windows/comptr-class.md) COM およびその他のオブジェクトの有効期間を管理するデスクトップ アプリにします。 次のコードでは、[!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] を使用して、`ICalculatorComponent` ポインターの有効期間を管理しています。 `CoInitializeWrapper` クラスは RAII ラッパーでの 1 つで、COM ライブラリが解放されることと、COM ライブラリの有効期間が `ComPtr` スマート ポインター オブジェクトよりも長く続くことを保証します。  
  
 [!code-cpp[wrl-classic-com-component#7](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_7.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [Windows ランタイム C++ テンプレート ライブラリ (WRL)](../Topic/Windows%20Runtime%20C++%20Template%20Library%20\(WRL\).md)