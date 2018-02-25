---
title: "independent_bits_engine クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- random/std::independent_bits_engine
dev_langs:
- C++
helpviewer_keywords:
- independent_bits_engine class
ms.assetid: 889e9a82-f457-49a7-9d2e-26e0fc3cd907
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d2f5b064b91aa6df766ff4ca460a6096f984ab8b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="independentbitsengine-class"></a>independent_bits_engine クラス
ベースのエンジンから返された値のビットを再パックすることで、指定したビット数で数値のランダム シーケンスを生成します。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Engine, size_t W, class UIntType>  
class independent_bits_engine;  
```  
  
### <a name="parameters"></a>パラメーター  
 `Engine`  
 ベースのエンジンの型。  
  
 `W`  
 **ワード サイズ**。 生成される各数値のサイズ (ビット数)。 **前提条件**: `0 < W ≤ numeric_limits<UIntType>::digits`  
  
 `UIntType`  
 結果を表す符号なし整数型。 使用可能な型については、[\<random>](../standard-library/random.md) をご覧ください。  
  
## <a name="members"></a>メンバー  
  
||||  
|-|-|-|  
|`independent_bits_engine::independent_bits_engine`|`independent_bits_engine::base`|`independent_bits_engine::discard`|  
|`independent_bits_engine::operator()`|`independent_bits_engine::base_type`|`independent_bits_engine::seed`|  
  
 エンジンのメンバーの詳細については、[\<random>](../standard-library/random.md) をご覧ください。  
  
## <a name="remarks"></a>コメント  
 このテンプレート クラスは、ベースのエンジンから返された値のビットを再パックして `W` ビットの値にすることで値を生成する*エンジン アダプター*を表します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<random>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [\<random>](../standard-library/random.md)

