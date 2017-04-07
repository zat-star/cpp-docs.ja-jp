---
title: "CComObjectRootEx クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComObjectRootEx
- ATLCOM/ATL::CComObjectRootEx
- ATLCOM/ATL::CComObjectRootEx
- ATLCOM/ATL::InternalAddRef
- ATLCOM/ATL::InternalRelease
- ATLCOM/ATL::Lock
- ATLCOM/ATL::Unlock
- ATLCOM/ATL::FinalConstruct
- ATLCOM/ATL::FinalRelease
- ATLCOM/ATL::OuterAddRef
- ATLCOM/ATL::OuterQueryInterface
- ATLCOM/ATL::OuterRelease
- ATLCOM/ATL::InternalQueryInterface
- ATLCOM/ATL::ObjectMain
- ATLCOM/ATL::m_dwRef
- ATLCOM/ATL::m_pOuterUnknown
dev_langs:
- C++
helpviewer_keywords:
- reference counting
ms.assetid: 894a3d7c-2daf-4fd0-8fa4-e6a05bcfb631
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: f3a6d26ddb4f612824f959ca3046531dc3bbf2a9
ms.lasthandoff: 02/24/2017

---
# <a name="ccomobjectrootex-class"></a>CComObjectRootEx クラス
このクラスは、非集計と集計の両方のオブジェクトのオブジェクト参照カウントの管理を処理するメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
template<class ThreadModel>  
class CComObjectRootEx : public CComObjectRootBase
```  
  
#### <a name="parameters"></a>パラメーター  
 `ThreadModel`  
 このクラスは、目的のスレッド処理モデルのメソッドとして実装されます。 明示的に設定して、スレッディング モデルを選択できます`ThreadModel`に[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)、 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)、または[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)します。 設定して、サーバーの既定のスレッド モデルを受け取ることができます`ThreadModel`に[CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)または[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)します。  

  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[CComObjectRootEx](#ccomobjectrootex)|コンストラクターです。|  
|[InternalAddRef](#internaladdref)|非集約オブジェクトの参照カウントをインクリメントします。|  
|[InternalRelease](#internalrelease)|非集約オブジェクトの参照カウントをデクリメントします。|  
|[ロック](#lock)|スレッド モデルがマルチ スレッドの場合は、クリティカル セクション オブジェクトの所有権を取得します。|  
|[ロックを解除します。](#unlock)|スレッド モデルがマルチ スレッドの場合は、クリティカル セクション オブジェクトの所有権を解放します。|  
  
### <a name="ccomobjectrootbase-methods"></a>CComObjectRootBase メソッド  
  
|||  
|-|-|  
|[作成しました。](#finalconstruct)|オブジェクトに必要な初期化を実行するクラスでオーバーライドします。|  
|[FinalRelease](#finalrelease)|オブジェクトに必要なクリーンアップを実行するクラスでオーバーライドします。|  
|[OuterAddRef](#outeraddref)|集約オブジェクトの参照カウントをインクリメントします。|  
|[OuterQueryInterface](#outerqueryinterface)|デリゲートを外部**IUnknown**集約オブジェクトのです。|  
|[OuterRelease](#outerrelease)|集約オブジェクトの参照カウントをデクリメントします。|  
  
### <a name="static-functions"></a>静的関数  
  
|||  
|-|-|  
|[InternalQueryInterface](#internalqueryinterface)|デリゲート、 **IUnknown**の非集約オブジェクトです。|  
|[ObjectMain](#objectmain)|モジュールの初期化と派生クラスのオブジェクト マップに一覧表示の終了時に呼び出されます。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|[m_dwRef](#m_dwref)|`m_pOuterUnknown`共用体の一部です。 参照カウントを保持するために、オブジェクトが集計されない場合に使用される`AddRef`と**リリース**します。|  
|[アグリゲート](#m_pouterunknown)|`m_dwRef`共用体の一部です。 外部の"不明"にポインターを保持するために集約オブジェクトの場合に使用されます。|  
  
## <a name="remarks"></a>コメント  
 `CComObjectRootEx`非集計と集計の両方のオブジェクトのオブジェクト参照カウントの管理を処理します。 オブジェクトは集計されていないと、オブジェクトが集約されている場合は、外部の"不明"にポインターを置く場合は、オブジェクトの参照カウントを保持します。 集約オブジェクトの`CComObjectRootEx`メソッドは、構成する際、内部オブジェクトのエラーを処理するために使用でき、内部のインターフェイスがリリースされたときに削除されないように、外部オブジェクトまたは内部のオブジェクトを保護するのには削除されます。  
  
 COM サーバーを実装するクラスを継承する必要が`CComObjectRootEx`または[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)します。  
  
 クラス定義を指定する場合、 [DECLARE_POLY_AGGREGATABLE](http://msdn.microsoft.com/library/7569e738-cfbc-4404-ba1d-78dcefa3bdb3)マクロのインスタンスを作成する ATL **CComPolyObject\<CYourClass >**ときに**IClassFactory::CreateInstance**が呼び出されます。 作成時に、外部の"不明"の値がチェックされます。 ある場合**NULL**、 **IUnknown**非集約オブジェクトを実装します。 外側の unknown がない場合**NULL**、 **IUnknown**集約オブジェクトの実装です。  
  
 クラスが指定されていない場合、`DECLARE_POLY_AGGREGATABLE`マクロのインスタンスを作成する ATL **CAggComObject\<CYourClass >**集約オブジェクトのインスタンスの**と\<CYourClass >**の非集約オブジェクトです。  
  
 使用する利点`CComPolyObject`両方を避けることは、`CComAggObject`と`CComObject`モジュールで、集計データおよび非集計の状況に対処します。 単一の`CComPolyObject`オブジェクトがどちらの場合も、処理します。 そのため、vtable の&1; つだけコピーと関数の&1; つのコピーは、モジュール内に存在します。 Vtable のサイズが大きい場合は、モジュールのサイズを大幅に縮小このできます。 ただし、vtable が小さい場合を使用して`CComPolyObject`集計または非集約オブジェクトは、最適化されていないために、モジュールのサイズを少しだけ多めにつながると`CComAggObject`と`CComObject`です。  
  
 オブジェクトを集約される場合[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)によって実装される`CComAggObject`または`CComPolyObject`です。 これらのクラスに委任`QueryInterface`、`AddRef`と**リリース**への呼び出し`CComObjectRootEx`の`OuterQueryInterface`、 `OuterAddRef`、および`OuterRelease`を外部の"不明"に転送します。 通常をオーバーライドする`CComObjectRootEx::FinalConstruct`、集約オブジェクトを作成し、オーバーライドするクラスで`CComObjectRootEx::FinalRelease`を解放するオブジェクトを集約します。  
  
 場合は、オブジェクトは集計されません。 **IUnknown**によって実装される`CComObject`または`CComPolyObject`です。 この場合、呼び出しを`QueryInterface`、`AddRef`と**リリース**に委任`CComObjectRootEx`の`InternalQueryInterface`、 `InternalAddRef`、および`InternalRelease`実際の操作を実行します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="ccomobjectrootex"></a>CComObjectRootEx::CComObjectRootEx  
 コンス トラクターでは、参照カウントを 0 に初期化します。  
  
```
CComObjectRootEx();
```  
  
##  <a name="finalconstruct"></a>CComObjectRootEx::FinalConstruct  
 このメソッドは、作成したオブジェクトに必要な初期化を実行する派生クラスでオーバーライドできます。  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>戻り値  
 返す`S_OK`成功時または標準エラーのいずれかに`HRESULT`値。  
  
### <a name="remarks"></a>コメント  
 既定では、`CComObjectRootEx::FinalConstruct`を返すだけ`S_OK`します。  
  
 初期化を実行する利点は`FinalConstruct`クラスのコンス トラクターではなく。  
  
-   コンス トラクターからステータス コードを返すことはできませんが、返すことができます、`HRESULT`の`FinalConstruct`の値を返します。 クラスのオブジェクトは作成時に ATL によって提供される標準のクラス ファクトリを使用して、この戻り値の詳細なエラー情報を入力することができます、COM クライアントに反映されます。  
  
-   クラスのコンス トラクターから仮想関数のメカニズムを通じて仮想関数を呼び出すことはできません。 継承階層で、その時点で定義されている中に、静的に解決される関数の呼び出し、結果をクラスのコンス トラクターから仮想関数を呼び出します。 純粋仮想関数への呼び出しは、リンカー エラーが発生します。  
  
     継承階層の最派生クラスではなく、一部の機能を提供する ATL によって提供される派生クラスに依存します。 高い確率で、初期化は、(これは特に、クラスのオブジェクトが他のオブジェクトを集計する必要がある場合) そのクラスによって提供される機能を使用する必要がありますが、クラスのコンス トラクターに、これらの機能にアクセスすることはできません。 クラスの構築用のコードは、最派生クラスが完全に構築される前に実行されます。  
  
     ただし、`FinalConstruct`は、後、ほとんどの派生クラスが仮想関数を呼び出すし、ATL で提供されて参照カウントの実装を使用することができますに完全に構築の直後に呼び出されます  
  
### <a name="example"></a>例  
 通常から派生したクラスでは、このメソッドをオーバーライド`CComObjectRootEx`いずれかを作成するには、オブジェクトを集約します。 例:  
  
 [!code-cpp[NVC_ATL_COM&#40;](../../atl/codesnippet/cpp/ccomobjectrootex-class_1.h)]  
  
 構築に失敗した場合は、エラーを返すことができます。 マクロを使用することもできます。[アグリゲート](http://msdn.microsoft.com/library/2d2e5ddc-057a-43ca-87c8-d3477a8193a0)されてから、外部のオブジェクトを保護する場合、作成中に、内部オブジェクト カウントをインクリメント デクリメントして参照カウントを 0 には削除されます。  
  
 集計を作成する一般的な方法を次に示します。  
  
-   追加、 **IUnknown**クラスへのポインターをそのオブジェクトを初期化**NULL**コンス トラクターでします。  
  
-   オーバーライド`FinalConstruct`集計を作成します。  
  
-   使用して、 **IUnknown**ポインターへのパラメーターとして定義されている、[で定義](http://msdn.microsoft.com/library/c671fa40-a57b-4797-ae88-c9762dabd4dc)マクロです。  
  
-   オーバーライド`FinalRelease`を解放する、 **IUnknown**ポインター。  
  
##  <a name="finalrelease"></a>CComObjectRootEx::FinalRelease  
 このメソッドは、作成したオブジェクトに必要なクリーンアップを実行する派生クラスでオーバーライドできます。  
  
```
void FinalRelease();
```  
  
### <a name="remarks"></a>コメント  
 既定では、`CComObjectRootEx::FinalRelease`何も行われません。  
  
 クリーンアップは実行`FinalRelease`は、オブジェクトの位置を表すポイントにも引き続き完全に構築するために、クラスのデストラクターにコードを追加することをお勧め`FinalRelease`が呼び出されます。 これにより、最派生クラスによって提供されるメソッドを安全にアクセスできます。 これは、削除する前に、集約オブジェクトを解放するために特に重要です。  
  
##  <a name="internaladdref"></a>CComObjectRootEx::InternalAddRef  
 1 には、非集約オブジェクトの参照カウントをインクリメントします。  
  
```
ULONG InternalAddRef();
```  
  
### <a name="return-value"></a>戻り値  
 診断に役立ちますしテスト可能性のある値。  
  
### <a name="remarks"></a>コメント  
 スレッド モデルがマルチ スレッドの場合**InterlockedIncrement**を複数のスレッドが同時に、参照カウントを変更することを防ぐために使用します。  
  
##  <a name="internalqueryinterface"></a>CComObjectRootEx::InternalQueryInterface  
 要求されたインターフェイスへのポインターを取得します。  
  
```
static HRESULT InternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `pThis`  
 [in]公開されるインターフェイスの COM マップを含んでいるオブジェクトへのポインター`QueryInterface`します。  
  
 `pEntries`  
 [in]ポインター、 **_ATL_INTMAP_ENTRY**構造体の使用可能なインターフェイス マップにアクセスします。  
  
 `iid`  
 [in]要求されているインターフェイスの GUID です。  
  
 `ppvObject`  
 [out]指定されたインターフェイス ポインターへのポインター `iid`、または**NULL**インターフェイスが見つからない場合。  
  
