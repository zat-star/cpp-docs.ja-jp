---
title: "_bstr_t::GetAddress |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _bstr_t::GetAddress
dev_langs: C++
helpviewer_keywords: GetAddress method [C++]
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c1b2b348277f7d33a32c8d0e6ad1fc80d51ec68d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="bstrtgetaddress"></a>_bstr_t::GetAddress
**Microsoft 固有の仕様**  
  
 既存の文字列を解放し、新しく割り当てられた文字列のアドレスを返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
BSTR* GetAddress( );  
  
```  
  
## <a name="return-value"></a>戻り値  
 `BSTR` でラップされた `_bstr_t` へのポインター。  
  
## <a name="remarks"></a>コメント  
 `GetAddress` は、`_bstr_t` を共有するすべての `BSTR` オブジェクトに影響します。 複数の `_bstr_t` がコピー コンストラクターおよび `BSTR` を使用して `operator=` を共有できます。  
  
## <a name="example"></a>例  
 参照してください[_bstr_t::assign](../cpp/bstr-t-assign.md)使用例については`GetAddress`します。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [_bstr_t クラス](../cpp/bstr-t-class.md)