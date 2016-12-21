---
title: "CLinkCtrl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CLinkCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLinkCtrl クラス"
  - "コントロール [MFC], リンク"
  - "リンク [C++], リンク コントロール"
  - "SysLink コントロール"
  - "Web ページ, リンク コントロール"
ms.assetid: d1cd876a-ecca-42db-8ac4-9cd327df0cd4
caps.latest.revision: 23
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CLinkCtrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows コモン SysLink コントロールの機能が用意されています。  
  
## 構文  
  
```  
class CLinkCtrl : public CWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CLinkCtrl::CLinkCtrl](../Topic/CLinkCtrl::CLinkCtrl.md)|`CLinkCtrl` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CLinkCtrl::Create](../Topic/CLinkCtrl::Create.md)|リンク コントロールを作成し、`CLinkCtrl` のオブジェクトにアタッチします。|  
|[CLinkCtrl::CreateEx](../Topic/CLinkCtrl::CreateEx.md)|拡張スタイルのリンク コントロールを作成し、`CLinkCtrl` のオブジェクトにアタッチします。|  
|[CLinkCtrl::GetIdealHeight](../Topic/CLinkCtrl::GetIdealHeight.md)|リンク コントロールの最適な高さを取得します。|  
|[CLinkCtrl::GetIdealSize](../Topic/CLinkCtrl::GetIdealSize.md)|リンクの幅指定して、現在のリンク コントロールのリンク テキストの指定した高さを計算します。|  
|[CLinkCtrl::GetItem](../Topic/CLinkCtrl::GetItem.md)|リンク コントロールの項目のステータスと属性を取得します。|  
|[CLinkCtrl::GetItemID](../Topic/CLinkCtrl::GetItemID.md)|リンク コントロールの項目の ID を取得します。|  
|[CLinkCtrl::GetItemState](../Topic/CLinkCtrl::GetItemState.md)|リンク コントロール項目の状態を取得します。|  
|[CLinkCtrl::GetItemUrl](../Topic/CLinkCtrl::GetItemUrl.md)|リンク コントロールの項目によって表される URL を取得します。|  
|[CLinkCtrl::HitTest](../Topic/CLinkCtrl::HitTest.md)|ユーザーが指定したリンクをクリックしたかどうかを判断します。|  
|[CLinkCtrl::SetItem](../Topic/CLinkCtrl::SetItem.md)|リンク コントロールの項目のステータスと属性を設定します。|  
|[CLinkCtrl::SetItemID](../Topic/CLinkCtrl::SetItemID.md)|リンク コントロールの項目の ID を設定します。|  
|[CLinkCtrl::SetItemState](../Topic/CLinkCtrl::SetItemState.md)|リンク コントロール項目の状態を設定します。|  
|[CLinkCtrl::SetItemUrl](../Topic/CLinkCtrl::SetItemUrl.md)|URL をリンク コントロールの項目によって表される設定します。|  
  
## 解説  
 「リンク コントロール」はウィンドウのハイパーテキスト リンクを埋め込むための便利な方法を提供します。  実際のコントロールは、ユーザーが埋め込まれたリンクをクリックすると表示のマークされたテキストが適切なアプリケーションを起動するウィンドウです。  いくつかのリンクが 1 のコントロールでサポートされており、から始まるインデックスでアクセスできます。  
  
 このコントロール \(したがって `CLinkCtrl` のクラス\) Windows XP では、以降で実行されるプログラムにのみ使用できます。  
  
 詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [SysLink コントロール](http://msdn.microsoft.com/library/windows/desktop/bb760706) を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CLinkCtrl`  
  
## 必要条件  
 **ヘッダー:** afxcmn.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../Topic/CWnd%20Class.md)