---
title: "コレクションと列挙子インターフェイス (ATL) の設計 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- enumerator interfaces
- collection interfaces
ms.assetid: ea19a39e-6333-41a1-be62-5435c236640e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 40aa94226b93a42b14dfd23a64e12fff00e22729
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="design-principles-for-collection-and-enumerator-interfaces"></a>コレクションと列挙子インターフェイスのデザインの原則
インターフェイスの種類ごとの背後にあるさまざまなデザインの原則があります。  
  
-   コレクション インターフェイスは提供*ランダム*へのアクセス、*単一*を使用してコレクション内の項目、**項目**メソッド、クライアントがコレクション内の項目の数を検出できます使用して、**カウント**プロパティ、でき、多くの場合、クライアントを追加し、項目を削除します。  
  
-   列挙子インターフェイス*シリアル*へのアクセスを*複数*コレクション内の項目を検出 (列挙子が返すことを停止するまで、コレクション内に項目の数は、クライアントを許可しません。アイテム)、追加または削除の方法を提供しません。  
  
 インターフェイスの各型は、コレクション内の要素へのアクセスを提供するさまざまな役割を果たします。  
  
## <a name="see-also"></a>関連項目  
 [コレクションと列挙子](../atl/atl-collections-and-enumerators.md)

