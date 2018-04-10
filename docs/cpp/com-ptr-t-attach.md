---
title: _com_ptr_t::Attach |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::Attach
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, attach pointer
- Attach method [C++]
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d8b9eac88c9387c6aeedd140159bb24482c829dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="comptrtattach"></a>_com_ptr_t::Attach
**Microsoft 固有の仕様**  
  
 このスマート ポインターの型の生のインターフェイス ポインターをカプセル化します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      void Attach(  
   Interface* pInterface   
) throw( );  
void Attach(  
   Interface* pInterface,  
   bool fAddRef   
) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pInterface`  
 生のインターフェイス ポインター。  
  
 `fAddRef`  
 場合は**true**、し`AddRef`と呼びます。 場合は**false**、`_com_ptr_t`オブジェクトは、所有権を呼び出さずに生のインターフェイス ポインターの`AddRef`します。  
  
## <a name="remarks"></a>コメント  
  
-   **アタッチ (**`pInterface`**)** `AddRef`は呼び出されません。 インターフェイスの所有権は、この `_com_ptr_t` オブジェクトに渡されます。 **リリース**は以前にカプセル化されたポインターの参照カウントをデクリメントするために呼び出されます。  
  
-   **アタッチ (** `pInterface` **、**`fAddRef`**)**場合`fAddRef`は**true**、`AddRef`参照をインクリメントするために呼び出されるカプセル化されたインターフェイス ポインターの数。 場合`fAddRef`は**false**、この`_com_ptr_t`オブジェクトは、所有権を呼び出さずに生のインターフェイス ポインターの`AddRef`します。 **リリース**は以前にカプセル化されたポインターの参照カウントをデクリメントするために呼び出されます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [_com_ptr_t クラス](../cpp/com-ptr-t-class.md)