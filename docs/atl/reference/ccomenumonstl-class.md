---
title: "CComEnumOnSTL クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComEnumOnSTL
- atlcom/ATL::CComEnumOnSTL
dev_langs:
- C++
helpviewer_keywords:
- CComEnumOnSTL class
ms.assetid: befe1a44-7a00-4f28-9a2e-cc0fa526643c
caps.latest.revision: 21
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 23e234f82ce8c77a6ebde50070475deeab59f362
ms.lasthandoff: 02/24/2017

---
# <a name="ccomenumonstl-class"></a>CComEnumOnSTL クラス
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
 列挙子インターフェイスによって公開される項目の種類。  
  
 `Copy`  
 A[ポリシーをコピー](../../atl/atl-copy-policy-classes.md)クラスです。  
  
 `CollType`  
 C++ 標準ライブラリのコンテナー クラスです。  
  
## <a name="remarks"></a>コメント  
 `CComEnumOnSTL`C++ 標準ライブラリ コレクションに基づく COM 列挙子オブジェクトを定義します。 このクラスは、独自にまたは組み合わせて使用[ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md)します。 このクラスを使用するための一般的な手順は次のとおりです。 詳細については、次を参照してください。 [ATL のコレクションと列挙子](../../atl/atl-collections-and-enumerators.md)します。  
  
## <a name="to-use-this-class-with-icollectiononstlimpl"></a>単独では、このクラスを使用します。  
  
- `typedef`このクラスの特殊化します。  
  
-   使用して、`typedef`の特殊化の最終的なテンプレート引数として`ICollectionOnSTLImpl`します。  
  
 参照してください[ATL のコレクションと列挙子](../../atl/atl-collections-and-enumerators.md)例については、です。  
  
## <a name="to-use-this-class-independently-of-icollectiononstlimpl"></a>ICollectionOnSTLImpl とは無関係に、このクラスを使用します。  
  
- `typedef`このクラスの特殊化します。  
  
-   使用して、`typedef`の特殊化のテンプレート引数として`CComObject`します。  
  
-   インスタンスを作成、`CComObject`特殊化します。  
  
-   呼び出して、列挙子オブジェクトを初期化[保ちます](../../atl/reference/ienumonstlimpl-class.md#init)します。  
  
-   列挙子インターフェイスをクライアントに返します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [つまり](../../atl/reference/ienumonstlimpl-class.md)  
  
 `CComEnumOnSTL`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
## <a name="example"></a>例  
 次に示すコードでは、作成、列挙子オブジェクトの初期化を処理するジェネリック関数を提供します。  
  
 [!code-cpp[NVC_ATL_COM&#34;](../../atl/codesnippet/cpp/ccomenumonstl-class_1.h)]  
  
 このテンプレート関数を実装するために使用できる、`_NewEnum`次に示すように、コレクション インターフェイスのプロパティ。  
  
 [!code-cpp[NVC_ATL_COM&#35;](../../atl/codesnippet/cpp/ccomenumonstl-class_2.h)]  
  
 このコードを作成、`typedef`の`CComEnumOnSTL`のベクターを公開する`CComVariant`の s、 **IEnumVariant**インターフェイスです。 **CVariantCollection**クラスを特化するだけ**CreateSTLEnumerator**この型の列挙子オブジェクトを使用します。  
  
## <a name="see-also"></a>関連項目  
 [つまり](../../atl/reference/ienumonstlimpl-class.md)   
 [ATLCollections サンプル: ICollectionOnSTLImpl、CComEnumOnSTL、およびカスタム コピー ポリシー クラス](../../visual-cpp-samples.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)   
 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)   
 [つまりクラス](../../atl/reference/ienumonstlimpl-class.md)

