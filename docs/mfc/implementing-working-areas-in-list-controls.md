---
title: "リスト コントロールの作業領域を実装する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- list controls [MFC], working areas
- working areas in list control [MFC]
ms.assetid: fbbb356b-3359-4348-8603-f1cb114cadde
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cefb8007fd9b73dda4c0e8a99e9ae9daa1bfcc34
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="implementing-working-areas-in-list-controls"></a>リスト コントロールの作業領域の実装
既定では、リスト コントロールは、標準的なグリッドのすべてのアイテムを配置します。 ただし、別の方法がサポートされて、作業領域、四角形のグループに、リスト項目を配置します。 作業領域を実装するリスト コントロールのイメージは、Windows SDK でリスト ビュー コントロールの使用を参照してください。  
  
> [!NOTE]
>  作業領域は、リスト コントロールがアイコンまたは小さいアイコンのモードである場合にのみ表示されます。 ただし、すべて現在の作業領域には、ビューは、レポートまたはリスト モードに切り替えられた場合は保持されます。  
  
 (上、左、上またはアイテムの右側)、空の境界線を表示したりできますいずれかの場合に表示される、水平スクロール バーを発生させるのには、作業領域を使用できます。 別の一般的な使用法では、複数の作業領域に項目を移動したり削除を作成します。 このメソッドにより、異なる意味を持つ 1 つのビューの領域を作成できます。 ユーザーは、別の領域に配置して項目を分類し、可能性があります。 この例は、読み取り/書き込みファイルの領域と読み取り専用ファイルの別の領域を持つファイル システムの表示になります。 ファイルの項目は、読み取り専用領域に移動された場合に自動的になります読み取り専用。 読み取り専用領域から読み取り/書き込み領域にファイルの移動は、読み取り/書き込みです。  
  
 `CListCtrl`作成すると、リスト コントロールでの作業領域を管理するには、いくつかのメンバー関数を提供します。 [GetWorkAreas](../mfc/reference/clistctrl-class.md#getworkareas)と[SetWorkAreas](../mfc/reference/clistctrl-class.md#setworkareas)を取得および設定の配列`CRect`オブジェクト (または`RECT`構造体)、リスト コントロールの現在の実装での作業領域を格納します。 さらに、 [GetNumberOfWorkAreas](../mfc/reference/clistctrl-class.md#getnumberofworkareas)リスト コントロールの作業領域の現在の数を取得します (既定では、ゼロ)。  
  
## <a name="items-and-working-areas"></a>アイテムし、作業領域  
 作業領域の作成時に作業領域内にある項目のメンバーになります。 同様に、作業領域に項目を移動する場合、移動先となる作業領域のメンバーになります。 どの作業領域内で項目を設定することはありませんと、(インデックス 0) の最初の作業領域のメンバーが自動的になります。 項目を作成し、特定の作業領域に配置する場合は、項目を作成しを呼び出して目的の作業領域に移動して必要があります。 [SetItemPosition](../mfc/reference/clistctrl-class.md#setitemposition)です。 次の 2 番目の例では、この手法を実証します。  
  
 次の例は、次の 4 つの作業領域を実装 (`rcWorkAreas`)、ピクセル幅の 10 のリスト コントロール内の各の作業領域は、境界線と等しいサイズの (`m_WorkAreaListCtrl`)。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#20](../mfc/codesnippet/cpp/implementing-working-areas-in-list-controls_1.cpp)]  
  
 呼び出し[例で](../mfc/reference/clistctrl-class.md#approximateviewrect)を 1 つの地域のすべてのアイテムの表示に必要な合計領域の推定値を取得しました。 この推定値は、4 つの領域に分割され、5 ピクセル全体の枠線で埋められます。  
  
 次の例では、既存のリスト アイテムを各グループに割り当てます (`rcWorkAreas`) し、コントロールのビューを更新 (`m_WorkAreaListCtrl`) 効果を完了します。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#21](../mfc/codesnippet/cpp/implementing-working-areas-in-list-controls_2.cpp)]  
  
## <a name="see-also"></a>参照  
 [CListCtrl の使い方](../mfc/using-clistctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

