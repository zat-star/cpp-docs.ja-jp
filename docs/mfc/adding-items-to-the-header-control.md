---
title: "ヘッダー コントロールに項目を追加する |Microsoft ドキュメント"
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
- controls [MFC], header
- CHeaderCtrl class [MFC], adding items
- header controls [MFC], adding items to
ms.assetid: 2e9a28b1-7302-4a93-8037-c5a4183e589a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4de62d534da103f17df113b04b88021561739cfc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="adding-items-to-the-header-control"></a>ヘッダー コントロールへの項目の追加
ヘッダー コントロールを作成した後 ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md))、その親ウィンドウで項目数だけ追加"ヘッダー"ようにする必要があります: 通常は 1 列あたり 1 台。  
  
### <a name="to-add-a-header-item"></a>ヘッダー項目を追加するには  
  
1.  準備、 [HD_ITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247)構造体。  
  
2.  呼び出す[として](../mfc/reference/cheaderctrl-class.md#insertitem)、構造体を渡します。  
  
3.  追加の項目を手順 1. と 2. を繰り返します。  
  
 詳細については、次を参照してください。[アイテムをヘッダー コントロールに追加する](http://msdn.microsoft.com/library/windows/desktop/bb775238)Windows SDK に含まれています。  
  
## <a name="see-also"></a>参照  
 [CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

