---
title: "ビューの描画 | Microsoft Docs"
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
  - "デバイス コンテキスト, 画面描画"
  - "描画, ビューで"
  - "描画メッセージ (ビュー クラスの)"
  - "印刷 [MFC], ビュー"
  - "印刷 (ビューの)"
  - "ビュー, 印刷"
  - "ビュー, 描画"
  - "ビュー, 更新"
ms.assetid: e3761db6-0f19-4482-a4cd-ac38ef7c4d3a
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ビューの描画
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

アプリケーションのほぼすべての描画は、ビュー クラスでオーバーライドする必要があるの `OnDraw` ビューのメンバー関数で発生します。ただし、[ビューによるユーザー入力の解釈](../mfc/interpreting-user-input-through-a-view.md)で説明するマウス描画です\)。`OnDraw` のオーバーライド:  
  
1.  指定したドキュメントのメンバー関数を呼び出してデータを取得します。  
  
2.  デバイス コンテキスト オブジェクトのメンバー関数を呼び出してデータを表示しますが `OnDraw`フレームワークに渡す。  
  
 ドキュメント内のデータがなんらかの方法で変更されたときに変更を反映するように、再描画されなければなりません。  通常は、ユーザーがドキュメントに表示して変更を行った場合に発生します。  この場合、それ自体を更新するために、同じドキュメント内のすべてのビューに通知するようにドキュメントの [UpdateAllViews](../Topic/CDocument::UpdateAllViews.md) メンバー関数を呼び出します。  `UpdateAllViews` は 各ビューに [OnUpdate](../Topic/CView::OnUpdate.md) メンバー関数を呼び出します。  `OnUpdate` の既定の実装は、ビューのクライアント領域全体を無効化します。  ドキュメントの変更部分に割り当てられたクライアント領域だけを無効化するために、この関数をオーバーライドすることもできます。  
  
 クラス **CDocument** の `UpdateAllViews` のメンバー関数とクラス `CView` の `OnUpdate` メンバー関数はドキュメントの部分を変更したかに関する情報を渡すことができます。  この「情報」機能は再描画しなければビューがある領域を制限することができます。  `OnUpdate` は 2 個の「情報」の引数を受け取ります。  1 番目は、`lHint`、型 **LPARAM**、が 2 番 `CObject`型の `pHint`、目的のデータを渡すことができます `CObject`\*、から派生されるオブジェクトへのポインターを渡すことができます。  
  
 ビューが無効になると、Windows は、`WM_PAINT` メッセージを送信します。  ビューの [OnPaint](../Topic/CWnd::OnPaint.md) のハンドラー関数は、メッセージにクラス [CPaintDC](../mfc/reference/cpaintdc-class.md) のデバイス コンテキスト オブジェクトを作成して応答、ビューの `OnDraw` メンバー関数を呼び出します。  通常 `OnPaint` のオーバーライドのハンドラー関数を記述する必要はありません。  
  
 [デバイス コンテキスト](../Topic/Device%20Contexts.md) は表示やプリンターなどのデバイスに描画属性に関する情報を含む Windows のデータ構造です。  すべての描画呼び出しはデバイス コンテキスト オブジェクトを介して行われます。  画面に描画するために、`OnDraw` は `CPaintDC` オブジェクトが渡されます。  プリンターを描画するときに、現在のプリンター用に設定された [CDC](../Topic/CDC%20Class.md) オブジェクトが渡されます。  
  
 ビューの描画のためのコードはドキュメントにポインターを取得しましたり、デバイス コンテキストによって描画呼び出しを作成します。  `OnDraw` の次の簡単な例で、プロセスを説明する:  
  
 [!code-cpp[NVC_MFCDocView#1](../mfc/codesnippet/CPP/drawing-in-a-view_1.cpp)]  
  
 この例では、ドキュメントの派生クラスのメンバーと `GetData` 関数を定義します。  
  
 検索する文字列がドキュメントから取得するビューの中央の例を出力します。  `OnDraw` の呼び出しが画面の描画を行う場合、`pDC` に渡される `CDC` オブジェクトはコンストラクターが既に `BeginPaint`を呼び出している `CPaintDC` です。  描画する関数の呼び出しはデバイスコンテキストのポインターを通じて行われます。  デバイス コンテキストと描画呼び出しについては、*" MFC リファレンス"* と [ウィンドウ オブジェクトの使用](../Topic/Working%20with%20Window%20Objects.md)クラス [CDC](../Topic/CDC%20Class.md) を参照してください。  
  
 `OnDraw`を記述する方法の例については [MFC Samples](../top/visual-cpp-samples.md)を参照してください。  
  
## 参照  
 [ビューの使い方](../mfc/using-views.md)