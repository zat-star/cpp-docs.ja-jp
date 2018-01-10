---
title: alignment_of Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::alignment_of
dev_langs: C++
helpviewer_keywords:
- alignment_of class
- alignment_of
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: de94e34dd0e00a2902454b4ab41f1790c194b6dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="alignmentof-class"></a>alignment_of クラス
指定された型のアラインメントを取得します。 この構造体は、[alignof](../cpp/alignof-and-alignas-cpp.md) の観点から実装されています。 単にアラインメント値を照会すればよい場合は、`alignof` を直接使用します。 タグ ディスパッチを行うときのように整数定数が必要な場合は、alignment_of を使用します。  
  
## <a name="syntax"></a>構文  
  
```
template <class Ty>
struct alignment_of;
```  
  
#### <a name="parameters"></a>パラメーター  
 `Ty`  
 照会する型。  
  
## <a name="remarks"></a>コメント  
 型クエリは、型 `Ty` のアラインメントの値を保持します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [<type_traits>](../standard-library/type-traits.md)   
 [aligned_storage クラス](../standard-library/aligned-storage-class.md)
