---
title: "コマンド ルーティング クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.command"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コマンド ルーティング, クラス"
  - "MFC, コマンド ルーティング"
ms.assetid: 4b50e689-2c54-4e6c-90f0-37333e22b2a1
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# コマンド ルーティング クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ユーザーがアプリケーションをマウスでメニューまたはコントロールバー ボタンをクリックしてやり取りされると、影響を受けるユーザー インターフェイス オブジェクトから適切なコマンドターゲット アプリケーションへの送信メッセージを指定します。  `CCmdTarget` からコマンドターゲット クラスの派生が [CWinApp](../mfc/reference/cwinapp-class.md)、[CWnd](../Topic/CWnd%20Class.md)、[CDocTemplate](../mfc/reference/cdoctemplate-class.md)、[CDocument](../Topic/CDocument%20Class.md)、[CView](../Topic/CView%20Class.md)とから派生されるクラスが含まれています。  フレームワークは、コマンドがアプリケーションで現在アクティブなほとんどの適切なオブジェクトで処理することができるように、自動コマンド ルーティングをサポートします。  
  
 クラス `CCmdUI` オブジェクトをコマンドの対象の更新コマンド UI \([ON\_UPDATE\_COMMAND\_UI](../Topic/ON_UPDATE_COMMAND_UI.md)\) ハンドラーに固有のコマンドのユーザー インターフェイス \(UI\) 状態を更新するために渡されます \(たとえば、チェックを削除するメニュー項目のチェックや\)。  UI のオブジェクトの状態を更新するに `CCmdUI` オブジェクトのメンバー関数を呼び出します。  このプロセスは、特定のコマンドに関連付けられた UI オブジェクトがメニュー項目やボタンまたはその両方かに同じです。  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
 メッセージの受け取り、応答できるオブジェクトのすべてのクラスの基本クラスとして機能します。  
  
 [CCmdUI](../Topic/CCmdUI%20Class.md)  
 メニュー項目やコントロールバー ボタンなどのユーザー インターフェイス オブジェクトを更新するようにプログラミング インターフェイスを提供します。  コマンドの対象のオブジェクトは、無効化、チェック、またはクリアこのオブジェクトを使用してユーザー インターフェイス オブジェクト有効になります。  
  
## 参照  
 [クラスの概要](../mfc/class-library-overview.md)