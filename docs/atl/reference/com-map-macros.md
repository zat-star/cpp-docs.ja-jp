---
title: "COM マップ マクロ |Microsoft ドキュメント"
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
- COM interfaces, COM map macros
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
caps.latest.revision: 16
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
ms.openlocfilehash: 79658b6ac22719af7172c9d2848675faf2a23a0c
ms.lasthandoff: 02/24/2017

---
# <a name="com-map-macros"></a>COM マップ マクロ
これらのマクロは、COM インターフェイス マップを定義します。  
  
|||  
|-|-|  
|[BEGIN_COM_MAP](#begin_com_map)|COM インターフェイス マップのエントリの先頭をマークします。|  
|[COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00)|COM インターフェイス マップにインターフェイスを入力します。|  
|[COM_INTERFACE_ENTRY2](#com_interface_entry2)|継承の&2; つの分岐を区別するために、このマクロを使用します。|  
|[COM_INTERFACE_ENTRY_IID](#com_interface_entry_iid)|インターフェイスを COM マップに入力し、インターフェイスの IID を指定するには、このマクロを使用します。|  
|[COM_INTERFACE_ENTRY2_IID](#com_interface_entry2_iid)|同じ[COM_INTERFACE_ENTRY2](#com_interface_entry2)、別の IID を指定することができます。|  
|[定義](#com_interface_entry_aggregate)|インターフェイスがによって識別されると`iid`、照会`COM_INTERFACE_ENTRY_AGGREGATE`転送`punk`します。|  
|[COM_INTERFACE_ENTRY_AGGREGATE_BLIND](#com_interface_entry_aggregate_blind)|同じ[で定義](#com_interface_entry_aggregate)にクエリを転送するために結果の任意の IID のクエリを実行することを除き、`punk`です。|  
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)|同じ[で定義](#com_interface_entry_aggregate)、場合を除く`punk`は**NULL**、によって記述された集計を自動的に作成、`clsid`です。|  
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](#com_interface_entry_autoaggregate_blind)|同じ[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)にクエリを転送するために結果の任意の IID のクエリを実行することを除き、 `punk`、場合`punk`は**NULL**、自動的にで説明されている集計の作成、`clsid`です。|  
|[COM_INTERFACE_ENTRY_BREAK](#com_interface_entry_break)|呼び出さないと、 [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297)について、指定したインターフェイスが照会されたとき。|  
|[COM_INTERFACE_ENTRY_CACHED_TEAR_OFF](#com_interface_entry_cached_tear_off)|インスタンスごとにインターフェイスに固有のデータを保存します。|  
|[COM_INTERFACE_ENTRY_TEAR_OFF](#com_interface_entry_tear_off)|ティアオフ インターフェイスを公開します。|  
|[COM_INTERFACE_ENTRY_CHAIN](#com_interface_entry_chain)|処理には、COM マップ内のこのエントリに達すると、基本クラスの COM マップを処理します。|  
|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)|ATL にフックするための一般的な機構`QueryInterface`ロジックです。|  
|[COM_INTERFACE_ENTRY_FUNC_BLIND](#com_interface_entry_func_blind)|同じ[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)への呼び出しの結果、IID に対するクエリを実行することを除き、`func`です。|  
|[COM_INTERFACE_ENTRY_NOINTERFACE](#com_interface_entry_nointerface)|返します。 **E_NOINTERFACE**し、COM マップ処理について、指定したインターフェイスが照会されたときに終了します。|  
|[END_COM_MAP](#end_com_map)|COM インターフェイス マップのエントリの終了を示します。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
   
##  <a name="a-namebegincommapa--begincommap"></a><a name="begin_com_map"></a>BEGIN_COM_MAP  
 COM マップを介してクライアントにオブジェクトのインターフェイスを公開するメカニズムは、`QueryInterface`です。  
  
```
BEGIN_COM_MAP(x)
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]インターフェイスを公開するのには、クラス オブジェクトの名前。  
  
### <a name="remarks"></a>コメント  
 [CComObjectRootEx::InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) COM マップ内のインターフェイスに対してポインターだけを返します。 インターフェイス マップを開始、`BEGIN_COM_MAP`マクロを使用して、インターフェイスの各エントリを追加、 [COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/c5363b8b-a1a2-471e-ad3a-d472f6c356c5)マクロまたはそのバリエーションの&1; つを使用して、地図を完了、 [END_COM_MAP](#end_com_map)マクロです。  

  
### <a name="example"></a>例  
 ATL から[BEEPER](../../visual-cpp-samples.md)サンプル。  
  
 [!code-cpp[NVC_ATL_COM&1;](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  
##  <a name="a-namecominterfaceentrymacrosa--cominterfaceentry-macros"></a><a name="com_interface_entry_macros"></a>COM_INTERFACE_ENTRY マクロ  
 アクセスできるように、これらのマクロがその COM マップに、オブジェクトのインターフェイスを入力`QueryInterface`します。 COM マップ エントリの順序では注文インターフェイスをチェックして、一致する対象となる**IID**中に`QueryInterface`します。  
  
##  <a name="a-namecominterfaceentry2x2a--cominterfaceentry2"></a><a name="com_interface_entry2_x2"></a>COM_INTERFACE_ENTRY2  
 継承の&2; つの分岐を区別するために、このマクロを使用します。  
  
```
COM_INTERFACE_ENTRY2(x, x2)
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]オブジェクトから公開するインターフェイスの名前。  
  
 `x2`  
 [in]分岐の名前、継承元となる*x*公開されます。  
  
### <a name="remarks"></a>コメント  
 たとえば、2 つのデュアル インターフェイス オブジェクトのクラスを派生する場合を公開する`IDispatch`を使用して`COM_INTERFACE_ENTRY2`ので`IDispatch`インターフェイスのいずれかから取得できます。  
  
 参照してください[COM_INTERFACE_ENTRY マクロ](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00)マップ エントリを com には、「解説」の場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&118;](../../atl/codesnippet/cpp/com-map-macros_2.h)]  
  
##  <a name="a-namecominterfaceentryiida--cominterfaceentryiid"></a><a name="com_interface_entry_iid"></a>COM_INTERFACE_ENTRY_IID  
 インターフェイスを COM マップに入力し、インターフェイスの IID を指定するには、このマクロを使用します。  
  
```
COM_INTERFACE_ENTRY_IID(iid, x)
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]公開されるインターフェイスの GUID です。  
  
 *x*  
 [in]Vtable がで識別されるインターフェイスとして公開されるクラスの名前`iid`します。  
  
### <a name="remarks"></a>コメント  
 参照してください[COM_INTERFACE_ENTRY マクロ](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00)マップ エントリを com には、「解説」の場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&117;](../../atl/codesnippet/cpp/com-map-macros_3.h)]  
  
##  <a name="a-namecominterfaceentry2iida--cominterfaceentry2iid"></a><a name="com_interface_entry2_iid"></a>COM_INTERFACE_ENTRY2_IID  
 同じ[COM_INTERFACE_ENTRY2](#com_interface_entry2)、別の IID を指定することができます。  
  
```
COM_INTERFACE_ENTRY2_IID(iid, x, x2)
```   
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]インターフェイスの指定した GUID です。  
  
 *x*  
 [in]クラスのオブジェクトが直接から派生したインターフェイスの名前。  
  
 `x2`  
 [in]クラスのオブジェクトが直接から派生する&2; 番目のインターフェイスの名前。  
  
### <a name="remarks"></a>コメント  
 参照してください[COM_INTERFACE_ENTRY マクロ](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00)マップ エントリを com には、「解説」の場合。  
  
##  <a name="a-namecominterfaceentry2a--cominterfaceentry2"></a><a name="com_interface_entry2"></a>COM_INTERFACE_ENTRY2  
 継承の&2; つの分岐を区別するために、このマクロを使用します。  
  
```
COM_INTERFACE_ENTRY2(x, x2)
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]オブジェクトから公開するインターフェイスの名前。  
  
 `x2`  
 [in]分岐の名前、継承元となる*x*公開されます。  
  
### <a name="remarks"></a>コメント  
 たとえば、2 つのデュアル インターフェイス オブジェクトのクラスを派生する場合を公開する`IDispatch`を使用して`COM_INTERFACE_ENTRY2`ので`IDispatch`インターフェイスのいずれかから取得できます。  
  
 参照してください[COM_INTERFACE_ENTRY マクロ](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00)マップ エントリを com には、「解説」の場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&118;](../../atl/codesnippet/cpp/com-map-macros_2.h)]  
  
##  <a name="a-namecominterfaceentryaggregate2a--cominterfaceentryaggregate"></a><a name="com_interface_entry_aggregate2"></a>定義  
 インターフェイスがによって識別されると`iid`、照会`COM_INTERFACE_ENTRY_AGGREGATE`転送`punk`します。  
  
```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]クエリを要求するインターフェイスの GUID です。  
  
 `punk`  
 [in]名前、 **IUnknown**ポインター。  
  
### <a name="remarks"></a>コメント  
 `punk`パラメーターは、内部の不明な集計の をポイントすると見なされます**NULL**、その場合、エントリは無視されます。 通常、 **CoCreate**で集計`FinalConstruct`します。  
  
 参照してください[COM_INTERFACE_ENTRY マクロ](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00)マップ エントリを com には、「解説」の場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&112;](../../atl/codesnippet/cpp/com-map-macros_4.h)]  
  
##  <a name="a-namecominterfaceentryaggregateblinda--cominterfaceentryaggregateblind"></a><a name="com_interface_entry_aggregate_blind"></a>COM_INTERFACE_ENTRY_AGGREGATE_BLIND  
 同じ[で定義](#com_interface_entry_aggregate)にクエリを転送するために結果の任意の IID のクエリを実行することを除き、`punk`です。  
  
```
COM_INTERFACE_ENTRY_AGGREGATE_BLIND(punk)
```  
  
### <a name="parameters"></a>パラメーター  
 `punk`  
 [in]名前、 **IUnknown**ポインター。  
  
### <a name="remarks"></a>コメント  
 かどうかは、インターフェイスのクエリが失敗すると、COM マップの処理は継続します。  
  
 参照してください[COM_INTERFACE_ENTRY マクロ](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00)マップ エントリを com には、「解説」の場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&113;](../../atl/codesnippet/cpp/com-map-macros_5.h)]  
  
##  <a name="a-namecominterfaceentryaggregate3a--cominterfaceentryaggregate"></a><a name="com_interface_entry_aggregate3"></a>定義  
 インターフェイスがによって識別されると`iid`、照会`COM_INTERFACE_ENTRY_AGGREGATE`転送`punk`します。  
  
```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]クエリを要求するインターフェイスの GUID です。  
  
 `punk`  
 [in]名前、 **IUnknown**ポインター。  
  
### <a name="remarks"></a>コメント  
 `punk`パラメーターは、内部の不明な集計の をポイントすると見なされます**NULL**、その場合、エントリは無視されます。 通常、 **CoCreate**で集計`FinalConstruct`します。  
  
 参照してください[COM_INTERFACE_ENTRY マクロ](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00)マップ エントリを com には、「解説」の場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&112;](../../atl/codesnippet/cpp/com-map-macros_4.h)]  
  
##  <a name="a-namecominterfaceentryautoaggregatea--cominterfaceentryautoaggregate"></a><a name="com_interface_entry_autoaggregate"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE  
 同じ[で定義](#com_interface_entry_aggregate)、場合を除く`punk`は**NULL**、によって記述された集計を自動的に作成、`clsid`です。  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```   
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]クエリを要求するインターフェイスの GUID です。  
  
 `punk`  
 [in]名前、 **IUnknown**ポインター。 COM マップを含むクラスのメンバーである必要があります。  
  
 `clsid`  
 [in]場合に作成される集計の識別子`punk`は**NULL**します。  
  
### <a name="remarks"></a>コメント  
 参照してください[COM_INTERFACE_ENTRY マクロ](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00)マップ エントリを com には、「解説」の場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&114;](../../atl/codesnippet/cpp/com-map-macros_6.h)]  
  
##  <a name="a-namecominterfaceentryaggregatea--cominterfaceentryaggregate"></a><a name="com_interface_entry_aggregate"></a>定義  
 インターフェイスがによって識別されると`iid`、照会`COM_INTERFACE_ENTRY_AGGREGATE`転送`punk`します。  
  
```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]クエリを要求するインターフェイスの GUID です。  
  
 `punk`  
 [in]名前、 **IUnknown**ポインター。  
  
### <a name="remarks"></a>コメント  
 `punk`パラメーターは、内部の不明な集計の をポイントすると見なされます**NULL**、その場合、エントリは無視されます。 通常、 **CoCreate**で集計`FinalConstruct`します。  
  
 参照してください[COM_INTERFACE_ENTRY マクロ](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00)マップ エントリを com には、「解説」の場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&112;](../../atl/codesnippet/cpp/com-map-macros_4.h)]  
  
##  <a name="a-namecominterfaceentryautoaggregateblinda--cominterfaceentryautoaggregateblind"></a><a name="com_interface_entry_autoaggregate_blind"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND  
 同じ[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)にクエリを転送するために結果の任意の IID のクエリを実行することを除き、 `punk`、場合`punk`は**NULL**、自動的にで説明されている集計の作成、`clsid`です。  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(punk, clsid)
```  
  
### <a name="parameters"></a>パラメーター  
 `punk`  
 [in]名前、 **IUnknown**ポインター。 COM マップを含むクラスのメンバーである必要があります。  
  
 `clsid`  
 [in]場合に作成される集計の識別子`punk`は**NULL**します。  
  
### <a name="remarks"></a>コメント  
 かどうかは、インターフェイスのクエリが失敗すると、COM マップの処理は継続します。  
  
 参照してください[COM_INTERFACE_ENTRY マクロ](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00)マップ エントリを com には、「解説」の場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&115;](../../atl/codesnippet/cpp/com-map-macros_7.h)]  
  
