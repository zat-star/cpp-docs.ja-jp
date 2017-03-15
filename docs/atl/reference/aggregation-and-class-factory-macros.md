---
title: "集計とクラス ファクトリ マクロ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- class factories, ATL macros
- aggregation [C++], ATL macros
ms.assetid: d99d379a-0eec-481f-8daa-252dac18f163
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 4509f7be36e45cf96a938e30ec0f82ec0c9836b5
ms.lasthandoff: 02/24/2017

---
# <a name="aggregation-and-class-factory-macros"></a>集計とクラス ファクトリ マクロ
これらのマクロは、クラス ファクトリの宣言および集計を制御する方法を提供します。  
  
|||  
|-|-|  
|[DECLARE_AGGREGATABLE](#declare_aggregatable)|オブジェクトができることを宣言します (既定値) を集計します。|  
|[DECLARE_CLASSFACTORY](#declare_classfactory)|宣言するクラス ファクトリ[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)ATL の既定のクラス ファクトリです。|  
|[DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex)|クラス ファクトリをクラス ファクトリ オブジェクトを宣言します。|  
|[DECLARE_CLASSFACTORY2](#declare_classfactory2)|宣言[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)出荷時のクラスにします。|  
|[DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)|宣言[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)出荷時のクラスにします。|  
|[DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)|宣言[CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)出荷時のクラスにします。|  
|[DECLARE_GET_CONTROLLING_UNKNOWN](#declare_get_controlling_unknown)|バーチャル マシンを宣言して`GetControllingUnknown`関数です。|  
|[DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable)|オブジェクトを集約できないことを宣言します。|  
|[集約](#declare_only_aggregatable)|オブジェクトを集約する必要があることを宣言します。|  
|[DECLARE_POLY_AGGREGATABLE](#declare_poly_aggregatable)|外部の"不明"の値をチェックし、集計または集計可能でない、必要に応じて、オブジェクトを宣言します。|  
|[アグリゲート](#declare_protect_final_construct)|内部オブジェクトの構築中に削除されないように、外部オブジェクトを保護します。|  
|[DECLARE_VIEW_STATUS](#declare_view_status)|指定、**な VIEWSTATUS**コンテナーへのフラグ。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
   
##  <a name="a-namedeclareaggregatablea--declareaggregatable"></a><a name="declare_aggregatable"></a>DECLARE_AGGREGATABLE  
 オブジェクトを集計できることを指定します。  
  
```
DECLARE_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]集約可能として定義するクラスの名前。  
  
### <a name="remarks"></a>コメント  
 [示す](../../atl/reference/ccomcoclass-class.md)既定の集計モデルを指定するには、このマクロが含まれています。 この既定をオーバーライドするには、どちらかを指定、 [DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable)または[集約](#declare_only_aggregatable)クラスの定義でマクロです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&121;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]  
  
##  <a name="a-namedeclareclassfactorya--declareclassfactory"></a><a name="declare_classfactory"></a>DECLARE_CLASSFACTORY  
 宣言[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)出荷時のクラスにします。  
  
```
DECLARE_CLASSFACTORY()
```  
  
### <a name="remarks"></a>コメント  
 [示す](../../atl/reference/ccomcoclass-class.md)このマクロを使って、オブジェクトの既定のクラス ファクトリを宣言します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM&#55;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_2.h)]  
  
##  <a name="a-nameccomclassfactoryclassa--ccomclassfactory-class"></a><a name="ccomclassfactory_class"></a>CComClassFactory クラス  
 このクラスは、実装、 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)インターフェイスです。  
  
```
class CComClassFactory : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
### <a name="remarks"></a>コメント  
 `CComClassFactory`実装して、 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)インターフェイスで、特定の CLSID のオブジェクトを作成するだけでなく、クラス ファクトリをより迅速に作成する新しいオブジェクトを許可するようにメモリ内のロックのためのメソッドが含まれています。 **IClassFactory**システム レジストリのとを割り当てる、CLSID を登録するすべてのクラスに実装する必要があります。  
  
 ATL オブジェクトから派生することにより、クラス ファクトリを通常取得[示す](../../atl/reference/ccomcoclass-class.md)します。 このクラスには、マクロが含まれています。 [DECLARE_CLASSFACTORY](#declare_classfactory)、宣言`CComClassFactory`既定のクラス ファクトリとして。 この既定をオーバーライドするには、いずれかを指定、 `DECLARE_CLASSFACTORY` *XXX*クラスの定義でマクロです。 たとえば、 [DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex)マクロは、クラス ファクトリの指定したクラスを使用します。  
  
 [!code-cpp[NVC_ATL_COM&8;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]  
  
 上記のクラス定義を指定する**CMyClassFactory**オブジェクトの既定のクラス ファクトリとして使用されます。 **CMyClassFactory**から派生する必要があります`CComClassFactory`させ`CreateInstance`します。  
  
 ATL には、クラス ファクトリを宣言するその他の&3; つのマクロが用意されています。  
  
- [DECLARE_CLASSFACTORY2](#declare_classfactory2)を使用して[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)ライセンスの作成を制御します。  
  
- [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)を使用して[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)、複数のアパートメントにオブジェクトを作成します。  
  
- [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)を使用して[CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)を構築する&1; つの[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)オブジェクトです。  
  
##  <a name="a-namedeclareclassfactoryexa--declareclassfactoryex"></a><a name="declare_classfactory_ex"></a>DECLARE_CLASSFACTORY_EX  
 宣言`cf`出荷時のクラスにします。  
  
```
DECLARE_CLASSFACTORY_EX( cf )
```  
  
### <a name="parameters"></a>パラメーター  
 `cf`  
 [in]クラス ファクトリ オブジェクトを実装するクラスの名前。  
  
### <a name="remarks"></a>コメント  
 `cf`パラメーターから派生する必要があります[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)させ、`CreateInstance`メソッドです。  
  
 [示す](../../atl/reference/ccomcoclass-class.md)を含む、 [DECLARE_CLASSFACTORY](#declare_classfactory)マクロで、指定`CComClassFactory`既定のクラス ファクトリとして。 ただし、含めることによって、`DECLARE_CLASSFACTORY_EX`マクロ オブジェクトのクラス定義では、この既定の設定をオーバーライドします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM&8;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]  
  
##  <a name="a-namedeclareclassfactory2a--declareclassfactory2"></a><a name="declare_classfactory2"></a>DECLARE_CLASSFACTORY2  
 宣言[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)出荷時のクラスにします。  
  
```
DECLARE_CLASSFACTORY2( lic )
```  
  
### <a name="parameters"></a>パラメーター  
 *使用許諾契約書*  
 [in]実装するクラス`VerifyLicenseKey`、 `GetLicenseKey`、および`IsLicenseValid`です。  
  
### <a name="remarks"></a>コメント  
 [示す](../../atl/reference/ccomcoclass-class.md)を含む、 [DECLARE_CLASSFACTORY](#declare_classfactory)マクロで、指定[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)既定のクラス ファクトリとして。 ただし、含めることによって、`DECLARE_CLASSFACTORY2`マクロ オブジェクトのクラス定義では、この既定の設定をオーバーライドします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM&2;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]  
  
##  <a name="a-nameccomclassfactory2classa--ccomclassfactory2-class"></a><a name="ccomclassfactory2_class"></a>CComClassFactory2 クラス  
 このクラスは、実装、 [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720)インターフェイスです。  
  
```
template <class license>
class  CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```    
  
### <a name="parameters"></a>パラメーター  
 *ライセンス*  
 次の静的関数を実装するクラス。  
  
- **静的な BOOL VerifyLicenseKey (BSTR** `bstr` **) です。**  
  
- **静的な BOOL GetLicenseKey (DWORD** `dwReserved` **、BSTR\* ** `pBstr` **) です。**  
  
- **静的な BOOL IsLicenseValid ();**  
  
### <a name="remarks"></a>コメント  
 `CComClassFactory2`実装して、 [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720)拡張機能であるインターフェイスの[IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)します。 **IClassFactory2**コントロール オブジェクトを介して、ライセンスを作成します。 ライセンスのあるコンピューターで実行するクラス ファクトリと、ランタイム ライセンス キーを指定できます。 このライセンス キーには、コンピューターのフル ライセンスが存在しないときにオブジェクトをインスタンス化するアプリケーションことができます。  
  
 ATL オブジェクトから派生することにより、クラス ファクトリを通常取得[示す](../../atl/reference/ccomcoclass-class.md)します。 このクラスには、マクロが含まれています。 [DECLARE_CLASSFACTORY](#declare_classfactory)、宣言[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)既定のクラス ファクトリとして。 使用する`CComClassFactory2`、指定、 [DECLARE_CLASSFACTORY2](#declare_classfactory2)オブジェクトのクラスの定義でマクロです。 例:  
  
 [!code-cpp[NVC_ATL_COM&2;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]  
  
 **CMyLicense**、テンプレート パラメーターを`CComClassFactory2`、静的関数を実装する必要があります`VerifyLicenseKey`、 `GetLicenseKey`、および`IsLicenseValid`です。 簡単なライセンス クラスの例を次に示します。  
  
 [!code-cpp[NVC_ATL_COM&3;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_5.h)]  
  
 `CComClassFactory2`2 つの派生**CComClassFactory2Base**と*ライセンス*します。 **CComClassFactory2Base**から派生、 **IClassFactory2**と**CComObjectRootEx\< CComGlobalsThreadModel >**します。  
  
##  <a name="a-namedeclareclassfactoryautothreada--declareclassfactoryautothread"></a><a name="declare_classfactory_auto_thread"></a>DECLARE_CLASSFACTORY_AUTO_THREAD  
 宣言[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)出荷時のクラスにします。  
  
```
DECLARE_CLASSFACTORY_AUTO_THREAD()
```  
  
### <a name="remarks"></a>コメント  
 [示す](../../atl/reference/ccomcoclass-class.md)を含む、 [DECLARE_CLASSFACTORY](#declare_classfactory)マクロで、指定[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)既定のクラス ファクトリとして。 ただし、含めることによって、`DECLARE_CLASSFACTORY_AUTO_THREAD`マクロ オブジェクトのクラス定義では、この既定の設定をオーバーライドします。  
  
 アウト プロセス サーバーの場合) の「複数のアパートメント内でオブジェクトを作成するときに追加`DECLARE_CLASSFACTORY_AUTO_THREAD`をクラスにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM&9;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]  
  
##  <a name="a-nameccomclassfactoryautothreadclassa--ccomclassfactoryautothread-class"></a><a name="ccomclassfactoryautothread_class"></a>CComClassFactoryAutoThread クラス  
 このクラスは、実装、 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)インターフェイス、およびオブジェクトが複数のアパートメント内に作成することができます。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
```
class CComClassFactoryAutoThread : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
### <a name="remarks"></a>コメント  
 `CComClassFactoryAutoThread`ような[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)はオブジェクトを複数のアパートメント内で作成できるようにします。 このサポートを利用する、EXE モジュールから派生させる[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)します。  
  
 ATL オブジェクトから派生することにより、クラス ファクトリを通常取得[示す](../../atl/reference/ccomcoclass-class.md)します。 このクラスには、マクロが含まれています。 [DECLARE_CLASSFACTORY](#declare_classfactory)、宣言[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)既定のクラス ファクトリとして。 使用する`CComClassFactoryAutoThread`、指定、 [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)オブジェクトのクラスの定義でマクロです。 例:  
  
 [!code-cpp[NVC_ATL_COM&9;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]  
  
##  <a name="a-namedeclareclassfactorysingletona--declareclassfactorysingleton"></a><a name="declare_classfactory_singleton"></a>DECLARE_CLASSFACTORY_SINGLETON  
 宣言[CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)出荷時のクラスにします。  
  
```
DECLARE_CLASSFACTORY_SINGLETON( obj )
```  
  
### <a name="parameters"></a>パラメーター  
 `obj`  
 [in]クラスのオブジェクトの名前。  
  
### <a name="remarks"></a>コメント  
 [示す](../../atl/reference/ccomcoclass-class.md)を含む、 [DECLARE_CLASSFACTORY](#declare_classfactory)マクロで、指定[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)既定のクラス ファクトリとして。 ただし、含めることによって、`DECLARE_CLASSFACTORY_SINGLETON`マクロ オブジェクトのクラス定義では、この既定の設定をオーバーライドします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM&#10;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]  
  
##  <a name="a-nameccomclassfactorysingletonclassa--ccomclassfactorysingleton-class"></a><a name="ccomclassfactorysingleton_class"></a>CComClassFactorySingleton クラス  
 このクラスから派生[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を使用して[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)を&1; つのオブジェクトを構築します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 作成したクラス。  
  
 `CComClassFactorySingleton`派生した[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を使用して[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)を&1; つのオブジェクトを構築します。 呼び出すたび、`CreateInstance`メソッドは、単にインターフェイス ポインターに対して、このオブジェクトを照会します。  
  
### <a name="remarks"></a>コメント  
 ATL オブジェクトから派生することにより、クラス ファクトリを通常取得[示す](../../atl/reference/ccomcoclass-class.md)します。 このクラスには、マクロが含まれています。 [DECLARE_CLASSFACTORY](#declare_classfactory)、宣言`CComClassFactory`既定のクラス ファクトリとして。 使用する`CComClassFactorySingleton`、指定、 [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)オブジェクトのクラスの定義でマクロです。 例:  
  
 [!code-cpp[NVC_ATL_COM&#10;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]  
  
##  <a name="a-namedeclaregetcontrollingunknowna--declaregetcontrollingunknown"></a><a name="declare_get_controlling_unknown"></a>DECLARE_GET_CONTROLLING_UNKNOWN  
 仮想関数を宣言`GetControllingUnknown`します。  
  
```
DECLARE_GET_CONTROLLING_UNKNOWN()
```  
  
### <a name="remarks"></a>コメント  
 コンパイラ エラー メッセージが表示された場合、このマクロをオブジェクトに追加`GetControllingUnknown`は定義されていません (たとえば、 **CComAggregateCreator**)。  
  
##  <a name="a-namedeclarenotaggregatablea--declarenotaggregatable"></a><a name="declare_not_aggregatable"></a>DECLARE_NOT_AGGREGATABLE  
 オブジェクトを集約できないことを指定します。  
  
```
DECLARE_NOT_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]集計可能でないとして定義するクラスのオブジェクトの名前。  
  
### <a name="remarks"></a>コメント  
 `DECLARE_NOT_AGGREGATABLE`原因`CreateInstance`エラーを返すよう ( **CLASS_E_NOAGGREGATION**) 試みられた場合、オブジェクトに集計します。  
  
 既定では、[示す](../../atl/reference/ccomcoclass-class.md)を含む、 [DECLARE_AGGREGATABLE](#declare_aggregatable)マクロで、オブジェクトを集計できることを指定します。 この既定の動作をオーバーライドするには`DECLARE_NOT_AGGREGATABLE`クラス定義にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&121;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]  
  
##  <a name="a-namedeclareonlyaggregatablea--declareonlyaggregatable"></a><a name="declare_only_aggregatable"></a>集約  
 オブジェクトを集約する必要があることを指定します。  
  
```
DECLARE_ONLY_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]集計可能でのみとして定義するクラスのオブジェクトの名前。  
  
### <a name="remarks"></a>コメント  
 `DECLARE_ONLY_AGGREGATABLE`エラーが発生 ( **E_FAIL**) しようとした場合に**CoCreate**オブジェクトとして。  
  
 既定では、[示す](../../atl/reference/ccomcoclass-class.md)を含む、 [DECLARE_AGGREGATABLE](#declare_aggregatable)マクロで、オブジェクトを集計できることを指定します。 この既定の動作をオーバーライドするには`DECLARE_ONLY_AGGREGATABLE`クラス定義にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&125;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_8.h)]  
  
##  <a name="a-namedeclarepolyaggregatablea--declarepolyaggregatable"></a><a name="declare_poly_aggregatable"></a>DECLARE_POLY_AGGREGATABLE  
 指定のインスタンス**CComPolyObject \< ** *x* ** > **オブジェクトの作成時に作成します。  
  
```
DECLARE_POLY_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]集計または集計可能でないとして定義するクラスのオブジェクトの名前。  
  
### <a name="remarks"></a>コメント  
 作成時に、外部の"不明"の値がチェックされます。 ある場合**NULL**、 **IUnknown**非集約オブジェクトを実装します。 外側の unknown がない場合**NULL**、 **IUnknown**集約オブジェクトの実装です。  
  
 使用する利点`DECLARE_POLY_AGGREGATABLE`両方を避けることは、`CComAggObject`と`CComObject`モジュールで、集計データおよび非集計の状況に対処します。 単一の`CComPolyObject`オブジェクトがどちらの場合も、処理します。 つまり、モジュールで、vtable の&1; つだけのコピーと関数の&1; つのコピーが存在します。 Vtable のサイズが大きい場合は、モジュールのサイズを大幅に縮小このできます。 ただし、vtable が小さい場合を使用して`CComPolyObject`集計または非集約オブジェクトは、最適化されていないために、モジュールのサイズを少しだけ多めにつながると`CComAggObject`と`CComObject`です。  
  
 `DECLARE_POLY_AGGREGATABLE`マクロはフル コントロールを作成する、ATL コントロール ウィザードを使用する場合、自動的に、オブジェクトで宣言します。  
  
##  <a name="a-namedeclareprotectfinalconstructa--declareprotectfinalconstruct"></a><a name="declare_protect_final_construct"></a>アグリゲート  

 削除されるオブジェクトを保護する (中に[FinalConstruct](ccomobjectrootex-class.md#finalconstruct)) 内部オブジェクトが、カウントを 0 にデクリメントして参照カウントをインクリメントします。  
  
```
DECLARE_PROTECT_FINAL_CONSTRUCT()
```  
  
##  <a name="a-namedeclareviewstatusa--declareviewstatus"></a><a name="declare_view_status"></a>DECLARE_VIEW_STATUS  
 指定する、ATL の ActiveX コントロールのコントロール クラスでこのマクロを置き、**な VIEWSTATUS**コンテナーへのフラグ。  
  
```
DECLARE_VIEW_STATUS( statusFlags )
```  
  
### <a name="parameters"></a>パラメーター  
 `statusFlags`  
 [in]**な VIEWSTATUS**フラグ。 参照してください[な VIEWSTATUS](http://msdn.microsoft.com/library/windows/desktop/ms687201)フラグの一覧にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&126;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_9.h)]  
  
## <a name="see-also"></a>関連項目  
 [マクロ](../../atl/reference/atl-macros.md)

