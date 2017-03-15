---
title: "メッセージ マップ (ATL) | Microsoft Docs"
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
  - "ATL, メッセージ ハンドラー"
  - "メッセージ マップ, ATL"
ms.assetid: 9e100400-65c7-4a85-8857-4e6cb6dd7340
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# メッセージ マップ (ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

メッセージ マップでは、特定のメッセージ、コマンド、または通知とハンドラー関数を関連付けます。  ATL [メッセージ マップ マクロ](../atl/reference/message-map-macros-atl.md)を使用すると、ウィンドウにメッセージ マップを指定できます。  `CWindowImpl`、`CDialogImpl`と `CContainedWindowT` のウィンドウ プロシージャは、メッセージ マップにウィンドウのメッセージを表示します。  
  
 [メッセージ ハンドラー関数](../atl/message-handler-functions.md) の場合、型 `BOOL&`の追加の引数。  この引数は、メッセージが処理された `TRUE` に、既定でに設定されます。また。  ハンドラー関数が `FALSE` にメッセージが不要であることを示すには、引数を設定できます。  この場合、ATL には、メッセージ マップのハンドラー関数の詳細を検索します。  `FALSE`にこの引数を設定すると、メッセージに応答して最初にアクションを実行し、メッセージを処理する最後に既定の処理、または別のハンドラー関数を割り当てることができます。  
  
## チェーン メッセージ マップ  
 ATL は、別のクラスで定義されているメッセージ マップにメッセージ処理を指示するメッセージ マップをチェーンすることができます。  たとえば、そのクラスにチェーンするすべてのペインに均等な動作を提供するために別のクラスに共通メッセージ処理を実行できます。  基本クラスまたはクラスのデータ メンバーに連結できます。  
  
 ATL は、実行時に別のオブジェクトのメッセージ マップに連結できる動的チェインをサポートします。  動的チェインを実行するには、[CDynamicChain](../atl/reference/cdynamicchain-class.md)からクラスを派生させる必要があります。  次に、メッセージ マップの [CHAIN\_MSG\_MAP\_DYNAMIC](../Topic/CHAIN_MSG_MAP_DYNAMIC.md) のマクロを宣言します。  `CHAIN_MSG_MAP_DYNAMIC` は、チェーン対象のメッセージ マップとオブジェクトを識別する一意の数字が必要です。  `CDynamicChain::SetChainEntry`の呼び出しによってこの一意の値を定義する必要があります。  
  
 [CMessageMap](../atl/reference/cmessagemap-class.md)クラスがから派生する場合、メッセージ マップを宣言する任意のクラスにチェーンできます。  `CMessageMap` は、オブジェクトが他のオブジェクトにメッセージ マップを公開するようにします。  `CWindowImpl` が `CMessageMap`から派生します。  
  
## メッセージ マップを交互にします。  
 最後に、ATL は [ALT\_MSG\_MAP](../Topic/ALT_MSG_MAP.md) のマクロで宣言される代替メッセージ マップをサポートします。  それぞれの代替メッセージ マップでは、`ALT_MSG_MAP`に渡す一意の番号で識別されます。  代替メッセージ マップを使用して、1 種類のマップの複数のウィンドウのメッセージを処理できます。  は、`CWindowImpl` 使用しない代替メッセージ マップを既定では注意してください。  このサポートを追加し、それを `CWindowImpl`の `WindowProc` 派生クラスのメソッドをオーバーライドし、メッセージ マップの識別子との `ProcessWindowMessage` を呼び出します。  
  
## 参照  
 [ウィンドウの実装](../atl/implementing-a-window.md)