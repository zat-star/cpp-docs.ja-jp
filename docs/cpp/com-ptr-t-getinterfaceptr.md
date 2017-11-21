---
title: "_com_ptr_t::GetInterfacePtr |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_ptr_t::GetInterfacePtr
dev_langs: C++
helpviewer_keywords: GetInterfacePtr method [C++]
ms.assetid: 55e3e2c7-c939-48b5-a905-4b9cbefeea7e
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2d15bcec2527b15f70e2b7a5e5e38ddcd98e77bf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="comptrtgetinterfaceptr"></a>_com_ptr_t::GetInterfacePtr
**Microsoft 固有の仕様**  
  
 カプセル化されたインターフェイス ポインターを返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      Interface* GetInterfacePtr( ) const throw( );   
Interface*& GetInterfacePtr() throw();  
```  
  
## <a name="remarks"></a>コメント  
 可能性のあるカプセル化されたインターフェイス ポインターを返します。 **NULL**です。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_ptr_t クラス](../cpp/com-ptr-t-class.md)