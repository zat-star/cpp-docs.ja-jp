---
title: "WRL クラス ライブラリ プロジェクト テンプレート | Microsoft Docs"
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
ms.assetid: 628b0852-89e5-44f8-bf58-a09762bda15c
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# WRL クラス ライブラリ プロジェクト テンプレート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\) プロジェクトを作成するために Visual Studio を使用して WRL クラス ライブラリ プロジェクト テンプレートをダウンロードしてタスクを大幅に簡略化できます。  
  
> [!NOTE]
>  手動で既存のプロジェクトのプロジェクト設定が更新しなければ、参照してください [DLL \(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh699881\(v=vs.110\).aspx)。  
  
## WRL プロジェクト テンプレートをダウンロードします。  
 Visual Studio は [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] のプロジェクトにテンプレートはありません。  ここで [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]と [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリケーションの基本的なクラス ライブラリを作成するプロジェクト テンプレートをダウンロードする方法について示します。  
  
#### WRL プロジェクト テンプレートをダウンロードするには  
  
1.  メニュー バーで **\[ファイル\]**、**\[新しいプロジェクト\]** を順にクリックします。  
  
2.  **\[新しいプロジェクト\]** ダイアログ ボックスの左ペインで、**\[オンライン\]** を選択します、**\[テンプレート\]** を選択します。  
  
3.  右上隅に **\[オンライン テンプレートの検索\]** ボックスで、`WRL クラス ライブラリ`を入力します。  テンプレートが検索結果に表示されて、**\[OK\]** ボタンをクリックします。  
  
4.  **\[ダウンロードとインストール\]** ダイアログ ボックスでライセンス条項に同意する場合は、**\[インストール\]** ボタンをクリックします。  
  
5.  テンプレートをインストールしたら、`WRLClassLibrary` のテンプレートを選択します **\[ファイル\]** をクリックします、**\[新しいプロジェクト\]** によって、プロジェクトを作成します。  プロジェクトでは、DLL を作成します。  
  
## プロジェクト テンプレートの使用例  
 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] コンポーネントを作成するには、このテンプレートを使用する例については、" [チュートリアル: 基本的な Windows ランタイム コンポーネントの作成](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md) を読み込みます。  
  
## プロジェクト テンプレートで提供されるものを  
 プロジェクト テンプレートが提供する:  
  
-   MIDL を宣言する .idl ファイルは基本インターフェイスのクラス実装を求めます。  次に例を示します。  
  
     [!code-cpp[wrl-project-template#1](../windows/codesnippet/CPP/wrl-class-library-project-template_1.idl)]  
  
-   クラスの実装を定義する .cpp ファイル。  次に例を示します。  
  
     [!code-cpp[wrl-project-template#2](../windows/codesnippet/CPP/wrl-class-library-project-template_2.cpp)]  
  
     [RuntimeClass](../windows/runtimeclass-class.md) の基本クラスでは、モジュール内のすべてのオブジェクトのグローバルな参照を管理し、[IUnknown](http://msdn.microsoft.com/ja-jp/33f1d79a-33fc-4ce5-a372-e08bda378332) と [IInspectable](http://msdn.microsoft.com/ja-jp/0657e51f-d4c0-46c6-927d-b01e54b6846c) インターフェイスのメソッドを宣言します。  [InspectableClass](../windows/inspectableclass-macro.md) マクロは `IUnknown` と `IInspectable`を実装します。  [ActivatableClass](../Topic/ActivatableClass%20Macros.md) マクロは、クラスのインスタンスを作成するクラス ファクトリを作成します。  
  
-   ファイルは、ライブラリのエクスポート `DllMain`、`DllCanUnloadNow`、`DllGetActivationFactory`と `DllGetClassObject`を定義する module.cpp という名前です。  
  
## 参照  
 [Windows ランタイム C\+\+ テンプレート ライブラリ \(WRL\)](../Topic/Windows%20Runtime%20C++%20Template%20Library%20\(WRL\).md)