##  <a name="a-namecominterfaceentryautoaggregate2a--cominterfaceentryautoaggregate"></a><a name="com_interface_entry_autoaggregate2"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE  
 同じ[で定義](#com_interface_entry_aggregate)、場合を除く`punk`は**NULL**、によって記述された集計を自動的に作成、`clsid`です。  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```   
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]クエリを要求するインターフェイスの GUID です。  
  
 `punk`  
 [in]名前、 **IUnknown**ポインター。 COM マップを含むクラスのメンバーである必要があります。  
  
 `clsid`  
 [in]場合に作成される集計の識別子`punk`は**NULL**します。  
  
### <a name="remarks"></a>コメント  
 参照してください[COM_INTERFACE_ENTRY マクロ](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00)マップ エントリを com には、「解説」の場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&114;](../../atl/codesnippet/cpp/com-map-macros_6.h)]  
  
##  <a name="a-namecominterfaceentrybreaka--cominterfaceentrybreak"></a><a name="com_interface_entry_break"></a>COM_INTERFACE_ENTRY_BREAK  
 呼び出さないと、 [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297)について、指定したインターフェイスが照会されたとき。  
  
```
COM_INTERFACE_ENTRY_BREAK(x)
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]インターフェイス識別子を作成するために使用するテキストです。  
  
### <a name="remarks"></a>コメント  
 インターフェイスの IID を追加することによって作成される予定*x*に`IID_`します。 たとえば場合、 *x*は`IPersistStorage`、IID になります`IID_IPersistStorage`します。  
  
 参照してください[COM_INTERFACE_ENTRY マクロ](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00)マップ エントリを com には、「解説」の場合。  
  
##  <a name="a-namecominterfaceentrycachedtearoffa--cominterfaceentrycachedtearoff"></a><a name="com_interface_entry_cached_tear_off"></a>COM_INTERFACE_ENTRY_CACHED_TEAR_OFF  
 インスタンスごとにインターフェイスに固有のデータを保存します。  
  
```
COM_INTERFACE_ENTRY_CACHED_TEAR_OFF(iid, x, punk)
```   
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]ティアオフ インターフェイスの GUID です。  
  
 *x*  
 [in]インターフェイスを実装するクラスの名前。  
  
 `punk`  
 [in]名前、 **IUnknown**ポインター。 COM マップを含むクラスのメンバーである必要があります。 初期化する必要があります**NULL**クラス オブジェクトのコンス トラクターにします。  
  
### <a name="remarks"></a>コメント  
 インターフェイスを使用しない場合、オブジェクトのインスタンス全体のサイズが削減されます。  
  
 参照してください[COM_INTERFACE_ENTRY マクロ](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00)マップ エントリを com には、「解説」の場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM&#54;](../../atl/codesnippet/cpp/com-map-macros_8.h)]  
  
##  <a name="a-namecominterfaceentrytearoffa--cominterfaceentrytearoff"></a><a name="com_interface_entry_tear_off"></a>COM_INTERFACE_ENTRY_TEAR_OFF  
 ティアオフ インターフェイスを公開します。  
  
```
COM_INTERFACE_ENTRY_TEAR_OFF(iid, x)
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]ティアオフ インターフェイスの GUID です。  
  
 *x*  
 [in]インターフェイスを実装するクラスの名前。  
  
