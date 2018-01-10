---
title: "Comptr::operator::booltype 演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: cfba6521-fb30-4fb8-afb2-cfab1cb5e0b8
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f98ca8068495be46b795d361c969c4feb2c24169
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="comptroperator-microsoftwrldetailsbooltype-operator"></a>ComPtr::operator Microsoft::WRL::Details::BoolType 演算子
ComPtr がインターフェイスのオブジェクト有効期間を管理しているかどうかを示します。  
  
## <a name="syntax"></a>構文  
  
```  
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;  
```  
  
## <a name="return-value"></a>戻り値  
 インターフェイスのアドレス、この ComPtr に関連付けられているかどうか、 [boolstruct::member](../windows/boolstruct-member-data-member.md)データ メンバー以外の場合、`nullptr`です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [ComPtr クラス](../windows/comptr-class.md)   
 [ComPtr::Get メソッド](../windows/comptr-get-method.md)