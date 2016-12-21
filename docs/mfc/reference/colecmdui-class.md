---
title: "COleCmdUI クラス | Microsoft Docs"
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
  - "COleCmdUI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX ドキュメント [C++], ドキュメント サーバー"
  - "COleCmdUI クラス"
  - "docobject サーバー"
  - "ドキュメント オブジェクト サーバー"
  - "サーバー [C++], ActiveX ドキュメント"
  - "サーバー [C++], doc オブジェクト"
ms.assetid: a2d5ce08-6657-45d3-8673-2a9f32d50eec
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleCmdUI クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アプリケーションの `IOleCommandTarget` ドリブンの機能に関連するユーザー インターフェイス オブジェクトの状態を更新するメソッドを MFC に提供します。  
  
## 構文  
  
```  
class COleCmdUI : public CCmdUI  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleCmdUI::COleCmdUI](../Topic/COleCmdUI::COleCmdUI.md)|`COleCmdUI` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleCmdUI::Enable](../Topic/COleCmdUI::Enable.md)|設定またはクリアします。有効にするコマンドのフラグ。|  
|[COleCmdUI::SetCheck](../Topic/COleCmdUI::SetCheck.md)|オンとオフを切り替えるコマンドのステータスを設定します。|  
|[COleCmdUI::SetText](../Topic/COleCmdUI::SetText.md)|コマンドのテキストの名前または状態の文字列を返します。|  
  
## 解説  
 DocObjects が有効になっていないアプリケーションでは、ユーザーがアプリケーション、MFC メニュー **UPDATE\_COMMAND\_UI** の notifcations を処理する場合。  各通知は、特定のコマンドの状態を反映するために処理できる [CCmdUI](../Topic/CCmdUI%20Class.md) のオブジェクトが与えられます。  ただし、DocObjects のアプリケーションを有効にすると、MFC のプロセスの **UPDATE\_OLE\_COMMAND\_UI** の通知は `COleCmdUI` のオブジェクトを割り当てます。  
  
 `COleCmdUI` は、DocObject がコンテナーのユーザー インターフェイスに FileNew \(、など\) 開き、印刷するコマンドを受け取るように発生し、コンテナーが DocObject のユーザー インターフェイスで作成されたコマンドを受け取ります。  同じコマンドをディスパッチするに `IDispatch` を使用できますが `IOleCommandTarget` は、クエリ単純な方法を提供し、引数なしで標準セットのコマンドに、通常は、型情報依存しないため実行すると、複雑です。  `COleCmdUI` が DocObject のユーザー インターフェイスのコマンドの他のプロパティを有効にし、更新し、設定に使用できます。  コマンドを開始するとき [COleServerDoc::OnExecOleCmd](../Topic/COleServerDoc::OnExecOleCmd.md)を呼び出します。  
  
 DocObjects の詳細については、[CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) と [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md)を参照してください。  また [インターネットの対処方法: Active ドキュメント](../Topic/Active%20Documents%20on%20the%20Internet.md) と [Active ドキュメント](../Topic/Active%20Documents%20on%20the%20Internet.md)を参照してください。  
  
## 継承階層  
 [CCmdUI](../Topic/CCmdUI%20Class.md)  
  
 `COleCmdUI`  
  
## 必要条件  
 **Header:** afxdocobj.h  
  
## 参照  
 [CCmdUI クラス](../Topic/CCmdUI%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)