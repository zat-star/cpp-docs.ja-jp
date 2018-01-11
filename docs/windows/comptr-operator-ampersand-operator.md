---
title: "Comptr::operator&amp;演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::operator&
dev_langs: C++
helpviewer_keywords: operator& operator
ms.assetid: 2d77fda6-f4b2-45c1-8a0e-fbc355013531
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cc5234f10a16141fd91193d634f0d306886aff71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="comptroperatoramp-operator"></a>Comptr::operator&amp;演算子
これに関連付けられているインターフェイスを解放`ComPtr`オブジェクトし、のアドレスを取得し、`ComPtr`オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp  
Details::ComPtrRef<WeakRef> operator&()  
  
const Details::ComPtrRef<const WeakRef> operator&() const  
```  
  
## <a name="return-value"></a>戻り値  
 現在への弱い参照`ComPtr`です。  
  
## <a name="remarks"></a>コメント  
 このメソッドが異なる[comptr::getaddressof](../windows/comptr-getaddressof-method.md)点で、このメソッドは、インターフェイス ポインターへの参照を解放します。 使用して`ComPtr::GetAddressOf`インターフェイス ポインターのアドレスを必要なものの、そのインターフェイスを解放したくないとき。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [ComPtr クラス](../windows/comptr-class.md)