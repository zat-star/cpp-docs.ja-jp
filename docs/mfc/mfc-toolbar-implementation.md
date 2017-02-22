---
title: "MFC ツール バーの実装 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ビットマップ [C++], ツール バー"
  - "ボタン [C++], MFC ツール バー"
  - "CToolBar クラス, 作成 (ツール バーを)"
  - "CToolBarCtrl クラス, 実装 (ツール バーを)"
  - "ドッキング (ツール バー)"
  - "フローティング ツール バー"
  - "MFC ツール バー"
  - "ツール ヒント [C++], 有効化"
  - "ツール バー コントロール [MFC]"
  - "ツール バー [C++]"
  - "ツール バー [C++], 作成"
  - "ツール バー [C++], ドッキング"
  - "ツール バー [C++], フローティング"
  - "ツール バー [C++], 実装 (MFC ツール バーを)"
ms.assetid: af3319ad-c430-4f90-8361-e6a2c06fd084
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# MFC ツール バーの実装
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ツール バーとは、コントロールのビットマップ イメージを含む[コントロール バー](../Topic/Control%20Bars.md)のことです。  これらのイメージはプッシュ ボタン、チェック ボックス、オプション ボタンに似た動作をすることができます。  MFC には、ツール バーを管理するための [CToolbar](../mfc/reference/ctoolbar-class.md) クラスがあります。  
  
 これを有効にすると、MFC ツール バーのユーザーは、ツール バーをウィンドウの端にドッキングするか、アプリケーション ウィンドウ内の任意の場所にツール バーを "フローティング" させることができます。  MFC では、開発環境のようなカスタマイズ可能なツール バーをサポートしていません。  
  
 MFC では、ツール ヒントもサポートしています。これは、マウス ポインターをボタンの上に移動したときに、ツール バー ボタンの目的を説明する小さなポップアップ ウィンドウです。  既定では、ユーザーがツール バー ボタンをクリックすると、ステータス バー \(表示されている場合\) の中に、ステータス文字列が表示されます。  ボタンをクリックせずに、マウス ポインターをツール バー ボタンの上に移動したときに、ステータス文字列の表示を更新する、"フライ バイ" \(リアルタイム更新\) ステータス バーを有効にすることもできます。  
  
> [!NOTE]
>  MFC バージョン 4.0 の時点で、ツール バーとツール ヒントは、MFC 固有の以前の実装ではなく、Windows 95 以降の機能を使用して実装されています。  
  
 下位互換性のため、MFC では古いツール バーの実装をクラス **COldToolBar** の中に保持しています。  以前のバージョンの MFC に関するドキュメントは `CToolBar`の中で **COldToolBar** について説明しています。  
  
 アプリケーション ウィザードの \[ツール バー\] オプションをクリックし、プログラムの最初のツール バーを作成します。  追加のツール バーを作成することもできます。  
  
 この記事では、次の項目を紹介します。  
  
