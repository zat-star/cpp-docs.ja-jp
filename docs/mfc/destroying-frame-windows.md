---
title: "フレーム ウィンドウの破棄 | Microsoft Docs"
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
  - "PostNcDestroy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Default メソッド"
  - "破棄 (フレーム ウィンドウを)"
  - "DestroyWindow メソッド"
  - "ドキュメント フレーム ウィンドウ, 破棄"
  - "フレーム ウィンドウ [C++], 破棄"
  - "MFC [C++], フレーム ウィンドウ"
  - "OnClose メソッド"
  - "OnNcDestroy メソッド, およびフレーム ウィンドウ"
  - "PostNcDestroy メソッド"
  - "ウィンドウ [C++], 破棄"
ms.assetid: 5affca77-1999-4507-a2b2-9aa226611b4b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# フレーム ウィンドウの破棄
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC フレームワークは、フレームワーク ドキュメントとビューに関連付けられているウィンドウのウィンドウの破棄、または作成を管理します。  他のウィンドウを作成する場合、その破棄する必要があります。  
  
 フレームワークでは、ユーザーがフレーム ウィンドウを閉じるときには、ウィンドウの既定の [OnClose](../Topic/CWnd::OnClose.md) ハンドラーは [DestroyWindow](../Topic/CWnd::DestroyWindow.md)を呼び出します。  ウィンドウが破棄される Windows のクリーンアップを実行するときに呼び出されるをクリーンアップする最後のメンバー関数は、[OnNcDestroy](../Topic/CWnd::OnNcDestroy.md)の呼び出し [既定](../Topic/CWnd::Default.md) メンバー関数で最後に仮想メンバー関数 [PostNcDestroy](../Topic/CWnd::PostNcDestroy.md)を呼び出します。  `PostNcDestroy` の [CFrameWnd](../mfc/reference/cframewnd-class.md) の実装は C\+\+ のウィンドウ オブジェクトを削除します。  、フレーム ウィンドウの C\+\+ **delete** の演算子を使用する必要があります。  代わりに、`DestroyWindow` を使用してください。  
  
 メイン ウィンドウが閉じたとき、アプリケーションは終了します。  変更されたドキュメントが保存されていない場合、フレームワークはドキュメントにある保存された表示し、適切なドキュメントを必要に応じて保存されるようにするかどうかを確認するためのメッセージ ボックスを。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [ドキュメント フレーム ウィンドウの作成](../Topic/Creating%20Document%20Frame%20Windows.md)  
  
## 参照  
 [フレーム ウィンドウの使用](../Topic/Using%20Frame%20Windows.md)