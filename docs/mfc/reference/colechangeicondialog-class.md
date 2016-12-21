---
title: "COleChangeIconDialog クラス | Microsoft Docs"
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
  - "COleChangeIconDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "[アイコンの変更] ダイアログ ボックス"
  - "COleChangeIconDialog クラス"
  - "ダイアログ ボックス, OLE"
  - "OLE の [アイコンの変更] ダイアログ ボックス"
  - "OLE ダイアログ ボックス, [アイコンの変更]"
ms.assetid: 8d6e131b-ddbb-4dff-a432-f239efda8e3d
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleChangeIconDialog クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE の \[アイコンの変更\] ダイアログ ボックスに使用します。  
  
## 構文  
  
```  
class COleChangeIconDialog : public COleDialog  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleChangeIconDialog::COleChangeIconDialog](../Topic/COleChangeIconDialog::COleChangeIconDialog.md)|`COleChangeIconDialog` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleChangeIconDialog::DoChangeIcon](../Topic/COleChangeIconDialog::DoChangeIcon.md)|ダイアログ ボックスに指定した変更を実行します。|  
|[COleChangeIconDialog::DoModal](../Topic/COleChangeIconDialog::DoModal.md)|OLE 2 の変更のアイコン\]ダイアログ ボックスを表示します。|  
|[COleChangeIconDialog::GetIconicMetafile](../Topic/COleChangeIconDialog::GetIconicMetafile.md)|この項目の画像的なフォームに関連付けられたメタファイルのハンドルを取得します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[COleChangeIconDialog::m\_ci](../Topic/COleChangeIconDialog::m_ci.md)|ダイアログ ボックスの動作を制御する構造体。|  
  
## 解説  
 このダイアログ ボックスを使用すると `COleChangeIconDialog` クラスのオブジェクトを作成します。  `COleChangeIconDialog` オブジェクトの構築後、ダイアログ ボックスのコントロールの値や状態を初期化するために [m\_ci](../Topic/COleChangeIconDialog::m_ci.md) の構造を使用できます。  `m_ci` の構造は、型 **OLEUICHANGEICON**です。  このダイアログ クラスの使用方法の詳細については、[DoModal](../Topic/COleChangeIconDialog::DoModal.md) のメンバー関数に関するトピックを参照してください。  
  
 詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) の構造体を参照してください。  
  
 OLE 固有のダイアログ ボックスの詳細については、" " [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../Topic/CCommonDialog%20Class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeIconDialog`  
  
## 必要条件  
 **Header:** afxodlgs.h  
  
## 参照  
 [COleDialog クラス](../../mfc/reference/coledialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDialog クラス](../../mfc/reference/coledialog-class.md)