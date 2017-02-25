---
title: "ツリー コントロール項目の状態の概要 | Microsoft Docs"
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
  - "CTreeCtrl クラス, 項目の状態"
  - "状態, CTreeCtrl 項目"
  - "ツリー コントロール, 項目の状態の概要"
ms.assetid: 2db11ae0-0d87-499d-8c1f-5e0dbe9e94c8
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# ツリー コントロール項目の状態の概要
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ツリー コントロール \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) の各項目が現在の状態になります。  たとえば、項目が展開されて無効にされてなど、選択できます。  ほとんどの場合、ツリー コントロールは、自動的に項目の選択などのユーザー アクションを反映するように、項目の状態を設定します。  ただし、[SetItemState](../Topic/CTreeCtrl::SetItemState.md) メンバー関数を使用して、項目の状態を設定し、[GetItemState](../Topic/CTreeCtrl::GetItemState.md) メンバー関数を使用して項目の現在の状態を取得できます。  項目の条件の一覧については、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]の [ツリービュー コントロールの定数](http://msdn.microsoft.com/library/windows/desktop/bb759985) を参照してください。  
  
 項目の現在の状態が `nState` パラメーターによって指定されます。  ツリー項目コントロールは、項目を選択したり、フォーカスを設定するなどのユーザー アクションを反映するように、項目の状態を変更する場合があります。  また、アプリケーションは無効にするか、項目を非表示または状態イメージとオーバーレイ イメージを指定するために、項目の状態を変更する場合があります。  
  
 項目の状態を指定するか、または変更するときは、`nStateMask` パラメーターを設定する状態ビットと `nState` パラメーターがこれらのビットの新しい値を含む名前空間を指定します。  たとえば、次の例では **TVIS\_EXPANDPARTIAL**への `CTreeCtrl` オブジェクト \(`m_treeCtrl`\) の親項目の現在の状態 \(`hParentItem`で指定された\) 変更します:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#71](../mfc/codesnippet/CPP/tree-control-item-states-overview_1.cpp)]  
  
 状態を変更するもう一つの例では、項目のオーバーレイ イメージを設定します。  これを行うには、`nStateMask` は `TVIS_OVERLAYMASK` 値が格納 `nState` は [INDEXTOOVERLAYMASK](http://msdn.microsoft.com/library/windows/desktop/bb761408) マクロを使用して左シフト オーバーレイ イメージの 8 ビット インデックス番号が 1 から始まるなインデックスを含める必要があります。  インデックスは、オーバーレイ イメージを指定する 0 です。  オーバーレイ イメージは [CImageList::SetOverlayImage](../Topic/CImageList::SetOverlayImage.md) 関数への呼び出しでツリー コントロールのオーバーレイ イメージ リストに追加されている必要があります。  関数は、追加するイメージのインデックス番号が 1 から始まるなインデックスを指定します; これは **INDEXTOOVERLAYMASK** マクロで使用されるインデックスです。  ツリー コントロールには 4 個のオーバーレイ イメージを指定できます。  
  
 項目の状態イメージを設定するには、`nStateMask` は `TVIS_STATEIMAGEMASK` 値が格納 `nState` は [INDEXTOSTATEIMAGEMASK](http://msdn.microsoft.com/library/windows/desktop/bb775597) マクロを使用して左シフト状態イメージ 12 ビットのインデックス番号が 1 から始まるなインデックスを含める必要があります。  インデックスは状態イメージを指定する 0 です。  オーバーレイと状態イメージの詳細については、「[ツリー コントロールのイメージ リスト](../mfc/tree-control-image-lists.md)」を参照してください。  
  
## 参照  
 [CTreeCtrl の使い方](../Topic/Using%20CTreeCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)