---
title: "mem_fun_ref_t クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xfunctional/std::mem_fun_ref_t
dev_langs:
- C++
helpviewer_keywords:
- mem_fun_ref_t class
ms.assetid: 7dadcac3-8d33-4e4b-a792-81bd53d3df39
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 51bc614c3bb7f52c32dd8df2d80dd6f9160f4f27
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="memfunreft-class"></a>mem_fun_ref_t クラス
参照引数による初期化を行うときに、引数を使用しない **non_const** メンバー関数を単項関数オブジェクトとして呼び出せるようにするアダプター クラス。  
  
## <a name="syntax"></a>構文  
  
```
template <class Result, class Type>
class mem_fun_ref_t : public unary_function<Type, Result> {
    explicit mem_fun_ref_t(
    Result (Type::* _Pm)());

    Result operator()(Type& left) const;

 };
```  
  
#### <a name="parameters"></a>パラメーター  
 `_Pm`  
 関数オブジェクトに変換されるクラス **Type** のメンバー関数へのポインター。  
  
 `left`  
 `_Pm` メンバー関数が呼び出されるオブジェクト。  
  
## <a name="return-value"></a>戻り値  
 適合可能な単項関数。  
  
## <a name="remarks"></a>コメント  
 このテンプレート クラスは `_Pm` のコピーをプライベート メンバー オブジェクトに格納します。これは、クラス **Type** のメンバー関数へのポインターである必要があります。 そのメンバー関数 `operator()` は ( **left**.* `_Pm`)( ) を返すように定義されています。  
  
## <a name="example"></a>例  
  `mem_fun_ref_t` のコンストラクターは通常は直接使用されません。ヘルパー関数 `mem_fun_ref` を使用してメンバー関数を適合させます。 メンバー関数アダプターの使用例については、「[mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref)」を参照してください。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<functional>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)



