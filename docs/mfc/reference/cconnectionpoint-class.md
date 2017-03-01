---
title: "クラスの関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CConnectionPoint
dev_langs:
- C++
helpviewer_keywords:
- CConnectionPoint class
ms.assetid: f0f23a1e-5e8c-41a9-aa6c-1a4793b28e8f
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
ms.openlocfilehash: a511f252bf921433d070059518e6e67b952680eb
ms.lasthandoff: 02/24/2017

---
# <a name="cconnectionpoint-class"></a>関数のクラス
他の OLE オブジェクトと通信するために使われる "コネクション ポイント" と呼ばれる特別な型のインターフェイスを定義します。  
  
## <a name="syntax"></a>構文  
  
```  
class CConnectionPoint : public CCmdTarget  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CConnectionPoint::CConnectionPoint](#cconnectionpoint)|`CConnectionPoint` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[は](#getconnections)|コネクション マップ内のすべての接続ポイントを取得します。|  
|[CConnectionPoint::GetContainer](#getcontainer)|コネクション マップを所有するコントロールのコンテナーを取得します。|  
|[CConnectionPoint::GetIID](#getiid)|接続ポイントのインターフェイス ID を取得します。|  
|[CConnectionPoint::GetMaxConnections](#getmaxconnections)|コントロールによってサポートされている接続ポイントの最大数を取得します。|  
|[CConnectionPoint::GetNextConnection](#getnextconnection)|接続要素へのポインターを取得`pos`します。|  
|[CConnectionPoint::GetStartPosition](#getstartposition)|返すことによって、マップの反復処理を開始、**位置**値を渡すことができる、`GetNextConnection`呼び出します。|  
|[CConnectionPoint::OnAdvise](#onadvise)|確立されるか接続を解除するときに、フレームワークによって呼び出されます。|  
|[CConnectionPoint::QuerySinkInterface](#querysinkinterface)|要求されたシンク インターフェイスへのポインターを取得します。|  
  
## <a name="remarks"></a>コメント  
 標準の OLE インターフェイスを実装し、OLE コントロールの機能を公開に使用されるとは異なりは、接続ポイントは、イベントを発生させるなど、他のオブジェクトに対するアクションを開始して、変更通知が送信インターフェイスを実装します。  
  
 接続は、2 つの部分で構成されています: [ソース] と、インターフェイスを実装するオブジェクトと呼ばれるインターフェイスを呼び出すオブジェクトには、「シンク」が呼び出されます。 接続ポイントを公開するでは、ソースは、シンク自体への接続の確立を許可します。 コネクション ポイントでは、ソース オブジェクトは、シンクの一連のメンバー関数へのポインターを取得します。 たとえば、シンクによって実装されるイベントを発生させるには、ソースは、シンクの実装の適切なメソッドを呼び出すことができます。  
  
 既定では、 `COleControl`-派生クラスが&2; つのコネクション ポイントを実装します。 イベント用とプロパティの変更通知します。 これらの接続を使用する、それぞれ、イベントの発生し、シンク (たとえば、コントロールのコンテナー) をいつ通知するため、プロパティ値が変更されました。 サポートは、追加の接続ポイントを実装する OLE コントロールのも表示されます。 コントロール クラスに実装されている追加の接続ポイントごとに、接続ポイントを実装する「接続部分」を宣言する必要があります。 1 つまたは複数の接続ポイントを実装する場合は、1 つのコントロール クラスに"接続 map"を宣言する必要があります。  
  
 次の例は、単純な接続のマップと&1; つの接続ポイントです、 `Sample` OLE コントロール、コードの&2; つのフラグメントから成る: 最初の部分は、接続のマップとポイントを宣言は、2 つ目は、このマップとポイントを実装します。 最初のフラグメントがコントロール クラスの宣言に挿入された、`protected`セクション。  
  
 [!code-cpp[NVC_MFCConnectionPoints&#7;](../../mfc/codesnippet/cpp/cconnectionpoint-class_1.h)]  
  
 `BEGIN_CONNECTION_PART`と`END_CONNECTION_PART`マクロは、埋め込みのクラスを宣言`XSampleConnPt`(から派生した`CConnectionPoint`) この特定の接続ポイントを実装します。 オーバーライドする場合は、`CConnectionPoint`メンバー関数、または独自のメンバー関数を追加、これら&2; つのマクロの間、それらを宣言します。 たとえば、`CONNECTION_IID`マクロよりも優先、`CConnectionPoint::GetIID`メンバー関数はこれら&2; つのマクロの間に配置します。  
  
 2 番目のコード片は、実装ファイルに挿入されます (します。CPP) のコントロール クラス。 このコードでは、追加の接続ポイントが含まれており、接続のマップを実装します`SampleConnPt`:。  
  
 [!code-cpp[NVC_MFCConnectionPoints&#2;](../../mfc/codesnippet/cpp/cconnectionpoint-class_2.cpp)]  
  
 サンプルの OLE コントロールでのコネクション ポイントに公開以下のコード片が挿入されると、 **ISampleSink**インターフェイスです。  
  
 通常、接続ポイントは、「マルチキャスト」は、同じインターフェイスに接続されている複数のシンクにブロードキャストする機能をサポートします。 次のコード フラグメントでは、繰り返し処理で各シンク接続ポイントで使用してマルチキャストを実行する方法を示しています。  
  
 [!code-cpp[NVC_MFCConnectionPoints&4;](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]  
  
 この例では、接続の現在のセットを取得、`SampleConnPt`接続ポイントへの呼び出しが`CConnectionPoint::GetConnections`です。 接続と呼び出しを反復処理し、`ISampleSink::SinkFunc`アクティブ接続ごとにします。  
  
 使用する方法について`CConnectionPoint`、記事を参照して[コネクション ポイント](../../mfc/connection-points.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CConnectionPoint`  
  
