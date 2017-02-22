---
title: "範囲内のメッセージのハンドラー | Microsoft Docs"
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
  - "コマンド処理, コマンド更新ハンドラー"
  - "コマンド ID, メッセージ マップ"
  - "コマンド ルーティング, コマンド更新ハンドラー"
  - "コマンド更新ハンドラー"
  - "コントロール通知メッセージ"
  - "コントロール [MFC], 通知"
  - "ハンドラー関数"
  - "ハンドラー関数, 宣言"
  - "ハンドラー関数, メッセージ マップの範囲"
  - "ハンドラー"
  - "ハンドラー, メッセージ マップの範囲"
  - "マップ, メッセージの範囲"
  - "メッセージ ハンドラー"
  - "メッセージ処理, メッセージ ハンドラー関数"
  - "メッセージ マップ, メッセージ ハンドラー関数"
  - "メッセージ マップ, 範囲"
  - "メッセージの範囲"
  - "メッセージの範囲, マップ"
  - "メッセージ マップの範囲"
ms.assetid: a271478b-5e1c-46f5-9f29-e5be44b27d08
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 範囲内のメッセージのハンドラー
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、メッセージを一つのハンドラー関数にメッセージ内の範囲をマップする方法について説明します。1 \(関数のみへのマッピング 1 メッセージではなく\)。  
  
 複数のメッセージまたはコントロール通知と同様に処理する必要がある場合があります。  このような場合は、一つのハンドラー関数にメッセージをすべてマップする場合があります。  メッセージ マップの範囲はメッセージの連続した範囲の要素を指定することができます:  
  
-   コマンド ID の範囲をマップする:  
  
    -   コマンド ハンドラー関数。  
  
    -   更新コマンド ハンドラー関数。  
  
-   メッセージ ハンドラー関数にコントロールの ID の範囲のコントロール通知メッセージをマップできます。  
  
 この記事で説明されているトピックは次のとおりです。:  
  
