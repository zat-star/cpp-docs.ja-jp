---
title: _com_ptr_t::Attach |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::Attach
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, attach pointer
- Attach method [C++]
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7341695ad0cbc8384da859b80a72a63d8d52215f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
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
  
-   **アタッチ (**`pInterface`**)** `AddRef`は呼び出されません。     インターフェイスの所有権は、この `_com_ptr_t` オブジェクトに渡されます。 **リリース**は以前にカプセル化されたポインターの参照カウントをデクリメントするために呼び出されます。  
  
-   **アタッチ (** `pInterface` **、**`fAddRef`**)** 場合`fAddRef`は**true**、`AddRef`参照をインクリメントするために呼び出されるカプセル化されたインターフェイス ポインターの数。       場合`fAddRef`は**false**、この`_com_ptr_t`オブジェクトは、所有権を呼び出さずに生のインターフェイス ポインターの`AddRef`します。 **リリース**は以前にカプセル化されたポインターの参照カウントをデクリメントするために呼び出されます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_ptr_t クラス](../cpp/com-ptr-t-class.md)