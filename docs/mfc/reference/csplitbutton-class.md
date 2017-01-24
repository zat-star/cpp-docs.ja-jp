---
title: "CSplitButton クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/09/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSplitButton クラス"
ms.assetid: 6844d0a9-6408-4e44-9b5f-57628ed8bad6
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSplitButton クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CSplitButton` のクラスは、分割ボタン コントロールを表します。  分割ボタン コントロールは、ユーザーがボタンのメイン領域をクリックすると既定の動作を実行し、ユーザーがボタンのドロップダウン矢印をクリックするとドロップダウン メニューを表示します。  
  
## 構文  
  
```  
class CSplitButton : public CButton  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CSplitButton::CSplitButton](../Topic/CSplitButton::CSplitButton.md)|`CSplitButton` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSplitButton::Create](../Topic/CSplitButton::Create.md)|指定されたスタイルの分割ボタン コントロールを作成し、`CSplitButton` の現在のオブジェクトにアタッチします。|  
|[CSplitButton::SetDropDownMenu](../Topic/CSplitButton::SetDropDownMenu.md)|ユーザーが現在の分割ボタン コントロールのドロップダウン矢印をクリックすると表示されるドロップダウン メニューを設定します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSplitButton::OnDropDown](../Topic/CSplitButton::OnDropDown.md)|ユーザーが現在の分割ボタン コントロールのドロップダウン矢印をクリックすると、その `BCN_DROPDOWN` 通知をシステムが送信処理します。|  
  
## 解説  
 `CSplitButton` のクラスは [CButton](../../mfc/reference/cbutton-class.md) のクラスから派生します。  分割ボタン コントロールでは、スタイルを `BS_SPLITBUTTON`のボタン コントロールです。  これは、ユーザーがドロップダウン矢印をクリックしたときにカスタム メニューを表示します。  詳細については、[\[ボタン スタイル\]](http://msdn.microsoft.com/library/windows/desktop/bb775951)の `BS_SPLITBUTTON` と `BS_DEFSPLITBUTTON` のスタイルを参照してください。  
  
 次の図は、ページャー コントロールと \(1\) 分割ボタン コントロールを含むダイアログ ボックスを示しています。  \(2\) は既にドロップダウン矢印をクリックし、\(3\) サブメニューが表示されます。  
  
 ![splitbutton およびページャー コントロールを含むダイアログ。](../../mfc/reference/media/splitbutton_pager.png "SplitButton\_Pager")  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CSplitButton`  
  
## 必要条件  
 **ヘッダー:** afxcmn.h  
  
 このクラスは [!INCLUDE[windowsver](../Token/windowsver_md.md)] 以降でサポートされます。  
  
 このクラスの追加要件は [Windows Vista コモン コントロールの作成要件](../../mfc/build-requirements-for-windows-vista-common-controls.md)で説明します。  
  
## 参照  
 [CSplitButton Class](../../mfc/reference/csplitbutton-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CButton クラス](../../mfc/reference/cbutton-class.md)