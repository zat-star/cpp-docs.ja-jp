---
title: "_com_ptr_t::Detach |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method [C++]
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c04007df7d40e12f3f416b2f2cd437bdaf1314f4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="comptrtdetach"></a>_com_ptr_t::Detach
**Microsoft 固有の仕様**  
  
 カプセル化されたインターフェイス ポインターを抽出して返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
Interface* Detach( ) throw( );  
  
```  
  
## <a name="remarks"></a>コメント  
 抽出、カプセル化されたインターフェイス ポインターを返し、カプセル化されたポインター ストレージをクリア**NULL**です。 これによって、カプセル化からインターフェイス ポインターが削除されます。 呼び出すかどうかは**リリース**返されたインターフェイス ポインター。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [_com_ptr_t クラス](../cpp/com-ptr-t-class.md)