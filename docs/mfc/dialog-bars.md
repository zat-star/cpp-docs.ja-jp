---
title: "ダイアログ バー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC, control bars
- CDialogBar class [MFC], dialog bars
- control bars [MFC], dialog bars
- dialog bars
- dialog bars [MFC], about dialog bars
ms.assetid: 485c8055-6bb0-4051-8417-dd2971499321
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3d9d7319f23741f683e31cfd683a8ebd6d25acdd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="dialog-bars"></a>ダイアログ バー
ダイアログ バーとは、ツールバー、一種の[コントロール バー](../mfc/control-bars.md)あらゆる種類のコントロールを含めることができます。 モードレス ダイアログ ボックスの特性があるため、 [CDialogBar](../mfc/reference/cdialogbar-class.md)オブジェクトより強力なツールバーを使用します。  
  
 ツールバーのいくつかの主な違いがあると`CDialogBar`オブジェクト。 A `CDialogBar` Visual C ダイアログ エディターを使用して作成およびあらゆる種類の Windows コントロールを含めることができるダイアログ テンプレート リソースからオブジェクトを作成します。 ユーザーは、コントロールにコントロールからタブことができます。 親フレーム ウィンドウの任意の部分を持つダイアログ バーを整列するかものままにする場所で親のサイズが変更された場合、配置スタイルを指定できます。 次の図は、さまざまなコントロールのダイアログ バーを示します。  
  
 ![VC ダイアログ バー](../mfc/media/vc378t1.gif "vc378t1")  
ダイアログ バー  
  
 操作、他の点で、`CDialogBar`オブジェクトはモードレス ダイアログ ボックスの使用と同様です。 ダイアログ エディターを使用して、設計と、ダイアログ リソースを作成します。  
  
 ダイアログ バーの長所の 1 つは、ボタン以外のコントロールを格納できることです。  
  
 独自のダイアログ クラスを派生する通常は`CDialog`、ダイアログ バーの独自のクラスを通常は派生しません。 ダイアログ バーなどの拡張メイン ウィンドウおよびダイアログ バー コントロール通知メッセージは**BN_CLICKED**または**EN_CHANGE**、横棒グラフ、メイン ウィンドウ、ダイアログ ボックスの親に送信されます。  
  
## <a name="see-also"></a>参照  
 [ユーザー インターフェイス要素](../mfc/user-interface-elements-mfc.md)   
 [サンプル](../visual-cpp-samples.md)