### <a name="return-value"></a>戻り値  
 標準の`HRESULT`値。  
  
### <a name="remarks"></a>コメント  
 `InternalQueryInterface` が処理するのは、COM マップ テーブル内のインターフェイスのみです。 オブジェクトを集約すると場合、`InternalQueryInterface`外部への委任しません。 インターフェイスを入力するには、マクロを使用した、COM マップ テーブルに[COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00)またはそのバリエーションの&1; つです。  
  
##  <a name="internalrelease"></a>CComObjectRootEx::InternalRelease  
 1 で、非集約オブジェクトの参照カウントをデクリメントします。  
  
```
ULONG InternalRelease();
```  
  
### <a name="return-value"></a>戻り値  
 どちらも非デバッグし、デバッグ ビルド、テストや診断に使用できる値を返します。 参照カウントになるが、使用すると、オペレーティング システムなどのさまざまな要因場合や、ことはできません。 正確な値が返されます。  
  
### <a name="remarks"></a>コメント  
 スレッド モデルがマルチ スレッドの場合**InterlockedDecrement**を複数のスレッドが同時に、参照カウントを変更することを防ぐために使用します。  
  
##  <a name="lock"></a>CComObjectRootEx::Lock  
 このメソッドは、Win32 API 関数を呼び出してスレッド モデルがマルチ スレッドの場合は、 [EnterCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682608)スレッドがクリティカル セクション オブジェクトの所有権を取得するまで待機したどのがプライベート データ メンバーを取得します。  
  
