---
title: "既定の名前空間 |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
ms.assetid: 4712e9dc-57ba-43cc-811e-022e1dae4de8
caps.latest.revision: "6"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5a9d538e42d4173008343df186bd2579dc088fb5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="default-namespace"></a>既定の名前空間
`default`名前空間のスコープとは、組み込みの型がサポートする C + + CX です。  
  
## <a name="syntax"></a>構文  
  
```  
namespace default;  
```  
  
### <a name="members"></a>メンバー  
 組み込み型はすべて、次のメンバーを継承します。  
  
|||  
|-|-|  
|[default::(type_name)::Equals](../cppcx/default-type-name-equals-method.md)|指定したオブジェクトが、現在のオブジェクトと等しいかどうかを判断します。|  
|[default::(type_name)::GetHashCode](../cppcx/default-type-name-gethashcode-method.md)|このインスタンスのハッシュ コードを返します。|  
|[default::(type_name)::GetType](../cppcx/default-type-name-gettype-method.md)|現在の型を表す文字列を返します。|  
|[default::(type_name)::ToString](../cppcx/default-type-name-tostring-method.md)|現在の型を表す文字列を返します。|  
  
### <a name="built-in-types"></a>組み込み型  
  
|name|説明|  
|----------|-----------------|  
|`char16`|Unicode (UTF-16) コード ポイントを表す 16 ビットの数字以外の値。|  
|`float32`|32 ビットの IEEE 754 浮動小数点数。|  
|`float64`|64 ビットの IEEE 754 浮動小数点数。|  
|`int16`|16 ビット符号付き整数。|  
|`int32`|32 ビット符号付き整数。|  
|`int64`|64 ビット符号付き整数。|  
|`int8`|8 ビット符号付き数値。|  
|`uint16`|16 ビット符号なし整数。|  
|`uint32`|32 ビット符号なし整数|  
|`uint64`|64 ビット符号なし整数。|  
|`uint8`|8 ビット符号なし数値。|  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** vccorlib.h  
  
## <a name="see-also"></a>参照  
 [Visual C 言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)