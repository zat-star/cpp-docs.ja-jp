---
title: "COleChangeSourceDialog クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleChangeSourceDialog"
  - "OLEUICHANGESOURCE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleChangeSourceDialog クラス"
  - "ダイアログ ボックス, OLE"
  - "OLE の [リンク元の変更] ダイアログ ボックス"
  - "OLE ダイアログ ボックス, 変更 (ソースを)"
  - "OleUIChangeSource 構造体"
ms.assetid: d0e08be7-21ef-45e1-97af-fe27d99e3bac
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# COleChangeSourceDialog クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE の \[ソースの変更\] ダイアログ ボックスに使用します。  
  
## 構文  
  
```  
class COleChangeSourceDialog : public COleDialog  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleChangeSourceDialog::COleChangeSourceDialog](../Topic/COleChangeSourceDialog::COleChangeSourceDialog.md)|`COleChangeSourceDialog` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleChangeSourceDialog::DoModal](../Topic/COleChangeSourceDialog::DoModal.md)|OLE の\[ソースの変更\]ダイアログ ボックスを表示します。|  
|[COleChangeSourceDialog::GetDisplayName](../Topic/COleChangeSourceDialog::GetDisplayName.md)|完全なソース・の表示名を取得します。|  
|[COleChangeSourceDialog::GetFileName](../Topic/COleChangeSourceDialog::GetFileName.md)|ソース名からファイル名を取得します。|  
|[COleChangeSourceDialog::GetFromPrefix](../Topic/COleChangeSourceDialog::GetFromPrefix.md)|前のソースのプレフィックスを取得します。|  
|[COleChangeSourceDialog::GetItemName](../Topic/COleChangeSourceDialog::GetItemName.md)|ソース名から項目の名前を取得します。|  
|[COleChangeSourceDialog::GetToPrefix](../Topic/COleChangeSourceDialog::GetToPrefix.md)|新しいソースのプレフィックスを取得します|  
|[COleChangeSourceDialog::IsValidSource](../Topic/COleChangeSourceDialog::IsValidSource.md)|ソースが有効かどうかを示します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[COleChangeSourceDialog::m\_cs](../Topic/COleChangeSourceDialog::m_cs.md)|ダイアログ ボックスの動作を制御する構造体。|  
  
## 解説  
 このダイアログ ボックスを使用すると `COleChangeSourceDialog` クラスのオブジェクトを作成します。  `COleChangeSourceDialog` オブジェクトの構築後、ダイアログ ボックスのコントロールの値や状態を初期化するために [m\_cs](../Topic/COleChangeSourceDialog::m_cs.md) の構造を使用できます。  `m_cs` の構造は、型 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160)です。  このダイアログ クラスの使用方法の詳細については、[DoModal](../Topic/COleChangeSourceDialog::DoModal.md) のメンバー関数に関するトピックを参照してください。  
  
 詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) の構造体を参照してください。  
  
 OLE 固有のダイアログ ボックスの詳細については、" " [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../Topic/CCommonDialog%20Class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeSourceDialog`  
  
## 必要条件  
 **Header:** afxodlgs.h  
  
## 参照  
 [COleDialog クラス](../../mfc/reference/coledialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDialog クラス](../../mfc/reference/coledialog-class.md)