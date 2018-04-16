---
title: "lastprivate |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- lastprivate
dev_langs:
- C++
helpviewer_keywords:
- lastprivate OpenMP clause
ms.assetid: 6ef87b31-375a-47e8-8d0d-281be45fb56a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7945edb879d81bb50753619c1206b9da575dbcda
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="lastprivate"></a>lastprivate
いる変数の外側のコンテキストのバージョンを設定して、最後の反復処理 (for ループ コンストラクト) または最後のセクション (#pragma セクション) を実行したスレッドのプライベート バージョンを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
lastprivate(var)  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `var`  
 どのスレッドのプライベート バージョンと同じに設定されている変数は、最後の反復処理 (for ループ コンストラクト) または最後のセクション (#pragma セクション) を実行します。  
  
## <a name="remarks"></a>コメント  
 `lastprivate` 次のディレクティブに適用されます。  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 詳細については、次を参照してください。 [2.7.2.3 lastprivate](../../../parallel/openmp/2-7-2-3-lastprivate.md)です。  
  
## <a name="example"></a>例  
 参照してください[スケジュール](../../../parallel/openmp/reference/schedule.md)の使用例については`lastprivate`句。  
  
## <a name="see-also"></a>参照  
 [句](../../../parallel/openmp/reference/openmp-clauses.md)