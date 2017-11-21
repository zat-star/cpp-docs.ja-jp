---
title: "steady_clock 構造体 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: chrono/std::chrono::steady_clock
dev_langs: C++
ms.assetid: 970d12ec-fc80-4391-a2f7-b57b2aec668d
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4fa9b54e4fb65fe9e3309b06c87dc713df92ec16
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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
  
|名前|説明|  
|----------|-----------------|  
|`system_clock::is_steady`|`true` を保持します。 `steady_clock` は*安定*しています。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<chrono >  
  
 **名前空間:** std::chrono  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono>](../standard-library/chrono.md)   
 [system_clock 構造体](../standard-library/system-clock-structure.md)
