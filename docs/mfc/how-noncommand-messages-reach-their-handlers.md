---
title: "非コマンドのメッセージのハンドラー検索方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- messages [MFC], routing
- noncommand messages
- Windows messages [MFC], routing
- message handling [MFC], noncommand messages
ms.assetid: e7df8aef-9fae-41f4-9c11-881d8465f602
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 33d0d65c9916cfc571ecfd623138938c0c883ba5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="how-noncommand-messages-reach-their-handlers"></a>コマンド以外のメッセージのハンドラー検索方法
コマンドとは異なり標準 Windows メッセージは、チェーン コマンド ターゲットを通じてルーティングされませんが、Windows メッセージを送信する先ウィンドウによって処理される通常。 ウィンドウには、メイン フレーム ウィンドウ、MDI 子ウィンドウ、標準のコントロール、ダイアログ ボックス、ビュー、またはその他の何らかの子ウィンドウがあります。  
  
 実行時に、Windows の各ウィンドウがウィンドウのオブジェクトにアタッチ (から直接または間接的に派生`CWnd`) を持つ独自の関連するメッセージ マップおよびハンドラー関数。 フレームワークは、メッセージ マップを使用: コマンドです: 受信メッセージをハンドラーにマップします。  
  
## <a name="see-also"></a>参照  
 [フレームワークがハンドラーを呼び出す方法](../mfc/how-the-framework-calls-a-handler.md)

