---
title: "MFC ActiveX コントロール ウィザード | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.ctl.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX コントロール [C++], MFC"
  - "MFC ActiveX コントロール ウィザード"
  - "MFC ActiveX コントロール [C++], ウィザード"
  - "OLE コントロール [C++]"
  - "OLE コントロール [C++], 作成"
ms.assetid: f19d698c-bdc3-4c74-af97-3d6ccb441b75
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# MFC ActiveX コントロール ウィザード
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ActiveX コントロールとは特殊な[オートメーション サーバー](../../mfc/automation-servers.md)であり、再利用できるコンポーネントです。  ActiveX コントロールをホストするアプリケーションは、そのコントロールの[オートメーション クライアント](../../mfc/automation-clients.md)です。  ActiveX コントロールなどの再利用できるコンポーネントを作成する場合は、このウィザードを使用してコントロールを作成します。  詳細については、「[MFC ActiveX コントロール](../../mfc/mfc-activex-controls.md)」を参照してください。  
  
 また、[MFC アプリケーション ウィザード](../Topic/MFC%20Application%20Wizard.md)を使用して、オートメーション サーバー MFC アプリケーションを作成できます。  
  
 このウィザードで作成した ActiveX コントロールではユーザー インターフェイスを使用できます。また、コントロールが表示されないように設定することもできます。  コントロールが表示されないように指定するオプションは、ウィザードの [&#91;コントロールの設定&#93;](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) ページにあります。  表示が不要な ActiveX コントロールの例として、タイマー コントロールなどがあります。  
  
 ActiveX コントロールでは複雑なユーザー インターフェイスを使用できます。  カプセル化された複数のフォームを持つコントロールもあります。つまり、1 つのコントロールに多数のフィールドが含まれており、それぞれが Windows コントロールとして独立している場合があります。  たとえば、単一の MFC ActiveX コントロールとして実装された自動車部品オブジェクトをフォーム形式のユーザー インターフェイスとして表示できます。ユーザーは、このインターフェイスを通じて部品番号や部品名などの情報を読んだり編集したりできます。  詳細については、「[MFC ActiveX コントロール](../../mfc/mfc-activex-controls.md)」を参照してください。  
  
 ActiveX オブジェクトのコンテナーを作成する必要がある場合は、「[MFC ActiveX コントロール コンテナーの作成](../../mfc/reference/creating-an-mfc-activex-control-container.md)」を参照してください。  
  
 MFC の初期プログラムには、C\+\+ ソース \(.cpp\) ファイル、リソース \(.rc\) ファイル、およびプロジェクト \(.vcxproj\) ファイルが含まれます。  これらの初期ファイルで生成されたコードは、MFC に基づいています。  
  
 以下のトピックでは、ActiveX コントロールのタスクおよび拡張機能について説明しています。  
  
-   [MFC ActiveX コントロール : 最適化](../../mfc/mfc-activex-controls-optimization.md)  
  
-   [MFC ActiveX コントロール : ActiveX コントロールへのストック イベントの追加](../Topic/MFC%20ActiveX%20Controls:%20Adding%20Stock%20Events%20to%20an%20ActiveX%20Control.md)  
  
-   [MFC ActiveX コントロール : カスタム イベントの追加](../Topic/MFC%20ActiveX%20Controls:%20Adding%20Custom%20Events.md)  
  
-   [MFC ActiveX コントロール : ストック メソッドの追加](../../mfc/mfc-activex-controls-adding-stock-methods.md)  
  
-   [MFC ActiveX コントロール : カスタム メソッドの追加](../../mfc/mfc-activex-controls-adding-custom-methods.md)  
  
-   [MFC ActiveX コントロール : ストック プロパティの追加](../Topic/MFC%20ActiveX%20Controls:%20Adding%20Stock%20Properties.md)  
  
-   [MFC ActiveX コントロール : カスタム プロパティの追加](../../mfc/mfc-activex-controls-adding-custom-properties.md)  
  
-   [ActiveX コントロール コンテナー : ActiveX コントロール コンテナーでの ActiveX コントロールのプログラミング](../../mfc/programming-activex-controls-in-a-activex-control-container.md)  
  
## 概要  
 ウィザードのこのページでは、作成する MFC ActiveX コントロール プロジェクトの現在のアプリケーション設定が示されます。  既定では、このウィザードでは、次のようなウィザード プロジェクトが作成されます。  
  
-   既定のプロジェクトでは、ランタイム ライセンスもヘルプ ファイルも生成されません。  これらの既定の設定は、[&#91;アプリケーションの設定&#93;](../../mfc/reference/application-settings-mfc-activex-control-wizard.md) ページで変更できます。  ActiveX コントロール ウィザードのこのページで選択した内容だけが、\[概要\] ページに反映されます。  
  
-   プロジェクトには、プロジェクト名に基づくコントロール クラスとプロパティ ページ クラスが含まれます。  プロジェクト名とファイル名は、[&#91;コントロール名&#93;](../../mfc/reference/control-names-mfc-activex-control-wizard.md) ページで編集できます。  
  
-   コントロールは既存のどの Windows コントロールにも基づいていません。このコントロールは画面に表示されるとアクティブになり、ユーザー インターフェイスを使用し、**\[バージョン情報\]** ダイアログ ボックスを含みます。  これらの既定の設定は、[&#91;コントロールの設定&#93;](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) ページで変更できます。  
  
## 参照  
 [Visual C\+\+ プロジェクトの作成および管理](../../ide/creating-and-managing-visual-cpp-projects.md)   
 [Visual C\+\+ プロジェクトの種類](../../ide/visual-cpp-project-types.md)   
 [概念](../../atl/active-template-library-atl-concepts.md)