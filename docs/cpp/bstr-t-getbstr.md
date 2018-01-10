---
title: "_bstr_t::GetBSTR |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _bstr_t::GetBSTR
dev_langs: C++
helpviewer_keywords: GetBSTR method [C++]
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 00b2f7f487673c67aa7b681499462ea05a471b48
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="bstrtgetbstr"></a>_bstr_t::GetBSTR
**Microsoft 固有の仕様**  
  
 `BSTR` でラップされた `_bstr_t` の先頭を指します。  
  
## <a name="syntax"></a>構文  
  
```  
  
BSTR& GetBSTR( );  
  
```  
  
## <a name="return-value"></a>戻り値  
 `BSTR` でラップされた `_bstr_t` の先頭。  
  
## <a name="remarks"></a>コメント  
 `GetBSTR` は、`_bstr_t` を共有するすべての `BSTR` オブジェクトに影響します。 複数の `_bstr_t` がコピー コンストラクターおよび `BSTR` を使用して `operator=` を共有できます。  
  
## <a name="example"></a>例  
 参照してください[_bstr_t::assign](../cpp/bstr-t-assign.md)使用例については`GetBSTR`します。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [_bstr_t クラス](../cpp/bstr-t-class.md)