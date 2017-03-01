---
title: "アプリケーションの種類、MFC アプリケーション ウィザード |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.exe.apptype
dev_langs:
- C++
helpviewer_keywords:
- static libraries, MFC
ms.assetid: c3f62b0e-3f13-42c5-9859-d3890d0c3e1d
caps.latest.revision: 12
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 72ba028831f252717b6b1c75bbb263b2b1b28366
ms.lasthandoff: 02/24/2017

---
# <a name="application-type-mfc-application-wizard"></a>[アプリケーションの種類] (MFC アプリケーション ウィザード)
このページを使用して、 [MFC アプリケーション ウィザード](../../mfc/reference/mfc-application-wizard.md)を設計し、新しい MFC アプリケーションに基本的な機能を追加します。  
  
 **アプリケーションの種類**  
 アプリケーションで作成するドキュメントのサポートの種類を指定します。 選択したアプリケーションの種類では、アプリケーションで利用可能なユーザー インターフェイスのオプションを決定します。 参照してください[ユーザー インターフェイスの機能には、MFC アプリケーション ウィザード](../../mfc/reference/user-interface-features-mfc-application-wizard.md)の詳細。  
  
 ドキュメントの種類の詳細についてを参照してください。  
  
-   [SDI と MDI](../../mfc/sdi-and-mdi.md)  
  
-   [フレーム ウィンドウ](../../mfc/frame-windows.md)  
  
-   [フレーム ウィンドウ クラス](../../mfc/frame-window-classes.md)  
  
-   [ドキュメント、ビュー、およびフレームワーク](../../mfc/documents-views-and-the-framework.md)  
  
-   [ダイアログ ボックス](../../mfc/dialog-boxes.md)  
  
