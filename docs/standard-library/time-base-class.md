---
title: "time_base クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- time_base
- locale/std::time_base
dev_langs:
- C++
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
caps.latest.revision: 19
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 54b8f19ef063727c21559ab85e85255643131b87
ms.lasthandoff: 02/24/2017

---
# <a name="timebase-class"></a>time_base クラス
このクラスは、time_get テンプレート クラスのファセットの基底クラスとして使用されます。**dateorder** 列挙型とこの型の複数の定数のみを定義します。  
  
## <a name="syntax"></a>構文  
  
```
class time_base : public locale::facet {
public:
    enum dateorder {no_order,
    dmy,
 mdy,
    ymd,
 ydm};
    time_base(
 size_t _Refs = 0)
 ~time_base();

};
```  
  
## <a name="remarks"></a>コメント  
 各定数は、日付部分を順序付けるための異なる方法を特徴付けます。 定数は次のとおりです。  
  
- **no_order** は、特定の順序を指定しません。  
  
- **dmy** は、2 December 1979 のように日、月、年という順序を指定します。  
  
- **dmy** は、December 2, 1979 のように、月、日、年という順序を指定します。  
  
- **ymd** は、1979/12/2 のように、年、月、日という順序を指定します。  
  
- **ymd** は、1979: 2 Dec のように、年、日、月という順序を指定します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<locale>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)




