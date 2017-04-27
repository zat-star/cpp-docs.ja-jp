---
title: "collate_byname クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- locale/std::collate_byname
- collate_byname
dev_langs:
- C++
helpviewer_keywords:
- collate_byname class
ms.assetid: 3dc380df-867c-4763-b60e-ba62a8e63ca7
caps.latest.revision: 24
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
ms.openlocfilehash: a67e7f6ff915b53ba91c11c0c39d9bec6e4a380a
ms.lasthandoff: 02/24/2017

---
# <a name="collatebyname-class"></a>collate_byname クラス
特定のロケールの照合ファセットとして使用できるオブジェクトを表す派生テンプレート クラス。文字列の並べ替え規則に関する文化的領域に固有の情報を取得できるようにします。  
  
## <a name="syntax"></a>構文  
  
```
template <class CharType>
class collate_byname : public collate<CharType> {
public:
    explicit collate_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit collate_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~collate_byname();

};
```  
  
#### <a name="parameters"></a>パラメーター  
 `_Locname`  
 名前付きのロケール。  
  
 `_Refs`  
 最初の参照数。  
  
## <a name="remarks"></a>コメント  
 このテンプレート クラスは、[collate](../standard-library/collate-class.md#collate__collate)\<CharType> 型の[ロケール ファセット](../standard-library/locale-class.md#facet_class)として使用できるオブジェクトを表します。 その動作は[名前付き](../standard-library/locale-class.md#locale__name)のロケール `_Locname` で決まります。 各コンストラクターは、[collate](../standard-library/collate-class.md#collate__collate)\<CharType>( `_Refs`) を使用して、その基本オブジェクトを初期化します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<locale>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)




