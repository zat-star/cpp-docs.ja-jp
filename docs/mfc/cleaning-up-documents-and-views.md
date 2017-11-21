---
title: "ドキュメントとビューをクリーンアップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f9bb1cbcb58e2693b33693b390a09d3826c77cfd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="cleaning-up-documents-and-views"></a>ドキュメントとビューの後処理
ドキュメントを閉じるときに、まずフレームワークその[DeleteContents](../mfc/reference/cdocument-class.md#deletecontents)メンバー関数。 ドキュメントの操作の実行中にヒープにメモリを割り当てた場合`DeleteContents`割り当てを解除することをお勧めします。  
  
> [!NOTE]
>  ドキュメントのデストラクターでドキュメントのデータの割り当てを解除する必要がありますされません。 SDI アプリケーションの場合は、ドキュメント オブジェクトを再利用する可能性があります。  
  
 ヒープに割り当てられたメモリの割り当てを解除するビューのデストラクターを上書きすることができます。  
  
## <a name="see-also"></a>関連項目  
 [ドキュメントとビューの初期化と後処理](../mfc/initializing-and-cleaning-up-documents-and-views.md)