-   [メッセージ マップのエントリを作成できます。](#_core_writing_the_message.2d.map_entry)  
  
-   [ハンドラー関数の宣言](#_core_declaring_the_handler_function)  
  
-   [コマンド ID の範囲の例](#_core_example_for_a_range_of_command_ids)  
  
-   [コントロールの ID の範囲の例](#_core_example_for_a_range_of_control_ids)  
  
##  <a name="_core_writing_the_message.2d.map_entry"></a> メッセージ マップのエントリを作成できます。  
 .cpp ファイルで、次の例に示すように、メッセージ マップのエントリを追加する:  
  
 [!CODE [NVC_MFCMessageHandling#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCMessageHandling#6)]  
  
 メッセージ マップのエントリは、次の要素で構成されています:  
  
-   メッセージ マップ マクロ:範囲  
  
    -   [ON\_COMMAND\_RANGE](../Topic/ON_COMMAND_RANGE.md)  
  
    -   [ON\_UPDATE\_COMMAND\_UI\_RANGE](../Topic/ON_UPDATE_COMMAND_UI_RANGE.md)  
  
    -   [ON\_CONTROL\_RANGE](../Topic/ON_CONTROL_RANGE.md)  
  
-   マクロにパラメーター:  
  
     最初の 2 個のマクロは 3 個のパラメーターを受け取ります。:  
  
    -   範囲を開始するコマンド ID  
  
    -   範囲の最後のコマンド ID  
  
    -   メッセージ ハンドラー関数の名前  
  
     コマンド ID の範囲は連続している必要があります。  
  
     3 番目のマクロ、`ON_CONTROL_RANGE`、追加の最初のパラメーターを受け取ります。: **EN\_CHANGE**など、コントロール通知メッセージ。  
  
##  <a name="_core_declaring_the_handler_function"></a> ハンドラー関数の宣言  
 のハンドラー関数の宣言を追加します。H ファイル。  次のコードは、これがどのように見えるか示します。次に示すように:  
  
 [!CODE [NVC_MFCMessageHandling#7](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCMessageHandling#7)]  
  
 一つのコマンドでハンドラー関数は、通常はパラメーターを受け取りません。  更新ハンドラー関数を除いて、メッセージ マップの範囲のハンドラー関数は追加のパラメーター、型 **UINT**の `nID`が必要です。  このパラメーターは、最初のパラメーターです。  追加のパラメーターは、コマンドをユーザーが実際に選択したかを指定するために必要な追加のコマンド ID が格納されます。  
  
 ハンドラー関数を更新するためのパラメーター要件の詳細については、「[コマンド ID の範囲の例](#_core_example_for_a_range_of_command_ids)」を参照してください。  
  
##  <a name="_core_example_for_a_range_of_command_ids"></a> コマンド ID の範囲の例  
 いつ範囲を使用するかどうか。  1 番目の例では、MFC のサンプル [HIERSVR](../top/visual-cpp-samples.md)のズーム コマンドなどのコマンド処理にあります。  このコマンドは、拡大し、標準サイズの 25% と 300% の間で情報をスケーリングします。  HIERSVR のビュー クラスは次のようになります。メッセージ マップのエントリでズーム コマンドを処理するために範囲を使用します:  
  
 [!CODE [NVC_MFCMessageHandling#8](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCMessageHandling#8)]  
  
 メッセージ マップのエントリを作成すると、T:  
  
-   2 個のコマンド ID、開始と終了連続する範囲。  
  
     ここには `ID_VIEW_ZOOM25` と `ID_VIEW_ZOOM300`です。  
  
-   コマンドのハンドラー関数の名前。  
  
     ここでは、`OnZoom`です。  
  
 関数宣言は次のようになります。:  
  
 [!CODE [NVC_MFCMessageHandling#9](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCMessageHandling#9)]  
  
 更新ハンドラー関数には類似しており、便利で広範に高くなります。  これは、共通 `ON_UPDATE_COMMAND_UI` ハンドラーを一部のコマンドに書き込み、独自の検索に書き込み、または、同じコードを何度もコピーです。  ソリューションは `ON_UPDATE_COMMAND_UI_RANGE` マクロを使用して 1 人の更新ハンドラー関数にコマンド ID の範囲をマップします。  コマンド ID が連続する範囲を形成する必要があります。  例については、HIERSVR サンプルのビュー クラスの **OnUpdateZoom** ハンドラーと `ON_UPDATE_COMMAND_UI_RANGE` のメッセージ マップのエントリを参照してください。  
  
 一つのコマンドで更新ハンドラー関数は、単一のパラメーター、型 **CCmdUI\***の `pCmdUI`、を受け取ります。  ハンドラー関数とは異なり、メッセージ マップの範囲の更新ハンドラー関数は追加のパラメーター、型 **UINT**の `nID`を必要としません。  どのコマンドをユーザーが実際に選択したか指定する必要のあるコマンド ID が `CCmdUI` オブジェクトにあります。  
  
##  <a name="_core_example_for_a_range_of_control_ids"></a> コントロールの ID の範囲の例  
 別の重要なケースは単一のハンドラーにコントロールの ID の範囲のコントロール通知メッセージをマップします。  ユーザーが 10 のボタン クリックするとします。  すべてのボタンの 10 ~ 1 個のハンドラーをマップするには、メッセージ マップのエントリは次のようになります。:  
  
 [!CODE [NVC_MFCMessageHandling#10](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCMessageHandling#10)]  
  
 メッセージ マップに `ON_CONTROL_RANGE` マクロを作成する場合、指定する:  
  
-   特定のコントロール通知メッセージ。  
  
     ここでは、**BN\_CLICKED**です。  
  
-   コントロールの連続した範囲に関連付けられたコントロール ID 値。  
  
     ここでは、これら `IDC_BUTTON1` と `IDC_BUTTON10`です。  
  
-   メッセージ ハンドラー関数の名前。  
  
     ここでは、`OnButtonClicked`です。  
  
 ハンドラー関数を記述する場合は、次に示すように **UINT** 追加のパラメーターを指定する:  
  
 [!CODE [NVC_MFCMessageHandling#11](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCMessageHandling#11)]  
  
 **BN\_CLICKED** 一つのメッセージの `OnButtonClicked` ハンドラーはパラメーターを受け取りません。  ボタンの範囲の同じハンドラーは 1 **UINT**を受け取ります。  追加のパラメーターは **BN\_CLICKED** メッセージを生成する必要があるコントロールを識別するようにします。  
  
 例に示すコードはよくあることです: 値を変換するとメッセージの範囲、このケースに該当することをアサートすることで `int` に渡されました。  これで、ボタンがクリックされた別のアクションを実行する可能性があります。  
  
## 参照  
 [メッセージ ハンドラー関数の宣言](../mfc/declaring-message-handler-functions.md)