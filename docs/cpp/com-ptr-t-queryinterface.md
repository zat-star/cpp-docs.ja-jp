---
title: _com_ptr_t::QueryInterface |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::QueryInterface
- _com_ptr_t.QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- QueryInterface method [C++]
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c046f1b1d14b7e7dbd44ca9f5f012e632efef6e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="comptrtqueryinterface"></a>_com_ptr_t::QueryInterface
**Microsoft 固有の仕様**  
  
 呼び出し、`QueryInterface`のメンバー関数**IUnknown**カプセル化されたインターフェイス ポインター。  
  
## <a name="syntax"></a>構文  
  
```  
  
      template<typename _InterfaceType> HRESULT QueryInterface (  
   const IID& iid,  
   _InterfaceType*& p   
) throw ( );  
template<typename _InterfaceType> HRESULT QueryInterface (  
   const IID& iid,  
   _InterfaceType** p  
) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `iid`  
 **IID**のインターフェイス ポインター。  
  
 `p`  
 生のインターフェイス ポインター。  
  
## <a name="remarks"></a>コメント  
 呼び出し**iunknown::queryinterface** 、指定したカプセル化されたインターフェイス ポインターで**IID**で結果として得られる生のインターフェイス ポインターを返します`p`です。 このルーチンは、成功または失敗を示すために、`HRESULT` を返します。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_ptr_t クラス](../cpp/com-ptr-t-class.md)