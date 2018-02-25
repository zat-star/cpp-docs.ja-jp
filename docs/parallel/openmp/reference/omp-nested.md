---
title: OMP_NESTED | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- OMP_NESTED
dev_langs:
- C++
helpviewer_keywords:
- OMP_NESTED OpenMP environment variable
ms.assetid: c43f5287-a548-40d0-bd54-0c6b2b9f9a53
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 363a125cb7f9858b1ef4105234344d2a8d35b707
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="ompnested"></a>OMP_NESTED
入れ子になった並列処理が有効かどう、入れ子になった並列処理が有効か無効にしない限り、指定`omp_set_nested`です。  
  
## <a name="syntax"></a>構文  
  
```  
set OMP_NESTED[=TRUE | =FALSE]  
```  
  
## <a name="remarks"></a>コメント  
 `OMP_NESTED`で環境変数をオーバーライドすることができます、 [omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md)関数。  
  
 OpenMP の標準の Visual C 実装では既定値は`OMP_DYNAMIC=FALSE`します。  
  
 詳細については、次を参照してください。 [4.4 OMP_NESTED](../../../parallel/openmp/4-4-omp-nested.md)です。  
  
## <a name="example"></a>例  
 次のコマンド セット、`OMP_NESTED`環境変数を TRUE にします。  
  
```  
set OMP_NESTED=TRUE  
```  
  
 次のコマンドの現在の設定を表示する、`OMP_NESTED`環境変数。  
  
```  
set OMP_NESTED  
```  
  
## <a name="see-also"></a>参照  
 [環境変数](../../../parallel/openmp/reference/openmp-environment-variables.md)