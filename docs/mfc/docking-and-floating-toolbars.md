---
title: "ドッキング ツール バーとフローティング ツール バー | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CBRS_SIZE_DYNAMIC"
  - "CBRS_SIZE_FIXED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBRS_ALIGN_ANY 定数"
  - "CBRS_SIZE_DYNAMIC 定数"
  - "CBRS_SIZE_FIXED 定数"
  - "固定サイズのツール バー"
  - "フローティング パレット"
  - "フローティング ツール バー"
  - "フレーム ウィンドウ, ツール バーのドッキング"
  - "パレット, フローティング"
  - "サイズ"
  - "サイズ, ツール バー"
  - "ツール バー コントロール [MFC], ラップ"
  - "ツール バー [C++], ドッキング"
  - "ツール バー [C++], フローティング"
  - "ツール バー [C++], サイズ"
  - "ツール バー [C++], ラップ"
ms.assetid: b7f9f9d4-f629-47d2-a3c4-2b33fa6b51e4
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ドッキング ツール バーとフローティング ツール バー
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft Foundation Class ライブラリにはドッキング可能ツール バーをサポートします。  ドッキング可能ツール バーは添付にすることも、親ウィンドウの各辺にドッキングされて、独自のミニフレーム ウィンドウの辺またはデタッチします。  ここでは、アプリケーションでドッキング可能ツール バーを使用する方法について説明します。  
  
 アプリケーションのスケルトンを生成するときにアプリケーション ウィザードを使用してドッキング可能ツール バーが必要かを選択するように指示されます。  既定では、アプリケーション ウィザードはアプリケーションにドッキング可能ツール バーを配置するための 3 種類の操作を実行するコードを生成する:  
  
