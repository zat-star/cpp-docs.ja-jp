---
title: "CMDIFrameWnd クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMDIFrameWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMDIFrameWnd クラス"
  - "MDI フレーム ウィンドウ"
ms.assetid: fa8736e6-511b-4c51-8b4d-eba78378aeb9
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMDIFrameWnd クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows のマルチ ドキュメント インターフェイス \(MDI: Multiple Document Interface\) のフレーム ウィンドウの機能が用意されています。さらに、ウィンドウを管理するメンバーも用意されています。  
  
## 構文  
  
```  
class CMDIFrameWnd : public CFrameWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMDIFrameWnd::CMDIFrameWnd](../Topic/CMDIFrameWnd::CMDIFrameWnd.md)|`CMDIFrameWnd` を構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMDIFrameWnd::CreateClient](../Topic/CMDIFrameWnd::CreateClient.md)|この `CMDIFrameWnd`の Windows **MDICLIENT** ペインを作成します。  `CWnd`の `OnCreate` のメンバー関数によって呼び出されます。|  
|[CMDIFrameWnd::CreateNewChild](../Topic/CMDIFrameWnd::CreateNewChild.md)|新しい子ウィンドウを作成します。|  
|[CMDIFrameWnd::GetWindowMenuPopup](../Topic/CMDIFrameWnd::GetWindowMenuPopup.md)|ウィンドウのポップアップ メニューを返します。|  
|[CMDIFrameWnd::MDIActivate](../Topic/CMDIFrameWnd::MDIActivate.md)|別の MDI 子ウィンドウをアクティブにします。|  
|[CMDIFrameWnd::MDICascade](../Topic/CMDIFrameWnd::MDICascade.md)|カスケード形式のすべての子ウィンドウを並べ替えます。|  
|[CMDIFrameWnd::MDIGetActive](../Topic/CMDIFrameWnd::MDIGetActive.md)|子を最大化するかどうかを示すフラグとともに現在アクティブな MDI 子ウィンドウを取得します。|  
|[CMDIFrameWnd::MDIIconArrange](../Topic/CMDIFrameWnd::MDIIconArrange.md)|最小化されたすべてのドキュメントの子ウィンドウを並べ替えます。|  
|[CMDIFrameWnd::MDIMaximize](../Topic/CMDIFrameWnd::MDIMaximize.md)|MDI 子ウィンドウが最大化されます。|  
|[CMDIFrameWnd::MDINext](../Topic/CMDIFrameWnd::MDINext.md)|現在アクティブな子ウィンドウの後ろの子ウィンドウは直ちにアクティブにし、他のすべての子ウィンドウの後ろに現在アクティブな子ウィンドウを設定します。|  
|[CMDIFrameWnd::MDIPrev](../Topic/CMDIFrameWnd::MDIPrev.md)|前の子ウィンドウをアクティブにし、その後ろに現在アクティブな子ウィンドウを直ちに設定します。|  
|[CMDIFrameWnd::MDIRestore](../Topic/CMDIFrameWnd::MDIRestore.md)|最大化または最小化されたサイズの MDI 子ウィンドウを復元します。|  
|[CMDIFrameWnd::MDISetMenu](../Topic/CMDIFrameWnd::MDISetMenu.md)|MDI フレーム ウィンドウ、ウィンドウのポップアップ メニュー、または両方のメニューを置き換えます。|  
|[CMDIFrameWnd::MDITile](../Topic/CMDIFrameWnd::MDITile.md)|並べて表示された形式のすべての子ウィンドウを並べ替えます。|  
  
## 解説  
 アプリケーションのための便利な MDI フレーム ウィンドウを作成するには、`CMDIFrameWnd`からクラスを派生します。  アプリケーションに固有のデータを格納する、派生クラスにメンバー変数を追加します。  ウィンドウにメッセージが送られたときに行われる処理を指定するには、派生クラスにメッセージ処理メンバー関数とメッセージ マップを実装します。  
  
 `CFrameWnd`の [&#91;作成&#93;](../Topic/CFrameWnd::Create.md) または [LoadFrame](../Topic/CFrameWnd::LoadFrame.md) のメンバー関数を呼び出して、MDI フレーム ウィンドウを作成できます。  
  
 **\[作成\]** か `LoadFrame`を呼び出す前に、**new** C\+\+ の演算子を使用してヒープのフレーム ウィンドウ オブジェクトを構築する必要があります。  **\[作成\]** を呼び出す前に、[AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) のグローバル関数のクラスをフレーム ウィンドウのアイコンおよびクラスのスタイルを設定するには、登録できます。  
  
 イミディエイト引数としてフレームの作成のパラメーターを渡すために **\[作成\]** のメンバー関数を使用します。  
  
 `LoadFrame` は **\[作成\]**ほどの引数を必要とし、フレームのキャプション、アイコン、アクセラレータ テーブルとメニューを含むリソースからなく、既定のほとんどを取得します。  `LoadFrame`にアクセスするには、これらのリソースはすべて同じリソース id \(たとえば、**IDR\_MAINFRAME**\) が必要です。  
  
 **MDIFrameWnd** が `CFrameWnd`から派生したが、フレーム ウィンドウ クラスは `CMDIFrameWnd` から `DECLARE_DYNCREATE`で宣言する必要がありません書き込みます。  
  
 `CMDIFrameWnd` のクラスは `CFrameWnd`の既定の実装の大部分を継承します。  これらの機能の詳細については、[CFrameWnd](../../mfc/reference/cframewnd-class.md) のクラスの説明を参照してください。  `CMDIFrameWnd` のクラスに次の機能があります:  
  
-   MDI フレーム ウィンドウは、コントロール バーとともにそれを再配置 **MDICLIENT** のウィンドウを管理します。  MDI クライアント ウィンドウが MDI 子フレーム ウィンドウの直接の親です。  `CMDIFrameWnd` で指定された **WS\_HSCROLL** と **WS\_VSCROLL** のウィンドウ スタイルはメイン フレーム ウィンドウではなく、MDI クライアント ウィンドウに適用します。これによって、ユーザーは、MDI クライアント領域をスクロールできます \(Windows プログラム マネージャーと同様に、たとえば\)。  
  
-   MDI フレーム ウィンドウは、アクティブな MDI 子ウィンドウがない場合、メニュー バーとして使用される既定のメニューを所有します。  アクティブな MDI 子がの場合、MDI フレーム ウィンドウのメニュー バーは、MDI 子ウィンドウのメニューに自動的に置き換えられます。  
  
-   MDI フレーム ウィンドウには、現在の MDI 子ウィンドウと同様に 1 の場合、動作します。  たとえば、コマンド メッセージは、MDI フレーム ウィンドウの前の現在アクティブな MDI 子に転送されます。  
  
-   MDI フレーム ウィンドウは、次の標準的な\[ウィンドウ\]メニューのコマンドの既定のハンドラーがあります:  
  
    -   **ID\_WINDOW\_TILE\_VERT**  
  
    -   **ID\_WINDOW\_TILE\_HORZ**  
  
    -   **ID\_WINDOW\_CASCADE**  
  
    -   **ID\_WINDOW\_ARRANGE**  
  
-   MDI フレーム ウィンドウに、現在のドキュメントの新しいフレームとビューを作成する **ID\_WINDOW\_NEW**の実装があります。  アプリケーションは、MDI ウィンドウの処理をカスタマイズする場合、既定のコマンドの実装をオーバーライドできます。  
  
 フレーム ウィンドウを破棄するときに **\[削除\]** C\+\+ の演算子を使用しないでください。  代わりに、`CWnd::DestroyWindow` を使用してください。  `PostNcDestroy` の `CFrameWnd` の実装では、ウィンドウが破棄されると、C\+\+ のオブジェクトを削除します。  ユーザーがフレーム ウィンドウを閉じると、既定の `OnClose` のハンドラーを呼び出します `DestroyWindow`。  
  
 `CMDIFrameWnd`の詳細については、[フレーム ウィンドウ](../../mfc/frame-windows.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIFrameWnd`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [MFC MDI サンプル](../../top/visual-cpp-samples.md)   
 [MFC MDIDOCVW サンプル](../../top/visual-cpp-samples.md)   
 [MFC SNAPVW サンプル](../../top/visual-cpp-samples.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [CMDIChildWnd クラス](../../mfc/reference/cmdichildwnd-class.md)