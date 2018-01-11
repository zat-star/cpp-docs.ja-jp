---
title: "make_signed クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::make_signed
dev_langs: C++
helpviewer_keywords:
- make_signed class
- make_signed
ms.assetid: 686247c0-247c-496b-9b1b-ba9dcd633621
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f9b811f585370a19be47b0140adf74495b6d9019
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="makesigned-class"></a>make_signed クラス
サイズが型以上の型または最小の符号付きの型を作成します。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>
struct make_signed;

template <class T>
using make_signed_t = typename make_signed<T>::type;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 変更する型。  
  
## <a name="remarks"></a>コメント  
 この型修飾子のインスタンスは、`is_signed<T>` が true を保持している場合に `T` になる修飾型を保持します。 それ以外の場合は、`sizeof (T) <= sizeof (UT)` である最小の符号なしの型 `UT` になります。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [<type_traits>](../standard-library/type-traits.md)



