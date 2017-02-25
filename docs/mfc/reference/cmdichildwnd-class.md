---
title: "CMDIChildWnd クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMDIChildWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "子ウィンドウ, CMDIChildWnd クラス"
  - "CMDIChildWnd クラス"
  - "MDI [C++], 子ウィンドウ"
  - "ウィンドウ [C++], MDI"
ms.assetid: 6d07f5d4-9a3e-4723-9fa5-e65bb669fdd5
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CMDIChildWnd クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ウィンドウ管理用のメンバーも含めて、Windows のマルチ ドキュメント インターフェイス \(MDI: multiple document interface\) の子ウィンドウの機能が用意されています。  
  
## 構文  
  
```  
class CMDIChildWnd : public CFrameWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMDIChildWnd::CMDIChildWnd](../Topic/CMDIChildWnd::CMDIChildWnd.md)|`CMDIChildWnd` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMDIChildWnd::Create](../Topic/CMDIChildWnd::Create.md)|`CMDIChildWnd` のオブジェクトに関連付けられた Windows の MDI 子ウィンドウを作成します。|  
|[CMDIChildWnd::GetMDIFrame](../Topic/CMDIChildWnd::GetMDIFrame.md)|MDI クライアント ウィンドウの親 MDI フレームを返します。|  
|[CMDIChildWnd::MDIActivate](../Topic/CMDIChildWnd::MDIActivate.md)|この MDI 子ウィンドウをアクティブにします。|  
|[CMDIChildWnd::MDIDestroy](../Topic/CMDIChildWnd::MDIDestroy.md)|この MDI 子ウィンドウを破棄します。|  
|[CMDIChildWnd::MDIMaximize](../Topic/CMDIChildWnd::MDIMaximize.md)|この MDI 子ウィンドウを最大化します。|  
|[CMDIChildWnd::MDIRestore](../Topic/CMDIChildWnd::MDIRestore.md)|最大化または最小化されたサイズからこの MDI 子ウィンドウを復元します。|  
|[CMDIChildWnd::SetHandle](../Topic/CMDIChildWnd::SetHandles.md)|メニュー、アクセラレータのリソースのハンドルを設定します。|  
  
## 解説  
 MDI 子ウィンドウは一般的なフレーム ウィンドウによく似ていますが、MDI 子ウィンドウはデスクトップのではなく、MDI フレーム ウィンドウ内に表示されます。  MDI 子ウィンドウには独自のメニュー バーがありませんが、代わりに MDI フレーム ウィンドウのメニューを共有します。  フレームワークは、自動的に現在アクティブな MDI 子ウィンドウを表すために、MDI フレーム メニューを変更します。  
  
 アプリケーションのための便利な MDI 子ウィンドウを作成するには、`CMDIChildWnd`からクラスを派生します。  アプリケーションに固有のデータを格納する、派生クラスにメンバー変数を追加します。  ウィンドウにメッセージが送られたときに行われる処理を指定するには、派生クラスにメッセージ処理メンバー関数とメッセージ マップを実装します。  
  
 MDI 子ウィンドウを構築する方法の 3 つがあります:  
  
-   直接 **\[作成\]**を使用してそれを構築します。  
  
-   直接 `LoadFrame`を使用してそれを構築します。  
  
-   間接的にドキュメント テンプレートを通じてそのオブジェクトを構築します。  
  
 **\[作成\]** か `LoadFrame`を呼び出す前に、**new** C\+\+ の演算子を使用してヒープのフレーム ウィンドウ オブジェクトを構築する必要があります。  **\[作成\]** を呼び出す前に、[AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) のグローバル関数のクラスをフレーム ウィンドウのアイコンおよびクラスのスタイルを設定するには、登録できます。  
  
 イミディエイト引数としてフレームの作成のパラメーターを渡すために **\[作成\]** のメンバー関数を使用します。  
  
 `LoadFrame` は **\[作成\]**ほどの引数を必要とし、フレームのキャプション、アイコン、アクセラレータ テーブルとメニューを含むリソースからなく、既定のほとんどを取得します。  `LoadFrame`にアクセスできるため、これらのリソースはすべて同じリソース id \(たとえば、**IDR\_MAINFRAME**\) が必要です。  
  
 `CMDIChildWnd` のオブジェクトがビュー、ドキュメントが含まれる場合、これらはプログラマの代わりに、フレームワークによって直接間接的に作成されます。  `CDocTemplate` のオブジェクトは、フレームの作成、含むビューの作成、適切なドキュメント ビューへの接続を統合します。  `CDocTemplate` のコンストラクターのパラメーターに含める 3 個のクラスの `CRuntimeClass` を指定します \(ドキュメント、ビュー、およびフレーム\)。  ユーザーによって指定されたときに、フレームワークによって `CRuntimeClass` のオブジェクトが動的に新しいフレームの作成に使用されます \(たとえば、ファイルの新しいコマンドまたは MDI ウィンドウの新しいコマンドを使用\)。  
  
 `CMDIChildWnd` から派生したフレーム ウィンドウ クラスは `DECLARE_DYNCREATE` として宣言されて `RUNTIME_CLASS` の上記の機構が正しく動作するにする必要があります。  
  
 `CMDIChildWnd` のクラスは `CFrameWnd`の既定の実装の大部分を継承します。  これらの機能の詳細については、[CFrameWnd](../../mfc/reference/cframewnd-class.md) のクラスの説明を参照してください。  `CMDIChildWnd` のクラスに次の機能があります:  
  
-   `CMultiDocTemplate` のクラスとともに、同じドキュメント テンプレートから `CMDIChildWnd` の複数のオブジェクトは、Windows のシステム リソースを保存する同じメニューを共有します。  
  
-   現在アクティブな MDI 子ウィンドウのメニューは完全に MDI フレーム ウィンドウのメニューを置き換え、現在アクティブな MDI 子ウィンドウのキャプションは、MDI フレーム ウィンドウのキャプションに追加されます。  MDI フレーム ウィンドウと同様に実行される MDI 子ウィンドウの関数のそのほかの例については、`CMDIFrameWnd` のクラスの説明を参照してください。  
  
 フレーム ウィンドウを破棄するときに **\[削除\]** C\+\+ の演算子を使用しないでください。  代わりに、`CWnd::DestroyWindow` を使用してください。  `PostNcDestroy` の `CFrameWnd` の実装では、ウィンドウが破棄されると、C\+\+ のオブジェクトを削除します。  ユーザーがフレーム ウィンドウを閉じると、既定の `OnClose` のハンドラーを呼び出します `DestroyWindow`。  
  
 `CMDIChildWnd`の詳細については、[フレーム ウィンドウ](../../mfc/frame-windows.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIChildWnd`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [MFC MDI サンプル](../../top/visual-cpp-samples.md)   
 [MFC MDIDOCVW サンプル](../../top/visual-cpp-samples.md)   
 [MFC SNAPVW サンプル](../../top/visual-cpp-samples.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [CMDIFrameWnd クラス](../../mfc/reference/cmdiframewnd-class.md)