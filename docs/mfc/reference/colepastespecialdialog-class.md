---
title: "COlePasteSpecialDialog クラス | Microsoft Docs"
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
  - "COlePasteSpecialDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COlePasteSpecialDialog クラス"
  - "ダイアログ ボックス, [形式を選択して貼り付け]"
  - "OLE の [形式を選択して貼り付け] ダイアログ ボックス"
  - "[形式を選択して貼り付け] ダイアログ ボックス"
ms.assetid: 0e82ef9a-9bbe-457e-8240-42c86a0534f7
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COlePasteSpecialDialog クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE の \[形式を選択して貼り付け\] ダイアログ ボックス用に使用されます。  
  
## 構文  
  
```  
  
class COlePasteSpecialDialog : public COleDialog  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COlePasteSpecialDialog::COlePasteSpecialDialog](../Topic/COlePasteSpecialDialog::COlePasteSpecialDialog.md)|`COlePasteSpecialDialog` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COlePasteSpecialDialog::AddFormat](../Topic/COlePasteSpecialDialog::AddFormat.md)|アプリケーションに貼り付けることができる形式の一覧にカスタム書式を適用します。|  
|[COlePasteSpecialDialog::AddLinkEntry](../Topic/COlePasteSpecialDialog::AddLinkEntry.md)|サポートされているクリップボード形式のリストに新しいエントリを追加します。|  
|[COlePasteSpecialDialog::AddStandardFormats](../Topic/COlePasteSpecialDialog::AddStandardFormats.md)|**CF\_BITMAP**、**CF\_DIB**、`CF_METAFILEPICT`を追加し、必要に応じてアプリケーションに貼り付けることができる形式のリストへの `CF_LINKSOURCE`。|  
|[COlePasteSpecialDialog::CreateItem](../Topic/COlePasteSpecialDialog::CreateItem.md)|指定の形式を使用してコンテナー ドキュメントの項目を作成します。|  
|[COlePasteSpecialDialog::DoModal](../Topic/COlePasteSpecialDialog::DoModal.md)|OLE 貼り付け、特別なダイアログ ボックスが表示されます。|  
|[COlePasteSpecialDialog::GetDrawAspect](../Topic/COlePasteSpecialDialog::GetDrawAspect.md)|項目をアイコンとして描画するかどうかを示します。|  
|[COlePasteSpecialDialog::GetIconicMetafile](../Topic/COlePasteSpecialDialog::GetIconicMetafile.md)|この項目の画像的なフォームに関連付けられたメタファイルのハンドルを取得します。|  
|[COlePasteSpecialDialog::GetPasteIndex](../Topic/COlePasteSpecialDialog::GetPasteIndex.md)|ユーザーによって選択された貼り付け使用できるオプションのインデックスを取得します。|  
|[COlePasteSpecialDialog::GetSelectionType](../Topic/COlePasteSpecialDialog::GetSelectionType.md)|選択の種類を選択するを取得します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[COlePasteSpecialDialog::m\_ps](../Topic/COlePasteSpecialDialog::m_ps.md)|ダイアログ ボックスの関数を制御する型の構造 **OLEUIPASTESPECIAL**。|  
  
## 解説  
 このダイアログ ボックスを使用すると `COlePasteSpecialDialog` クラスのオブジェクトを作成します。  `COlePasteSpecialDialog` オブジェクトの構築後、関数ダイアログ ボックスにクリップボード形式を追加するに [AddFormat](../Topic/COlePasteSpecialDialog::AddFormat.md) と [AddStandardFormats](../Topic/COlePasteSpecialDialog::AddStandardFormats.md) のメンバーを使用できます。  ダイアログ ボックスのコントロールの値や状態を初期化するために [m\_ps](../Topic/COlePasteSpecialDialog::m_ps.md) の構造を使用できます。  `m_ps` の構造は、型 **OLEUIPASTESPECIAL**です。  
  
 詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [OLEUIPASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/ms692434) の構造体を参照してください。  
  
 OLE 固有のダイアログ ボックスに関する詳細については、" " [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../Topic/CCommonDialog%20Class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COlePasteSpecialDialog`  
  
## 必要条件  
 **Header:** afxodlgs.h  
  
## 参照  
 [MFC の OCLIENT サンプル](../../top/visual-cpp-samples.md)   
 [COleDialog クラス](../../mfc/reference/coledialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDialog クラス](../../mfc/reference/coledialog-class.md)