---
title: "OMP_DYNAMIC |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: OMP_DYNAMIC
dev_langs: C++
helpviewer_keywords: OMP_DYNAMIC OpenMP environment variable
ms.assetid: e306049d-b644-4b73-8b63-46c835bff98b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 900f3e4ddd0e9901e72ed65f12bc036d87a6956e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ompdynamic"></a>OMP_DYNAMIC
OpenMP ランタイムが、並行領域内のスレッドの数を調整できるかどうかを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
set OMP_DYNAMIC[=TRUE | =FALSE]  
```  
  
## <a name="remarks"></a>コメント  
 `OMP_DYNAMIC`で環境変数をオーバーライドすることができます、 [omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md)関数。  
  
 OpenMP の標準の Visual C 実装では既定値は`OMP_DYNAMIC=FALSE`します。  
  
 詳細については、次を参照してください。 [4.3 OMP_DYNAMIC](../../../parallel/openmp/4-3-omp-dynamic.md)です。  
  
## <a name="example"></a>例  
 次のコマンド セット、`OMP_DYNAMIC`環境変数を TRUE にします。  
  
```  
set OMP_DYNAMIC=TRUE  
```  
  
 次のコマンドの現在の設定を表示する、`OMP_DYNAMIC`環境変数。  
  
```  
set OMP_DYNAMIC  
```  
  
## <a name="see-also"></a>参照  
 [環境変数](../../../parallel/openmp/reference/openmp-environment-variables.md)