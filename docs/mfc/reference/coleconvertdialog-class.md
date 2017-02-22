---
title: "COleConvertDialog クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleConvertDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleConvertDialog クラス"
  - "[変換] ダイアログ ボックス"
  - "ダイアログ ボックス, OLE"
  - "OLE の [変換] ダイアログ ボックス"
  - "OLE ダイアログ ボックス, 変換"
ms.assetid: a7c57714-31e8-4b78-834d-8ddd1b856a1c
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# COleConvertDialog クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) の構造体を参照してください。  
  
## 構文  
  
```  
class COleConvertDialog : public COleDialog  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleConvertDialog::COleConvertDialog](../Topic/COleConvertDialog::COleConvertDialog.md)|`COleConvertDialog` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleConvertDialog::DoConvert](../Topic/COleConvertDialog::DoConvert.md)|ダイアログ ボックスに指定した変換を実行します。|  
|[COleConvertDialog::DoModal](../Topic/COleConvertDialog::DoModal.md)|OLE アイテムの変更\]ダイアログ ボックスを表示します。|  
|[COleConvertDialog::GetClassID](../Topic/COleConvertDialog::GetClassID.md)|**CLSID** を選択した項目に関連付けられているを取得します。|  
|[COleConvertDialog::GetDrawAspect](../Topic/COleConvertDialog::GetDrawAspect.md)|アイコンとして項目を描画するかどうかを指定します。|  
|[COleConvertDialog::GetIconicMetafile](../Topic/COleConvertDialog::GetIconicMetafile.md)|この項目の画像的なフォームに関連付けられたメタファイルのハンドルを取得します。|  
|[COleConvertDialog::GetSelectionType](../Topic/COleConvertDialog::GetSelectionType.md)|選択の種類を選択するを取得します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[COleConvertDialog::m\_cv](../Topic/COleConvertDialog::m_cv.md)|ダイアログ ボックスの動作を制御する構造体。|  
  
## 解説  
  
> [!NOTE]
>  アプリケーション ウィザードによって生成されたコンテナー コードは、このクラスを使用します。  
  
 OLE 固有のダイアログ ボックスの詳細については、" " [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../Topic/CCommonDialog%20Class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleConvertDialog`  
  
## 必要条件  
 **Header:** afxodlgs.h  
  
## 参照  
 [COleDialog クラス](../../mfc/reference/coledialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDialog クラス](../../mfc/reference/coledialog-class.md)