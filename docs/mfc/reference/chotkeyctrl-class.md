---
title: "CHotKeyCtrl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CHotKeyCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHotKeyCtrl クラス"
  - "ホット キー コントロール"
  - "Windows コモン コントロール [C++], CHotKeyCtrl"
ms.assetid: 896f9766-0718-4f58-aab2-20325e118ca6
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CHotKeyCtrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows コモン ホット キー コントロールの機能が用意されています。  
  
## 構文  
  
```  
class CHotKeyCtrl : public CWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CHotKeyCtrl::CHotKeyCtrl](../Topic/CHotKeyCtrl::CHotKeyCtrl.md)|`CHotKeyCtrl` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CHotKeyCtrl::Create](../Topic/CHotKeyCtrl::Create.md)|ホット キーのコントロールを作成し、`CHotKeyCtrl` のオブジェクトにアタッチします。|  
|[CHotKeyCtrl::CreateEx](../Topic/CHotKeyCtrl::CreateEx.md)|指定されたウィンドウの拡張スタイルのホット キーのコントロールを作成し、`CHotKeyCtrl` のオブジェクトにアタッチします。|  
|[CHotKeyCtrl::GetHotKey](../Topic/CHotKeyCtrl::GetHotKey.md)|ホット キーのコントロールからホット キーの仮想キー コードと修飾子のフラグを取得します。|  
|[CHotKeyCtrl::GetHotKeyName](../Topic/CHotKeyCtrl::GetHotKeyName.md)|キー名を、ホット キーに割り当てられているローカルの文字セットで取得します。|  
|[CHotKeyCtrl::GetKeyName](../Topic/CHotKeyCtrl::GetKeyName.md)|キー名を、指定された仮想キー コードに割り当てられているローカルの文字セットで取得します。|  
|[CHotKeyCtrl::SetHotKey](../Topic/CHotKeyCtrl::SetHotKey.md)|ホット キーのコントロールのホット キーを設定します。|  
|[CHotKeyCtrl::SetRules](../Topic/CHotKeyCtrl::SetRules.md)|ホット キーのコントロールに対して無効な組み合わせと、既定の修飾子の組み合わせを定義します。|  
  
## 解説  
 ホット キー「コントロール」はホット キーを作成できるようにするウィンドウです。  「ホット キーは」アクションをすぐに実行するためにユーザーがクリックできるキーの組み合わせです。  \(たとえば、ユーザーがホット キーを特定のウィンドウをアクティブにし、順番の z 軸上に取り込む作成できます\)。ホット キーのコントロールは、ユーザーのオプションを表示し、ユーザーが有効なキーの組み合わせを選択していることを確認します。  
  
 このコントロール \(したがって `CHotKeyCtrl` のクラス\) \/98 Windows 95 および Windows NT 3.51 以降で実行されるプログラムにのみ使用できます。  
  
 ユーザーがキーの組み合わせを選択した場合、アプリケーションはコントロールから指定されたキーの組み合わせを取得し、システムのホット キーを設定するに **WM\_SETHOTKEY** のメッセージを使用できます。  ユーザーが押したときに **SC\_HOTKEY**を指定する **WM\_SETHOTKEY** のメッセージに示されているシステムのパートから、そのホット キーは、ウィンドウ `WM_SYSCOMMAND` のメッセージを受信します。  このメッセージは、を受け取るウィンドウをアクティブにします。  ホット キーは **WM\_SETHOTKEY** の終了を呼び出し元のアプリケーションまで有効です。  
  
 この機構は **WM\_HOTKEY** のメッセージおよび Windows [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309) と [UnregisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646327) の関数に依存するホット キーのサポートとは異なります。  
  
 `CHotKeyCtrl`の使用の詳細については、[コントロール](../../mfc/controls-mfc.md) と [を使用して CHotKeyCtrl](../../mfc/using-chotkeyctrl.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CHotKeyCtrl`  
  
## 必要条件  
 **ヘッダー :** afxcmn.h  
  
## 参照  
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)