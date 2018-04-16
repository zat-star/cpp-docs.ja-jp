---
title: "Cstring の |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- semantics in Cstring
- CString objects, assignment semantics
- assignment statements, assigning CString objects
ms.assetid: d4023480-526f-499a-85f6-324b4de5b85f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 394e459a46003e3f1baccff7dd4c76f40b73e354
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cstring-semantics"></a>CString の評価
にもかかわらず[CString](../atl-mfc-shared/reference/cstringt-class.md)オブジェクトを拡張できる動的オブジェクトは、組み込みのプリミティブ型と単純なクラスのように動作します。 各`CString`オブジェクトを一意の値を表します。 `CString`オブジェクトは、文字列へのポインターではなく実際の文字列としての考える必要があります。  
  
 1 つを割り当てることができます**CString**を別のオブジェクト。 ただし、変更する場合、2 つのいずれかの`CString`オブジェクト、他の`CString`オブジェクトは変更されません、次の例に示すようにします。  
  
 [!code-cpp[NVC_ATLMFC_Utilities#188](../atl-mfc-shared/codesnippet/cpp/cstring-semantics_1.cpp)]  
  
 注の例を 2 つ`CString`オブジェクトが等しいと見なされる""同じ文字の文字列を表すためです。 `CString`クラスは、等値演算子をオーバー ロード (`==`) 2 つを比較する`CString`オブジェクト自身の id (アドレス) ではなく、値 (内容) をベースにします。  
  
## <a name="see-also"></a>参照  
 [文字列 (ATL と MFC)](../atl-mfc-shared/strings-atl-mfc.md)

