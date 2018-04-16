---
title: "pointer_to_binary_function クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xfunctional/std::pointer_to_binary
dev_langs:
- C++
helpviewer_keywords:
- pointer_to_binary_function function
- pointer_to_binary_function class
ms.assetid: fb50599f-bcb3-4076-a669-6dcc3eb189a5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c449d66dfe1889e403cd288361bb5cc20e7f884d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="pointertobinaryfunction-class"></a>pointer_to_binary_function クラス
二項関数ポインターを適応性のある二項関数に変換します。  
  
## <a name="syntax"></a>構文  
  
```
template <class Arg1, class Arg2, class Result>
class pointer_to_binary_function
    : public binary_function <Arg1, Arg2, Result>
{
public:
    explicit pointer_to_binary_function(
        Result(*pfunc)(Arg1, Arg2));
    Result operator()(Arg1 left, Arg2 right) const;
};
```  
  
#### <a name="parameters"></a>パラメーター  
 `pfunc`  
 変換する二項関数。  
  
 `left`  
 *\*pfunc* が呼び出される左辺のオブジェクト。  
  
 `right`  
 *\*pfunc* が呼び出される右側のオブジェクト。  
  
## <a name="return-value"></a>戻り値  
 テンプレート クラスは **pfunc** のコピーを格納します。 そのメンバー関数 `operator()` は (\* **pfunc**)(_ *Left*, \_ *Right*) を返すように定義されています。  
  
## <a name="remarks"></a>コメント  
 二項関数ポインターは関数オブジェクトであり、パラメーターとして二項関数を想定する C++ 標準ライブラリの任意のアルゴリズムに渡される場合がありますが、適応性はありません。 二項関数ポインターをアダプターと共に使用する (値をバインドしたり否定子と共に使用するなど) には、このような適応を可能にする、入れ子にされた型 (**first_argument_type**、**second_argument_type**、および **result_type**) と共に指定する必要があります。 `pointer_to_binary_function` による変換によって、関数アダプターを二項関数ポインターと共に使用できるようになります。  
  
## <a name="example"></a>例  
 `pointer_to_binary_function` のコンストラクターが直接使用されることはほとんどありません。 `pointer_to_binary_function` アダプターの述語を宣言および使用する方法の例については、ヘルパー関数 [ptr_fun](../standard-library/functional-functions.md#ptr_fun) をご覧ください。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<functional>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)



