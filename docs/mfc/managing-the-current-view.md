---
title: "現在のビューの管理 | Microsoft Docs"
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
  - "現在のビュー (フレーム ウィンドウ内の)"
  - "非アクティブ (ビューを)"
  - "フレーム ウィンドウ, 現在のビュー"
  - "OnActivateView メソッド"
  - "ビュー, アクティブ"
  - "ビュー, および OnActivateView メソッド"
  - "ビュー, 現在の"
  - "ビュー, 非アクティブ"
ms.assetid: 0a1cc22d-d646-4536-9ad2-3cb6d7092e4a
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 現在のビューの管理
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

フレーム ウィンドウの既定の実装の一部として、フレーム ウィンドウには、現在アクティブなビューを追跡します。  フレーム ウィンドウが複数のビューが含まれている場合、たとえば分割ウィンドウに、現在のビューが使用中の最新のビューです。  アクティブなビューが Windows または現在の入力フォーカスのアクティブ ウィンドウに依存しません。  
  
 アクティブなビューが変更されると、フレームワークは [OnActivateView](../Topic/CView::OnActivateView.md) のメンバー関数を呼び出すと、現在のビューに通知します。  ビューが `OnActivateView``bActivate` パラメーターを調べることによってアクティブまたは非アクティブになっているかを判断できます。  既定で、`OnActivateView` はアクティブ化の現在のビューにフォーカスを設定します。  ビューを非アクティブまたは再度アクティブにする特別な処理を実行するに `OnActivateView` をオーバーライドできます。  たとえば、アクティブでないビューを他のユーザーとアクティブなビューを区別するための特殊なビジュアル キューを提供する場合があります。  
  
 フレーム ウィンドウが現在の \(アクティブ\) ビューに標準コマンド ルーティングの一部として、[Command Routing](../mfc/command-routing.md)"に説明されているように、順方向に表示します。  
  
## 参照  
 [フレーム ウィンドウの使用](../Topic/Using%20Frame%20Windows.md)