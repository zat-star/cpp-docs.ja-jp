---
title: "アプリケーション ウィザードで作成されたレコード ビューのコード (MFC データ アクセス) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アプリケーション ウィザード [C++], レコード ビュー コード"
  - "レコード ビュー, アプリケーション ウィザード コード"
  - "レコード ビュー, 更新 (コントロールを)"
ms.assetid: 18fd4703-5939-491d-b759-985f767b951f
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# アプリケーション ウィザードで作成されたレコード ビューのコード (MFC データ アクセス)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[MFC アプリケーション ウィザード](../mfc/reference/database-support-mfc-application-wizard.md)を使用すると、ビューの `OnInitialUpdate` および `OnGetRecordset` メンバー関数がオーバーライドされます。  このフレームワークによってフレーム ウィンドウ、ドキュメント、およびビューが作成された後、`OnInitialUpdate` が呼び出されてビューが初期化されます。  `OnInitialUpdate` は、レコードセットへのポインターをドキュメントから取得します。  基本クラス [CView::OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) 関数が呼び出されると、レコードセットが開きます。  次のコードは、`CRecordView` に対するこの処理を示しています。`CDaoRecordView` に対するコードもほぼ同じです。  
  
```  
void CSectionForm::OnInitialUpdate()  
{  
   m_pSet = &GetDocument()->m_sectionSet;  
   CRecordView::OnInitialUpdate();  
}  
```  
  
 レコードセットが開くと、レコードが選択されます。  [CRecordset::Open](../Topic/CRecordset::Open.md) または [CDaoRecordset::Open](../Topic/CDaoRecordset::Open.md) を使用すると最初のレコードが現在のレコードに設定され、DDX により、レコードセットのフィールド データ メンバーからビュー内の該当するフォーム コントロールにデータが移動されます。  RFX の詳細については、「[レコード フィールド エクスチェンジ \(RFX\)](../data/odbc/record-field-exchange-rfx.md)」を参照してください。  DDX の詳細については、「[ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../mfc/dialog-data-exchange-and-validation.md)」を参照してください。  ドキュメント\/ビューの作成プロセスについては、「[クラスを使用した Windows アプリケーションの作成](../Topic/Using%20the%20Classes%20to%20Write%20Applications%20for%20Windows.md)」を参照してください。  
  
> [!NOTE]
>  エンド ユーザーには、レコードセットからレコード ビュー コントロールを更新するための機能を提供する必要があります。  この機能がないと、ユーザーがコントロールの値を無効な値に変更した場合に、現在のレコードを一切操作できなくなる可能性があります。  コントロールを更新するには、`CWnd` のメンバー関数 [UpdateData](../Topic/CWnd::UpdateData.md) をパラメーター **FALSE** で呼び出します。  
  
## 参照  
 [レコード ビューの使用法](../data/using-a-record-view-mfc-data-access.md)