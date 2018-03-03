---
title: "Eventsource::getsize メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::GetSize
dev_langs:
- C++
helpviewer_keywords:
- GetSize method
ms.assetid: 7825aab5-1a6b-465f-9159-3a6684142d1f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ef2f51d2f53b05ae651e811c1d53ceccdab7ad5c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="eventsourcegetsize-method"></a>EventSource::GetSize メソッド
現在の EventSource オブジェクトに関連付けられているイベント ハンドラーの数を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
size_t GetSize() const;  
```  
  
## <a name="return-value"></a>戻り値  
 内のイベント ハンドラーの数[targets _](../windows/eventsource-targets-data-member.md)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [EventSource クラス](../windows/eventsource-class.md)