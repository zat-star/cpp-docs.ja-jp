---
title: "discard_block_engine クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- discard_block_engine
- random/std::discard_block_engine
dev_langs:
- C++
helpviewer_keywords:
- discard_block_engine class
ms.assetid: aa84808e-38fe-4fa0-9f73-d5b9a653345b
caps.latest.revision: 18
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
ms.openlocfilehash: b770c9b353f126939a1d70c195b9cc421cb2e06e
ms.contentlocale: ja-jp
ms.lasthandoff: 04/19/2017

---
# <a name="discardblockengine-class"></a>discard_block_engine クラス
ベースとなるエンジンから返された値を破棄することによってランダム シーケンスを生成します。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Engine, size_t P, size_t R>  
class discard_block_engine;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `Engine`  
 ベースのエンジンの型。  
  
 `P`  
 **ブロック サイズ**。 各ブロックの値の数。  
  
 `R`  
 **使用されるブロック**。 使用される各ブロックの値の数。 残りは破棄されます (`P` - `R`)。 **前提条件**: `0 < R ≤ P`  
  
## <a name="members"></a>メンバー  
  
||||  
|-|-|-|  
|`discard_block_engine::discard_block_engine`|`discard_block_engine::base`|`discard_block_engine::discard`|  
|`discard_block_engine::operator()`|`discard_block_engine::base_type`|`discard_block_engine::seed`|  
  
 エンジンのメンバーの詳細については、[\<random>](../standard-library/random.md) をご覧ください。  
  
## <a name="remarks"></a>コメント  
 このテンプレート クラスは、ベースのエンジンによって返された値の一部を破棄することで値を生成するエンジン アダプターを表します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<random>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [\<random>](../standard-library/random.md)