```
void Lock();
```  
  
### <a name="remarks"></a>コメント  
 スレッドを呼び出す必要があります、保護されたコードでは、実行が終了したら、`Unlock`クリティカル セクションの所有権を解放します。  
  
 スレッド モデルがシングル スレッドの場合、このメソッドは何も行われません。  
  
##  <a name="m_dwref"></a>CComObjectRootEx::m_dwRef  
 4 バイトのメモリにアクセスする共用体の一部です。  
  
```
long m_dwRef;
```  
  
### <a name="remarks"></a>コメント  
 `m_pOuterUnknown`共用体の一部では。  
  
 `union`  
  
 `{`  
  
 `long m_dwRef;`  
  
 `IUnknown* m_pOuterUnknown;`  
  
 `};`  
  
 参照カウントを使用した場合は、オブジェクトは集計されません。`AddRef`と**リリース**は`m_dwRef`です。 外部へのポインターが格納されている場合は、オブジェクトを集約すると、[アグリゲート](#m_pouterunknown)します。  
  
##  <a name="m_pouterunknown"></a>CComObjectRootEx::m_pOuterUnknown  
 4 バイトのメモリにアクセスする共用体の一部です。  
  
```
IUnknown*
    m_pOuterUnknown;
```     
  
### <a name="remarks"></a>コメント  
 `m_dwRef`共用体の一部では。  
  
 `union`  
  
 `{`  
  
 `long m_dwRef;`  
  
 `IUnknown* m_pOuterUnknown;`  
  
 `};`  
  
 外部へのポインターが格納されている場合は、オブジェクトを集約すると、`m_pOuterUnknown`です。 参照カウントを使用した場合は、オブジェクトは集計されません。`AddRef`と**リリース**に入っている[m_dwRef](#m_dwref)します。  
  
##  <a name="objectmain"></a>CComObjectRootEx::ObjectMain  
 表示される各クラスに対して、[オブジェクト マップ](http://msdn.microsoft.com/en-us/b57619cc-534f-4b8f-bfd4-0c12f937202f)モジュールが初期化された時点でこの関数が呼び出され、もう一度が終了したとき。  
  
```
static void WINAPI ObjectMain(bool bStarting);
```  
  
### <a name="parameters"></a>パラメーター  
 `bStarting`  
 [out]値が**true**初期化以外の場合、クラスがされている場合は**false**します。  
  
### <a name="remarks"></a>コメント  
 値、`bStarting`パラメーターは、モジュールがされているかどうかを示す初期化または終了します。 既定の実装`ObjectMain`、何も行われませんが初期化またはクラスに割り当てるリソースをクリーンアップするのには、クラスでこの関数をオーバーライドできます。 なお`ObjectMain`クラスのすべてのインスタンスが要求される前に呼び出されます。  
  
 `ObjectMain`エントリ ポイント関数が実行できる操作の型が制限されるため、DLL のエントリ ポイントから呼び出されます。 これらの制限の詳細については、次を参照してください。[ランタイム ライブラリの動作](../../build/run-time-library-behavior.md)と[DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM&#41;](../../atl/codesnippet/cpp/ccomobjectrootex-class_2.h)]  
  
##  <a name="outeraddref"></a>CComObjectRootEx::OuterAddRef  
 集計の外側の不明な参照カウントをインクリメントします。  
  
```
ULONG OuterAddRef();
```  
  
### <a name="return-value"></a>戻り値  
 診断に役立ちますしテスト可能性のある値。  
  
##  <a name="outerqueryinterface"></a>CComObjectRootEx::OuterQueryInterface  
 要求されたインターフェイスへの間接ポインターを取得します。  
  
```
HRESULT OuterQueryInterface(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]要求されているインターフェイスの GUID です。  
  
 `ppvObject`  
 [out]指定されたインターフェイス ポインターへのポインター `iid`、または**NULL**集計関数は、インターフェイスをサポートしていない場合。  
  
### <a name="return-value"></a>戻り値  
 標準の`HRESULT`値。  
  
##  <a name="outerrelease"></a>CComObjectRootEx::OuterRelease  
 集計の外側の不明な参照カウントをデクリメントします。  
  
```
ULONG OuterRelease();
```  
  
### <a name="return-value"></a>戻り値  
 非デバッグ ビルドでは、常に 0 を返します。 デバッグ ビルドで、診断に役に立たないかテスト可能性のある値を返します。  
  
##  <a name="unlock"></a>CComObjectRootEx::Unlock  
 このメソッドは、Win32 API 関数を呼び出してスレッド モデルがマルチ スレッドの場合は、[により](http://msdn.microsoft.com/library/windows/desktop/ms684169)、クリティカル セクション オブジェクトの場合は、どのリリース所有権がプライベート データ メンバーを取得します。  
  
```
void Unlock();
```  
  
### <a name="remarks"></a>コメント  
 所有権を取得するスレッドを呼び出す必要があります`Lock`します。 各呼び出し`Lock`に対応する呼び出しを必要と`Unlock`クリティカル セクションの所有権を解放します。  
  
 スレッド モデルがシングル スレッドの場合、このメソッドは何も行われません。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../atl/reference/ccomaggobject-class.md)   
 [クラス](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject クラス](../../atl/reference/ccompolyobject-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

