---
title: "COleDBRecordView クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleDBRecordView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDBRecordView クラス"
  - "MFC, OLE DB"
ms.assetid: 98612427-c4c9-4760-b7e1-85b17448add9
caps.latest.revision: 20
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleDBRecordView クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コントロール内にデータベース レコードを表示するビューです。  
  
## 構文  
  
```  
class COleDBRecordView : public CFormView  
```  
  
## メンバー  
  
### プロテクト コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleDBRecordView::COleDBRecordView](../Topic/COleDBRecordView::COleDBRecordView.md)|`COleDBRecordView` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleDBRecordView::OnGetRowset](../Topic/COleDBRecordView::OnGetRowset.md)|`HRESULT` の標準値を返します。|  
|[COleDBRecordView::OnMove](../Topic/COleDBRecordView::OnMove.md)|書き出されますデータ ソースの現在のレコードを更新し、指定されたレコードに移動します \(次に、前、1 番目、または最後\)。|  
  
## 解説  
 ビューは直接 `CRowset` のオブジェクトに接続されているフォーム ビューです。  ビューでは、ダイアログ テンプレート リソースから作成され、ダイアログ テンプレートのコントロールの `CRowset` のオブジェクトのフィールドが表示されます。  `COleDBRecordView` のオブジェクトは、ダイアログ データ エクスチェンジ \(DDX\)、およびフォーム コントロールと行セットのフィールド間のデータの移動を自動化するに `CRowset`にビルド ナビゲーション機能を使用します。  `COleDBRecordView` は、ビューに現在表示されているレコードを更新するには、次の 1 番目の前に移動するための既定の実装をまたは最後のレコードとインターフェイスも用意されています。  
  
 **COleDbRecordView** で DDX 関数を使用して、データベース レコードセットから直接データを取得し、ダイアログ コントロールに表示できます。  **COleDbRecordView** では、**DDX\_Field\*** 関数 \(`DDX_FieldText` など\) ではなく、**DDX\_\*** メソッド \(`DDX_Text` など\) を使用する必要があります。  `DDX_FieldText` は **COleDbRecordView** を `DDX_FieldText` が型 **CRecordset\***`CRecordView` \(の場合\) または **CDaoRecordset\*** の追加の引数を受け取るため、使用しない。`CDaoRecordView`の場合\)。  
  
> [!NOTE]
>  \(DAO\) ではなく、並べ替える Data Access Objects を使用して OLE DB コンシューマー テンプレート クラスは、クラス [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) を代わりに使用します。  詳細については、" " [:概要 データベース プログラミング](../../data/data-access-programming-mfc-atl.md)を参照してください。  
  
 `COleDBRecordView` はレコード ビューがユーザー インターフェイスを更新できるように行セットのユーザーの位置を追跡します。  ユーザーが行セットのいずれかの最後に実行されると、レコード ビューは、さらに同じ方向の移動の…ユーザー インターフェイス オブジェクトを—メニュー項目やツール バー ボタンなどの無効にします。  
  
 行セット クラスの詳細については、[OLE DB コンシューマー テンプレートを使用する](../../data/oledb/ole-db-consumer-templates-cpp.md) の" "を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CView](../Topic/CView%20Class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `COleDBRecordView`  
  
## 必要条件  
 **Header:** afxoledb.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)