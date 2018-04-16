---
title: "TN032: MFC 例外処理機構 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.exceptions
dev_langs:
- C++
helpviewer_keywords:
- TN032
- MFC, exceptions
- CException class [MFC], using
ms.assetid: 0271f0aa-82cb-47a2-b7ea-e88126fc7e43
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bf82d4b158cedd2d8f6916dfb01d26db6c62d83b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="tn032-mfc-exception-mechanism"></a>テクニカル ノート 32: MFC 例外処理機構
Visual C の以前のバージョンが、標準の C++ 例外機構をサポートしていませんし、MFC に提供されるマクロ**TRY または CATCH/THROW**代わりに使用していた。 このバージョンの Visual C には、C++ の例外を完全にサポートしています。 このノートでは、従来のマクロの高度な実装の詳細の一部について説明スタック ベースのオブジェクトを自動的にクリーンアップする方法などです。 C++ 例外のスタック アンワインド既定ではサポートされているために、このテクニカル ノートは必要ではありません。  
  
 参照してください[例外: MFC マクロと C++ 例外](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)MFC マクロと C++ のキーワードの違いについての詳細。  
  
## <a name="see-also"></a>参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

