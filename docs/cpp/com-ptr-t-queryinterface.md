---
title: "_com_ptr_t::QueryInterface |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::QueryInterface
- _com_ptr_t.QueryInterface
dev_langs: C++
helpviewer_keywords: QueryInterface method [C++]
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1dd546da4730bfd2995b4d97be8017807d2ae161
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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