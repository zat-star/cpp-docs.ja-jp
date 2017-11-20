---
title: "ComPtr::Reset |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: aa6a46f7-f56b-4fd5-add0-7cea55f7abda
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1227a2d8c38fd26b82e09d58326cc3790a4e7b14
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="comptrreset"></a>ComPtr::Reset
この ComPtr に関連付けられているインターフェイスを指すポインターへのすべての参照を解放します。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned long Reset();  
```  
  
## <a name="return-value"></a>戻り値  
 解放された参照の数 (存在する場合)。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ComPtr クラス](../windows/comptr-class.md)