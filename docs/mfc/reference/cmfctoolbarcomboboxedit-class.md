---
title: "CMFCToolBarComboBoxEdit クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCComboEdit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarComboBoxEdit クラス"
  - "CMFCToolBarComboBoxEdit::PreTranslateMessage メソッド"
ms.assetid: 4789c34a-ce58-48ba-a26f-38748b601352
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CMFCToolBarComboBoxEdit クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCToolBarComboBoxEdit` クラスを使用して、フレームワークは編集可能なコンボ ボックス コントロールとして動作するツール バーのボタンを作成します。  
  
## 構文  
  
```  
class CMFCToolBarComboBoxEdit : public CEdit  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCToolBarComboBoxEdit::CMFCToolBarComboBoxEdit](../Topic/CMFCToolBarComboBoxEdit::CMFCToolBarComboBoxEdit.md)|`CMFCToolBarComboBoxEdit` オブジェクトを構築します。|  
|`CMFCToolBarComboBoxEdit::~CMFCToolBarComboBoxEdit`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|`CMFCToolBarComboBoxEdit::PreTranslateMessage`|Windows 関数の [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) や [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) にディスパッチする前にウィンドウ メッセージを変換します。  \([CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md) をオーバーライドします\)。|  
  
### 解説  
 `CMFCToolBarComboBoxEdit` クラスからクラスを派生させて、その編集操作をカスタマイズします。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CEdit](../Topic/CEdit%20Class.md)  
  
 [CMFCToolBarComboBoxEdit](../../mfc/reference/cmfctoolbarcomboboxedit-class.md)  
  
## 必要条件  
 **ヘッダー :** afxtoolbarcomboboxbutton.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCToolBarComboBoxButton クラス](../Topic/CMFCToolBarComboBoxButton%20Class.md)   
 [CMFCToolBarComboBoxButton::CreateEdit](../Topic/CMFCToolBarComboBoxButton::CreateEdit.md)