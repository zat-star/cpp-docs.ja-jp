---
title: "independent_bits_engine クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- independent_bits_engine
- random/std::independent_bits_engine
dev_langs:
- C++
helpviewer_keywords:
- independent_bits_engine class
ms.assetid: 889e9a82-f457-49a7-9d2e-26e0fc3cd907
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 9a4052e44457b08f7d74f3591bd8665f0679c9a5
ms.contentlocale: ja-jp
ms.lasthandoff: 04/19/2017

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
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<random>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [\<random>](../standard-library/random.md)