|オプション|説明|  
|------------|-----------------|  
|**1 つのドキュメント**|ビュー クラスのに基づいて、アプリケーションのシングル ドキュメント インターフェイス (SDI) アーキテクチャを作成[CView クラス](../../mfc/reference/cview-class.md)します。 ビューの基底クラスを変更することができます、[生成されたクラス、MFC アプリケーション ウィザード](../../mfc/reference/generated-classes-mfc-application-wizard.md)ウィザードのページです。 たとえば、フォーム ベースのアプリケーションを作成するを使用して[CFormView クラス](../../mfc/reference/cformview-class.md)ビュー クラスにします。<br /><br /> この種のアプリケーションでは、ドキュメントのフレーム ウィンドウは、1 つのドキュメントを保持できます。|  
|**複数のドキュメント**|ビュー クラスのに基づいて、アプリケーションの複数ドキュメント インターフェイス (MDI) アーキテクチャを作成`CView`します。 ビューの基底クラスを変更することができます、**生成されたクラス**ウィザードのページです。 たとえば、フォーム ベースのアプリケーションを作成するを使用して`CFormView`ビュー クラスにします。<br /><br /> この種のアプリケーションでは、ドキュメントのフレーム ウィンドウできます複数子ウィンドウを保持します。|  
|**タブ付きドキュメント**|別のタブには、各ドキュメントを配置します。|  
|**ダイアログ ベース**|ダイアログ クラスがに基づいては、アプリケーションのダイアログ ベースのアーキテクチャを作成`CDialog`します。 (HTML ダイアログを作成するには、ボックスをオン**HTML ダイアログ**)。|  
|**HTML のダイアログを使用します。**|ダイアログ ボックス アプリケーションのみです。 ダイアログ クラスから派生した[CDHtmlDialog クラス](../../mfc/reference/cdhtmldialog-class.md)の代わりに[CDialog クラス](../../mfc/reference/cdialog-class.md)します。 このボックスをオンにした場合`CDHtmlDialog`に記載されて、**基本クラス**ボックスに、[生成されたクラス、MFC アプリケーション ウィザード](../../mfc/reference/generated-classes-mfc-application-wizard.md)ウィザードのページです。<br /><br /> A `CDHtmlDialog`-派生 ダイアログ ボックスは、HTML ベースのダイアログ ボックスを表示、HTML を使用したデータの交換を制御し、HTML のイベントを処理します。|  
|**複数のトップレベル ドキュメント**|ビュー クラスのに基づいて、アプリケーションの複数の最上位レベル アーキテクチャを作成`CView`します。<br /><br /> この種のアプリケーション、ユーザーがクリックしたときに**新規**(または**新しいフレーム**) で、**ファイル**] メニューの [アプリケーションがその親は、デスクトップでは暗黙的にウィンドウを作成します。 新しいドキュメントのフレームでは、タスク バーに表示され、アプリケーション ウィンドウのクライアント領域に限定されません。|  
  
 **ドキュメント/ビュー アーキテクチャのサポート**  
 使用して、ドキュメント/ビュー アーキテクチャをアプリケーションに含めるかどうかを示す、 [CDocument クラス](../../mfc/reference/cdocument-class.md)と[CView クラス](../../mfc/reference/cview-class.md)(既定値)。 非 MFC アプリケーションを移植する場合、または、コンパイル済み実行可能ファイルのサイズを小さく場合は、このチェック ボックスをオフにします。 既定では、ドキュメント/ビュー アーキテクチャを備えていないアプリケーションがから派生した[CWinApp クラス](../../mfc/reference/cwinapp-class.md)、ディスク ファイルからドキュメントを開くために MFC サポートは含まれません。  
  
 **リソース言語**  
 リソースの言語を設定します。 一覧は、Visual Studio がインストールされている、システムで使用できる言語を表示します。 システムの言語以外の言語を選択する場合に、その言語の適切なテンプレート フォルダーがインストールされている必要があります。 使用可能な既定値から別の言語リソースのインストールの詳細については、**リソース言語**ボックスの一覧を参照してください[ウィザードでサポートされるその他の言語](../../ide/wizard-support-for-other-languages.md)です。  
  
 選択した言語に反映されます、**ローカライズ文字列**のオプション、[ドキュメント テンプレート文字列、MFC アプリケーション ウィザード](../../mfc/reference/document-template-strings-mfc-application-wizard.md)ウィザードのページです。  
  
 **Unicode ライブラリを使用します。**  
 Unicode と Unicode 以外のバージョンの MFC ライブラリを使用するかどうかを指定します。  
  
 **プロジェクトのスタイル**  
 アプリケーションが、標準的な MFC、ファイル エクスプ ローラー、Visual Studio または Office アーキテクチャおよび表示にするかどうかを示します。 詳細については、次を参照してください。[ファイル エクスプ ローラー スタイルの MFC アプリケーションの作成](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)します。  
  
|オプション|説明|  
|------------|-----------------|  
|**MFC の標準**|標準的な MFC アプリケーション アーキテクチャを提供します。|  
|**ファイル エクスプ ローラー**|ここで、左側のペインは分割ウィンドウを使用して、ファイル エクスプ ローラーに似たアプリケーションを実装して、 [CTreeView クラス](../../mfc/reference/ctreeview-class.md)し、右側の領域は、 [CListView クラス](../../mfc/reference/clistview-class.md)します。|  
|**Visual Studio**|4 つのドッキング可能なペインを含む Visual Studio – ようなアプリケーションを実装 (**ファイル ビュー**、**クラス ビュー**、**プロパティ**、および**出力**) 型から派生した[CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)から派生したメイン フレーム ウィンドウと[CMDIFrameWndEx クラス](../../mfc/reference/cmdiframewndex-class.md)(既定値)。|  
|**Office**|派生したリボンを含む Office に似たアプリケーションを実装する[CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)から派生した Outlook バー[があります](../../mfc/reference/cmfcoutlookbar-class.md)から派生したキャプション バー [CMFCCaptionBar クラス](../../mfc/reference/cmfccaptionbar-class.md)、およびメインフレームから派生した[CMDIFrameWndEx クラス](../../mfc/reference/cmdiframewndex-class.md)します。|  
  
 **視覚スタイルと色**  
 アプリケーションの visual スタイルを決定します。 次のオプションを使用できます。  
  
-   **Windows ネイティブ/既定**  
  
-   **Office 2003**  
  
-   **Visual Studio 2005**  
  
-   **Office 2007 (青のテーマ)**  
  
-   **Office 2007 (黒のテーマ)**  
  
-   **Office 2007 (銀色のテーマ)**  
  
-   **Office 2007 (水色のテーマ)**  
  
 **視覚スタイルの切り替えを有効にします。**  
 かどうかユーザーできる視覚スタイルを変更、実行時にアプリケーションの通常メニューまたはリボンから、適切な視覚スタイルを選択して、指定します。  
  
 **MFC の使用法**  
 MFC ライブラリをリンクする方法を指定します。 既定では、MFC は、共有 DLL としてリンクされます。  
  
|オプション|説明|  
|------------|-----------------|  
|**共有 DLL で MFC を使用します。**|MFC ライブラリを共有 DLL としてアプリケーションにリンクします。 アプリケーションでは、MFC ライブラリへの呼び出しが実行時に行います。 このオプションには、MFC ライブラリを使用して複数の実行可能ファイルで構成されるアプリケーションのディスクとメモリの量が削減されます。 Win32 と MFC の両方のアプリケーションが DLL (既定値) の関数を呼び出すことができます。|  
|**スタティック ライブラリで MFC を使用します。**|ビルド時にアプリケーションを静的の MFC ライブラリをリンクします。|  
  
## <a name="see-also"></a>関連項目  
 [MFC アプリケーション ウィザード](../../mfc/reference/mfc-application-wizard.md)   
 [Visual C プロジェクトに対して作成されるファイルの種類](../../ide/file-types-created-for-visual-cpp-projects.md)


