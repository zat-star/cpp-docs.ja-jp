---
title: "mem_fun_t クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mem_fun_t
- xfunctional/std::mem_fun_t
dev_langs:
- C++
helpviewer_keywords:
- mem_fun_t class
ms.assetid: 242566d4-750c-4c87-9d63-2e2c9d19ca2a
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
ms.openlocfilehash: 88b79a99f04dc247fe52c7b65e6a9fd5f7cd4c2f
ms.contentlocale: ja-jp
ms.lasthandoff: 04/19/2017

---
# <a name="memfunt-class"></a>mem_fun_t クラス
ポインター引数による初期化を行うときに、引数を使用しない **non_const** メンバー関数を単項関数オブジェクトとして呼び出せるようにするアダプター クラス。  
  
## <a name="syntax"></a>構文  
  
```
template <class Result, class Type>
class mem_fun_t : public unary_function<Type *, Result> {
    explicit mem_fun_t(Result (Type::* _Pm)());

    Result operator()(Type* _Pleft) const;

 };
```  
  
#### <a name="parameters"></a>パラメーター  
 `_Pm`  
 関数オブジェクトに変換される **Type** クラスのメンバー関数へのポインター。  
  
 `_Pleft`  
 `_Pm` メンバー関数が呼び出されるオブジェクト。  
  
## <a name="return-value"></a>戻り値  
 適合可能な単項関数。  
  
## <a name="remarks"></a>コメント  
 このテンプレート クラスは `_Pm` のコピーをプライベート メンバー オブジェクトに格納します。これは、クラス **Type** のメンバー関数へのポインターである必要があります。 そのメンバー関数 `operator()` は ( `_Pleft`->* `_Pm`)( ) を返すように定義されています。  
  
## <a name="example"></a>例  
 `mem_fun_t` のコンストラクターは通常は直接使用されません。ヘルパー関数 `mem_fun` を使用してメンバー関数を適合させます。 メンバー関数アダプターの使用例については、「[mem_fun](../standard-library/functional-functions.md#mem_fun)」を参照してください。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<functional>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [\<functional>](../standard-library/functional.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)




