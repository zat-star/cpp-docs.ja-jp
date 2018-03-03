---
title: "レコード ビュー (MFC データ アクセス) を使用して |Microsoft ドキュメント"
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
- record views, customizing default code
ms.assetid: 91f2828f-0666-4273-ae28-e4703fd98521
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 18d3b4b36d63013fcb5e3762f96e5970644cbff0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="using-a-record-view--mfc-data-access"></a>レコード ビューの使用法 (MFC データ アクセス)
このトピックでは、ウィザードで生成したレコード ビュー用の既定のコードをカスタマイズする一般的な方法について説明します。 一般に、必要な制約によるレコードの選択、[フィルター](../data/odbc/recordset-filtering-records-odbc.md)または[パラメーター](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)、おそらく[並べ替え](../data/odbc/recordset-sorting-records-odbc.md)レコード、SQL ステートメントのカスタマイズします。  
  
 使用して`CRecordView`が使用する場合とほぼ同じ[CFormView](../mfc/reference/cformview-class.md)です。 基本的には、レコード ビューを使用して、1 つのレコードセットのレコードを表示し、場合によっては更新します。 さらに、できるだけでなくで説明した他のレコード セットを使用する可能性があります[レコード ビュー: セカンド レコード セットからリスト ボックス](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md)です。  
  
## <a name="see-also"></a>参照  
 [レコード ビュー (MFC データ アクセス)](../data/record-views-mfc-data-access.md)   
 [ODBC ドライバーの一覧](../data/odbc/odbc-driver-list.md)