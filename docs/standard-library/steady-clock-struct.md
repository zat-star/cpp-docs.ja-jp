---
title: "steady_clock 構造体 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- chrono/std::chrono::steady_clock
dev_langs:
- C++
ms.assetid: 970d12ec-fc80-4391-a2f7-b57b2aec668d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2651b8d7bdb50997c7757f85687dcf425f6d7e2f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="steadyclock-struct"></a>steady_clock 構造体
`steady` クロックを表します。  
  
## <a name="syntax"></a>構文  
  
```  
struct steady_clock;  
```  
  
## <a name="remarks"></a>コメント  
 Windows では、steady_clock は QueryPerformanceCounter 関数をラップします。  
  
 `now()` の最初の呼び出しによって返される値が、常に `now()` の以降の呼び出しによって返される値以下である場合、クロックは*単調*になります。  
  
 *単調*であり、かつクロック ティックの間隔が一定のクロックは*安定*しています。  
  
 High_resolution_clock は、steady_clock の typdef です。  
  
## <a name="public-functions"></a>パブリック関数  
  
|関数|説明|  
|--------------|-----------------|  
|now|現在の時刻を time_point 値として返します。|  
  
## <a name="public-constants"></a>パブリック定数  
  
|name|説明|  
|----------|-----------------|  
|`system_clock::is_steady`|`true` を保持します。 `steady_clock` は*安定*しています。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<chrono >  
  
 **名前空間:** std::chrono  
  
## <a name="see-also"></a>参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono>](../standard-library/chrono.md)   
 [system_clock 構造体](../standard-library/system-clock-structure.md)
