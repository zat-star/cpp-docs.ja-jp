---
title: "WRL クラス ライブラリ プロジェクト テンプレート |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: 628b0852-89e5-44f8-bf58-a09762bda15c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ea8f4609be920c03ff718ab79ba5a3693ec7d8e5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="wrl-class-library-project-template"></a>WRL クラス ライブラリ プロジェクト テンプレート
Visual Studio を使用して、Windows ランタイム C++ テンプレート ライブラリ (WRL) プロジェクトを作成する場合、WRL クラス ライブラリ プロジェクト テンプレートをダウンロードして大幅に、タスクを簡略化することができます。  
  
> [!NOTE]
>  既存のプロジェクトのプロジェクト設定を手動で更新した場合は、次を参照してください。 [Dll (C + + CX)](http://msdn.microsoft.com/library/windows/apps/hh699881\(v=vs.110\).aspx)です。  
  
## <a name="download-the-wrl-project-template"></a>WRL プロジェクト テンプレートをダウンロードします。  
 Visual Studio では、Windows ランタイム C++ テンプレート ライブラリ プロジェクトのテンプレートを提供しません。 Windows ランタイム C++ テンプレート ライブラリのユニバーサル Windows プラットフォーム アプリの基本クラス ライブラリを作成するプロジェクト テンプレートをダウンロードする方法を次に示します。  
  
#### <a name="to-download-the-wrl-project-template"></a>WRL プロジェクト テンプレートをダウンロードするには  
  
1.  メニュー バーで、次のように選択します。**ファイル**、**新しいプロジェクト**です。  
  
2.  左側のウィンドウで、**新しいプロジェクト**ダイアログ ボックスで、**オンライン**、し、**テンプレート**です。  
  
3.  **オンライン テンプレートを検索**ボックスの右上隅の種類に`WRL Class Library`です。 テンプレートは、検索結果が表示されたら、選択、 **OK**ボタンをクリックします。  
  
4.  **をダウンロードしてインストール**条項のダイアログ ボックスで、ライセンスに同意する場合は、選択、**インストール**ボタンをクリックします。  
  
5.  テンプレートをインストールした後を選択してプロジェクトを作成**ファイル**、**新しいプロジェクト**を選択し、`WRLClassLibrary`テンプレート。 プロジェクトでは、DLL を作成します。  
  
## <a name="examples-that-use-the-project-template"></a>プロジェクト テンプレートを使用する例  
 読み取り[チュートリアル: 基本的な Windows ランタイム コンポーネントを作成する](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md)このテンプレートを使用して、Windows ランタイム コンポーネントを作成する例についてはします。  
  
## <a name="what-the-project-template-provides"></a>プロジェクト テンプレートが用意されています  
 プロジェクト テンプレートを提供します。  
  
-   .idl ファイルの基本インターフェイスの MIDL 属性をそのクラスの実装を宣言です。 次に例を示します。  
  
     [!code-cpp[wrl-project-template#1](../windows/codesnippet/CPP/wrl-class-library-project-template_1.idl)]  
  
-   クラスの実装を定義する .cpp ファイルです。 次に例を示します。  
  
     [!code-cpp[wrl-project-template#2](../windows/codesnippet/CPP/wrl-class-library-project-template_2.cpp)]  
  
     [RuntimeClass](../windows/runtimeclass-class.md)基底クラスがモジュール内のすべてのオブジェクトのグローバルの参照の管理に役立つし、のメソッドを宣言、 [IUnknown](http://msdn.microsoft.com/en-us/33f1d79a-33fc-4ce5-a372-e08bda378332)と[IInspectable](http://msdn.microsoft.com/en-us/0657e51f-d4c0-46c6-927d-b01e54b6846c)インターフェイスです。 [InspectableClass](../windows/inspectableclass-macro.md)マクロを実装する`IUnknown`と`IInspectable`です。 [ActivatableClass](../windows/activatableclass-macros.md)マクロは、クラスのインスタンスを作成するクラス ファクトリを作成します。  
  
-   ライブラリを定義する module.cpp をという名前のファイルにエクスポート`DllMain`、 `DllCanUnloadNow`、 `DllGetActivationFactory`、および`DllGetClassObject`です。  
  
## <a name="see-also"></a>関連項目  
 [Windows ランタイム C++ テンプレート ライブラリ (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)