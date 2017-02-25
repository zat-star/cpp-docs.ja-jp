---
title: "メッセージ マップ マクロ (MFC) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.messages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Windows メッセージの定義"
  - "メッセージ マップ マクロ"
  - "メッセージ マップの範囲"
  - "メッセージ割り当てマクロ"
  - "メッセージ マップ [C++], 宣言と定義"
  - "メッセージ マップ [C++], マクロ"
  - "範囲, メッセージ マップ"
  - "Windows メッセージ [C++], 宣言"
ms.assetid: 531b15ce-32b5-4ca0-a849-bb519616c731
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# メッセージ マップ マクロ (MFC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

メッセージ マップをサポートするために、MFC では次のマクロを指定する:  
  
### メッセージ マップの宣言と区切りマクロ  
  
|||  
|-|-|  
|[DECLARE\_MESSAGE\_MAP](../Topic/DECLARE_MESSAGE_MAP.md)|関数にメッセージをマップするためにメッセージ マップをクラスで使用することを宣言します。クラスの宣言の中で使用する必要があります。|  
|[BEGIN\_MESSAGE\_MAP](../Topic/BEGIN_MESSAGE_MAP.md)|メッセージ マップの定義を開始します。クラスの実装の中で使用する必要があります。|  
|[END\_MESSAGE\_MAP](../Topic/END_MESSAGE_MAP.md)|メッセージ マップの定義を終了します。クラスの実装の中で使用する必要があります。|  
  
### メッセージ マップ マクロ  
  
|||  
|-|-|  
|[ON\_COMMAND](../Topic/ON_COMMAND.md)|どの関数で指定されたコマンド メッセージを処理するかを示します。|  
|[ON\_CONTROL](../Topic/ON_CONTROL.md)|どの関数で指定コントロール通知メッセージを処理するかを示します。|  
|[ON\_MESSAGE](../Topic/ON_MESSAGE.md)|ユーザー定義メッセージをどの関数で処理するかを示します。|  
|[ON\_OLECMD](../Topic/ON_OLECMD.md)|どの関数で DocObject またはコンテナーのメニュー コマンドを処理するかを示します。|  
|[ON\_REGISTERED\_MESSAGE](../Topic/ON_REGISTERED_MESSAGE.md)|どの関数で登録されたユーザー定義メッセージを処理するかを示します。|  
|[ON\_REGISTERED\_THREAD\_MESSAGE](../Topic/ON_REGISTERED_THREAD_MESSAGE.md)|`CWinThread` クラスがある場合、関数が登録されているユーザー定義メッセージを処理するかを示します。|  
|[ON\_THREAD\_MESSAGE](../Topic/ON_THREAD_MESSAGE.md)|`CWinThread` クラスがある場合、関数がユーザー定義メッセージを処理するかを示します。|  
|[ON\_UPDATE\_COMMAND\_UI](../Topic/ON_UPDATE_COMMAND_UI.md)|どの関数で指定したユーザー インターフェイス更新コマンド メッセージを処理するかを示します。|  
  
### メッセージマップの範囲のマクロ  
  
|||  
|-|-|  
|[ON\_COMMAND\_RANGE](../Topic/ON_COMMAND_RANGE.md)|どの関数がマクロの最初の 2 個のパラメーターで指定されたコマンド ID の範囲を処理するかを示します。|  
|[ON\_UPDATE\_COMMAND\_UI\_RANGE](../Topic/ON_UPDATE_COMMAND_UI_RANGE.md)|いずれかの更新ハンドラーがマクロの最初の 2 個のパラメーターで指定されたコマンド ID の範囲を処理するかを示します。|  
|[ON\_CONTROL\_RANGE](../Topic/ON_CONTROL_RANGE.md)|どの関数がマクロの 2 番目と 3 番目のパラメーターで指定したコントロール ID の範囲からの通知を処理するかを示します。  最初のパラメーターは **BN\_CLICKED**など、コントロール通知メッセージです。|  
  
 メッセージ マップ、メッセージ マップの宣言と区切りマクロの詳細については、メッセージ マップ マクロ、[メッセージ マップ](../../mfc/reference/message-maps-mfc.md) と [メッセージの処理とマップ"](../../mfc/message-handling-and-mapping.md)を参照します。  メッセージマップの範囲についての詳細については、「[メッセージ マップの範囲のハンドラー](../../mfc/handlers-for-message-map-ranges.md)」を参照してください。  
  
## 参照  
 [メッセージ マップ](../../mfc/reference/message-maps-mfc.md)