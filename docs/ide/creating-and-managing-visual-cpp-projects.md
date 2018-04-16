---
title: "作成して、Visual C プロジェクトの管理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vcprojects
- creatingmanagingVC
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, creating
- Visual C++ projects, creating
- projects [C++], creating
- Visual C++ projects
- ATL projects
ms.assetid: 11003cd8-9046-4630-a189-a32bf3b88047
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0c38f4c75a41de8b2f2b494941c6a52b1ff46fa4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="creating-and-managing-msbuild-based-visual-c-projects"></a>作成して、MSBuild ベースの Visual C プロジェクトの管理
MSBuild は Visual C のネイティブのビルド システム、一般的に最適な MFC または ATL のライブラリを使用するデスクトップ アプリケーションだけでなく、UWP アプリに使用するシステムを構築します。 MSBuild は Visual Studio IDE、プロジェクト システムと緊密に統合されてがコマンドラインから使用することもできます。 Visual Studio 2017 以降、Visual C がサポートしている[CMake と他の非 MSBuild システム フォルダーを開く機能を通じて](non-msbuild-projects.md)です。

MSBuild ベースのプロジェクトが、プログラムだけでなく、ターゲット プラットフォーム (x 86、x64、または ARM) の使用例とビルドしているか、他の構成設定をコンパイルするために必要なすべてのファイルとリソースを指定する XML 形式 (.vcxproj) でプロジェクト ファイル、リリース バージョンまたはプログラムのデバッグ バージョンです。 プロジェクト (1 つまたは複数) は *ソリューション*に含められます。たとえば、ソリューションには、いくつかの Win32 DLL プロジェクトと、それらの DLL を使用する 1 つの Win32 コンソール アプリケーションを含めることができます。 プロジェクトをビルドすると、MSBuild エンジンがプロジェクト ファイルを使用して、実行可能ファイルやその他の指定されたカスタム出力を生成します。

Visual C プロジェクトを作成するには選択して**ファイル &#124;です。新しい &#124;です。プロジェクト**、左側のウィンドウで、Visual C が選択されていることを確認し、中央のペインでプロジェクト テンプレートの一覧から選択します。 クリックすると、テンプレートに、多くの場合、ウィザードが表示されます、プロジェクトを作成する前に、さまざまなプロジェクトのプロパティを設定することができます。 表示およびプロジェクトのプロパティ ページを使用して、後でこれらのプロパティを変更できます (**プロジェクト &#124;です。プロパティ**)。  
  
 新しいプロジェクトを作成することもできます。  
  
-   選択**ファイル &#124;です。新しい &#124;です。既存のコードからプロジェクト**を既存のソース コード ファイルを追加する画面の指示に従います。 このオプションは、ソース コード ファイルが 25 以下で、複雑な依存関係がなく、比較的小規模で単純なプロジェクトに最も適しています。  
  
-   メイクファイルから始め、[全般] タブでメイクファイル プロジェクト テンプレートを選択します。  
  
-   空のプロジェクトを作成する (下にある、**全般** タブ) ソリューション エクスプ ローラーでプロジェクト ノードを右クリックし を選択してソース コード ファイルを手動で追加および**追加 &#124;です。既存の項目**です。  
  
-   using the [Win32 Application Wizard](../windows/win32-application-wizard.md)の使用。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [Visual C++ プロジェクトの種類](../ide/visual-cpp-project-types.md)  
 Visual C で使用できる MSBuild ベースのプロジェクトの種類について説明します。  
  
 [Visual C++ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)  
 さまざまな MSBuild プロジェクトの種類で使用されるファイルの種類について説明します。  
  
 [アプリケーション ウィザードを使用したデスクトップ プロジェクトの作成](../ide/creating-desktop-projects-by-using-application-wizards.md)  
 ウィザードを使用して Visual C++ プロジェクトを作成する方法について説明します。  
  
 [プロジェクトのプロパティの操作](../ide/working-with-project-properties.md)  
 プロパティ ページおよびプロパティ シートを使用して、プロジェクト設定を指定する方法について説明します。  
  
 [コード ウィザードによる機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)  
 機能を追加するために、クラス、メソッド、変数などの要素をプロジェクトに追加する方法について説明します。  
  
 [方法 : ビルドのプロジェクト出力ファイルを編成する](../ide/how-to-organize-project-output-files-for-builds.md)  
 プロジェクトの出力ファイルを管理する方法について説明します。  
  
## <a name="related-sections"></a>関連項目  
 [C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)  
 コマンド ラインまたは Visual Studio の統合開発環境からプログラムをビルドする方法について説明するトピックへのリンクがあります。  
  
 [Visual C++ リファレンス](http://msdn.microsoft.com/en-us/1ba03b5c-8229-4f63-b08c-6c12141d6ab1)  
 C と C++ の言語リファレンス、Visual C++ で提供されるライブラリ、Visual C++ 機能拡張オブジェクト モデル、および MASM (Microsoft Macro Assembler) に関するトピックへのリンクがあります。  
  
## <a name="see-also"></a>参照  
 [Visual Studio SDK](http://msdn.microsoft.com/vstudio/extend)
