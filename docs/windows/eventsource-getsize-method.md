---
title: "Eventsource::getsize メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::EventSource::GetSize
dev_langs: C++
helpviewer_keywords: GetSize method
ms.assetid: 7825aab5-1a6b-465f-9159-3a6684142d1f
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e7b7d3af084bad27660d8451c9cb09015731aec3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="eventsourcegetsize-method"></a>EventSource::GetSize メソッド
現在の EventSource オブジェクトに関連付けられているイベント ハンドラーの数を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
size_t GetSize() const;  
```  
  
## <a name="return-value"></a>戻り値  
 内のイベント ハンドラーの数[targets _](../windows/eventsource-targets-data-member.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [EventSource クラス](../windows/eventsource-class.md)