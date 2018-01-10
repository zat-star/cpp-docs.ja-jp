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
ms.workload: cplusplus
ms.openlocfilehash: 6a95193d5ca3df890c9c97f458b76413e588bc59
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cleaning-up-documents-and-views"></a>ドキュメントとビューの後処理
ドキュメントを閉じるときに、まずフレームワークその[DeleteContents](../mfc/reference/cdocument-class.md#deletecontents)メンバー関数。 ドキュメントの操作の実行中にヒープにメモリを割り当てた場合`DeleteContents`割り当てを解除することをお勧めします。  
  
> [!NOTE]
>  ドキュメントのデストラクターでドキュメントのデータの割り当てを解除する必要がありますされません。 SDI アプリケーションの場合は、ドキュメント オブジェクトを再利用する可能性があります。  
  
 ヒープに割り当てられたメモリの割り当てを解除するビューのデストラクターを上書きすることができます。  
  
## <a name="see-also"></a>参照  
 [ドキュメントとビューの初期化と後処理](../mfc/initializing-and-cleaning-up-documents-and-views.md)

