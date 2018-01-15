---
title: "Asyncbase::firecompletion メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::FireCompletion
dev_langs: C++
helpviewer_keywords: FireCompletion method
ms.assetid: b5e29d6d-52e7-4148-a7f3-a313b1359819
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 49716e31148c119d5a8c9eca05b449cea75b405a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="asyncbasefirecompletion-method"></a>AsyncBase::FireCompletion メソッド
完了イベント ハンドラーが呼び出されます。 または内部の進行状況のデリゲートをリセットします。  
  
## <a name="syntax"></a>構文  
  
```  
void FireCompletion(  
   void  
) override;  
  
virtual void FireCompletion();  
```  
  
## <a name="remarks"></a>コメント  
 FireCompletion() の最初のバージョンでは、内部の進行状況デリゲート変数をリセットします。 2 番目のバージョンは、非同期操作が完了している場合、完了イベント ハンドラーを呼び出します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [AsyncBase クラス](../windows/asyncbase-class.md)