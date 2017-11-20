---
title: "pointer_to_unary_function クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xfunctional/std::pointer_to_unary
dev_langs: C++
helpviewer_keywords:
- pointer_to_unary_function function
- pointer_to_unary_function class
ms.assetid: 05600207-b916-4759-beca-6b6facd2d6f6
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9495bb988c8273967eefa35eb1ec89da753a4deb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="pointertounaryfunction-class"></a>pointer_to_unary_function クラス
単項関数ポインターを適応性のある単項関数に変換します。  
  
## <a name="syntax"></a>構文  
  
```
template <class Arg, class Result>
class pointer_to_unary_function
    : public unary_function<Arg, Result>
{
public:
    explicit pointer_to_unary_function(Result(*pfunc)(Arg));
    Result operator()(Arg left) const;
};
```  
  
#### <a name="parameters"></a>パラメーター  
 `pfunc`  
 変換する二項関数。  
  
 `left`  
 *\*pfunc* が呼び出されるオブジェクト。  
  
## <a name="return-value"></a>戻り値  
 テンプレート クラスは **pfunc** のコピーを格納します。 そのメンバー関数 `operator()` は (\* **pfunc**)(_ *Left*) を返すように定義されています。  
  
## <a name="remarks"></a>コメント  
 単項関数ポインターは関数オブジェクトであり、パラメーターとして単項関数を想定する C++ 標準ライブラリの任意のアルゴリズムに渡される場合がありますが、適合性はありません。 単項関数ポインターをアダプターと共に使用する (値をバインドしたり否定子と共に使用するなど) には、このような適合を可能にする、入れ子にされた型 (**argument_type** および **result_type**) と共に指定する必要があります。 `pointer_to_unary_function` による変換によって、関数アダプターを二項関数ポインターと共に使用できるようになります。  
  
## <a name="example"></a>例  
 `pointer_to_unary_function` のコンストラクターが直接使用されることはほとんどありません。 `pointer_to_unary_function` アダプターの述語を宣言および使用する方法の例については、ヘルパー関数 [ptr_fun](../standard-library/functional-functions.md#ptr_fun) をご覧ください。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<functional>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)



