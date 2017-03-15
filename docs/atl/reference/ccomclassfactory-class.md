---
title: "CComClassFactory クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComClassFactory
- CComClassFactory
- ATL::CComClassFactory
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactory class
ms.assetid: e56dacf7-d5c4-4c42-aef4-a86d91981a1b
caps.latest.revision: 20
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c7c488732d7b32248acaaa5c5c9c6a29404c3872
ms.lasthandoff: 02/24/2017

---
# <a name="ccomclassfactory-class"></a>CComClassFactory クラス
このクラスは、実装、 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)インターフェイスです。  
  
## <a name="syntax"></a>構文  
  
```
class CComClassFactory 
   : public IClassFactory,  
     public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComClassFactory::CreateInstance](#createinstance)|指定された CLSID のオブジェクトを作成します。|  
|[CComClassFactory::LockServer](#lockserver)|メモリ内のクラス ファクトリをロックします。|  
  
## <a name="remarks"></a>コメント  
 `CComClassFactory`実装して、 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)インターフェイスで、特定の CLSID のオブジェクトを作成するだけでなく、クラス ファクトリをより迅速に作成する新しいオブジェクトを許可するようにメモリ内のロックのためのメソッドが含まれています。 **IClassFactory**システム レジストリのとを割り当てる、CLSID を登録するすべてのクラスに実装する必要があります。  
  
 ATL オブジェクトから派生することにより、クラス ファクトリを通常取得[示す](../../atl/reference/ccomcoclass-class.md)します。 このクラスには、マクロが含まれています。 [DECLARE_CLASSFACTORY](http://msdn.microsoft.com/library/51a6b925-07c0-4d3a-9174-0b8c808975e4)、宣言`CComClassFactory`既定のクラス ファクトリとして。 この既定をオーバーライドするには、いずれかを指定、 `DECLARE_CLASSFACTORY` *XXX*クラスの定義でマクロです。 たとえば、 [DECLARE_CLASSFACTORY_EX](http://msdn.microsoft.com/library/4181ef00-0f30-4e19-b0ee-e7648062e926)マクロは、クラス ファクトリの指定したクラスを使用します。  
  
 [!code-cpp[NVC_ATL_COM&8;](../../atl/codesnippet/cpp/ccomclassfactory-class_1.h)]  
  
 上記のクラス定義を指定する**CMyClassFactory**オブジェクトの既定のクラス ファクトリとして使用されます。 **CMyClassFactory**から派生する必要があります`CComClassFactory`させ`CreateInstance`します。  
  
 ATL には、クラス ファクトリを宣言するその他の&3; つのマクロが用意されています。  
  
- [DECLARE_CLASSFACTORY2](http://msdn.microsoft.com/library/38a6c969-7297-4bb1-9ba6-1fe2d355b285)を使用して[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)ライセンスの作成を制御します。  
  
- [DECLARE_CLASSFACTORY_AUTO_THREAD](http://msdn.microsoft.com/library/19d7105e-03e8-4412-9f5e-5384c8a5e18f)を使用して[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)、複数のアパートメントにオブジェクトを作成します。  
  
- [DECLARE_CLASSFACTORY_SINGLETON](http://msdn.microsoft.com/library/0e4a3964-c03d-463e-884c-fe3b416db478)を使用して[CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)を構築する&1; つの[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)オブジェクトです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="a-namecreateinstancea--ccomclassfactorycreateinstance"></a><a name="createinstance"></a>CComClassFactory::CreateInstance  
 指定された CLSID のオブジェクトを作成し、このオブジェクトへのインターフェイス ポインターを取得します。  
  
```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```  
  
### <a name="parameters"></a>パラメーター  
 `pUnkOuter`  
 [in]オブジェクトが作成されるかどうか、集計の一部として、`pUnkOuter`外側の不明な使用する必要があります。 それ以外の場合、`pUnkOuter`する必要があります**NULL**します。  
  
 `riid`  
 [in]要求されたインターフェイスの IID です。 場合`pUnkOuter`以外は、 **NULL**、`riid`する必要があります**IID_IUnknown**します。  
  
 `ppvObj`  
 [out]によって識別されるインターフェイス ポインターへのポインター`riid`します。 オブジェクトがこのインターフェイスをサポートしていない場合`ppvObj`に設定されている**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="a-namelockservera--ccomclassfactorylockserver"></a><a name="lockserver"></a>CComClassFactory::LockServer  
 インクリメントおよびデクリメント モジュールのロックを呼び出すことによってカウント**_Module::Lock**と**_Module::Unlock**、それぞれします。  
  
```
STDMETHOD(LockServer)(BOOL fLock);
```  
  
### <a name="parameters"></a>パラメーター  
 `fLock`  
 [in]場合**TRUE**ロック数がインクリメントされます。 それ以外の場合、ロック カウントがデクリメントします。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 **_Module**のグローバル インスタンスを指す[CComModule](../../atl/reference/ccommodule-class.md)またはその派生クラスです。  
  
 呼び出す`LockServer`クライアントは、複数のオブジェクトをすばやく作成できるように、クラス ファクトリを保持できます。  
  
## <a name="see-also"></a>関連項目  
 [CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [クラスの概要](../../atl/atl-class-overview.md)

