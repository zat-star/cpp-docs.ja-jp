---
title: "リッチ エディット コントロールでのワード区切り |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CRichEditCtrl class [MFC], word breaks in
- word breaks
- breaking words in CRichEditCtrl
- rich edit controls [MFC], word breaks in
ms.assetid: 641dcf9e-7b40-4dc0-85f7-575a8c142f73
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c438a6c3e1891a7ffa85445355d5b08a3f79f2a8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="word-breaks-in-rich-edit-controls"></a>リッチ エディット コントロールでのワード区切り
リッチ エディット コントロール ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) という「単語区切りプロシージャ」関数を呼び出します単語の区切り記号を検索し、行を壊すことを決定します。 コントロールは、テキストの折り返しの操作を実行して、ctrl キーを押しながら左および ctrl キーを押しながら右キーの組み合わせを処理するときに、この情報を使用します。 アプリケーションでは、メッセージ、リッチ エディット コントロールが既定単語区切りプロシージャ、単語区切りの情報を取得し、指定された文字がある行を決定するに当たるを送信できます。  
  
## <a name="see-also"></a>関連項目  
 [CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

