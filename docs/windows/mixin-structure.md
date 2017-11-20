---
title: "MixIn 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::MixIn
dev_langs: C++
helpviewer_keywords: MixIn structure
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e1df2de0a8c645b957a5c3e93f8c4ebbb3b2fb94
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="mixin-structure"></a>MixIn 構造体
ランタイム クラスが Windows ランタイム インターフェイス (存在する場合) から派生し、次にクラシック COM インターフェイスから派生していることを確認します。  
  
## <a name="syntax"></a>構文  
  
```  
template<  
   typename Derived,  
   typename MixInType,  
   bool hasImplements = __is_base_of(Details::ImplementsBase,  
   MixInType)  
>  
struct MixIn;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `Derived`  
 派生した型、 [Implements](../windows/implements-structure.md)構造体。  
  
 `MixInType`  
 基本型。  
  
 `hasImplements`  
 `true`場合`MixInType`は現在の実装から派生した基本型です。`false`それ以外の場合。  
  
## <a name="remarks"></a>コメント  
 Windows ランタイムと COM クラス インターフェイスの両方から派生したクラスは、クラス宣言リストする必要がありますまず他の Windows ランタイム インターフェイスを一覧表示し、し、すべてのクラシック COM インターフェイスです。 MixIn のインターフェイスが正しい順序で指定されていることを確認します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `MixIn`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)