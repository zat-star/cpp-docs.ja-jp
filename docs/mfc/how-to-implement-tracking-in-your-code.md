---
title: "コードでのトラッカーの実装方法 | Microsoft Docs"
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
  - "CRectTracker クラス, 実装 (トラッカーを)"
ms.assetid: baaeca2c-5114-485f-bf58-8807db1bc973
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# コードでのトラッカーの実装方法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

OLE アイテムを追跡するには、その項目をクリックするか、ドキュメントのビューを更新するなどの項目に関連する特定のイベントを処理しなければなりません。  いずれの場合も、[CRectTracker](../mfc/reference/crecttracker-class.md) の一時オブジェクトを宣言し、このオブジェクトによって項目を処理するだけで十分です。  
  
 ユーザーが項目を選択したとき、またはメニュー コマンドを使用してオブジェクトを挿入する場合、OLE アイテムの状態を表す適切なスタイルのトラッカーを初期化しなければなりません。  次の表は、OCLIENT サンプルで使用される規則の概要を示します。  これらのスタイルの詳細については、「`CRectTracker`」を参照してください。  
  
### OLE アイテムのコンテナーのスタイルと状態  
  
|表示されるスタイル|OLE アイテムの状態|  
|---------------|-----------------|  
|点を打たれた境界|項目がリンクされます|  
|実線の境界|項目はドキュメントに埋め込まれます。|  
|ハンドルを拡大します。|アイテムは現在選択|  
|ハッチ境界|アイテムは現在埋め込み先編集。|  
|陰影パターンは、項目に重なって表示します。|項目のサーバーは開いています|  
  
 OLE アイテムの状態をチェックして、適切なスタイルを設定する手順を使用してこの初期化を簡単に処理できます。  OCLIENT サンプルにある **SetupTracker** 関数はトラッカーの初期化を示します。  この関数のパラメーターは、*pTracker*トラッカーのアドレスが; トラッカーに関連するクライアント項目、`pItem`へのポインター; 四角形と、*pTrueRect*へのポインター。  この関数のコード例全体については、MFC の OLE [OCLIENT](../top/visual-cpp-samples.md)サンプルを参照してください。  
  
 **SetupTracker** のコード例は、単一の関数を示します; 関数の機能の説明と関数の行が混在している:  
  
 [!code-cpp[NVC_MFCOClient#1](../mfc/codesnippet/CPP/how-to-implement-tracking-in-your-code_1.cpp)]  
  
 TRACKER は最小サイズを設定し、トラッカーのスタイルをクリアして初期化されます。  
  
 [!code-cpp[NVC_MFCOClient#2](../mfc/codesnippet/CPP/how-to-implement-tracking-in-your-code_2.cpp)]  
  
 次の行では、項目が現在選択されているかどうか、および項目をドキュメントにリンクまたは内に埋め込まれているかどうかを確認します。  境界の内側に置かれているハンドルを追加されます。項目が現在選択されていることを示すスタイルにサイズを変更します。  項目がドキュメントにリンクした場合は、点を打たれた境界線スタイルが使用されます。  実線の境界は項目が埋め込まれる場合に使用されます。  
  
 [!code-cpp[NVC_MFCOClient#3](../mfc/codesnippet/CPP/how-to-implement-tracking-in-your-code_3.cpp)]  
  
 次のコードは、ハッチ パターンと項目が現在開いている項目に重なって表示します。  
  
 [!code-cpp[NVC_MFCOClient#4](../mfc/codesnippet/CPP/how-to-implement-tracking-in-your-code_4.cpp)]  
  
 トラッカーが表示するたびにこの関数を呼び出すことができます。  たとえば、ビュー クラスの `OnDraw` の関数がこの関数を呼び出します。  これは、ビューが再描画されるたびにトラッカーの外観を更新します。  コード例全体については、MFC サンプルの OLE [OCLIENT](../top/visual-cpp-samples.md)の **CMainView::OnDraw** 関数を参照してください。  
  
 アプリケーションでは、トラッカー コードを、サイズを変更する場合などに、移動して必要な検出するイベント、またはヒットが発生します。  これらの操作は、通常、その項目をつかみます、または移動する試みられていることを示します。  このような場合、つかまれたかを決定する必要があります: 境界間のサイズ変更ハンドルまたは部分はハンドルのサイズを変更します。  `OnLButtonDown` のメッセージ ハンドラーは、項目に対するマウスの位置をテストに適しています。  `CRectTracker::HitTest`に呼び出しを行ってください。  テストが **CRectTracker::hitOutside**属性以外のものを返した場合、列のサイズが変更された、または移動されます。  したがって、`Track` のメンバー関数を呼び出す必要があります。  コード例全体については、" MFC サンプルの OLE [OCLIENT](../top/visual-cpp-samples.md) にある **CMainView::OnLButtonDown** 関数を参照してください。  
  
 `CRectTracker` クラスは、移動、サイズ変更、またはドラッグ操作が行われているかどうかを示すために使用される複数のカーソルの図形を提供します。  このイベントは、マウスの下にある項目が現在選択されているかどうかを参照するために処理するため、チェック。  そうである場合、呼び出しを `CRectTracker::SetCursor`にするか、または既定のハンドラーを呼び出します。  次の例では、MFC の OLE サンプル: [OCLIENT](../top/visual-cpp-samples.md)からです。  
  
 [!code-cpp[NVC_MFCOClient#5](../mfc/codesnippet/CPP/how-to-implement-tracking-in-your-code_5.cpp)]  
  
## 参照  
 [トラッカー : OLE アプリケーションでのトラッカーの実装](../mfc/trackers-implementing-trackers-in-your-ole-application.md)