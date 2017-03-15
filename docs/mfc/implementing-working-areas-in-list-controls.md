---
title: "リスト コントロールの作業領域の実装 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "リスト コントロール, 作業領域"
  - "作業領域 (リスト コントロールの)"
ms.assetid: fbbb356b-3359-4348-8603-f1cb114cadde
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# リスト コントロールの作業領域の実装
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

既定でリスト コントロールは、標準グリッド スキームのすべてのアイテムを配置します。  ただし、四角形のグループにリスト項目を配置する別のメソッドは、作業領域サポートされます。  作業領域を実装するリスト コントロールのイメージの場合、参照しまリスト ビュー コントロールを [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]で使用します。  
  
> [!NOTE]
>  作業領域はリスト コントロールがアイコンまたは小さいアイコンのモードのときにのみ表示されます。  ただし、ビューがレポートまたはリスト モードに切り替えられれば、現在の作業領域が保持されます。  
  
 作業領域が空の境界を表示するために \(項目の左側に、上、または右\) 使用できますが、または 1 は通常、ときに水平スクロール バーが表示されます。  もう一つの一般的な用途は、項目を移動または削除することができる複数の作業領域を作成します。  このメソッドによって、一つのビューで意味が異なる領域を作成できます。  ユーザーが個別の領域に入れて項目にラベルを付けることができます。  次の例は、読み取り\/書き込みファイルの区分および読み取り専用ファイルの個別の領域のファイル システムのビューです。  ファイル項目が読み取り専用領域に移動されている場合、自動的に読み取り専用になります。  読み取り\/書き込み領域に読み取り専用領域からファイルを移動すると、読み取り\/書き込みファイルを作成します。  
  
 `CListCtrl` は リスト コントロールの作成と管理の作業領域に複数のメンバー関数を提供します。  [GetWorkAreas](../Topic/CListCtrl::GetWorkAreas.md) と [SetWorkAreas](../Topic/CListCtrl::SetWorkAreas.md) はリスト コントロールの現在実装された作業領域を格納する `RECT` 構造体\) 取得し、設定、または `CRect` オブジェクトの配列 \(。  また、[GetNumberOfWorkAreas](../Topic/CListCtrl::GetNumberOfWorkAreas.md) はリスト コントロール \(既定ではゼロ\) の作業領域の現在の数を取得します。  
  
## 項目と作業領域  
 作業領域が作成されると、作業領域内にある項目はそのメンバーになります。  同様に、項目が作業領域に移動すると、移動した作業領域のメンバーになります。  項目がどの作業領域内に存在しない場合は、自動的に最初の \(インデックス 0\) 作業領域のメンバーになります。  項目を作成し、特定の作業領域内に配置するか、項目を作成し、[SetItemPosition](../Topic/CListCtrl::SetItemPosition.md)と目的の作業領域に移動する必要があります。  2 番目の例では、この方法を示しています。  
  
 次の例では、リスト コントロール \(`m_WorkAreaListCtrl`\) の各作業領域の周囲に 4 個の作業領域 \(10 ピクセル全体の境界で同じサイズの`rcWorkAreas`\) を、実装します。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#20](../mfc/codesnippet/CPP/implementing-working-areas-in-list-controls_1.cpp)]  
  
 [ApproximateViewRect](../Topic/CListCtrl::ApproximateViewRect.md) の呼び出しは 1 スペースのすべての項目を表示するために必要な全域の見積もりを取得できるようになりました。  この見積もりは 4 スペースと分割され、5 ピクセルの境界全体で埋められます。  
  
 次の例は、各グループ`rcWorkAreas` \(\) と更新に効果を完了するために既存のリスト項目のコントロール ビュー \(`m_``WorkAreaListCtrl`\) を割り当てます。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#21](../mfc/codesnippet/CPP/implementing-working-areas-in-list-controls_2.cpp)]  
  
## 参照  
 [CListCtrl の使い方](../Topic/Using%20CListCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)