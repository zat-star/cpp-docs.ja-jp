---
title: "リッチ エディット コントロールでのワード区切り |Microsoft ドキュメント"
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
- CRichEditCtrl class [MFC], word breaks in
- word breaks
- breaking words in CRichEditCtrl
- rich edit controls [MFC], word breaks in
ms.assetid: 641dcf9e-7b40-4dc0-85f7-575a8c142f73
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 12ae5d682515a6f266b7e41a2ff89148ea98c0b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="word-breaks-in-rich-edit-controls"></a>リッチ エディット コントロールでのワード区切り
リッチ エディット コントロール ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) という「単語区切りプロシージャ」関数を呼び出します単語の区切り記号を検索し、行を壊すことを決定します。 コントロールは、テキストの折り返しの操作を実行して、ctrl キーを押しながら左および ctrl キーを押しながら右キーの組み合わせを処理するときに、この情報を使用します。 アプリケーションでは、メッセージ、リッチ エディット コントロールが既定単語区切りプロシージャ、単語区切りの情報を取得し、指定された文字がある行を決定するに当たるを送信できます。  
  
## <a name="see-also"></a>参照  
 [CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

