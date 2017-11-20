---
title: "Criticalsection::trylock メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::CriticalSection::TryLock
dev_langs: C++
helpviewer_keywords: TryLock method
ms.assetid: 504bb87c-2cd0-4f54-b458-b3efb9789053
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 225131a48e6ba5079ef2008b11ac6b22197f71d8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="criticalsectiontrylock-method"></a>CriticalSection::TryLock メソッド
ブロックすることがなく、クリティカル セクションを入力しようとしています。 呼び出しが成功した場合、呼び出し元スレッドは、クリティカル セクションの所有権を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
SyncLock TryLock();  
  
static SyncLock TryLock(  
   _In_ CRITICAL_SECTION* cs  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cs`  
 クリティカル セクションのユーザーが指定したオブジェクトです。  
  
## <a name="return-value"></a>戻り値  
 クリティカル セクションが正しく入力された場合は 0 以外の値または現在のスレッドは、クリティカル セクションを既に所有しています。 別のスレッドには、クリティカル セクション既に所有している場合は 0 を返します。  
  
## <a name="remarks"></a>コメント  
 最初の**TryLock**関数が現在のクリティカル セクション オブジェクトに影響します。 2 番目**TryLock**関数、ユーザー指定のクリティカル セクションに影響します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [CriticalSection クラス](../windows/criticalsection-class.md)