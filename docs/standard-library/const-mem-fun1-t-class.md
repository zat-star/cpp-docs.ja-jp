---
title: "const_mem_fun1_t クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xfunctional/std::const_mem_fun1_t
dev_langs: C++
helpviewer_keywords: const_mem_fun1_t class
ms.assetid: 250fac30-9663-4133-9051-6303f76ea259
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 788f49d3aa4cefd46e5ea97517a02a35a9747403
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="constmemfun1t-class"></a>const_mem_fun1_t クラス
ポインター引数による初期化を行うときに、1 つの引数を使用する **const** メンバー関数を二項関数オブジェクトとして呼び出せるようにするアダプター クラス。  
  
## <a name="syntax"></a>構文  
  
```
template <class Result, class Type, class Arg>
class const_mem_fun1_t
 : public binary_function<const Type *, Arg, Result>  
{
    explicit const_mem_fun1_t(Result (Type::* _Pm)(Arg) const);
    Result operator()(const Type* _Pleft, Arg right) const;
 };
```  
  
#### <a name="parameters"></a>パラメーター  
 `_Pm`  
 関数オブジェクトに変換される **Type** クラスのメンバー関数へのポインター。  
  
 `_Pleft`  
 `_Pm` メンバー関数が呼び出される **const** オブジェクト。  
  
 `right`  
 `_Pm` に渡す引数。  
  
## <a name="return-value"></a>戻り値  
 適合可能な二項関数。  
  
## <a name="remarks"></a>コメント  
 このテンプレート クラスは `_Pm` のコピーをプライベート メンバー オブジェクトに格納します。これは、**Type** クラスのメンバー関数へのポインターである必要があります。 そのメンバー関数 `operator()` は、(**_Pleft**->\* *Pm)(***Right**) **const** を返すように定義されています。  
  
## <a name="example"></a>例  
 `const_mem_fun1_t` のコンストラクターは通常は直接使用されません。ヘルパー関数 `mem_fun` を使用してメンバー関数を適合させます。 メンバー関数アダプターの使用例については、「[mem_fun](../standard-library/functional-functions.md#mem_fun)」を参照してください。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<functional>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)



