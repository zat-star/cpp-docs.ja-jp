---
title: "Synclockt::islocked メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked
dev_langs: C++
helpviewer_keywords: IsLocked method
ms.assetid: a81fea43-f99a-4708-812a-7fd6af500d3d
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6db98e844d864e8b3ac719ec797527ed3ded56f8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="synclocktislocked-method"></a>SyncLockT::IsLocked メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
bool IsLocked() const;  
```  
  
## <a name="return-value"></a>戻り値  
 **true** SyncLockT オブジェクトがロックされている、それ以外の場合は**false**です。  
  
## <a name="remarks"></a>コメント  
 SyncLockT、現在、リソースを所有しているかどうかを示しますSyncLockT オブジェクトは、つまり、*ロック*です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>関連項目  
 [SyncLockT クラス](../windows/synclockt-class.md)