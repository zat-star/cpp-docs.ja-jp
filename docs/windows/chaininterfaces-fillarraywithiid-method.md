---
title: "Chaininterfaces::fillarraywithiid メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::ChainInterfaces::FillArrayWithIid
dev_langs: C++
helpviewer_keywords: FillArrayWithIid method
ms.assetid: f1ce699c-dfb6-40a9-9ea0-e6703d3cf971
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a45a9f8a709b70ae48597923bb153d28b22980af
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="chaininterfacesfillarraywithiid-method"></a>ChainInterfaces::FillArrayWithIid メソッド
ストアで定義されているインターフェイス ID、`I0`インターフェイス Id の指定した配列内の指定した場所にテンプレート パラメーター。  
  
## <a name="syntax"></a>構文  
  
```  
__forceinline static void FillArrayWithIid(  
   _Inout_ unsigned long &index,  
   _In_ IID* iids  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `index`  
 インデックスへのポインター、`iids`配列。  
  
 `iids`  
 インターフェイスの Id の配列。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ChainInterfaces 構造体](../windows/chaininterfaces-structure.md)