---
title: "標準コントロールからのコントロールの派生 | Microsoft Docs"
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
  - "コモン コントロール [C++], 派生"
  - "コントロール [MFC], 派生"
  - "派生コントロール"
  - "標準コントロール"
  - "標準コントロール, 派生 (コントロールを)"
  - "Windows コモン コントロール [C++], 派生"
ms.assetid: a6f84315-7007-4e0e-8576-78be81254802
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 標準コントロールからのコントロールの派生
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CWnd](../Topic/CWnd%20Class.md)と同様に\-派生クラス、既存のコントロール クラスから新しいクラスを派生することによって、コントロールの動作を変更できます。  
  
### コントロールの派生クラスを作成するには  
  
1.  基本クラスの **作成** 関数に必要な引数を指定するようにクラスを既存のコントロール クラスから派生し、必要に応じて **作成** のメンバー関数をオーバーライドします。  
  
2.  特定の Windows メッセージに応答してコントロールの動作を変更するには、メッセージ ハンドラー メンバー関数とメッセージ マップのエントリを提供します。  「[関数へのメッセージの割り当て](../Topic/Mapping%20Messages%20to%20Functions.md)」を参照してください。  
  
3.  コントロールの機能を提供します \(省略可能な\) 拡張する新しいメンバー関数を示します。  
  
 ダイアログ ボックスの派生コントロールを使用して追加の作業が必要です。  ダイアログ ボックスのコントロールの種類と位置はダイアログ テンプレート リソース \(通常は指定されます。  コントロールの派生クラスを作成すると、リソース コンパイラが派生クラスに関する知識がわからないため、ダイアログ テンプレートで指定できません。  
  
#### 派生コントロールをダイアログ ボックスに配置するには  
  
1.  派生ダイアログ クラスの宣言で派生コントロール クラスのオブジェクトを埋め込みます。  
  
2.  派生コントロールの `SubclassDlgItem` のメンバー関数を呼び出すに `OnInitDialog` ダイアログ クラスのメンバー関数をオーバーライドします。  
  
 `SubclassDlgItem` は 「動的に」ダイアログ テンプレートから作成されるコントロールをサブクラス化します。  コントロールが動的にサブクラス化されると、Windows に引っ掛かりましたり、独自のアプリケーション内のすべてのメッセージを処理し、Windows に残りのメッセージを渡します。  詳細については、" *MFC リファレンス"の*" `CWnd` クラスの [SubclassDlgItem](../Topic/CWnd::SubclassDlgItem.md) メンバー関数を参照します。  `SubclassDlgItem`を呼び出す方法に `OnInitDialog` のオーバーライドを書き込む方法を次の例に示します。:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#3](../mfc/codesnippet/CPP/deriving-controls-from-a-standard-control_1.cpp)]  
  
 派生コントロールは、ダイアログ クラスに埋め込まれているため、ダイアログ ボックスが破棄されるときにダイアログ ボックスの作成と構成され、破棄されます。  [コントロールを手動で追加します。](../mfc/adding-controls-by-hand.md)の例でこのコードを比較します。  
  
## 参照  
 [コントロールの作成方法と使い方](../mfc/making-and-using-controls.md)   
 [コントロール](../mfc/controls-mfc.md)