-   [ツール バー ボタン](#_core_toolbar_buttons)  
  
-   [ツール バーのフローティングとドッキング](#_core_docking_and_floating_toolbars)  
  
-   [ツール バーとツール ヒント](#_core_toolbars_and_tool_tips)  
  
-   [CToolBar クラスと CToolBarCtrl クラス](#_core_the_ctoolbar_and_ctoolbarctrl_classes)  
  
-   [ツール バー ビットマップ](#_core_the_toolbar_bitmap)  
  
##  <a name="_core_toolbar_buttons"></a> ツール バー ボタン  
 ツール バー内のボタンは、メニュー内の項目に似ています。  どちらの種類のユーザー インターフェイス オブジェクトも、コマンドを生成します。プログラムはハンドラー関数を提供して、これらのコマンドを処理します。  多くの場合、ツール バー ボタンはメニュー コマンドの機能を複製したものであり、同じ機能に対する別のユーザー インターフェイスを提供します。  このような重複は、単純にボタンとメニュー項目に対して同じ ID を付与する方法で実現できます。  
  
 ツール バー内で、プッシュ ボタン、チェック ボックス、またはオプション ボタンと同じ外観でボタンを作成し、同じ動作をさせることができます。  詳細については、["CToolBar \(CToolBar\)"](../mfc/reference/ctoolbar-class.md) クラスを参照してください。  
  
##  <a name="_core_docking_and_floating_toolbars"></a> ツール バーのドッキングとフローティング  
 MFC ツール バーでは、次のことを実行できます。  
  
-   親ウィンドウの 1 つの辺に固定したままにします。  
  
-   ドラッグして、親ウィンドウの任意の辺に "ドッキング" させます \(取り付けます\)。  
  
-   フレーム ウィンドウから切り離し、ミニフレーム ウィンドウの形でツール バーとして使用します。このツール バーは、ユーザーが任意の場所に移動できます。  
  
-   フローティング中にサイズを変更します。  
  
 詳細については、「[ドッキング ツール バーとフローティング ツール バー](../mfc/docking-and-floating-toolbars.md)」を参照してください。  
  
##  <a name="_core_toolbars_and_tool_tips"></a> ツール バーとツール ヒント  
 MFC ツール バーには "ツール ヒント" を表示させることもできます。ツール ヒントとは、ツール バー ボタンの用途を説明する短いテキストを表示する小さなポップアップ ウィンドウのことです。  ユーザーがツール バー ボタンの上にマウス ポインタを置くと、ヒントを示すツール ヒントのウィンドウがポップアップ表示されます。  詳細については、「[ツール バーのツール ヒント](../Topic/Toolbar%20Tool%20Tips.md)」を参照してください。  
  
##  <a name="_core_the_ctoolbar_and_ctoolbarctrl_classes"></a> CToolBar クラスと CToolBarCtrl クラス  
 アプリケーションのツール バーは、[CToolBar](../mfc/reference/ctoolbar-class.md) クラスを通じて管理します。  MFC Version 4.0 では、Windows 95 以降、および Windows NT Version 3.51 以降のバージョンで使用されているツール バー コモン コントロールを使用できるように、`CToolBar` が再実装されています。  
  
 この再実装により、それらのオペレーティング システムでサポートされているコントロールを MFC で利用できるため、ツール バー関連の MFC コードは少なくなりました。  また、この再実装によって性能も向上しています。  `CToolBar` のメンバー関数を使用してツール バーを操作できます。また、基になる [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) オブジェクトへの参照を取得し、そのメンバー関数を呼び出して、ツール バーをカスタマイズしたり機能を追加したりできます。  
  
> [!TIP]
>  以前の形式の `CToolBar` を実装するために多大な労力を費やしてきた場合は、そのまま以前の形式のツール バーを使用できます。  「[古い形式のツール バーの使用方法](../Topic/Using%20Your%20Old%20Toolbars.md)」を参照してください。  
  
 また、MFC の「標準のサンプル」の「[DOCKTOOL](../top/visual-cpp-samples.md)」も参照してください。  
  
##  <a name="_core_the_toolbar_bitmap"></a> ツール バーのビットマップ  
 `CToolBar` オブジェクトは、いったん生成された後は、各ボタンのイメージを含む 1 つのビットマップを読み込んでツール バー イメージを作成します。  アプリケーション ウィザードでは、Visual C\+\+ [ツール バー エディター](../mfc/toolbar-editor.md)を使用してカスタマイズできる標準ツール バー ビットマップが作成されます。  
  
### さらに詳しくは次のトピックをクリックしてください  
  
-   [ツール バーに関する基本事項](../mfc/toolbar-fundamentals.md)  
  
-   [ツール バーのフローティングとドッキング](../mfc/docking-and-floating-toolbars.md)  
  
-   [ツール バーのツール ヒント](../Topic/Toolbar%20Tool%20Tips.md)  
  
-   [ToolBar コントロールの操作](../Topic/Working%20with%20the%20Toolbar%20Control.md)  
  
-   [古い形式のツール バーの使用方法](../Topic/Using%20Your%20Old%20Toolbars.md)  
  
-   [CToolBar](../mfc/reference/ctoolbar-class.md) クラスと [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) クラス  
  
## 参照  
 [ツール バー](../mfc/toolbars.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)