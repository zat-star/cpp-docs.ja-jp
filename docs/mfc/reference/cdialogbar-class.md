---
title: "CDialogBar クラス | Microsoft Docs"
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
  - "CDialogBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDialogBar クラス"
  - "ダイアログ バー, Windows モードレス ダイアログ ボックス"
  - "ダイアログ ボックス, モードレス"
ms.assetid: da2f7a30-970c-44e3-87f0-6094bd002cab
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDialogBar クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コントロール バー内の Windows のモードレス ダイアログ ボックスの機能を提供します。  
  
## 構文  
  
```  
class CDialogBar : public CControlBar  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CDialogBar::CDialogBar](../Topic/CDialogBar::CDialogBar.md)|`CDialogBar` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDialogBar::Create](../Topic/CDialogBar::Create.md)|Windows のダイアログ バーを作成し、`CDialogBar` のオブジェクトにアタッチします。|  
  
## 解説  
 ダイアログ バーは、ユーザーがレコード間、Windows の標準コントロールを含む、ダイアログ ボックスに似ています。  別の部分がダイアログ バーを表すためにダイアログ テンプレートを作成します。  
  
 ダイアログ バーを作成して使用することは `CFormView` のオブジェクトを作成し、使用することに似ています。  最初に、スタイル、およびそのほかの **WS\_CHILD** のダイアログ テンプレートを定義するために [dialog editor](../../mfc/dialog-editor.md) スタイルを使用しないでください。  テンプレートは、スタイル **WS\_VISIBLE**はありません。  アプリケーション コードでは、`CDialogBar` のオブジェクトを構築するコンストラクターを呼び出して、ダイアログ バー ペインを作成し、`CDialogBar` のオブジェクトにアタッチするに **\[作成\]** を呼び出します。  
  
 `CDialogBar`の詳細については、" " [ダイアログ バー](../../mfc/dialog-bars.md) と [テクニカル ノート 31](../../mfc/tn031-control-bars.md)、コントロール バーを参照してください。  
  
> [!NOTE]
>  現在のリリースでは、`CDialogBar` のオブジェクトはホスト ウィンドウの書式制御できません。  Visual C\+\+ の Windows フォーム コントロールの詳細については、[MFC での Windows フォーム ユーザー コントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CDialogBar`  
  
## 必要条件  
 **Header:** afxext.h  
  
## 参照  
 [MFC CTRLBARS サンプル](../../top/visual-cpp-samples.md)   
 [CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFormView クラス](../../mfc/reference/cformview-class.md)   
 [CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)