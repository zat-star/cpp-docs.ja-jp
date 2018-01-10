---
title: "データ オブジェクトとデータ ソース (OLE) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- data objects [MFC], definition
- data transfer [MFC]
- OLE [MFC], data transfer
- data sources [MFC], definition
- data transfer [MFC], definition
- OLE [MFC], data objects
- OLE [MFC], data sources
ms.assetid: 8f68eed8-0ce8-4489-a4cc-f95554f89090
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 04619ee7851d2e2d6ad569583dfbb2e619d37026
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="data-objects-and-data-sources-ole"></a>データ オブジェクトとデータ ソース (OLE)
データ転送では、クリップボードまたはドラッグ アンド ドロップを使用して、いずれかを実行すると、データには、ソースおよび変換先があります。 1 つのアプリケーションは、コピーするため、データを提供し、別のアプリケーションでは、それを受け入れ貼り付けられるようにします。 転送のそれぞれの側では、同じデータを正常に転送するために別の操作を実行する必要があります。 Microsoft Foundation Class (MFC) ライブラリには、この転送のそれぞれの側を表す 2 つのクラスが用意されています。  
  
-   データ ソース (によって実装される`COleDataSource`オブジェクト) データ転送のソース側を表します。 データは、クリップボードにコピーするとき、またはドラッグ アンド ドロップ操作のデータが提供される送信元アプリケーションによって作成されます。  
  
-   データ オブジェクト (によって実装される`COleDataObject`オブジェクト) データ転送のターゲット側を表します。 コピー先のアプリケーションがあるデータか、クリップボードから貼り付け操作を実行することが求められたときに削除されるときに作成されます。  
  
 次の記事では、データ オブジェクトと、アプリケーションでデータ ソースを使用する方法について説明します。 この情報は、どちらも呼び出すことができますにデータをコピーして貼り付けるために、コンテナーとサーバーの両方のアプリケーションに適用されます。  
  
-   [データ オブジェクトとデータ ソース: 作成と破棄](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [データ オブジェクトとデータ ソース: 操作](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## <a name="in-this-section"></a>このセクションの内容  
 [ドラッグ アンド ドロップ](../mfc/drag-and-drop-ole.md)  
  
 [クリップボード](../mfc/clipboard.md)  
  
## <a name="see-also"></a>参照  
 [OLE](../mfc/ole-in-mfc.md)   
 [COleDataObject クラス](../mfc/reference/coledataobject-class.md)   
 [COleDataSource クラス](../mfc/reference/coledatasource-class.md)
