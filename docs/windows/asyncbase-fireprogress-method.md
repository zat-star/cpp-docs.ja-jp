---
title: "Asyncbase::fireprogress メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::FireProgress
dev_langs: C++
helpviewer_keywords: FireProgress method
ms.assetid: 4512bef6-0ebc-4465-9b8a-4c9dfa82084c
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 358a85f6ec0a451534684f2201caffefb1c1ad1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="asyncbasefireprogress-method"></a>AsyncBase::FireProgress メソッド
現在の進行状況イベント ハンドラーを呼び出します。  
  
## <a name="syntax"></a>構文  
  
```  
void FireProgress(  
   const typename ProgressTraits::Arg2Type arg  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `arg`  
 イベント ハンドラー メソッドを呼び出します。  
  
## <a name="remarks"></a>コメント  
 `ProgressTraits`派生した[ArgTraitsHelper 構造体](../windows/argtraitshelper-structure.md)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [AsyncBase クラス](../windows/asyncbase-class.md)