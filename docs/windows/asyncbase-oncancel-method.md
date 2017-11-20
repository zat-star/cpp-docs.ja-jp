---
title: "Asyncbase::oncancel メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::OnCancel
dev_langs: C++
helpviewer_keywords: OnCancel method
ms.assetid: 4bd0b68e-a9df-4913-9f6c-e093ed55c3f9
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e46f673329697ef503dafcc6a3b683fa2224525a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="asyncbaseoncancel-method"></a>AsyncBase::OnCancel メソッド
派生クラスでオーバーライドされると、非同期操作をキャンセルします。  
  
## <a name="syntax"></a>構文  
  
```  
virtual void OnCancel(  
   void  
) = 0;  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [AsyncBase クラス](../windows/asyncbase-class.md)   
 [AsyncBase::Cancel メソッド](../windows/asyncbase-cancel-method.md)