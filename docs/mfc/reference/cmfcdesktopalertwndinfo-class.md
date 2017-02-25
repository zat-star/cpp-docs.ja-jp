---
title: "CMFCDesktopAlertWndInfo クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCDesktopAlertWndInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDesktopAlertWndInfo クラス"
ms.assetid: 5c9bb84e-6c96-4748-8e74-6951b6ae8e84
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CMFCDesktopAlertWndInfo クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCDesktopAlertWndInfo` クラスは、[CMFCDesktopAlertWnd クラス](../../mfc/reference/cmfcdesktopalertwnd-class.md)と共に使用されます。  デスクトップ通知ウィンドウがポップアップする場合に表示されるコントロールを指定します。  
  
## 構文  
  
```  
class CMFCDesktopAlertWndInfo  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|`CMFCDesktopAlertWndInfo::~CMFCDesktopAlertWndInfo`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCDesktopAlertWndInfo::operator\=](../Topic/CMFCDesktopAlertWndInfo::operator=.md)||  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CMFCDesktopAlertWndInfo::m\_hIcon](../Topic/CMFCDesktopAlertWndInfo::m_hIcon.md)|表示されるアイコンへのハンドル。|  
|[CMFCDesktopAlertWndInfo::m\_nURLCmdID](../Topic/CMFCDesktopAlertWndInfo::m_nURLCmdID.md)|デスクトップ通知ウィンドウのリンクに関連付けられたコマンド ID。|  
|[CMFCDesktopAlertWndInfo::m\_strText](../Topic/CMFCDesktopAlertWndInfo::m_strText.md)|デスクトップ通知ウィンドウに表示されるテキスト。|  
|[CMFCDesktopAlertWndInfo::m\_strURL](../Topic/CMFCDesktopAlertWndInfo::m_strURL.md)|デスクトップ通知ウィンドウに表示されるリンク。|  
  
## 解説  
 `CMFCDesktopAlertWndInfo` クラスは [CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md) メソッドに渡され、デスクトップ通知ウィンドウの既定のダイアログ ボックスに表示される要素を指定します。  既定のダイアログ ボックスには次の 3 つの項目を含めることができます。  
  
-   アイコン。[CMFCDesktopAlertWndInfo::m\_hIcon](../Topic/CMFCDesktopAlertWndInfo::m_hIcon.md) を呼び出すことで設定されます。  
  
-   ラベル、またはテキスト メッセージ。 [CMFCDesktopAlertWndInfo::m\_strText](../Topic/CMFCDesktopAlertWndInfo::m_strText.md) を呼び出すことで設定されます。  
  
-   リンク。[CMFCDesktopAlertWndInfo::m\_strURL](../Topic/CMFCDesktopAlertWndInfo::m_strURL.md) を呼び出すことで設定されます。  リンクがクリックされたとき実行されるコマンドを設定するには、[CMFCDesktopAlertWndInfo::m\_nURLCmdID](../Topic/CMFCDesktopAlertWndInfo::m_nURLCmdID.md) を呼び出します。  
  
 既定のダイアログ ボックスでは不十分な場合は、このクラスを使用する代わりに、カスタム ダイアログ ボックスを作成して [CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md) メソッドに渡します。  詳細については、「[CMFCDesktopAlertDialog クラス](../../mfc/reference/cmfcdesktopalertdialog-class.md)」を参照してください。  
  
## 使用例  
 次の例は、`CMFCDesktopAlertWndInfo` クラスのさまざまなメンバーの使用方法を説明しています。  この例は、表示されるアイコンへのハンドルの設定方法、デスクトップ通知ウィンドウに表示されるテキスト、デスクトップ通知ウィンドウに表示されるリンク、およびデスクトップ通知ウィンドウのリンクと関連するコマンド ID を示します。  この例では [デスクトップ通知デモのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#3](../../mfc/reference/codesnippet/CPP/cmfcdesktopalertwndinfo-class_1.cpp)]  
  
## 継承階層  
 [CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)  
  
## 必要条件  
 **ヘッダー :** afxDesktopAlertDialog.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCDesktopAlertWnd クラス](../../mfc/reference/cmfcdesktopalertwnd-class.md)   
 [CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md)   
 [CMFCDesktopAlertDialog クラス](../../mfc/reference/cmfcdesktopalertdialog-class.md)