### <a name="remarks"></a>コメント  
 ティアオフ インターフェイスがインスタンス化されるたびに、インターフェイスを表す個別のオブジェクトが照会されたとして実装されます。 通常、インターフェイスの使用頻度は、主要なオブジェクトのすべてのインスタンスに vtable へのポインターが保存されますので場合に、ティアオフとして、インターフェイスを構築します。 参照カウントがゼロになると、ティアオフは削除されます。 ティアオフを実装するクラスを派生させる必要があります`CComTearOffObjectBase`独自の COM マップがあるとします。  
  
 参照してください[COM_INTERFACE_ENTRY マクロ](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00)マップ エントリを com には、「解説」の場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM&1;](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  
##  <a name="a-namecominterfaceentrychaina--cominterfaceentrychain"></a><a name="com_interface_entry_chain"></a>COM_INTERFACE_ENTRY_CHAIN  
 処理には、COM マップ内のこのエントリに達すると、基本クラスの COM マップを処理します。  
  
```
COM_INTERFACE_ENTRY_CHAIN(classname)
```  
  
### <a name="parameters"></a>パラメーター  
 *クラス名*  
 [in]現在のオブジェクトの基本クラス。  
  
### <a name="remarks"></a>コメント  
 たとえば、次のコード。  
  
 [!code-cpp[NVC_ATL_Windowing&116; 位](../../atl/codesnippet/cpp/com-map-macros_9.h)]  
  
 注意を COM マップの最初のエントリは、COM マップを格納するオブジェクトのインターフェイスである必要があります。 したがってで、COM マップ エントリを開始することはできません`COM_INTERFACE_ENTRY_CHAIN`、それが原因で、ポイントを検索する別のオブジェクトの COM マップに**COM_INTERFACE_ENTRY_CHAIN (**`COtherObject`**)**オブジェクトの COM マップに表示されます。 別のオブジェクトの COM マップを最初に検索する場合は、追加のインターフェイスのエントリを**IUnknown** COM マップを他のオブジェクトの COM マップを連結します。 例:  
  
 [!code-cpp[NVC_ATL_Windowing #&111;](../../atl/codesnippet/cpp/com-map-macros_10.h)]  
  
 参照してください[COM_INTERFACE_ENTRY マクロ](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00)マップ エントリを com には、「解説」の場合。  
  
##  <a name="a-namecominterfaceentryfunc2a--cominterfaceentryfunc"></a><a name="com_interface_entry_func2"></a>COM_INTERFACE_ENTRY_FUNC  
 ATL にフックするための一般的な機構`QueryInterface`ロジックです。  
  
```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```   
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]公開されるインターフェイスの GUID です。  
  
 `dw`  
 [in]パラメーターに渡す、`func`です。  
  
 `func`  
 [in]関数ポインターを返す`iid`します。  
  
### <a name="remarks"></a>コメント  
 場合*iid*で指定された関数に対して、クエリを行うインターフェイスの IID と一致する`func`が呼び出されます。 関数の宣言になります。  
  
 `HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`  
  
 関数が呼び出されると、`pv`クラス オブジェクトをポイントします。 `riid`パラメーターは、クエリ対象のインターフェイスを表します`ppv`関数が、インターフェイスへのポインターを格納する必要がありますの場所へのポインターと`dw`エントリで指定するパラメーターです。 関数を設定する必要があります\*`ppv`に**NULL**を返すと**E_NOINTERFACE**または**S_FALSE**自由にインターフェイスを返す場合。 **E_NOINTERFACE**、COM マップの処理を終了します。 **S_FALSE**、インターフェイス ポインターが返されなかった場合でも、COM マップの処理を続行します。 返すようにかどうかは、インターフェイス ポインターを返します、`S_OK`です。  
  
 参照してください[COM_INTERFACE_ENTRY マクロ](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00)マップ エントリを com には、「解説」の場合。  
  
##  <a name="a-namecominterfaceentryfuncblinda--cominterfaceentryfuncblind"></a><a name="com_interface_entry_func_blind"></a>COM_INTERFACE_ENTRY_FUNC_BLIND  
 同じ[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)への呼び出しの結果、IID に対するクエリを実行することを除き、`func`です。  
  
```
COM_INTERFACE_ENTRY_FUNC_BLIND(dw, func)
```  
  
### <a name="parameters"></a>パラメーター  
 `dw`  
 [in]パラメーターに渡す、`func`です。  
  
 `func`  
 [in]この関数は、COM マップ内のこのエントリが処理されるときに呼び出されます。  
  
### <a name="remarks"></a>コメント  
 失敗すると、COM マップの処理は継続します。 返すようにかどうかは、インターフェイス ポインターを返します、`S_OK`です。  
  
 参照してください[COM_INTERFACE_ENTRY マクロ](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00)マップ エントリを com には、「解説」の場合。  
  
##  <a name="a-namecominterfaceentryfunca--cominterfaceentryfunc"></a><a name="com_interface_entry_func"></a>COM_INTERFACE_ENTRY_FUNC  
 ATL にフックするための一般的な機構`QueryInterface`ロジックです。  
  
```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```   
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]公開されるインターフェイスの GUID です。  
  
 `dw`  
 [in]パラメーターに渡す、`func`です。  
  
 `func`  
 [in]関数ポインターを返す`iid`します。  
  
### <a name="remarks"></a>コメント  
 場合*iid*で指定された関数に対して、クエリを行うインターフェイスの IID と一致する`func`が呼び出されます。 関数の宣言になります。  
  
 `HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`  
  
 関数が呼び出されると、`pv`クラス オブジェクトをポイントします。 `riid`パラメーターは、クエリ対象のインターフェイスを表します`ppv`関数が、インターフェイスへのポインターを格納する必要がありますの場所へのポインターと`dw`エントリで指定するパラメーターです。 関数を設定する必要があります\*`ppv`に**NULL**を返すと**E_NOINTERFACE**または**S_FALSE**自由にインターフェイスを返す場合。 **E_NOINTERFACE**、COM マップの処理を終了します。 **S_FALSE**、インターフェイス ポインターが返されなかった場合でも、COM マップの処理を続行します。 返すようにかどうかは、インターフェイス ポインターを返します、`S_OK`です。  
  
 参照してください[COM_INTERFACE_ENTRY マクロ](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00)マップ エントリを com には、「解説」の場合。  
  
##  <a name="a-namecominterfaceentrynointerfacea--cominterfaceentrynointerface"></a><a name="com_interface_entry_nointerface"></a>COM_INTERFACE_ENTRY_NOINTERFACE  
 返します。 **E_NOINTERFACE**し、COM マップ処理について、指定したインターフェイスが照会されたときに終了します。  
  
```
COM_INTERFACE_ENTRY_NOINTERFACE(x)
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]インターフェイス識別子を作成するために使用するテキストです。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用すると、インターフェイスが特定のケースで使用されていることを防止します。 このマクロを使用している COM に挿入するなどの直前にマップ`COM_INTERFACE_ENTRY_AGGREGATE_BLIND`をインターフェイスのクエリが、集計の内部の"不明"に転送されることを防ぐためにします。  
  
 インターフェイスの IID を追加することによって作成される予定*x*に`IID_`します。 たとえば場合、 *x*は`IPersistStorage`、IID になります`IID_IPersistStorage`します。  
  
 参照してください[COM_INTERFACE_ENTRY マクロ](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00)マップ エントリを com には、「解説」の場合。  
  
##  <a name="a-nameendcommapa--endcommap"></a><a name="end_com_map"></a>END_COM_MAP  
 COM インターフェイス マップの定義を終了します。  
  
```
END_COM_MAP()
```  
  
## <a name="see-also"></a>関連項目  
 [マクロ](../../atl/reference/atl-macros.md)   
 [COM マップ グローバル関数](../../atl/reference/com-map-global-functions.md)

