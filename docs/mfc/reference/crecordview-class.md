---
title: "CRecordView クラス | Microsoft Docs"
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
  - "CRecordView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRecordView クラス"
  - "ODBC レコードセット, 表示 (レコードを)"
  - "レコード, 表示 (ODBC を)"
  - "ビュー, ODBC"
ms.assetid: 9b4b0897-bd50-4d48-a0b4-f3323f5ccc55
caps.latest.revision: 25
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRecordView クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コントロール内にデータベース レコードを表示するビューです。  
  
## 構文  
  
```  
class AFX_NOVTABLE CRecordView : public CFormView  
```  
  
## メンバー  
  
### プロテクト コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CRecordView::CRecordView](../Topic/CRecordView::CRecordView.md)|`CRecordView` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CRecordView::IsOnFirstRecord](../Topic/CRecordView::IsOnFirstRecord.md)|現在のレコードが関連付けられたレコードセットの最初のレコードの場合はを返します。|  
|[CRecordView::IsOnLastRecord](../Topic/CRecordView::IsOnLastRecord.md)|現在のレコードが関連付けられたレコードセットの最後のレコードの場合はを返します。|  
|[CRecordView::OnGetRecordset](../Topic/CRecordView::OnGetRecordset.md)|`CRecordset`から派生したクラスのオブジェクトへのポインターを返します。  ClassWizard には、この関数をオーバーライドし、必要に応じてレコードセットを作成します。|  
|[CRecordView::OnMove](../Topic/CRecordView::OnMove.md)||  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CRecordView::OnMove](../Topic/CRecordView::OnMove.md)|現在のレコードが変更されている場合、データ ソースのスキーマを更新し、指定されたレコードに移動します \(次に、前、1 番目、または最後\)。|  
  
## 解説  
 ビューは直接 `CRecordset` のオブジェクトに接続されているフォーム ビューです。  ビューでは、ダイアログ テンプレート リソースから作成され、ダイアログ テンプレートのコントロールの `CRecordset` のオブジェクトのフィールドが表示されます。  `CRecordView` のオブジェクトは、ダイアログ データ エクスチェンジ \(DDX\) とフォームのコントロールとレコードセットのフィールド間のデータの移動を自動化するレコード フィールド エクスチェンジ \(RFX\)。  `CRecordView` は、ビューに現在表示されているレコードを更新するには、次の 1 番目の前に移動するための既定の実装をまたは最後のレコードとインターフェイスも用意されています。  
  
> [!NOTE]
>  \(DAO\) ではなく、並べ替える Data Access Objects を使用すると、ODBC \(Open Database Connectivity\) クラスは、クラス [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) を代わりに使用します。  詳細については、" " [:概要 データベース プログラミング](../../data/data-access-programming-mfc-atl.md)を参照してください。  
  
 、レコード ビューを作成する最も一般的な方法は、アプリケーション ウィザードを使ってあります。  Tge のアプリケーション ウィザードでは、のスケルトン初期アプリケーションの一部として両方のレコード ビュー クラスおよび関連付けられたレコードセット クラスを作成します。  アプリケーション ウィザードを使ってレコード ビュー クラスを作成すると、ClassWizard の後でそのファイルを作成できます。  一つのフォームを簡単に必要な場合は、アプリケーション ウィザードの方法が簡単です。  ClassWizard は、開発プロセスでレコード ビューを後で使用できるようにすることができます。  ClassWizard を使用して、レコードセット クラスを参照するより詳細に制御できるため、レコード ビュー、およびレコードセットを別に作成し、それらを接続する最も柔軟な方法です。H\/.CPP ファイル。  この方法では、同じレコードセット クラスの複数のレコード ビューを持つことができます。  
  
 エンド ユーザーがレコードからレコード ビューのレコードに移動するには、アプリケーション ウィザードが 1 番目に移動するか、を、前または最後のレコードのメニュー \(およびオプションでツール バーします\) リソースを簡単にするために、作成する。  ClassWizard のレコード ビュー クラスを作成すると、メニューに基づいて、ビットマップ エディターこれらのリソースを作成する必要があります。  
  
 レコードのレコードに移動するための既定の実装については、`IsOnFirstRecord` と `IsOnLastRecord`[レコード ビューの使用](../../data/using-a-record-view-mfc-data-access.md)" "および" "を参照してください。  
  
 `CRecordView` はレコード ビューがユーザー インターフェイスを更新できるように、レコードセットのユーザーの位置を追跡します。  ユーザーがレコードセットのいずれかの最後に実行されると、レコード ビューは、さらに同じ方向の移動の…ユーザー インターフェイス オブジェクトを—メニュー項目やツール バー ボタンなどの無効にします。  
  
 使ってレコード ビュー、およびレコードセット クラスを宣言して使用する方法の詳細については、「" [ビューを記録します。](../../data/record-views-mfc-data-access.md)のレコード ビュー」をデザインする方法と作成\) "を参照してください。  レコード ビューが、これらを使用する方法についての詳細に機能するか [レコード ビューの使用](../../data/using-a-record-view-mfc-data-access.md)" "を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CView](../Topic/CView%20Class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `CRecordView`  
  
## 必要条件  
 **Header:** afxdb.h  
  
## 参照  
 [CFormView クラス](../../mfc/reference/cformview-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CRecordset クラス](../Topic/CRecordset%20Class.md)   
 [CFormView クラス](../../mfc/reference/cformview-class.md)