---
title: "CRectTracker クラス | Microsoft Docs"
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
  - "CRectTracker"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRectTracker クラス"
  - "表示 (項目を)"
  - "サイズ変更 (アイテムを)"
ms.assetid: 99caa7f2-3c0d-4a42-bbee-e5d1d342d4ee
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRectTracker クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

項目が異なる方法で表示され、実行されるため、サイズを変更できるようにします。  
  
## 構文  
  
```  
  
class CRectTracker  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CRectTracker::CRectTracker](../Topic/CRectTracker::CRectTracker.md)|`CRectTracker` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CRectTracker::AdjustRect](../Topic/CRectTracker::AdjustRect.md)|四角形のサイズが変更されたときに呼び出されます。|  
|[CRectTracker::Draw](../Topic/CRectTracker::Draw.md)|四角形を表示します。|  
|[CRectTracker::DrawTrackerRect](../Topic/CRectTracker::DrawTrackerRect.md)|`CRectTracker` のオブジェクトの境界線を描画するときに呼び出されます。|  
|[CRectTracker::GetHandleMask](../Topic/CRectTracker::GetHandleMask.md)|`CRectTracker`の項目のサイズ変更ハンドルのマスクを取得するために呼び出されます。|  
|[CRectTracker::GetTrueRect](../Topic/CRectTracker::GetTrueRect.md)|サイズ変更ハンドルを含む四角形の幅と高さを返します。|  
|[CRectTracker::HitTest](../Topic/CRectTracker::HitTest.md)|`CRectTracker` オブジェクトに関連するカーソルの現在位置を返します。|  
|[CRectTracker::NormalizeHit](../Topic/CRectTracker::NormalizeHit.md)|ヒット テスト コードを正規化します。|  
|[CRectTracker::OnChangedRect](../Topic/CRectTracker::OnChangedRect.md)|四角形のサイズが変更された、または移動されたときに呼び出されます。|  
|[CRectTracker::SetCursor](../Topic/CRectTracker::SetCursor.md)|四角形の上にカーソル位置によってを設定します。|  
|[CRectTracker::Track](../Topic/CRectTracker::Track.md)|ユーザーを四角形を操作できるようにします。|  
|[CRectTracker::TrackRubberBand](../Topic/CRectTracker::TrackRubberBand.md)|ユーザー「」ゴム バンドに選択されます。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CRectTracker::m\_nHandleSize](../Topic/CRectTracker::m_nHandleSize.md)|サイズ変更ハンドルのサイズが決まります。|  
|[CRectTracker::m\_nStyle](../Topic/CRectTracker::m_nStyle.md)|TRACKER の現在のスタイル。|  
|[CRectTracker::m\_rect](../Topic/CRectTracker::m_rect.md)|四角形の現在位置 \(ピクセル単位\)。|  
|[CRectTracker::m\_sizeMin](../Topic/CRectTracker::m_sizeMin.md)|最小の四角形の幅と高さが決まります。|  
  
## 解説  
 `CRectTracker` には、基本クラスはありません。  
  
 ユーザーが OLE アイテムと対話できるように `CRectTracker` のクラスがグラフィカル インターフェイスを使用して設計されていますが、使用は、OLE 対応のアプリケーションに限定されません。  ここで要求されますどこでもそのようなユーザー インターフェイス使用できます。  
  
 `CRectTracker` の境界線が点線または実線です。  項目は、ハッチ境界線を指定したまたはハッチ パターンと項目のさまざまな状態を示すために隠すことができます。  項目の外部または内部の境界線に 8 個のサイズ変更ハンドルを設定できます。  \(サイズ変更ハンドルの詳細については、[GetHandleMask](../Topic/CRectTracker::GetHandleMask.md)を参照してください\)。最後に、`CRectTracker` は、サイズ変更時に項目の方向を変更することができます。  
  
 `CRectTracker`を使用するには、`CRectTracker` オブジェクトを構築し、表示の状態が初期化されるかを指定します。  をユーザーに `CRectTracker` のオブジェクトに関連付けられている OLE アイテムの現在の状態を視覚的フィードバックを提供するためにこのインターフェイスを使用できます。  
  
 `CRectTracker`の使用の詳細については、" " [TRACKER](../../mfc/trackers.md)を参照してください。  
  
## 継承階層  
 `CRectTracker`  
  
## 必要条件  
 **Header:** afxext.h  
  
## 参照  
 [MFC の TRACKER サンプル](../../top/visual-cpp-samples.md)   
 [MFC の DRAWCLI サンプル](../../top/visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleResizeBar クラス](../../mfc/reference/coleresizebar-class.md)   
 [CRect クラス](../../atl-mfc-shared/reference/crect-class.md)   
 [CRectTracker::GetHandleMask](../Topic/CRectTracker::GetHandleMask.md)