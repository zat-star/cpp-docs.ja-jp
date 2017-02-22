---
title: "メッセージ マップ クロス リファレンスの使い方 | Microsoft Docs"
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
  - "ウィンドウ [C++], メッセージ マップ"
ms.assetid: 2e863d23-9e58-45ba-b5e4-a8ceefccd0c8
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# メッセージ マップ クロス リファレンスの使い方
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

memberFxn というエントリ \<で\>は [CWnd](../Topic/CWnd%20Class.md) の派生クラスでは、独自のメンバー関数を記述します。  関数には任意の名前を付けることができます。  その他の関数、たとえば `OnActivate` などは、`CWnd` クラスのメンバー関数です。  呼び出されると Windows の `DefWindowProc` 関数にメッセージを渡します。  Windows の通知メッセージを処理する場合は、派生クラスで該当する `CWnd` のメンバー関数をオーバーライドします。  独自に作成する関数では、基本クラスや Windows がメッセージに応答できるように、オーバーライドされた基本クラスの関数を呼び出す必要があります。  
  
 どのような場合でも、`CWnd` 派生クラスのヘッダーに関数のプロトタイプを記述し、さらにメッセージ マップのエントリをコーディングする必要があります。  
  
 リファレンスでは、次に示す用語を使っています。  
  
|語句|定義|  
|--------|--------|  
|id|ユーザー定義のメニュー項目 ID \(**WM\_COMMAND** メッセージ\) またはコントロール ID \(子ウィンドウからの通知メッセージ\)。|  
|"message" および "wNotifyCode"|WINDOWS.H に定義された Windows のメッセージ ID。|  
|nMessageVariable|Windows の **RegisterWindowMessage** 関数の戻り値を持つ変数の名前。|  
  
## 参照  
 [メッセージ マップ](../../mfc/reference/message-maps-mfc.md)