---
title: "CDaoRecordView クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDaoRecordView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アプリケーション ウィザード [C++], 作成 (レコード ビューを)"
  - "バインド コントロール [C++], 表示 (データベースのデータを)"
  - "CDaoRecordView クラス"
  - "コントロール [MFC], data binding"
  - "データ バインディング [C++], DAO のビュー"
  - "データ バインド コントロール [C++], DAO コントロール"
ms.assetid: 5aa7d0e2-bd05-413e-b216-80c404ce18ac
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDaoRecordView クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コントロール内にデータベース レコードを表示するビューです。  
  
## 構文  
  
```  
  
class AFX_NOVTABLE CDaoRecordView : public CFormView  
  
```  
  
## メンバー  
  
### プロテクト コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CDaoRecordView::CDaoRecordView](../Topic/CDaoRecordView::CDaoRecordView.md)|`CDaoRecordView` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDaoRecordView::IsOnFirstRecord](../Topic/CDaoRecordView::IsOnFirstRecord.md)|現在のレコードが関連付けられたレコードセットの最初のレコードの場合はを返します。|  
|[CDaoRecordView::IsOnLastRecord](../Topic/CDaoRecordView::IsOnLastRecord.md)|現在のレコードが関連付けられたレコードセットの最後のレコードの場合はを返します。|  
|[CDaoRecordView::OnGetRecordset](../Topic/CDaoRecordView::OnGetRecordset.md)|`CDaoRecordset`から派生したクラスのオブジェクトへのポインターを返します。  ClassWizard には、この関数をオーバーライドし、必要に応じてレコードセットを作成します。|  
|[CDaoRecordView::OnMove](../Topic/CDaoRecordView::OnMove.md)|現在のレコードが変更されている場合、データ ソースのスキーマを更新し、指定されたレコードに移動します \(次に、前、1 番目、または最後\)。|  
  
## 解説  
 ビューは直接 `CDaoRecordset` のオブジェクトに接続されているフォーム ビューです。  ビューでは、ダイアログ テンプレート リソースから作成され、ダイアログ テンプレートのコントロールの `CDaoRecordset` のオブジェクトのフィールドが表示されます。  `CDaoRecordView` のオブジェクトは、ダイアログ データ エクスチェンジ \(DDX\) とフォームのコントロールとレコードセットのフィールド間のデータの移動を自動化する DAO レコード フィールド エクスチェンジ \(DFX\)。  `CDaoRecordView` は、ビューに現在表示されているレコードを更新するには、次の 1 番目の前に移動するための既定の実装をまたは最後のレコードとインターフェイスも用意されています。  
  
> [!NOTE]
>  DAO データベース クラスは、ODBC \(Open Database Connectivity\) に基づく MFC データベース クラスとは異なります。  すべての DAO データベース クラス名に「CDao」が付きます。  まだ DAO クラスと ODBC データ ソースにアクセスできます; DAO クラスは、一般に Microsoft Jet データベース エンジンを使用するため、優れた機能を提供します。  
  
 、レコード ビューを作成する最も一般的な方法は、アプリケーション ウィザードを使ってあります。  アプリケーション ウィザードでは、のスケルトン初期アプリケーションの一部として両方のレコード ビュー クラスおよび関連付けられたレコードセット クラスを作成します。  
  
 一つのフォームを簡単に必要な場合は、アプリケーション ウィザードの方法が簡単です。  ClassWizard は、開発プロセスでレコード ビューを後で使用できるようにすることができます。  アプリケーション ウィザードを使ってレコード ビュー クラスを作成すると、ClassWizard の後でそのファイルを作成できます。  ClassWizard を使用して、レコードセット クラスを参照するより詳細に制御できるため、レコード ビュー、およびレコードセットを別に作成し、それらを接続する最も柔軟な方法です。H\/.CPP ファイル。  この方法では、同じレコードセット クラスの複数のレコード ビューを持つことができます。  
  
 エンド ユーザーがレコードからレコード ビューのレコードに移動するには、アプリケーション ウィザードが 1 番目に移動するか、を、前または最後のレコードのメニュー \(およびオプションでツール バーします\) リソースを簡単にするために、作成する。  ClassWizard のレコード ビュー クラスを作成すると、メニューに基づいて、ビットマップ エディターこれらのリソースを作成する必要があります。  
  
 レコードのレコードに移動するための既定の実装については、`IsOnFirstRecord` と `IsOnLastRecord` と `CRecordView` と `CDaoRecordView`両方に適用される [レコード ビューの使用](../../data/using-a-record-view-mfc-data-access.md)" "を参照してください。  
  
 `CDaoRecordView` はレコード ビューがユーザー インターフェイスを更新できるように、レコードセットのユーザーの位置を追跡します。  ユーザーがレコードセットのいずれかの最後に実行されると、レコード ビューは、さらに同じ方向の移動の…ユーザー インターフェイス オブジェクトを—メニュー項目やツール バー ボタンなどの無効にします。  
  
 使ってレコード ビュー、およびレコードセット クラスを宣言して使用する方法の詳細については、「" [ビューを記録します。](../../data/record-views-mfc-data-access.md)のレコード ビュー」をデザインする方法と作成\) "を参照してください。  レコード ビューが、これらを使用する方法についての詳細に機能するか [レコード ビューの使用](../../data/using-a-record-view-mfc-data-access.md)" "を参照してください。  上記のすべての項目を `CRecordView` と `CDaoRecordView`両方に適用されます。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CView](../Topic/CView%20Class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `CDaoRecordView`  
  
## 必要条件  
 **Header:** afxdao.h  
  
## 参照  
 [CFormView クラス](../../mfc/reference/cformview-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset クラス](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef クラス](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef クラス](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoWorkspace クラス](../../mfc/reference/cdaoworkspace-class.md)   
 [CFormView クラス](../../mfc/reference/cformview-class.md)