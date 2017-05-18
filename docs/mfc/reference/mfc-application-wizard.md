---
title: "MFC アプリケーション ウィザード |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.exe.overview
dev_langs:
- C++
helpviewer_keywords:
- MFC Application Wizard
- executable files, creating
ms.assetid: 227ac090-921d-4b2f-be0a-66a5f4cab0d4
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 2d1d950ac5adb5d17b172fa058a40593e4e61c34
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="mfc-application-wizard"></a>MFC アプリケーション ウィザード
MFC アプリケーション ウィザードでは、コンパイル時に Windows 実行可能アプリケーション (.exe) の基本機能が実装されるアプリケーションが生成されます。 MFC の初期アプリケーションには、C++ ソース (.cpp) ファイル、リソース (.rc) ファイル、ヘッダー (.h) ファイル、およびプロジェクト (.vcxproj) ファイルが含まれます。 これらの初期ファイルで生成されるコードは、MFC に基づいています。  
  
> [!NOTE]
>  選択したオプションに応じて、ウィザードがこの他のファイルをプロジェクトに作成します。 例では、選択した場合の**状況依存のヘルプ**上、[高度な機能](../../mfc/reference/advanced-features-mfc-application-wizard.md) ページで、ウィザードは、プロジェクトのヘルプ ファイルをコンパイルするために必要なファイルを作成します。 ウィザードで作成されるファイルの詳細については、次を参照してください。 [Visual c プロジェクトに対して作成されるファイルの種類](../../ide/file-types-created-for-visual-cpp-projects.md)、およびプロジェクトの Readme.txt ファイルを参照してください。  
  
## <a name="overview"></a>概要  
 ウィザードのこのページでは、作成する MFC アプリケーションの現在のアプリケーション設定が示されます。 既定では、このウィザードでは、次のようなウィザード プロジェクトが作成されます。  
  
-   [アプリケーションの種類、MFC アプリケーション ウィザード](../../mfc/reference/application-type-mfc-application-wizard.md)  
  
    -   タブ付きのマルチ ドキュメント インターフェイス (MDI: Multiple Document Interface) をサポートするプロジェクト。 詳細については、次を参照してください。 [SDI と MDI](../../mfc/sdi-and-mdi.md)します。  
  
    -   プロジェクトを使用して、[ドキュメント/ビュー アーキテクチャ](../../mfc/document-view-architecture.md)します。  
  
    -   Unicode ライブラリを使用するプロジェクト  
  
    -   Visual Studio のプロジェクト形式を使用して作成された、表示形式の切り替えができるプロジェクト  
  
    -   共有 DLL 内の MFC を使用するプロジェクト 詳細については、次を参照してください。 [Visual c の Dll](../../build/dlls-in-visual-cpp.md)します。  
  
-   [MFC アプリケーション ウィザード 複合ドキュメント サポート](../../mfc/reference/compound-document-support-mfc-application-wizard.md)  
  
    -   複合ドキュメントをサポートするプロジェクト  
  
-   [MFC アプリケーション ウィザードの ドキュメント テンプレート文字列](../../mfc/reference/document-template-strings-mfc-application-wizard.md)  
  
    -   既定のドキュメント テンプレート文字列としてプロジェクト名を使用するプロジェクト  
  
-   [データベースのサポート、MFC アプリケーション ウィザード](../../mfc/reference/database-support-mfc-application-wizard.md)  
  
    -   データベースをサポートするプロジェクト  
  
-   [ユーザー インターフェイス機能を MFC アプリケーション ウィザード](../../mfc/reference/user-interface-features-mfc-application-wizard.md)  
  
    -   標準の Windows ユーザー インターフェイスがシステム メニューのステータス バーを最大化し、ボックスに、最小限に抑えるように機能を実装するプロジェクト、**に関する**ボックス、標準のメニュー バーとドッキング ツールバー、および子フレーム。  
  
-   [高度な機能を MFC アプリケーション ウィザード](../../mfc/reference/advanced-features-mfc-application-wizard.md)  
  
    -   印刷と印刷プレビューをサポートするプロジェクト  
  
    -   ActiveX コントロールをサポートするプロジェクト 詳細については、次を参照してください。[シーケンスの操作を作成する ActiveX コントロールの](../../mfc/sequence-of-operations-for-creating-activex-controls.md)です。  
  
    -   プロジェクトには、サポートされていません[オートメーション](../../mfc/automation.md)、 [MAPI](../../mfc/mapi-support-in-mfc.md)、 [Windows Sockets](../../mfc/windows-sockets-in-mfc.md)、または Active Accessibility します。  
  
    -   サポートするプロジェクト、**エクスプ ローラー** 、ドッキング ペイン、**出力**、ドッキング ペイン、および**プロパティ**ドッキング ペインです。  
  
-   [生成されたクラス、MFC アプリケーション ウィザード](../../mfc/reference/generated-classes-mfc-application-wizard.md)  
  
    -   プロジェクトのビュー クラス、 [CView クラス](../../mfc/reference/cview-class.md)します。  
  
    -   プロジェクトのアプリケーションのクラスから派生、 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)します。  
  
    -   プロジェクトのドキュメント クラス、 [CDocument クラス](../../mfc/reference/cdocument-class.md)します。  
  
    -   プロジェクトのメイン フレーム クラス、 [CMDIFrameWndEx クラス](../../mfc/reference/cmdiframewndex-class.md)します。  
  
    -   プロジェクトの子フレーム クラスから派生、 [CMDIChildWndEx クラス](../../mfc/reference/cmdichildwndex-class.md)します。  
  
 これらの既定の設定を変更するには、ウィザードの左の列で該当するタブ タイトルをクリックし、表示されるページで必要な変更を行います。  
  
 オブジェクトやコントロールを追加 Visual C を使用して、プロジェクトに MFC アプリケーション プロジェクトを作成したら、[コード ウィザード](../../ide/adding-functionality-with-code-wizards-cpp.md)します。  
  
## <a name="see-also"></a>関連項目  
 [MFC アプリケーションの作成](../../mfc/reference/creating-an-mfc-application.md)   
 [MFC デスクトップ アプリケーション](../../mfc/mfc-desktop-applications.md)   
 [Windows アプリケーションの作成にクラスを使用します。](../../mfc/using-the-classes-to-write-applications-for-windows.md)

