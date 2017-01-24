---
title: "仮想リスト コントロール | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "キャッシュ, 仮想リスト コントロール項目のデータ"
  - "リスト コントロール, リスト ビュー"
  - "リスト コントロール, virtual"
  - "仮想リスト コントロール"
ms.assetid: 319f841f-e426-423a-8276-d93f965b0b45
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 仮想リスト コントロール
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

仮想リスト コントロールは **LVS\_OWNERDATA** のスタイルがあるリスト ビュー コントロールです。  このスタイルは、コントロールが `DWORD` まで項目数をサポートすることができます \(既定の項目の数が `int`のみ Extends\)。  ただし、このスタイルによって提供される最も大きな利点はメモリのデータ項目のサブセットを一度に処理できるだけ機能です。  これは仮想一覧表示のコントロールがデータにアクセスする特定のメソッドが既に設定された情報の大きなデータベースで使用するために Loan ようにします。  
  
> [!NOTE]
>  `CListCtrl`の仮想一覧の機能に加えて、MFC は、[CListView](../mfc/reference/clistview-class.md) クラスと同じ機能を提供します。  
  
 、注意が必要である互換性の問題があります仮想リスト コントロールを開発するとき。  詳細については、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]のリスト ビュー コントロールの互換性の問題セクションを参照します。  
  
## LVN\_GETDISPINFO 通知の処理  
 仮想リスト コントロールは若干項目情報を保持します。  選択項目とフォーカス情報を除き、すべての項目情報はコントロールのオーナーによって管理されます。  情報は **LVN\_GETDISPINFO** 通知メッセージによってフレームワークで要求されます。  要求された情報を提供するには、仮想リスト コントロールのオーナー \(またはコントロール自体\) この通知を処理しなければなりません。  これはプロパティ ウィンドウを使用して簡単に行うことができます。[関数へのメッセージの割り当て](../Topic/Mapping%20Messages%20to%20Functions.md)を参照してください。  生成されるコード \(`CMyDialog` が仮想リスト コントロール オブジェクトを所有し、ダイアログで通知を処理している場合に\) は、次の例のようになります。:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#23](../mfc/codesnippet/CPP/virtual-list-controls_1.cpp)]  
  
 **LVN\_GETDISPINFO** 通知メッセージに対するハンドラーでどのような情報が要求されているか確認する必要があります。  次の値を指定できます。  
  
-   `LVIF_TEXT`は  `pszText` のメンバー入力する必要があります。  
  
-   `LVIF_IMAGE`は  `iImage` のメンバー入力する必要があります。  
  
-   **LVIF\_INDENT**は  *iIndent* メンバー入力する必要があります。  
  
-   `LVIF_PARAM`は  *lParam* メンバーに入力する必要があります。\(サブ項目の存在しない\)。  
  
-   `LVIF_STATE`メンバーは *、*入力する必要があります。  
  
 その後、どの情報をフレームワークが要求されるも提供する必要があります。  
  
 次の例では、リスト コントロール オブジェクトの通知ハンドラーの本体から取得した\) 項目のテキスト バッファーとイメージの情報を指定して、1 とおりのメソッドを示しています。:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#24](../mfc/codesnippet/CPP/virtual-list-controls_2.cpp)]  
  
## キャッシュと仮想リスト コントロール  
 リスト コントロールでこの型は大きなデータ セットを目的としているため、検索のパフォーマンスを向上するために要求した項目データをキャッシュすることをお勧めします。  フレームワークは、キャッシュの最適化に役立つ **LVN\_ODCACHEHINT** 通知メッセージを送信することによってキャッシュ ヒント機構を提供します。  
  
 次の例では、ハンドラー関数に渡される範囲を持つキャッシュを更新します。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#25](../mfc/codesnippet/CPP/virtual-list-controls_3.cpp)]  
  
 キャッシュを準備し、維持する詳細については、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]のリスト ビュー コントロールのトピックのキャッシュ管理セクションを参照します。  
  
## 特定の項目を検索できます。  
 **LVN\_ODFINDITEM** 通知メッセージが仮想リスト コントロールで特定のリスト コントロール項目が存在する必要がある場合に送信されます。  通知メッセージは、リスト ビュー コントロールが高速なアクセス権を付与または **LVM\_FINDITEM** メッセージを受け取ったときに送信されます。  検索情報は **NMLVFINDITEM** の構造体のメンバーです **LVFINDINFO** 構造体の形式に渡されます。  リスト コントロール内のオブジェクトの `OnChildNotify` 関数をオーバーライドして、このメッセージを処理すれば内部は **LVN\_ODFINDITEM** メッセージがハンドラーの本体、検証します。  見つかった場合、適切なアクションを実行します。  
  
 リスト ビュー コントロールによって提供される情報に一致する項目を検索するように準備する必要があります。  一致する項目がない場合、または \-1 を成功した項目のインデックスを返す必要があります。  
  
## 参照  
 [CListCtrl の使い方](../Topic/Using%20CListCtrl.md)   
 [コントロール](../mfc/controls-mfc.md)