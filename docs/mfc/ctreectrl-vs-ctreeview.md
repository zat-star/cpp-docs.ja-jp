---
title: "CTreeCtrl と CTreeView の比較 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CTreeCtrl"
  - "CTreeView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTreeCtrl クラス, vs. CTreeView クラス"
  - "CTreeView クラス, vs. CTreeCtrl クラス"
  - "ツリー コントロール, およびツリー ビュー"
  - "ツリー ビュー コントロール"
ms.assetid: bba5af25-103f-4b53-84d3-071bc9bd6494
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTreeCtrl と CTreeView の比較
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC では、ツリー コントロールをカプセル化するクラスを 2 つあります。: [CTreeCtrl](../mfc/reference/ctreectrl-class.md) と [CTreeView](../mfc/reference/ctreeview-class.md)。  各クラスは、さまざまな状況で役立ちます。  
  
 明確な子ウィンドウのコントロールが必要な場合 `CTreeCtrl` ;を使用します。たとえば、ダイアログ ボックスです。  ウィンドウに他の子コントロールがある場合は特に一般的なダイアログ ボックスと同様に `CTreeCtrl` を使用する必要があります。  
  
 ツリー コントロールにドキュメント\/ビュー アーキテクチャ、ツリー コントロール ビュー ウィンドウのように動作させること `CTreeView` を使用します。  `CTreeView` はフレーム ウィンドウまたは分割ウィンドウのクライアント領域全体を占有します。  これは自動的に親ウィンドウのサイズが変更され、メニュー、アクセラレータ キーとツール バーからコマンド メッセージを処理できるようにサイズ変更されます。  ツリー コントロールのツリーを表示するために必要なデータが含まれているため、対応するドキュメント オブジェクトは複雑でなくてもかまいません。—ドキュメント テンプレートでドキュメント型として [CDocument](../Topic/CDocument%20Class.md) を使用できます。  
  
## 参照  
 [CTreeCtrl の使い方](../Topic/Using%20CTreeCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)