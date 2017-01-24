---
title: "COleDropSource クラス | Microsoft Docs"
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
  - "COleDropSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDropSource クラス"
  - "ドラッグ アンド ドロップ, ドロップ ソース"
  - "ドラッグ操作"
  - "ドロップ ターゲット, ドラッグ (データを)"
ms.assetid: d3eecc5f-a70b-4a01-b705-7d2c098ebe17
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleDropSource クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ドロップ ターゲットにドラッグされる割り当てデータ。  
  
## 構文  
  
```  
class COleDropSource : public CCmdTarget  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleDropSource::COleDropSource](../Topic/COleDropSource::COleDropSource.md)|`COleDropSource` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleDropSource::GiveFeedback](../Topic/COleDropSource::GiveFeedback.md)|ドラッグ アンド ドロップ操作中にカーソルを変更します。|  
|[COleDropSource::OnBeginDrag](../Topic/COleDropSource::OnBeginDrag.md)|ドラッグ アンド ドロップ操作中でマウス キャプチャ。|  
|[COleDropSource::QueryContinueDrag](../Topic/COleDropSource::QueryContinueDrag.md)|ドラッグ継続するかどうかを確認します。|  
  
## 解説  
 [COleDropTarget](../Topic/COleDropTarget%20Class.md) のクラスは、ドラッグ アンド ドロップ操作の受信する部分を処理します。  `COleDropSource` のオブジェクトは、ドラッグ操作中にドラッグ操作がいつ開始位置を決定し、フィードバックを提供し、ドラッグ操作の終了を確認する必要があります。  
  
 `COleDropSource` のオブジェクトを使用するには、コンストラクターを呼び出します。  これは、どのイベントは、マウス クリックなど [COleDataSource::DoDragDrop](../Topic/COleDataSource::DoDragDrop.md)、[COleClientItem::DoDragDrop](../Topic/COleClientItem::DoDragDrop.md)、または [COleServerItem::DoDragDrop](../Topic/COleServerItem::DoDragDrop.md) 関数を使用して、ドラッグ操作を開始するかを決定するプロセスを簡略化します。  これらの関数は、の `COleDropSource` のオブジェクトを作成します。  `COleDropSource` のオーバーライド可能な関数の既定の動作を変更する場合があります。  これらのメンバー関数は、フレームワークによって適切なときに呼び出されます。  
  
 を使用して OLE ドラッグ アンド ドロップ操作の詳細については、" " [ドラッグ アンド ドロップ \(OLE\)](../../mfc/drag-and-drop-ole.md)を参照してください。  
  
 詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [IDropSource](http://msdn.microsoft.com/library/windows/desktop/ms690071) を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 `COleDropSource`  
  
## 必要条件  
 **Header:** afxole.h  
  
## 参照  
 [MFC HIERSVR サンプル](../../top/visual-cpp-samples.md)   
 [MFC の OCLIENT サンプル](../../top/visual-cpp-samples.md)   
 [CCmdTarget クラス](../Topic/CCmdTarget%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)