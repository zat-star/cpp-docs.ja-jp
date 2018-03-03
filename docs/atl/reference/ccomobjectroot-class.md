---
title: "CComObjectRoot クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComObjectRoot
- atlcom/ATL::CComObjectRoot
dev_langs:
- C++
helpviewer_keywords:
- CComObjectRoot class
ms.assetid: f8797c38-6e73-4f67-85c2-71654cffa8eb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3acd4d91082d79cff0e945f841389fb2428396f8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ccomobjectroot-class"></a>CComObjectRoot クラス
この typedef の[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)は既定のサーバーのモデルのスレッドでテンプレート化されます。  
  
## <a name="syntax"></a>構文  
  
```
typedef CComObjectRootEx<CComObjectThreadModel> CComObjectRoot;
```  
  
## <a name="remarks"></a>コメント  
 `CComObjectRoot``typedef`の[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)スレッド モデルがサーバーの既定のテンプレート化されます。 したがって[CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)を参照するか[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)または[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)です。  
  
 `CComObjectRootEx`非集計と集計の両方のオブジェクトのオブジェクト参照カウントの管理を処理します。 オブジェクトの参照カウントを保持している場合は、オブジェクトがない集計されているし、オブジェクトが集計されている場合、外側の不明なへのポインターを保持します。 集約オブジェクトは、の`CComObjectRootEx`を作成する内部オブジェクトのエラーを処理するメソッドを使用でき、内部のインターフェイスがリリースされたときに削除されないように、外部オブジェクトまたは内部オブジェクトを保護するのには削除します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcom.h  
  
## <a name="see-also"></a>参照  
 [CComObjectRootEx クラス メンバー](http://msdn.microsoft.com/en-us/e3ce9c3d-9c8e-4fe5-b682-8e56740a0164)   
 [CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)   
 [クラス](../../atl/reference/ccomaggobject-class.md)   
 [CComObject クラス](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject クラス](../../atl/reference/ccompolyobject-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
