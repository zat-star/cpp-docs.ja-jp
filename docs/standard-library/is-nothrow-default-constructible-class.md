---
title: "is_nothrow_default_constructible クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_nothrow_default_constructible
- type_traits/std::is_nothrow_default_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_default_constructible
ms.assetid: c576fcc9-5be1-43aa-b93a-64d3f1848887
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: 60850f93178fe05511dedddc680eec1adf46f2c0
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="isnothrowdefaultconstructible-class"></a>is_nothrow_default_constructible クラス
スローしない既定コンストラクターが型に存在するかどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```
template <class Ty>
struct is_nothrow_default_constructible;
```  
  
#### <a name="parameters"></a>パラメーター  
 `Ty`  
 照会する型。  
  
## <a name="remarks"></a>コメント  
 スローしない既定コンストラクターが型 `Ty` に存在する場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。 型述語のインスタンスは `is_nothrow_constructible<Ty>` と同じです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [<type_traits>](../standard-library/type-traits.md)




