---
title: "common_type 構造体 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- chrono/std::common_type
dev_langs:
- C++
ms.assetid: 2b42722c-c3dc-4d62-8613-0271e52b6f00
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e4bf10d771dbf65c4f86d1dabb90e327de0a6ffb
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="commontype-structure"></a>common_type 構造体
[duration](../standard-library/common-type-class.md) および [time_point](../standard-library/duration-class.md) のインスタンス化のテンプレート クラス [common_type](../standard-library/time-point-class.md) を記述します。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Rep1, class Period1,  
    class Rep2, class Period2>  
struct common_type  
<chrono::duration<Rep1, Period1>,   
chrono::duration<Rep2, Period2>>;  
 
template <class Clock,  
    class Duration1, class Duration2>  
struct common_type  
<chrono::time_point<Clock, Duration1>,  
chrono::time_point<Clock, Duration2>>;  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<chrono >  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono>](../standard-library/chrono.md)

