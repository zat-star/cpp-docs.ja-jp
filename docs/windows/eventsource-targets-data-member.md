---
title: "Eventsource::targets _ データ メンバー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::EventSource::targets_
dev_langs: C++
helpviewer_keywords: targets_ data member
ms.assetid: 5d5cee05-3315-4514-bce2-19173c923c7d
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1fb14e7cfa25cd34d6bbaf6d0b48870f1d93f991
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="eventsourcetargets-data-member"></a>EventSource::targets_ データ メンバー
1 つまたは複数のイベント ハンドラーの配列。  
  
## <a name="syntax"></a>構文  
  
```  
ComPtr<Details::EventTargetArray> targets_;  
```  
  
## <a name="remarks"></a>コメント  
 現在の EventSource オブジェクトによって表されるイベントが発生するイベント ハンドラーが呼び出されます。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>参照
 [EventSource クラス](../windows/eventsource-class.md)