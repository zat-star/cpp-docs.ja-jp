---
title: "リッチ エディット コントロールでの操作をストリーム配信 |Microsoft ドキュメント"
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
- CRichEditCtrl class [MFC], stream operations
- CRichEditCtrl class [MFC], stream storage
- rich edit controls [MFC], stream operations
- storage, stream in CRichEditCtrl
- stream operations in CRichEditCtrl
- stream storage and CRichEditCtrl
ms.assetid: 110b4684-1e76-4ca6-9ef0-5bc8b2d93c78
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c1a73790124adbc1ff8a89290bf4e1d7a4fa6824
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="stream-operations-in-rich-edit-controls"></a>リッチ エディット コントロールでのストリーム操作
リッチ エディット コントロールの内外にデータを転送するストリームを使用することができます ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md))。 ストリームがによって定義された、 [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891)構造体は、バッファーと、アプリケーション定義のコールバック関数を指定します。  
  
 データをリッチ エディット コントロールを読み取れません (つまり、内のデータ ストリーム) を使用して、 [StreamIn](../mfc/reference/cricheditctrl-class.md#streamin)メンバー関数。 コントロールでは、バッファーにデータの一部を転送するたびに、アプリケーション定義のコールバック関数を繰り返し呼び出します。  
  
 保存するには、リッチ エディット コントロールの内容 (つまり、データをストリーム アウト)、使用することができます、 [StreamOut](../mfc/reference/cricheditctrl-class.md#streamout)メンバー関数。 コントロールは、繰り返し、バッファーに書き込みます、アプリケーション定義のコールバック関数を呼び出します。 各呼び出しは、コールバック関数は、バッファーの内容を保存します。  
  
## <a name="see-also"></a>参照  
 [CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

