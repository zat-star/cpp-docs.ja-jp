---
title: "クラスの |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComEnumOnSTL
- atlcom/ATL::CComEnumOnSTL
dev_langs: C++
helpviewer_keywords: CComEnumOnSTL class
ms.assetid: befe1a44-7a00-4f28-9a2e-cc0fa526643c
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d42d99baf154bc5434f2d771aeaabb71c5502b30
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ccomenumonstl-class"></a>クラス
このクラスは、C++ 標準ライブラリ コレクションに基づく COM 列挙子オブジェクトを定義します。  
  
## <a name="syntax"></a>構文  
  
```
template <class Base,
    const IID* piid, class T, class Copy, class CollType, class ThreadModel = CComObjectThreadModel>  
class ATL_NO_VTABLE CComEnumOnSTL : public IEnumOnSTLImpl<Base, piid,
 T,
    Copy,
 CollType>,
    public CComObjectRootEx<ThreadModel>
```  
  
#### <a name="parameters"></a>パラメーター  
 `Base`  
 COM の列挙子 ([として](https://msdn.microsoft.com/library/ms680089.aspx)) インターフェイス。  
  
 `piid`  
 列挙子インターフェイスのインターフェイス ID へのポインター。  
  
 `T`  
 列挙子インターフェイスによって公開されている項目の種類。  
  
 `Copy`  
 A[ポリシーをコピー](../../atl/atl-copy-policy-classes.md)クラスです。  
  
 `CollType`  
 C++ 標準ライブラリのコンテナー クラスです。  
  
## <a name="remarks"></a>コメント  
 `CComEnumOnSTL`C++ 標準ライブラリ コレクションに基づく COM 列挙子オブジェクトを定義します。 自身またはと共に、このクラスを使用することができます[単独](../../atl/reference/icollectiononstlimpl-class.md)です。 このクラスを使用するための一般的な手順は次のとおりです。 詳細については、次を参照してください。 [ATL のコレクションと列挙子](../../atl/atl-collections-and-enumerators.md)です。  
  
## <a name="to-use-this-class-with-icollectiononstlimpl"></a>単独では、このクラスを使用します。  
  
- `typedef`このクラスの特殊化です。  
  
-   使用して、`typedef`の特殊化での最終的なテンプレート引数として`ICollectionOnSTLImpl`です。  
  
 参照してください[ATL のコレクションと列挙子](../../atl/atl-collections-and-enumerators.md)例についてはします。  
  
## <a name="to-use-this-class-independently-of-icollectiononstlimpl"></a>クラスを使用するこのクライアントとは無関係に。  
  
- `typedef`このクラスの特殊化です。  
  
-   使用して、`typedef`の特殊化のテンプレート引数として`CComObject`です。  
  
-   インスタンスを作成、`CComObject`特殊化です。  
  
-   呼び出して列挙子オブジェクトを初期化する[保ちます](../../atl/reference/ienumonstlimpl-class.md#init)です。  
  
-   列挙子インターフェイスをクライアントに返します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [つまり](../../atl/reference/ienumonstlimpl-class.md)  
  
 `CComEnumOnSTL`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcom.h  
  
## <a name="example"></a>例  
 次に示すコードでは、作成、列挙子オブジェクトの初期化を処理するジェネリック関数を示します。  
  
 [!code-cpp[NVC_ATL_COM#34](../../atl/codesnippet/cpp/ccomenumonstl-class_1.h)]  
  
 このテンプレート関数を実装するために使用できる、`_NewEnum`次に示すように、コレクション インターフェイスのプロパティ。  
  
 [!code-cpp[NVC_ATL_COM#35](../../atl/codesnippet/cpp/ccomenumonstl-class_2.h)]  
  
 このコードを作成、`typedef`の`CComEnumOnSTL`のベクターを公開する`CComVariant`により s、 **IEnumVariant**インターフェイスです。 **CVariantCollection**クラスを特化するだけ**CreateSTLEnumerator**この型の列挙子オブジェクトを使用します。  
  
## <a name="see-also"></a>参照  
 [つまり](../../atl/reference/ienumonstlimpl-class.md)   
 [ATLCollections サンプル: 単独、CComEnumOnSTL、およびカスタム コピー ポリシー クラス](../../visual-cpp-samples.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)   
 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)   
 [IEnumOnSTLImpl クラス](../../atl/reference/ienumonstlimpl-class.md)
