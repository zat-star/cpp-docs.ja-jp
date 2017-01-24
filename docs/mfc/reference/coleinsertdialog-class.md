---
title: "COleInsertDialog クラス | Microsoft Docs"
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
  - "COleInsertDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleInsertDialog クラス"
  - "ダイアログ ボックス, OLE"
  - "[オブジェクトの挿入] ダイアログ ボックス"
  - "OLE の [オブジェクトの挿入] ダイアログ ボックス"
ms.assetid: a9ec610b-abde-431e-bd01-c40159a66dbb
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleInsertDialog クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE の \[オブジェクトの挿入\] ダイアログ ボックスで使用されます。  
  
## 構文  
  
```  
class COleInsertDialog : public COleDialog  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleInsertDialog::COleInsertDialog](../Topic/COleInsertDialog::COleInsertDialog.md)|`COleInsertDialog` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleInsertDialog::CreateItem](../Topic/COleInsertDialog::CreateItem.md)|ダイアログ ボックスで選択した項目を作成します。|  
|[COleInsertDialog::DoModal](../Topic/COleInsertDialog::DoModal.md)|OLE の\[オブジェクトの挿入\]ダイアログ ボックスを表示します。|  
|[COleInsertDialog::GetClassID](../Topic/COleInsertDialog::GetClassID.md)|**CLSID** を選択した項目に関連付けられているを取得します。|  
|[COleInsertDialog::GetDrawAspect](../Topic/COleInsertDialog::GetDrawAspect.md)|アイコンとして項目を描画するかどうかを示します。|  
|[COleInsertDialog::GetIconicMetafile](../Topic/COleInsertDialog::GetIconicMetafile.md)|この項目の画像的なフォームに関連付けられたメタファイルのハンドルを取得します。|  
|[COleInsertDialog::GetPathName](../Topic/COleInsertDialog::GetPathName.md)|ダイアログ ボックスで選択したファイルの完全パスを取得します。|  
|[COleInsertDialog::GetSelectionType](../Topic/COleInsertDialog::GetSelectionType.md)|オブジェクトの種類を選択するを取得します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[COleInsertDialog::m\_io](../Topic/COleInsertDialog::m_io.md)|ダイアログ ボックスの動作を制御する型の構造 **OLEUIINSERTOBJECT**。|  
  
## 解説  
 このダイアログ ボックスを使用すると `COleInsertDialog` クラスのオブジェクトを作成します。  `COleInsertDialog` オブジェクトの構築後、ダイアログ ボックスのコントロールの値や状態を初期化するために [m\_io](../Topic/COleInsertDialog::m_io.md) の構造を使用できます。  `m_io` の構造は、型 **OLEUIINSERTOBJECT**です。  このダイアログ クラスの使用方法の詳細については、[DoModal](../Topic/COleInsertDialog::DoModal.md) のメンバー関数に関するトピックを参照してください。  
  
> [!NOTE]
>  アプリケーション ウィザードによって生成されたコンテナー コードは、このクラスを使用します。  
  
 詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [OLEUIINSERTOBJECT](http://msdn.microsoft.com/library/windows/desktop/ms691316) の構造体を参照してください。  
  
 OLE 固有のダイアログ ボックスに関する詳細については、" " [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../Topic/CCommonDialog%20Class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleInsertDialog`  
  
## 必要条件  
 **Header:** afxodlgs.h  
  
## 参照  
 [MFC の OCLIENT サンプル](../../top/visual-cpp-samples.md)   
 [COleDialog クラス](../../mfc/reference/coledialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDialog クラス](../../mfc/reference/coledialog-class.md)