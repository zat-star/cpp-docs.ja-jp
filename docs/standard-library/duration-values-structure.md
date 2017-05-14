---
title: "duration_values 構造体 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chrono/std::chrono::duration_values
- chrono/std::chrono::duration_values::max
- chrono/std::chrono::duration_values::min
- chrono/std::chrono::duration_values::zero
dev_langs:
- C++
ms.assetid: 7f66d2e3-1faf-47c3-b47e-08f2a87f20e8
caps.latest.revision: 13
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
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: b170debfdb4759b41963bc0faca13b3db11ad39a
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="durationvalues-structure"></a>duration_values 構造体
[duration](../standard-library/duration-class.md) テンプレート パラメーター `Rep` に対して特定の値を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Rep>  
struct duration_values;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[max](#max)|静的。 `Rep` 型の値の上限を指定します。|  
|[min](#min)|静的。 `Rep` 型の値の下限を指定します。|  
|[0](#zero)|静的。 `Rep(0)` を返します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<chrono >  
  
 **名前空間:** std::chrono  
  
##  <a name="max"></a>  duration_values::max  
 `Ref` 型の値の上限の境界を返す静的メソッドです。  
  
```  
static constexpr Rep max();
```  
  
### <a name="return-value"></a>戻り値  
 実際には、`numeric_limits<Rep>::max()` を返します。  
  
### <a name="remarks"></a>コメント  
 `Rep` がユーザー定義型の場合、戻り値は [duration_values::zero](#zero) より大きい必要があります。  
  
##  <a name="min"></a>  duration_values::min  
 `Ref` 型の値の下限の境界を返す静的メソッドです。  
  
```  
static constexpr Rep min();
```  
  
### <a name="return-value"></a>戻り値  
 実際には、`numeric_limits<Rep>::lowest()` を返します。  
  
### <a name="remarks"></a>コメント  
 `Rep` がユーザー定義型の場合、戻り値は [duration_values::zero](#zero) 以下である必要があります。  
  
##  <a name="zero"></a>  duration_values::zero  
 `Rep(0)` を返します。  
  
```  
static constexpr Rep zero();
```  
  
### <a name="remarks"></a>コメント  
 `Rep` がユーザー定義型の場合、戻り値は追加の無限を示す必要があります。  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono>](../standard-library/chrono.md)


