---
title: "CBitmapButton クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CBitmapButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ビットマップ, ボタン コントロール"
  - "ボタン, ビットマップ"
  - "CBitmapButton クラス"
ms.assetid: 9ad6cb45-c3c4-4fb1-96d3-1fe3df7bbcfc
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CBitmapButton クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ラベルがテキストではなくビットマップ イメージのプッシュ ボタン コントロールを作成します。  
  
## 構文  
  
```  
class CBitmapButton : public CButton  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CBitmapButton::CBitmapButton](../Topic/CBitmapButton::CBitmapButton.md)|`CBitmapButton` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CBitmapButton::AutoLoad](../Topic/CBitmapButton::AutoLoad.md)|ダイアログ ボックスのボタンを `CBitmapButton` のクラスのオブジェクトと関連付け、ビットマップを名前で読み込んで、ビットマップに合わせてボタンのサイズを設定します。|  
|[CBitmapButton::LoadBitmaps](../Topic/CBitmapButton::LoadBitmaps.md)|オブジェクトへのアプリケーションのリソース ファイルから一つ以上の名前付きビットマップ リソースの読み込みおよびビットマップを割り当てることによってオブジェクトを初期化します。|  
|[CBitmapButton::SizeToContent](../Topic/CBitmapButton::SizeToContent.md)|ボタンのビットマップが収まるようにサイズが調整されます。|  
  
## 解説  
 `CBitmapButton` のオブジェクトは、ボタンが判断できるさまざまな状態のイメージを持つ 4 つまでのビットマップが含まれています: の上 \(または標準\)、\(または選択される\)、ローカライズされ、無効にします。  最初のビットマップのみ必要です; そのほかは省略可能です。  
  
 ビットマップ ボタンのイメージは、イメージ、またはイメージの周囲に境界線が含まれます。  境界線は、通常、ボタンの状態の表示の役割を果たします。  たとえば、フォーカスがある状態のビットマップは、その境界に上向きの状態の、境界線または太い実線の破線の四角形のくぼんだと通常のようになります。  無効な状態のビットマップは通常、上向きの状態を表す 1 桁に似ていますが、下位のコントラストがあります \(淡色または灰色のメニュー選択など\)。  
  
 これらのビットマップは、任意のサイズですが、同じサイズと上向きの状態のビットマップのようにすべてが処理されます。  
  
 さまざまなアプリケーションでビットマップ イメージのさまざまな組み合わせが必要です:  
  
|上へ|下へ|Focused|Disabled|アプリケーション|  
|--------|--------|-------------|--------------|--------------|  
|×||||ビットマップ|  
|×|×|||**WS\_TABSTOP** のないボタンのスタイル|  
|×|×|×|×|すべての状態のダイアログのボタン|  
|×|×|×||**WS\_TABSTOP** のスタイルのダイアログのボタン|  
  
 ビットマップ ボタン コントロールを作成する場合、ボタンがオーナー描画するように指定するに **BS\_OWNERDRAW** のスタイルを設定します。  これにより、Windows はボタンの `WM_MEASUREITEM` と `WM_DRAWITEM` のメッセージを送信します; フレームワークは、これらのメッセージを処理してのボタンの外観を管理します。  
  
### ウィンドウのクライアント領域のビットマップ ボタン コントロールを作成するには  
  
1.  ボタンの 1 ~ 4 個のビットマップ イメージを生成します。  
  
2.  [CBitmapButton](../Topic/CBitmapButton::CBitmapButton.md) のオブジェクトを構築します。  
  
3.  Windows のボタン コントロールを作成し、`CBitmapButton` のオブジェクトにアタッチするに [&#91;作成&#93;](../Topic/CButton::Create.md) 関数を呼び出します。  
  
4.  ビットマップ ボタンが構築されたらビットマップ リソースを読み込むように [LoadBitmaps](../Topic/CBitmapButton::LoadBitmaps.md) のメンバー関数を呼び出します。  
  
### ビットマップ ボタン コントロールをダイアログ ボックスに含めるには  
  
1.  ボタンの 1 ~ 4 個のビットマップ イメージを生成します。  
  
2.  ビットマップ ボタンを目的の位置に設定されているオーナー描画ボタンを含むダイアログ テンプレートを作成します。  テンプレートのボタンのサイズは重要ではありません。  
  
3.  ボタンのキャプションを**MYIMAGE**「」などの値に設定し、**IDC\_MYIMAGE**などのボタンのシンボルを定義します。  
  
4.  アプリケーションのリソース スクリプトでは、手順 3.でボタンのキャプションに使用する文字列にボタン用に作成されたイメージをそれぞれ文字「U の 1 種類の」、「D 追加に構築された」、ID 「F」、または「X」 \(の場合は、ローカライズされ、無効化\) 付けます。  ボタンのキャプション**MYIMAGE**「の」たとえば、ID は、「**MYIMAGEU**」、「**MYIMAGED**」、「**MYIMAGEF**」、および「」**MYIMAGEX**。**must** 二重引用符で囲むのビットマップの ID を指定します。  他のエディターでリソースが、リソースに整数を割り当て、イメージを読み込むときに、MFC は失敗します。  
  
5.  アプリケーションのダイアログ クラスでは `CDialog` \(から派生\)、`CBitmapButton` のメンバー オブジェクトを追加します。  
  
6.  `CDialog` のオブジェクトの [OnInitDialog](../Topic/CDialog::OnInitDialog.md) ルーチンでは、`CBitmapButton` のオブジェクトの [自動ロード](../Topic/CBitmapButton::AutoLoad.md) 関数を呼び出し、パラメーターとしてボタンのコントロール ID と `CDialog` のオブジェクトの **this** のポインター使用します。  
  
 処理する場合、Windows の通知メッセージ、親にビットマップ ボタン コントロールから送信された **BN\_CLICKED**のような \(通常 **CDialog\)**から派生したクラスは、`CDialog`派生オブジェクトへ各メッセージのメッセージ マップのエントリとメッセージ ハンドラー メンバー関数追加します。  `CBitmapButton` のオブジェクトから送信される通知は [CButton](../../mfc/reference/cbutton-class.md) のオブジェクトが送信した場合と同じです。  
  
 クラス [CToolBar](../../mfc/reference/ctoolbar-class.md) は、ビットマップ ボタンに別の方法を受け取ります。  
  
 `CBitmapButton`の詳細については、[コントロール](../../mfc/controls-mfc.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CBitmapButton`  
  
## 必要条件  
 **Header:** afxext.h  
  
## 参照  
 [MFC CTRLTEST サンプル](../../top/visual-cpp-samples.md)   
 [CButton クラス](../../mfc/reference/cbutton-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)