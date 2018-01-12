---
title: "_variant_t::SetString |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _variant_t::SetString
dev_langs: C++
helpviewer_keywords: SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9c433aafbe9799486d141e04ca747cbb4f7c3e22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="varianttsetstring"></a>_variant_t::SetString
**Microsoft 固有の仕様**  
  
 この `_variant_t` オブジェクトに文字列を代入します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      void SetString(  
   const char* pSrc   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pSrc`  
 文字列へのポインター。  
  
## <a name="remarks"></a>コメント  
 ANSI 文字列を Unicode `BSTR` 文字列に変換し、この `_variant_t` オブジェクトに割り当てます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [_variant_t クラス](../cpp/variant-t-class.md)