## <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h  
  
##  <a name="a-namecconnectionpointa--cconnectionpointcconnectionpoint"></a><a name="cconnectionpoint"></a>CConnectionPoint::CConnectionPoint  
 `CConnectionPoint` オブジェクトを構築します。  
  
```  
CConnectionPoint();
```  
  
##  <a name="a-namegetconnectionsa--cconnectionpointgetconnections"></a><a name="getconnections"></a>は  
 コネクション ポイントのすべてのアクティブな接続を取得するには、この関数を呼び出します。  
  
```  
const CPtrArray* GetConnections();
```  
  
### <a name="return-value"></a>戻り値  
 アクティブな接続 (シンク) の配列へのポインター。 NULL ポインター、配列内のいくつかの可能性があります。 この配列内の各 NULL ポインターは、キャスト演算子を使用して、シンク インターフェイスへのポインターに安全に変換できます。  
  
##  <a name="a-namegetcontainera--cconnectionpointgetcontainer"></a><a name="getcontainer"></a>CConnectionPoint::GetContainer  
 取得するためにフレームワークによって呼び出される、 **IConnectionPointContainer**コネクション ポイントのです。  
  
```  
virtual LPCONNECTIONPOINTCONTAINER GetContainer();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、コンテナーへのポインターそれ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 この関数は、通常実装、`BEGIN_CONNECTION_PART`マクロです。  
  
##  <a name="a-namegetiida--cconnectionpointgetiid"></a><a name="getiid"></a>CConnectionPoint::GetIID  
 接続ポイントのインターフェイス ID を取得するためにフレームワークによって呼び出されます。  
  
```  
virtual REFIID GetIID() = 0;  
```  
  
### <a name="return-value"></a>戻り値  
 コネクション ポイントのインターフェイス ID への参照  
  
### <a name="remarks"></a>コメント  
 この接続ポイントのインターフェイス ID を返す関数をオーバーライドします。  
  
##  <a name="a-namegetmaxconnectionsa--cconnectionpointgetmaxconnections"></a><a name="getmaxconnections"></a>CConnectionPoint::GetMaxConnections  
 接続ポイントでサポートされている接続の最大数を取得するためにフレームワークによって呼び出されます。  
  
```  
virtual int GetMaxConnections();
```  
  
### <a name="return-value"></a>戻り値  
 制限がない場合は、コントロール、または-1 でサポートされている接続の最大数。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、制限がないことを示す-1 を返します。  
  
 コントロールに接続できるシンクの数を制限する場合は、この関数をオーバーライドします。  
  
##  <a name="a-namegetnextconnectiona--cconnectionpointgetnextconnection"></a><a name="getnextconnection"></a>CConnectionPoint::GetNextConnection  
 接続要素へのポインターを取得`pos`します。  
  
```  
LPUNKNOWN GetNextConnection(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 参照を指定、**位置**以前から返される値`GetNextConnection`または[中](#getstartposition)呼び出します。  
  
### <a name="return-value"></a>戻り値  
 指定した接続要素へのポインター `pos`、または NULL。  
  
### <a name="remarks"></a>コメント  
 この関数は、接続のマップ内のすべての要素を反復処理する方が適しています。 を反復処理する場合は、この関数から返されたすべての Null をスキップします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCConnectionPoints&4;](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]  
  
##  <a name="a-namegetstartpositiona--cconnectionpointgetstartposition"></a><a name="getstartposition"></a>CConnectionPoint::GetStartPosition  
 返すことによって、マップの反復処理を開始、**位置**値を渡すことができる、[順次アクセス](#getnextconnection)呼び出します。  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A**位置**マップを反復処理するための開始位置を表す値または**NULL**マップが空の場合。  
  
### <a name="remarks"></a>コメント  
 繰り返しシーケンスは予想外のです。したがって、マップの最初の要素""には、特別な意味はありません。  
  
### <a name="example"></a>例  
  例を参照してください[CConnectionPoint::GetNextConnection](#getnextconnection)します。  
  
##  <a name="a-nameonadvisea--cconnectionpointonadvise"></a><a name="onadvise"></a>CConnectionPoint::OnAdvise  
 確立または切断されているは、接続時にフレームワークによって呼び出されます。  
  
```  
virtual void OnAdvise(BOOL bAdvise);
```  
  
### <a name="parameters"></a>パラメーター  
 `bAdvise`  
 **TRUE**確立されているそれ以外の場合、接続されている場合は、 **FALSE**します。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、何も行われません。  
  
 通知をシンクに接続するか、接続ポイントから切断するときに使用する場合は、この関数をオーバーライドします。  
  
##  <a name="a-namequerysinkinterfacea--cconnectionpointquerysinkinterface"></a><a name="querysinkinterface"></a>CConnectionPoint::QuerySinkInterface  
 要求されたシンク インターフェイスへのポインターを取得します。  
  
```  
virtual HRESULT QuerySinkInterface(
    LPUNKNOWN pUnkSink,  
    void** ppInterface);
```  
  
### <a name="parameters"></a>パラメーター  
 `pUnkSink`  
 要求されているシンク インターフェイスの識別子。  
  
 `ppInterface`  
 によって識別されるインターフェイス ポインターへのポインター`pUnkSink`します。 オブジェクトがこのインターフェイスをサポートしていない場合\*`ppInterface`に設定されている**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
## <a name="see-also"></a>関連項目  
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)


