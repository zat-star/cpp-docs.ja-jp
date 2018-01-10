---
title: "once_flag 構造体 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: mutex/std::once_flag
dev_langs: C++
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fc66f322490bc728ab6d25e185f6b8d4ce0f0179
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="onceflag-structure"></a>once_flag 構造体
テンプレート関数 [call_once](../standard-library/mutex-functions.md#call_once) で使用する `struct` を表し、実行する複数スレッドがある場合でも、初期化コードが 1 回だけ呼び出されるようにします。  
  
## <a name="syntax"></a>構文  
  
struct once_flag { constexpr once_flag() noexcept; once_flag(const once_flag&); once_flag& operator=(const once_flag&); };  
  
## <a name="remarks"></a>コメント  
 `once_flag` `struct`既定のコンス トラクターのみです。  
  
 `once_flag` 型のオブジェクトは、作成することはできますがコピーはできません。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<ミュー テックス >  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)



