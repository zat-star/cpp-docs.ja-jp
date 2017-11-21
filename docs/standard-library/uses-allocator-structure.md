---
title: "uses_allocator 構造体 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: future/std::uses_allocator
dev_langs: C++
ms.assetid: c418f002-62e9-4806-b70c-41c663cae583
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 623cc9cfbc99a6cf617974f6401bb45d6f5f34f0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="usesallocator-structure"></a>uses_allocator 構造体
常に true を保持する特殊化です。  
  
## <a name="syntax"></a>構文  
  
```
template <class Ty, class Alloc>
struct uses_allocator<promise<Ty>, Alloc> : true_type;
template <class Ty, class Alloc>
struct uses_allocator<packaged_task<Ty>, Alloc> : true_type;
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<将来 >  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<future>](../standard-library/future.md)



