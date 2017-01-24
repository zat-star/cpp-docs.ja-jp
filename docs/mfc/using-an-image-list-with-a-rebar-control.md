---
title: "Rebar コントロールでのイメージ リストの使い方 | Microsoft Docs"
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
  - "イメージ リスト [C++], rebar コントロール"
  - "rebar コントロール, イメージ リスト"
ms.assetid: 1a5836ac-019a-46aa-8741-b35c3376b839
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Rebar コントロールでのイメージ リストの使い方
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

各 rebar バンドは、特に、関連するイメージ リストからイメージを含めることができます。  次の手順では、rebar バンドのイメージを表示するために必要な手順を詳しく説明します。  
  
### rebar バンドにイメージを表示するには  
  
1.  呼び出すことによって、既存のイメージ リストへのポインターを渡す [SetImageList](../Topic/CReBarCtrl::SetImageList.md)への Rebar コントロール オブジェクトには、イメージ リストを接続します。  
  
2.  rebar バンドにイメージを割り当てるに **REBARBANDINFO** の構造を変更する:  
  
    -   必要に応じて追加のフラグが含まれるようにビットごとの OR 演算子を使用して **RBBIM\_IMAGE**に **fMask** のメンバーを設定します。  
  
    -   表示するイメージのイメージ リスト内のインデックスに `iImage` のメンバーを設定します。  
  
3.  必要な情報に含まれる子ウィンドウのサイズ、テキストやハンドルなどの残りのデータ メンバーを、初期化してください。  
  
4.  **REBARBANDINFO** 構造体を渡す [CReBarCtrl::InsertBand](../Topic/CReBarCtrl::InsertBand.md)を呼び出して新しいバンド \(イメージ\) を挿入します。  
  
 次の例は、Rebar コントロール オブジェクト \(`m_wndReBar`\) への 2 回のイメージの既存のイメージ リスト オブジェクトに接続されていることを前提としています。  最初のイメージを含む新しい rebar バンド \(`rbi`で定義される\) `InsertBand`と追加されます:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#28](../mfc/codesnippet/CPP/using-an-image-list-with-a-rebar-control_1.cpp)]  
  
## 参照  
 [CReBarCtrl の使い方](../Topic/Using%20CReBarCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)