---
title: "CPrintInfo 構造体 | Microsoft Docs"
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
  - "CPrintInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPrintInfo 構造体"
ms.assetid: 0b3de849-d050-4386-9a14-f4c1a25684f7
caps.latest.revision: 21
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPrintInfo 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

印刷や印刷プレビューのジョブに関する情報を格納します。  
  
## 構文  
  
```  
struct CPrintInfo  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CPrintInfo::GetFromPage](../Topic/CPrintInfo::GetFromPage.md)|印刷される最初のページ数を返します。|  
|[CPrintInfo::GetMaxPage](../Topic/CPrintInfo::GetMaxPage.md)|ドキュメントの最後のページ数を返します。|  
|[CPrintInfo::GetMinPage](../Topic/CPrintInfo::GetMinPage.md)|文書の最初のページ数を返します。|  
|[CPrintInfo::GetOffsetPage](../Topic/CPrintInfo::GetOffsetPage.md)|DocObject の結合された印刷ジョブで出力される DocObject の項目の最初のページ、前のページ数を返します。|  
|[CPrintInfo::GetToPage](../Topic/CPrintInfo::GetToPage.md)|印刷される最後のページ数を返します。|  
|[CPrintInfo::SetMaxPage](../Topic/CPrintInfo::SetMaxPage.md)|ドキュメントの最後のページ数を設定します。|  
|[CPrintInfo::SetMinPage](../Topic/CPrintInfo::SetMinPage.md)|文書の最初のページ数を設定します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CPrintInfo::m\_bContinuePrinting](../Topic/CPrintInfo::m_bContinuePrinting.md)|フレームワークが印刷ループを続行するかどうかを示すフラグが含まれます。|  
|[CPrintInfo::m\_bDirect](../Topic/CPrintInfo::m_bDirect.md)|ドキュメントが直接出力するかどうかを示すフラグが含まれます \(印刷ダイアログ ボックスの表示を除いた部分。|  
|[CPrintInfo::m\_bDocObject](../Topic/CPrintInfo::m_bDocObject.md)|印刷されるドキュメントが DocObject かどうかを示すフラグが含まれます。|  
|[CPrintInfo::m\_bPreview](../Topic/CPrintInfo::m_bPreview.md)|文書をプレビューするかどうかを示すフラグが含まれます。|  
|[CPrintInfo::m\_dwFlags](../Topic/CPrintInfo::m_dwFlags.md)|DocObject の印刷操作を指定します。|  
|[CPrintInfo::m\_lpUserData](../Topic/CPrintInfo::m_lpUserData.md)|ユーザー定義の構造体へのポインターを格納します。|  
|[CPrintInfo::m\_nCurPage](../Topic/CPrintInfo::m_nCurPage.md)|現在印刷するページの数を指定します。|  
|[CPrintInfo::m\_nJobNumber](../Topic/CPrintInfo::m_nJobNumber.md)|オペレーティング システムによって割り当てられた現在の印刷ジョブについてがジョブ番号を指定します|  
|[CPrintInfo::m\_nNumPreviewPages](../Topic/CPrintInfo::m_nNumPreviewPages.md)|プレビュー ウィンドウに表示されるページの数を指定します; 1 または 2。|  
|[CPrintInfo::m\_nOffsetPage](../Topic/CPrintInfo::m_nOffsetPage.md)|ドット DocObject のオフセットを最初にページの DocObject 結合された印刷ジョブで指定します。|  
|[CPrintInfo::m\_pPD](../Topic/CPrintInfo::m_pPD.md)|印刷ダイアログ ボックスを使用する `CPrintDialog` のオブジェクトへのポインターが格納されます。|  
|[CPrintInfo::m\_rectDraw](../Topic/CPrintInfo::m_rectDraw.md)|現在の使用可能なページの領域を定義する四角形を指定します。|  
|[CPrintInfo::m\_strPageDesc](../Topic/CPrintInfo::m_strPageDesc.md)|表示するページ数の書式指定文字列が含まれます。|  
  
## 解説  
 `CPrintInfo` は構造体で、基本クラスはありません。  
  
 フレームワークは、コマンドが完了すると印刷や印刷プレビュー コマンドが選択される作成と破棄するたびに `CPrintInfo` オブジェクトを提供します。  
  
 `CPrintInfo` は、現在印刷するページなどの印刷ジョブの現在の状態を印刷する、ページのスコープなどの全体として印刷ジョブに関する情報が格納されます。  情報は [CPrintDialog](../Topic/CPrintDialog%20Class.md) に関連付けられたオブジェクトに格納されます; このオブジェクトは、印刷ダイアログ ボックスでユーザーが入力した値を含みます。  
  
 印刷プロセス中にフレームワークと、からビュー クラスの間で `CPrintInfo` のオブジェクトが渡され、2 の間で情報を交換するために使用されます。  たとえば、フレームワークは `CPrintInfo`かの `m_nCurPage` のメンバーに値を割り当てることが印刷するドキュメント内のどのページ ビュー クラスを通知します; ビュー クラスが値を取得し、指定したページの実際の印刷を実行します。  
  
 また、出力されるまでドキュメントの長さがわからない場合です。  ページが印刷されるたびにこの場合、ドキュメントの末尾のビュー クラスのテスト。  末尾に到達すると、ビュー クラスは **FALSE**に `CPrintInfo` の `m_bContinuePrinting` のメンバーを設定します; これは、印刷ループを停止するために、フレームワークに通知します。  
  
 `CPrintInfo` は `CView` 関数がの下に「も参照」Work メンバーによって使用されますMicrosoft Foundation Class ライブラリに用意されている印刷のアーキテクチャに関する詳細については、[フレーム ウィンドウ](../../mfc/frame-windows.md) と [ドキュメント\/ビュー アーキテクチャ](../Topic/Document-View%20Architecture.md) と [&#91;印刷中&#93;](../../mfc/printing.md)[印刷: マルチページのドキュメント](../../mfc/multipage-documents.md)" "および" "を参照してください。  
  
## 継承階層  
 `CPrintInfo`  
  
## 必要条件  
 **Header:** afxext.h  
  
## 参照  
 [MFC DIBLOOK サンプル](../../top/visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CView::OnBeginPrinting](../Topic/CView::OnBeginPrinting.md)   
 [CView::OnEndPrinting](../Topic/CView::OnEndPrinting.md)   
 [CView::OnEndPrintPreview](../Topic/CView::OnEndPrintPreview.md)   
 [CView::OnPrepareDC](../Topic/CView::OnPrepareDC.md)   
 [CView::OnPreparePrinting](../Topic/CView::OnPreparePrinting.md)   
 [CView::OnPrint](../Topic/CView::OnPrint.md)