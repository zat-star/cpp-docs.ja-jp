---
title: "CComObjectRoot クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComObjectRoot
dev_langs:
- C++
helpviewer_keywords:
- CComObjectRoot class
ms.assetid: f8797c38-6e73-4f67-85c2-71654cffa8eb
caps.latest.revision: 17
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
ms.sourcegitcommit: 31295a07704e272799398aa82c6a9f0bbac17717
ms.openlocfilehash: 34653d55091a8e872f075010a0ef7cecbb3484c8
ms.lasthandoff: 02/24/2017

---
# <a name="ccomobjectroot-class"></a>CComObjectRoot クラス
この typedef [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)はスレッド処理モデルは、サーバーの既定のテンプレート化されます。  
  
## <a name="syntax"></a>構文  
  
```
typedef CComObjectRootEx<CComObjectThreadModel> CComObjectRoot;
```  
  
## <a name="remarks"></a>コメント  
 `CComObjectRoot``typedef`の[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)スレッド処理モデルは、サーバーの既定のテンプレート化されます。 したがって[CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)いずれかを参照する[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)または[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)します。  
  
 `CComObjectRootEx`非集計と集計の両方のオブジェクトのオブジェクト参照カウントの管理を処理します。 オブジェクトが集計されていませんが、オブジェクトが集約されている場合は、外部の"不明"にポインターを置く場合は、オブジェクトの参照カウントを保持します。 集約オブジェクトの`CComObjectRootEx`メソッドは、構成する際、内部オブジェクトのエラーを処理するために使用でき、内部のインターフェイスがリリースされたときに削除されないように、外部オブジェクトまたは内部のオブジェクトを保護するのには削除されます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
## <a name="see-also"></a>関連項目  
 [CComObjectRootEx クラス メンバー](http://msdn.microsoft.com/en-us/e3ce9c3d-9c8e-4fe5-b682-8e56740a0164)   
 [CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)   
 [クラス](../../atl/reference/ccomaggobject-class.md)   
 [クラス](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject クラス](../../atl/reference/ccompolyobject-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

