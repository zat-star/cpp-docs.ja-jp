---
title: "CToolBar クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CToolBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ビットマップ [C++], ボタン コントロール"
  - "ボタン [C++], MFC ツール バー"
  - "コントロール バー [C++], CToolBar クラス"
  - "CToolBar クラス"
  - "ツール バー [C++], CToolBar クラス"
  - "Windows コモン コントロール [C++], CToolBar クラス"
  - "Windows ツール バーのコモン コントロール [C++]"
ms.assetid: e868da26-5e07-4607-9651-e2f863ad9059
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CToolBar クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

一連のビットマップ ボタンおよびオプションの区切り記号を含むコントロール バーです。  
  
## 構文  
  
```  
class CToolBar : public CControlBar  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CToolBar::CToolBar](../Topic/CToolBar::CToolBar.md)|`CToolBar` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CToolBar::CommandToIndex](../Topic/CToolBar::CommandToIndex.md)|指定したコマンド ID を持つボタンのインデックスを返します。|  
|[CToolBar::Create](../Topic/CToolBar::Create.md)|Windows ツール バーを作成して `CToolBar` のオブジェクトにアタッチします。|  
|[CToolBar::CreateEx](../Topic/CToolBar::CreateEx.md)|`CToolBarCtrl` の埋め込みオブジェクトの追加スタイルの `CToolBar` のオブジェクトを作成します。|  
|[CToolBar::GetButtonInfo](../Topic/CToolBar::GetButtonInfo.md)|ボタンの ID、スタイル、およびイメージ数を取得します。|  
|[CToolBar::GetButtonStyle](../Topic/CToolBar::GetButtonStyle.md)|ボタンのスタイルを取得します。|  
|[CToolBar::GetButtonText](../Topic/CToolBar::GetButtonText.md)|ボタンに表示されるテキストを取得します。|  
|[CToolBar::GetItemID](../Topic/CToolBar::GetItemID.md)|指定したインデックス位置にあるボタンまたは区切り記号のコマンド ID を返します。|  
|[CToolBar::GetItemRect](../Topic/CToolBar::GetItemRect.md)|指定されたインデックスの項目を表示する四角形を取得します。|  
|[CToolBar::GetToolBarCtrl](../Topic/CToolBar::GetToolBarCtrl.md)|基になるコモン コントロールであるに直接アクセスできます。|  
|[CToolBar::LoadBitmap](../Topic/CToolBar::LoadBitmap.md)|ビットマップ ボタンのイメージを含むビットマップを読み込みます。|  
|[CToolbar::LoadToolBar](../Topic/CToolBar::LoadToolBar.md)|リソース エディターで作成されたツール バー リソースを読み込みます。|  
|[CToolBar::SetBitmap](../Topic/CToolBar::SetBitmap.md)|ビットマップ イメージを設定します。|  
|[CToolBar::SetButtonInfo](../Topic/CToolBar::SetButtonInfo.md)|ボタンの ID、スタイル、およびイメージ数を設定します。|  
|[CToolBar::SetButtons](../Topic/CToolBar::SetButtons.md)|セットは、ビットマップ内のボタン イメージのスタイルとインデックスにボタンの値。|  
|[CToolBar::SetButtonStyle](../Topic/CToolBar::SetButtonStyle.md)|ボタンのスタイルを設定します。|  
|[CToolBar::SetButtonText](../Topic/CToolBar::SetButtonText.md)|ボタンに表示されるテキストを設定します。|  
|[CToolBar::SetHeight](../Topic/CToolBar::SetHeight.md)|ツール バーの高さを設定します。|  
|[CToolBar::SetSizes](../Topic/CToolBar::SetSizes.md)|ボタンおよびビットマップのサイズを設定します。|  
  
## 解説  
 ボタンは、プッシュ ボタン、チェック ボックスのボタン、またはラジオ ボタンのように動作します。  `CToolBar` のオブジェクトは、通常、クラス [CFrameWnd](../../mfc/reference/cframewnd-class.md) か [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)から派生したフレーム ウィンドウ オブジェクトの埋め込みメンバーです。  
  
 [CToolBar::GetToolBarCtrl](../Topic/CToolBar::GetToolBarCtrl.md)の MFC 4.0 に新しいメンバー関数は、ツール バーのカスタマイズと追加の機能の Windows コモン コントロールのサポートを利用できるようにします。  `CToolBar` のメンバー関数は、Windows コモン コントロールの機能の最もいます; ただし、`GetToolBarCtrl`を呼び出すと、\/98 のツール バー、ツール バー、Windows 95 の特性をさらに指定できます。  `GetToolBarCtrl`を呼び出すと、`CToolBarCtrl` のオブジェクトへの参照を返します。  Windows コモン コントロールを使用してツール バーのデザインに関する詳細については、[CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) を参照してください。  コモン コントロールについては、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [\[コモン コントロール\]](http://msdn.microsoft.com/library/windows/desktop/bb775493) を参照してください。  
  
 Visual C\+\+ は 2 とおりの方法をツール バーを作成する方法について説明します。  リソース エディターを使用してツール バー リソースを作成するには、次の手順を実行する:  
  
1.  ツール バー リソースを作成します。  
  
2.  `CToolBar` オブジェクトを構築します。  
  
3.  Windows ツール バーを作成して `CToolBar` のオブジェクトにアタッチするに [&#91;作成&#93;](../Topic/CToolBar::Create.md) \(または\) [CreateEx](../Topic/CToolBar::CreateEx.md)関数を呼び出します。  
  
4.  ツール バー リソースを読み込みます [LoadToolBar](../Topic/CToolBar::LoadToolBar.md)。  
  
 それ以外の場合は、次の手順を実行します。  
  
1.  `CToolBar` オブジェクトを構築します。  
  
2.  Windows ツール バーを作成して `CToolBar` のオブジェクトにアタッチするに [&#91;作成&#93;](../Topic/CToolBar::Create.md) \(または\) [CreateEx](../Topic/CToolBar::CreateEx.md)関数を呼び出します。  
  
3.  ツール バー ボタンのイメージを含むビットマップを読み込むに [LoadBitmap](../Topic/CToolBar::LoadBitmap.md) を呼び出します。  
  
4.  ボタンのスタイルを設定し、ビットマップ イメージと各ボタンを関連付けるに [SetButtons](../Topic/CToolBar::SetButtons.md) を呼び出します。  
  
 ツール バーのすべてのボタンのイメージは、ボタンごとに 1 のイメージを含める必要がある 1 個のビットマップから作成されます。  すべてのイメージは同じサイズである必要があります; 既定の幅は 16 ピクセル、高さ 15 ピクセルです。  イメージはビットマップで side\-by\-side である必要があります。  
  
 `SetButtons` 関数は、コントロールの ID と配列の要素の数を指定する整数の配列へのポインターを渡します。  関数は、配列の対応する要素の値に、各ボタンの ID を設定し、各ボタンにビットマップでボタンのイメージの位置を指定するイメージのインデックスを割り当てます。  配列要素に値 **ID\_SEPARATOR**がある場合、イメージ インデックスは使用できません。  
  
 ビットマップ イメージの順序は、通常は、それらが画面に描画、イメージの順序と描画の順序との関係を変更するに [SetButtonInfo](../Topic/CToolBar::SetButtonInfo.md) 関数を使用する順序です。  
  
 ツール バーのすべてのボタンは同じサイズです。  既定値は、*ソフトウェア設計の Windows インターフェイスのガイドライン*に従って、24 x 22 ピクセルです。  イメージとボタンの寸法間の追加の空間がイメージの周囲に境界線を形成するために使用されます。  
  
 各ボタンに、1 種類のイメージがあります。  さまざまなボタンの状態とスタイル \(、無効にすると、中間無効な上で押す\)、1 種類のイメージから生成されます。  ビットマップがどの色ですが、色合い灰色の黒のイメージの最適な結果を得ることができます。  
  
> [!WARNING]
>  `CToolBar` は最大 16 色のビットマップをサポートします。  ツール バー エディターにイメージを読み込むと、Visual Studio は 16 色のビットマップに自動的にイメージが変換済みイメージを必要に応じて変換し、警告メッセージが表示されます。  16 色以上のイメージ \(イメージを編集する外部エディターを使用して\) を使用する場合は、アプリケーションが予期せずに終了することがあります。  
  
 ツール バー ボタンはプッシュ ボタンが既定でシミュレートします。  ただし、ツール バー ボタンまたはチェック ボックスのボタン \(ラジオ ボタンをシミュレートできます。  チェック ボックスのボタンは、3 種類の状態があります: オン、オフにすると、中間。  ラジオ ボタンは 2 種類の状態だけがあります: チェックし、を選択します。  
  
 配列に指定しないで個々のボタンまたは区切り記号のスタイルを設定するには、スタイルを取得するために [GetButtonStyle](../Topic/CToolBar::GetButtonStyle.md) を呼び出して次に `SetButtons`の代わりに [SetButtonStyle](../Topic/CToolBar::SetButtonStyle.md) を呼び出します。  `SetButtonStyle` は、実行時にボタンのスタイルを変更する場合に便利です。  
  
 ボタンに表示するテキストをに割り当てるにはテキストをボタンに表示されるように取得できるように [GetButtonText](../Topic/CToolBar::GetButtonText.md) を呼び出し、次にテキストを設定するに [SetButtonText](../Topic/CToolBar::SetButtonText.md) を呼び出します。  
  
 チェック ボックスのボタンを作成するか、スタイル **TBBS\_CHECKBOX** を割り当てるか、または `CCmdUI` のオブジェクトの `SetCheck` のメンバー関数を `ON_UPDATE_COMMAND_UI` のハンドラーで実行します。  `SetCheck` を呼び出すと、チェック ボックスのボタンにプッシュ ボタンを切り替えます。  `SetCheck` にオフの場合は 0、チェックされたの 1、または中間の 2 引数を渡します。  
  
 ラジオ ボタンを作成するには、`ON_UPDATE_COMMAND_UI` のハンドラーから [CCmdUI](../Topic/CCmdUI%20Class.md) のオブジェクトの [SetRadio](../Topic/CCmdUI::SetRadio.md) のメンバー関数を呼び出します。  `SetRadio` にチェックインされるのかオフに非ゼロの 0 引数を渡します。  オプション グループの相互に排他的な動作を提供するには、グループのすべてのボタンの `ON_UPDATE_COMMAND_UI` のハンドラーが必要です。  
  
 `CToolBar`の使用の詳細については、" " [MFC ツール バーの実装](../../mfc/mfc-toolbar-implementation.md) と [テクニカル ノート 31: コントロール バー](../../mfc/tn031-control-bars.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CToolBar`  
  
## 必要条件  
 **Header:** afxext.h  
  
## 参照  
 [MFC CTRLBARS サンプル](../../top/visual-cpp-samples.md)   
 [MFC DLGCBR32 サンプル](../../top/visual-cpp-samples.md)   
 [MFC DOCKTOOL サンプル](../../top/visual-cpp-samples.md)   
 [CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CToolBarCtrl クラス](../../mfc/reference/ctoolbarctrl-class.md)   
 [CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)   
 [CToolBar::Create](../Topic/CToolBar::Create.md)   
 [CToolBar::LoadBitmap](../Topic/CToolBar::LoadBitmap.md)   
 [CToolBar::SetButtons](../Topic/CToolBar::SetButtons.md)   
 [CCmdUI::SetCheck](../Topic/CCmdUI::SetCheck.md)   
 [CCmdUI::SetRadio](../Topic/CCmdUI::SetRadio.md)