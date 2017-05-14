---
title: "ctype_base クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- locale/std::ctype_base
- ctype_base
dev_langs:
- C++
helpviewer_keywords:
- ctype_base class
ms.assetid: ccffe891-d7ab-4d22-baf8-8eb6d438a96d
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 74c13251b63018e00490487cb9a45c4bb6d52a21
ms.contentlocale: ja-jp
ms.lasthandoff: 04/19/2017

---
# <a name="ctypebase-class"></a>ctype_base クラス
このクラスは、テンプレート クラス [ctype](../standard-library/ctype-class.md) のファセットの基底クラスとして機能します。 個々の文字または範囲全体の文字を分類またはテストするための列挙型を定義するために使用される ctype クラスの基底クラス。  
  
## <a name="syntax"></a>構文  
  
```
struct ctype_base : public locale::facet
{
    enum
 {
    alnum,
 alpha,
    cntrl,
 digit,
    graph,
 lower,
    print,
 punct,
    space,
 upper,
    xdigit
 };
    typedef short mask;
    ctype_base(
 size_t _Refs = 0);

 ~ctype_base();

};
```  
  
## <a name="remarks"></a>コメント  
 列挙マスクを定義します。 ヘッダー \<ctype.h> に宣言されている同様の関数で定義されているように、列挙定数はそれぞれ、文字を分類する別の方法の特徴となっています。 定数は次のとおりです。  
  
- **space** (関数 [isspace](../standard-library/locale-functions.md#isspace))  
  
- **print** (関数 [isprint](../standard-library/locale-functions.md#isprint))  
  
- **cntrl** (関数 [iscntrl](../standard-library/locale-functions.md#iscntrl))  
  
- **upper** (関数 [isupper](../standard-library/locale-functions.md#isupper))  
  
- **lower** (関数 [islower](../standard-library/locale-functions.md#islower))  
  
- **digit** (関数 [isdigit](../standard-library/locale-functions.md#isdigit))  
  
- **punct** (関数 [ispunct](../standard-library/locale-functions.md#ispunct))  
  
- **xdigit** (関数 [isxdigit](../standard-library/locale-functions.md#isxdigit))  
  
- **alpha** (関数 [isalpha](../standard-library/locale-functions.md#isalpha))  
  
- **alnum** (関数 [isalnum](../standard-library/locale-functions.md#isalnum))  
  
- **graph** (関数 [isgraph](../standard-library/locale-functions.md#isgraph))  
  
 これらの定数を OR 演算することで、分類の組み合わせを特徴付けることができます。 特に、**alnum** == ( **alpha**``&#124; **digit**\) and **graph** \=\= \( **alnum**``&#124; **punct**) は常に true になります。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<locale>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)




