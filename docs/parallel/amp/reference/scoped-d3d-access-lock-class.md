---
title: "scoped_d3d_access_lock クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- scoped_d3d_access_lock
- AMPRT/scoped_d3d_access_lock
- AMPRT/concurrency::direct3d::scoped_d3d_access_lock::scoped_d3d_access_lock
dev_langs:
- C++
ms.assetid: 0ad333e6-9839-4736-a722-16d95d70c4b1
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: fd7f377e1dfe4e99f566da4782be5c2ccfdddbff
ms.lasthandoff: 03/17/2017

---
# <a name="scopedd3daccesslock-class"></a>scoped_d3d_access_lock クラス
accelerator_view オブジェクトに対する D3D アクセス ロックの RAII ラッパーです。  
  
### <a name="syntax"></a>構文  
  
```  
class scoped_d3d_access_lock;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[scoped_d3d_access_lock コンス トラクター](#ctor)|オーバーロードされます。 `scoped_d3d_access_lock` オブジェクトを構築します。 このオブジェクトがスコープから外れると、ロックは解放されます。|  
|[~ scoped_d3d_access_lock デストラクター](#dtor)|関連付けられた `accelerator_view` オブジェクトに対する D3D アクセスのロックを解除します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator=](#operator_eq)|別の `scoped_d3d_access_lock` からロックの所有権を取得します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `scoped_d3d_access_lock`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amprt.h  
  
 **Namespace:** concurrency::direct3d  

##  <a name="ctor"></a>scoped_d3d_access_lock 

 `scoped_d3d_access_lock` オブジェクトを構築します。 このオブジェクトがスコープから外れると、ロックは解放されます。  
 
```  
explicit scoped_d3d_access_lock(// [1] constructor  
    accelerator_view& _Av);

 
explicit scoped_d3d_access_lock(// [2] constructor  
    accelerator_view& _Av,  
    adopt_d3d_access_lock_t _T);

 
scoped_d3d_access_lock(// [3] move constructor  
    scoped_d3d_access_lock&& _Other);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Av`  
 導入するロックの `accelerator_view`。  
  
 `_T`  
 `adopt_d3d_access_lock_t` オブジェクト。  
  
 `_Other`  
 既存のロックの移動元の `scoped_d3d_access_lock` オブジェクト。  
  
## <a name="construction"></a>構築  
 [1] コンストラクター  
 に対する D3D アクセス ロックを取得、指定された[accelerator_view](accelerator-view-class.md)オブジェクトです。 ロックが取得されるまでの構築ブロック。  
  
 [2] のコンス トラクター  
 D3D アクセスのロックを導入する、指定された[accelerator_view](accelerator-view-class.md)オブジェクトです。  
  
 [3] 移動コンストラクター  
 別の `scoped_d3d_access_lock` オブジェクトから既存の D3D アクセスのロックを受け取ります。 構造体はブロックを行いません。  

  
##  <a name="dtor"></a>~ scoped_d3d_access_lock 

 関連付けられた `accelerator_view` オブジェクトに対する D3D アクセスのロックを解除します。  
  
```  
~scoped_d3d_access_lock();
```  
## <a name="operator_eq"></a>演算子 = 

以前のロックを解放して、別の `scoped_d3d_access_lock` オブジェクトから D3D アクセスのロックの所有権を取得します。  
 
```  
scoped_d3d_access_lock& operator= (scoped_d3d_access_lock&& _Other);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 D3D アクセスのロックの移動元である accelerator_view。  
  
### <a name="return-value"></a>戻り値  
 この `scoped_accelerator_view_lock` への参照。  

## <a name="see-also"></a>関連項目  
 [Concurrency::direct3d 名前空間](concurrency-direct3d-namespace.md)

