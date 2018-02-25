---
title: OMP_SCHEDULE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- OMP_SCHEDULE
dev_langs:
- C++
helpviewer_keywords:
- OMP_SCHEDULE OpenMP environment variable
ms.assetid: 2295a801-e584-4d2f-826f-7ca4c88846a6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ff09bf142fd1c8bbbd61d1e1d3bd76102f7d86b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="ompschedule"></a>OMP_SCHEDULE
動作を変更して、[スケジュール](../../../parallel/openmp/reference/schedule.md)句と`schedule(runtime)`で指定された、`for`または`parallel for`ディレクティブです。  
  
## <a name="syntax"></a>構文  
  
```  
set OMP_SCHEDULE[=type[,size]]  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `size` (省略可能)  
 イテレーションのサイズを指定します。 `size` 正の整数を指定する必要があります。 既定値は 1 の場合を除き、`type`は静的です。 有効でない場合に`type`は`runtime`します。  
  
 `type`  
 スケジュールの種類。  
  
-   `dynamic`  
  
-   `guided`  
  
-   `runtime`  
  
-   `static`  
  
## <a name="remarks"></a>コメント  
 OpenMP の標準の Visual C 実装では既定値は`OMP_SCHEDULE=static,0`します。  
  
 詳細については、次を参照してください。 [4.1 OMP_SCHEDULE](../../../parallel/openmp/4-1-omp-schedule.md)です。  
  
## <a name="example"></a>例  
 次のコマンド セット、 **OMP_SCHEDULE**環境変数。  
  
```  
set OMP_SCHEDULE="guided,2"  
```  
  
 次のコマンドの現在の設定を表示する、 **OMP_SCHEDULE**環境変数。  
  
```  
set OMP_SCHEDULE  
```  
  
## <a name="see-also"></a>参照  
 [環境変数](../../../parallel/openmp/reference/openmp-environment-variables.md)