---
title: "lastprivate |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: lastprivate
dev_langs: C++
helpviewer_keywords: lastprivate OpenMP clause
ms.assetid: 6ef87b31-375a-47e8-8d0d-281be45fb56a
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9429a54a21d58be7f2dd1667478ae653da5a8c35
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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
 `lastprivate`次のディレクティブに適用されます。  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [セクション](../../../parallel/openmp/reference/sections-openmp.md)  
  
 詳細については、次を参照してください。 [2.7.2.3 lastprivate](../../../parallel/openmp/2-7-2-3-lastprivate.md)です。  
  
## <a name="example"></a>例  
 参照してください[スケジュール](../../../parallel/openmp/reference/schedule.md)の使用例については`lastprivate`句。  
  
## <a name="see-also"></a>関連項目  
 [句](../../../parallel/openmp/reference/openmp-clauses.md)