-   [フレーム ウィンドウのドッキング](#_core_enabling_docking_in_a_frame_window)。  
  
-   [ツール バーのドッキングを有効にする](#_core_enabling_docking_for_a_toolbar)。  
  
-   [ツール バーをドッキングしてください \(フレーム ウィンドウに\)](#_core_docking_the_toolbar)。  
  
 これらの手順のいずれかが存在しない場合、アプリケーションは標準ツール バーが表示されます。  最後の 2 つの手順は、アプリケーションの各ドッキング可能ツール バーごとに必要です。  
  
 この記事で説明されている他のトピックは次のとおりです。:  
  
-   [フローティング ツール バー](#_core_floating_the_toolbar)  
  
-   [動的にツール バーのサイズを変更できます。](#_core_dynamically_resizing_the_toolbar)  
  
-   [固定スタイルのツール バーの折り返しの位置の設定](#_core_setting_wrap_positions_for_a_fixed.2d.style_toolbar)  
  
 MFC に例の一般的な [DOCKTOOL](../top/visual-cpp-samples.md) サンプルを参照してください。  
  
##  <a name="_core_enabling_docking_in_a_frame_window"></a> フレーム ウィンドウのドッキングを有効にします。  
 ツール バーをフレーム ウィンドウにドッキングするには、フレーム ウィンドウ \(または対象\) ドッキングすることのできるようにする必要があります。  次に示す一連のスタイル ビットのドッキング先のフレーム ウィンドウの辺を受け入れるとともにある `DWORD` 1 個のパラメーターを受け取る [CFrameWnd::EnableDocking](../Topic/CFrameWnd::EnableDocking.md) 関数を使用します。  にドッキングできるツール バーがドッキングされるとしており、複数の側がある場合 `EnableDocking` に渡されるパラメーターで指定されている側は次の順序で使用されています: Top、Left、Right です。  任意のコントロール バーをドッキングできるようにするには `EnableDocking`に `CBRS_ALIGN_ANY` を渡します。  
  
##  <a name="_core_enabling_docking_for_a_toolbar"></a> ツール バーのドッキングを有効にします。  
 ドッキングの出力先の準備が整ったら、ツール バー \(ソース\) を同じように準備する必要があります。  ドッキングし、各ツール バーの呼び出し [CControlBar::EnableDocking](../Topic/CControlBar::EnableDocking.md) ツール バーがドッキングする必要のある先の辺を指定します。  `CControlBar::EnableDocking` の一致がフレーム ウィンドウのドッキングの呼び出しで指定した辺が有効になっている側のドッキング ツール バー、—置きます。  いったんフローティング状態になると、そのツール バーはフローティング ツール バーのままとなり、フレーム ウィンドウにはドッキングできません。  
  
 表示する効果が完全にフローティング ツール バー、呼び出す 0 のパラメーターの `EnableDocking` である場合。  [CFrameWnd::FloatControlBar](../Topic/CFrameWnd::FloatControlBar.md)を呼び出す。  ツール バーは、任意の場所にドッキングすると、完全にフローティングに残ります。  
  
##  <a name="_core_docking_the_toolbar"></a> ツールバーのドッキング  
 フレームワークは、ユーザーがその割り当てのフレーム ウィンドウの辺にドッキング バーを削除しようとしたとき [CFrameWnd::DockControlBar](../Topic/CFrameWnd::DockControlBar.md) を呼び出します。  
  
 また、コントロール バーをフレーム ウィンドウにドッキングする場合は、この関数をいつでも呼び出すことができます。  これは、初期化中に、されます。  複数のツール バーがフレーム ウィンドウの指定した辺にドッキングすることもできます。  
  
##  <a name="_core_floating_the_toolbar"></a> フローティング ツール バー  
 ドッキング可能ツール バーをフレーム ウィンドウからデタッチ ツール バーをフローティングと呼ばれます。  これを行う [CFrameWnd::FloatControlBar](../Topic/CFrameWnd::FloatControlBar.md) 呼び出し。  フローティングにツール バーを配置する必要があるとフローティング ツール バーを水平または垂直のどちらであるかを判断配置スタイルをポイントを指定してください。  
  
 フレームワークは、ユーザーがドッキングが有効になっていない場所にドッキングされた場所とドロップからツール バーを描画するときにこの関数を呼び出します。  これは、フレーム ウィンドウ内にまたは外のどこでもかまいません。  `DockControlBar`と同様に、初期化中にこの関数を呼び出すことができます。  
  
 ドッキング可能ツール バーの MFC 実装はドッキング可能ツール バーをサポートするアプリケーションにある拡張機能の一部を提供しません。  カスタマイズ可能なツール バーなどの機能は提供されません。  
  
##  <a name="_core_dynamically_resizing_the_toolbar"></a> 動的にツール バーのサイズを変更できます。  
 Visual C\+\+ 4.0 以降では、アプリケーションのユーザーがフローティング ツール バーのサイズを動的に変更できるようにすることができます。  通常、ツール バーに水平に表示されている長い、線形図形があります。  ただし、ツール バーの方向と形状を変更できます。  たとえば、ユーザーがフレーム ウィンドウの垂直方向の端に 1 に対してツール バーをドッキングすると、図形は縦のレイアウトに変更します。  ボタンを複数の行に四角形にツール バーを作成することもできます。  
  
 次の操作を行うことができます。  
  
-   ツール バーの特性として動的なサイズ変更を指定します。  
  
-   ツール バーの特性として固定サイズを指定します。  
  
 この機能をサポートするには、[CToolBar::Create](../Topic/CToolBar::Create.md) のメンバー関数呼び出しの 2 種類の新しいツール バー スタイルです。  それらは次のとおりです。  
  
-   **CBRS\_SIZE\_DYNAMIC** コントロール バーは動的です。  
  
-   **CBRS\_SIZE\_FIXED** コントロール バーが修正されます。  
  
 サイズの動的なスタイルは重ねると、がない場合、ドッキングされるユーザーがツール バーのサイズを変更できるようにします。  ツール バーは、「ユーザーのドラッグとして変換に必要末尾位置にラップします」。  
  
 サイズの固定のスタイルは、各列のボタンの位置を修正するツール バーの折り返しの状態を維持します。  アプリケーションのユーザーは、ツール バーの形状を変更できません。  ボタンの間に区切り記号の位置などの指定された位置のツール バーにラップします。  また、ツール バーがドッキングされるフローティングかどうかこの図形を保持します。  効果はボタンを複数の列を使用して固定パレットです。  
  
 ツール バーのボタンの状態およびスタイルを返すために [CToolBar::GetButtonStyle](../Topic/CToolBar::GetButtonStyle.md) を使用できます。  ボタンのスタイルがボタンの表示、およびユーザー入力に応答するかを; 状態は、ボタンがラップされた状態かどうかを示します。  
  
##  <a name="_core_setting_wrap_positions_for_a_fixed.2d.style_toolbar"></a> 固定スタイルのツール バーの折り返しの位置の設定  
 固定サイズのスタイルのツール バーでは、選択されたツール バー ボタンのインデックスをラップするツール バー。  次のコードは、メイン フレーム ウィンドウの `OnCreate` のオーバーライドでこれを行う方法を説明します:  
  
 [!code-cpp[NVC_MFCDocViewSDI#10](../mfc/codesnippet/CPP/docking-and-floating-toolbars_1.cpp)]  
  
 MFC の一般的なサンプル [DOCKTOOL](../top/visual-cpp-samples.md) 表示クラス [CControlBar](../mfc/reference/ccontrolbar-class.md) と [CToolBar](../mfc/reference/ctoolbar-class.md) メンバー関数をツール バーの動的レイアウトを管理する方法を示します。  DOCKTOOL のファイル EDITBAR.CPP を参照してください。  
  
### さらに詳しくは次のトピックをクリックしてください  
  
-   [ツール バーに関する基本事項](../mfc/toolbar-fundamentals.md)  
  
-   [ツール バーのツール ヒント](../Topic/Toolbar%20Tool%20Tips.md)  
  
-   [古いツール バーを使用する](../Topic/Using%20Your%20Old%20Toolbars.md)  
  
## 参照  
 [MFC ツール バーの実装](../mfc/mfc-toolbar-implementation.md)