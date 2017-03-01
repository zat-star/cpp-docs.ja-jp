---
title: "クラスを示す |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComCoClass
- ATL.CComCoClass
- ATL::CComCoClass
dev_langs:
- C++
helpviewer_keywords:
- CComCoClass class
- aggregation [C++], aggregation models
ms.assetid: 67cfefa4-8df9-47fa-ad58-2d1a1ae25762
caps.latest.revision: 19
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
ms.openlocfilehash: 6201051a38ac65788086dcf7ee4c3f3441988e71
ms.lasthandoff: 02/24/2017

---
# <a name="ccomcoclass-class"></a>示すクラス
このクラスは、クラスのインスタンスを作成し、そのプロパティを取得するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
template <class T, const CLSID* pclsid = &CLSID_NULL>  
class CComCoClass
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラスに、`CComCoClass`です。  
  
 *pclsid の値*  
 オブジェクトの CLSID へのポインター。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[あって](#createinstance)|(静的)クラスとインターフェイスのクエリのインスタンスを作成します。|  
|[CComCoClass::Error](#error)|(静的)詳細なエラー情報をクライアントに返します。|  
|[CComCoClass::GetObjectCLSID](#getobjectclsid)|(静的)オブジェクトのクラス識別子を返します。|  
|[CComCoClass::GetObjectDescription](#getobjectdescription)|(静的)オブジェクトの説明を返すようにオーバーライドします。|  
  
## <a name="remarks"></a>コメント  
 `CComCoClass`オブジェクトの CLSID を取得する、エラー情報を設定すると、クラスのインスタンスを作成するには、メソッドを提供します。 登録されている任意のクラス、[オブジェクト マップ](http://msdn.microsoft.com/en-us/b57619cc-534f-4b8f-bfd4-0c12f937202f)から派生する必要があります`CComCoClass`します。  
  
 `CComCoClass`また、オブジェクトの既定のクラス ファクトリと集計モデルを定義します。 `CComCoClass`次の&2; つのマクロを使用します。  
  
- [DECLARE_CLASSFACTORY](http://msdn.microsoft.com/library/51a6b925-07c0-4d3a-9174-0b8c808975e4)宣言するクラス ファクトリ[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)します。  
  
- [DECLARE_AGGREGATABLE](http://msdn.microsoft.com/library/e7e568d7-04e0-4226-b5dc-224deed229ab)オブジェクトを集計できることを宣言します。  
  
 これらの既定値のいずれかのクラスの定義で別のマクロを指定することによってオーバーライドできます。 たとえば、使用する[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)の代わりに`CComClassFactory`、指定、 [DECLARE_CLASSFACTORY2](http://msdn.microsoft.com/library/38a6c969-7297-4bb1-9ba6-1fe2d355b285)マクロ。  
  
 [!code-cpp[NVC_ATL_COM&2;](../../atl/codesnippet/cpp/ccomcoclass-class_1.h)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="a-namecreateinstancea--ccomcoclasscreateinstance"></a><a name="createinstance"></a>あって  
 これらを使用して`CreateInstance`COM のインスタンスを作成する関数オブジェクトし、COM API を使用せずにインターフェイス ポインターを取得します。  
  
```
template <class  Q>
static HRESULT CreateInstance( Q** pp);

template <class  Q>
static HRESULT CreateInstance(IUnknown* punkOuter, Q** pp);
```  
  
### <a name="parameters"></a>パラメーター  
 `Q`  
 COM インターフェイス経由で返される`pp`です。  
  
 *punkOuter*  
 [in]外側の不明なまたは集計の不明を制御します。  
  
 `pp`  
 [out]作成が成功した場合は、要求されたインターフェイス ポインターを受け取るポインター変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。 参照してください[CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]可能な戻り値の詳細についてです。  
  
### <a name="remarks"></a>コメント  
 この関数の最初のオーバー ロードを使用して一般的なオブジェクトの作成の作成されるオブジェクトを集計する必要がある場合は、2 番目のオーバー ロードを使用します。  
  
 必須の COM オブジェクトを実装する ATL クラス (最初のテンプレート パラメーターとして使用されるクラスは、[示す](../../atl/reference/ccomcoclass-class.md)) 呼び出し元のコードと同じプロジェクトである必要があります。 COM オブジェクトの作成は、この ATL に登録されているクラス ファクトリで実行されます。  
  
 これらの関数を使用して外部で作成可能になる妨げとしているオブジェクトの作成に役立つ、[役立つ](http://msdn.microsoft.com/library/abdc093c-6502-42de-8419-b7ebf45299d1)マクロです。 これらも効率を上げるのために COM API を避けたい場合に便利です。  
  
 注意してください、インターフェイス`Q`を使用して取得できる IID 関連付けられている必要があります、 [_ _uuidof](../../cpp/uuidof-operator.md)演算子。  
  
### <a name="example"></a>例  
 次の例で`CDocument`ATL ウィザードで生成されたクラスから派生`CComCoClass`を実装する、 **IDocument**インターフェイスです。 オブジェクト マップに、クラスが登録されている、`OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO`マクロ クライアントを使用してドキュメントのインスタンスを作成できないように[CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615)します。 `CApplication`ドキュメント クラスのインスタンスを作成する独自の COM インターフェイスの&1; つのメソッドを提供するコクラスです。 いかに簡単かを示す次のコードを使用するドキュメント クラスのインスタンスを作成すること、`CreateInstance`から継承されたメンバー、`CComCoClass`基本クラスです。  
  
 [!code-cpp[NVC_ATL_COM&#11;](../../atl/codesnippet/cpp/ccomcoclass-class_2.cpp)]  
  
##  <a name="a-nameerrora--ccomcoclasserror"></a><a name="error"></a>CComCoClass::Error  
 この静的関数、`IErrorInfo`をクライアントにエラー情報を提供するインターフェイスです。  
  
```
static HRESULT WINAPI Error(
    LPCOLESTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCOLESTR lpszDesc,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCSTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCSTR lpszDesc,
    DWORD dwHelpID,
    LPCSTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    UINT nID,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance ());

static HRESULT Error(
    UINT nID,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszDesc`  
 [in]エラーを説明する文字列。 Unicode バージョンの`Error`ことを指定`lpszDesc`型**LPCOLESTR**; ANSI バージョンの種類を指定する`LPCSTR`です。  
  
 `iid`  
 [in]エラーを定義するインターフェイスの IID または`GUID_NULL`(既定値)、エラーが、オペレーティング システムによって定義されている場合。  
  
 `hRes`  
 [in]`HRESULT`する呼び出し元に返されます。 既定値は 0 です。 詳細については`hRes`、「解説」を参照してください。  
  
 `nID`  
 [in]エラーの説明文字列が格納されているリソースの識別子です。 この値が範囲の 0x0200 から 0 xffff の間にする必要があります。 デバッグ ビルドでは、 **ASSERT**になります`nID`有効な文字列のインデックスは作成されません。 リリース ビルドでエラーを説明する文字列を「不明なエラー」に設定されます。  
  
 `dwHelpID`  
 [in]エラーのヘルプ コンテキスト id。  
  
 `lpszHelpFile`  
 [in]パスと、エラーを説明するヘルプ ファイルの名前。  
  
 `hInst`  
 [in]リソースへのハンドル。 このパラメーターは、既定では、 **_AtlModule::GetResourceInstance**ここで、 **_AtlModule**のグローバル インスタンスは、[不要](../../atl/reference/catlmodule-class.md)します。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。 詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>コメント  
 呼び出す`Error`、オブジェクトを実装する必要があります、`ISupportErrorInfo Interface`インターフェイスです。  
  
 場合、`hRes`パラメーターは、0 以外、`Error`の値を返します`hRes`します。 場合`hRes`が&0; の場合、最初の&4; つのバージョンの`Error`返す`DISP_E_EXCEPTION`します。 最後の 2 つのバージョンは、マクロの結果を返す**MAKE_HRESULT (1, FACILITY_ITF、** `nID` **)**します。  
  
##  <a name="a-namegetobjectclsida--ccomcoclassgetobjectclsid"></a><a name="getobjectclsid"></a>CComCoClass::GetObjectCLSID  
 一貫性のあるオブジェクトの CLSID を取得する方法を提供します。  
  
```
static const CLSID& WINAPI GetObjectCLSID();
```  
  
### <a name="return-value"></a>戻り値  
 オブジェクトのクラスの識別子です。  
  
##  <a name="a-namegetobjectdescriptiona--ccomcoclassgetobjectdescription"></a><a name="getobjectdescription"></a>CComCoClass::GetObjectDescription  
 この静的関数は、クラス オブジェクトのテキストの説明を取得します。  
  
```
static LPCTSTR WINAPI GetObjectDescription();
```  
  
### <a name="return-value"></a>戻り値  
 クラス オブジェクトの説明です。  
  
### <a name="remarks"></a>コメント  
 既定の実装**NULL**します。 このメソッドはオーバーライドすることができます、 [DECLARE_OBJECT_DESCRIPTION](http://msdn.microsoft.com/library/32ac881c-97b1-44e2-a017-0e23eb99ac93)マクロです。 例:  
  
 [!code-cpp[NVC_ATL_COM&#12;](../../atl/codesnippet/cpp/ccomcoclass-class_3.h)]  
  
 `GetObjectDescription`によって呼び出される**IComponentRegistrar::GetComponents**します。 **IComponentRegistrar**オートメーション インターフェイスを登録し、DLL 内の個々 のコンポーネントの登録を解除することができます。 ATL プロジェクト ウィザードを使用してコンポーネントの登録オブジェクトを作成するときに、ウィザードは自動的に実装、 **IComponentRegistrar**インターフェイスです。 **IComponentRegistrar**通常は Microsoft Transaction Server で使用します。  
  
 ATL プロジェクト ウィザードの詳細については、記事を参照してください。 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

