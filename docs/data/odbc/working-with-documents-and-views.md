---
title: ドキュメントとビューの操作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], documents
- MFC [C++], views
- views [C++], MFC
- documents [C++], MFC
ms.assetid: 349b142d-1c5a-4b99-9de4-241e41d3d2f1
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5558e106ead5b56e982c6280fecc8a8418b3ebc6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="working-with-documents-and-views"></a>ドキュメントとビューの使用
Microsoft Foundation Classes (MFC) ライブラリは、その機能の多くのドキュメント/ビュー アーキテクチャに依存します。 通常、ドキュメントは、データを格納し、ビュー、フレーム ウィンドウのクライアント領域内に表示してユーザーと対話データ。 ビューは、ドキュメントを取得し、データの更新と通信します。 フレームワークの有無には、データベース クラスを使用することができます。  
  
 データベース クラスをフレームワークに使用する方法の詳細については、次を参照してください。 [MFC: ドキュメントとビューを用いたデータベース クラス](../../data/mfc-using-database-classes-with-documents-and-views.md)です。  
  
 既定では、MFC アプリケーション ウィザードはデータベースのサポートなしで、スケルトン アプリケーションを作成します。 ただし、最小限のデータベースのサポートやより詳細なフォーム ベースのサポートを含めるオプションを選択できます。 アプリケーション ウィザードのオプションの詳細については、次を参照してください。[データベースのサポート、MFC アプリケーション ウィザード](../../mfc/reference/database-support-mfc-application-wizard.md)です。  
  
 完全ドキュメント/ビュー アーキテクチャを使用せず、またデータベース クラスを使用することができます。 詳細については、次を参照してください。 [MFC: 用いないデータベース クラスとビュー](../../data/mfc-using-database-classes-without-documents-and-views.md)です。  
  
## <a name="see-also"></a>参照  
 [ODBC と MFC](../../data/odbc/odbc-and-mfc.md)