---
title: "コネクション マップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.maps
dev_langs:
- C++
helpviewer_keywords:
- connection maps
ms.assetid: 1f25a9bc-6d09-4614-99cf-dc38e8ddfa73
caps.latest.revision: 12
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 8947930d20cc65075abe442b233e4c086f10f76e
ms.lasthandoff: 02/24/2017

---
# <a name="connection-maps"></a>コネクション マップ
OLE コントロールは、他のアプリケーションに対するインターフェイスを公開できます。 これらのインターフェイスは、そのコントロールにのみ、コンテナーからのアクセスを許可します。 OLE コントロールは、他の OLE オブジェクトの外部インターフェイスにアクセスする場合、接続ポイントを確立する必要があります。 この接続ポイントは、コントロールからイベント マップや通知関数などの外部のディスパッチ マップへのアクセスを許可します。  
  
 Microsoft Foundation Class ライブラリは、接続ポイントをサポートするプログラミング モデルを提供します。 このモデルでは「接続マップ」インターフェイスまたは OLE コントロールのコネクション ポイントを指定するために使用します。 コネクション マップには、各接続ポイントの&1; つのマクロが含まれています。 コネクション マップの詳細については、次を参照してください。、[関数](../../mfc/reference/cconnectionpoint-class.md)クラスです。  
  
 通常、コントロールが&2; つのコネクション ポイントをサポートします。 イベント、プロパティの通知のもう&1; つのいずれかです。 これらは実装、`COleControl`基本クラスとコントロールの記述者による追加作業は必要ありません。 クラスで実装する追加のコネクション ポイントを手動で追加する必要があります。 コネクション マップとポイントをサポートするためには、MFC には、次のマクロが用意されています。  
  
### <a name="connection-map-declaration-and-demarcation"></a>コネクション マップの宣言と定義  
  
|||  
|-|-|  
|[BEGIN_CONNECTION_PART](#begin_connection_part)|埋め込み (クラス宣言で使用する必要があります) 追加の接続ポイントを実装するクラスを宣言します。|  
|[END_CONNECTION_PART](#end_connection_part)|接続ポイント (クラス宣言で使用する必要があります) の宣言を終了します。|  
|[CONNECTION_IID](#connection_iid)|コントロールのコネクション ポイントのインターフェイス ID を指定します。|  
|[DECLARE_CONNECTION_MAP](#declare_connection_map)|コネクション マップがクラス (クラス宣言で使用する必要があります) で使用されることを宣言します。|  
|[BEGIN_CONNECTION_MAP](#begin_connection_map)|コネクション マップ (クラスの実装で使用する必要があります) の定義を開始します。|  
|[END_CONNECTION_MAP](#end_connection_map)|コネクション マップ (クラスの実装で使用する必要があります) の定義を終了します。|  
|[CONNECTION_PART](#connection_part)|コントロールの接続のマップ内の接続ポイントを指定します。|  
  
 次の関数では、シンクを参考に確立して、接続ポイントを使用して接続を切断します。  
  
### <a name="initializationtermination-of-connection-points"></a>コネクション ポイントの初期化/終了  
  
|||  
|-|-|  
|[AfxConnectionAdvise](#afxconnectionadvise)|ソースとシンクの間の接続を確立します。|  
|[AfxConnectionUnadvise](#afxconnectionunadvise)|ソースとシンクの間の接続を切断します。|  
  
##  <a name="a-namebeginconnectionparta--beginconnectionpart"></a><a name="begin_connection_part"></a>BEGIN_CONNECTION_PART  
 使用して、`BEGIN_CONNECTION_PART`イベントおよびプロパティの通知の接続ポイントを超えて追加の接続ポイントの定義を開始するマクロ。  
  
```   
BEGIN_CONNECTION_PART(theClass, localClass)   
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 コネクション ポイントを持つコントロール クラスの名前を指定します。  
  
 *マクロ*  
 接続ポイントを実装するローカル クラスの名前を指定します。  
  
### <a name="remarks"></a>コメント  
 クラスのメンバー関数を定義する宣言 (.h) ファイル、起動接続ポイントが、`BEGIN_CONNECTION_PART`マクロを追加、`CONNECTION_IID`マクロおよび実装しとの接続ポイントのマップを完了するその他のメンバー関数、`END_CONNECTION_PART`マクロです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="a-nameendconnectionparta--endconnectionpart"></a><a name="end_connection_part"></a>END_CONNECTION_PART  
 接続ポイントの宣言を終了します。  
  
```   
END_CONNECTION_PART(localClass)   
```  
  
### <a name="parameters"></a>パラメーター  
 *マクロ*  
 接続ポイントを実装するローカル クラスの名前を指定します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="a-nameconnectioniida--connectioniid"></a><a name="connection_iid"></a>CONNECTION_IID  
 間で使用して、`BEGIN_CONNECTION_PART`と`END_CONNECTION_PART`OLE コントロールでサポートされている接続ポイントのインターフェイス ID を定義するマクロ。  
  
```   
CONNECTION_IID(iid)   
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 接続ポイントによると呼ばれるインターフェイスのインターフェイス ID です。  
  
### <a name="remarks"></a>コメント  
 `iid`引数は、接続ポイントは接続されているシンクで呼び出すインターフェイスを識別するインターフェイス ID です。 例:  
  
 [!code-cpp[NVC_MFCConnectionPoints&#10;](../../mfc/codesnippet/cpp/connection-maps_1.h)]  
  
 呼び出す接続ポイントの指定、`ISinkInterface`インターフェイスです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="a-namedeclareconnectionmapa--declareconnectionmap"></a><a name="declare_connection_map"></a>DECLARE_CONNECTION_MAP  
 各`COleControl`-プログラム内の派生クラスは、コントロールがサポートする追加の接続ポイントを指定する接続のマップを提供できます。  
  
```   
DECLARE_CONNECTION_MAP() 
```  
  
### <a name="remarks"></a>コメント  
 使用して、コントロールは、追加の点をサポートする場合、`DECLARE_CONNECTION_MAP`クラス宣言の末尾のマクロです。 クラスのメンバー関数を定義する .cpp ファイルで使用して、`BEGIN_CONNECTION_MAP`マクロ、`CONNECTION_PART`用の各コントロールの接続ポイントでは、マクロ、および`END_CONNECTION_MAP`接続マップの最後を宣言するマクロ。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="a-namebeginconnectionmapa--beginconnectionmap"></a><a name="begin_connection_map"></a>BEGIN_CONNECTION_MAP  
 各`COleControl`-プログラム内の派生クラスには、コントロールがサポートする接続ポイントを指定する接続のマップが用意されています。  
  
```   
BEGIN_CONNECTION_MAP(theClass, theBase)   
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 コネクション マップを持つコントロール クラスの名前を指定します。  
  
 *基底*  
 基本クラスの名前を指定`theClass`します。  
  
### <a name="remarks"></a>コメント  
 実装 (します。CPP) ファイル、クラスのメンバー関数を定義すると接続のマップを開始する、`BEGIN_CONNECTION_MAP`マクロを使用して、接続ポイントの各マクロのエントリを追加、 [CONNECTION_PART](#connection_part)マクロです。 コネクション マップでの最後に、完了、 [END_CONNECTION_MAP](#end_connection_map)マクロです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="a-nameendconnectionmapa--endconnectionmap"></a><a name="end_connection_map"></a>END_CONNECTION_MAP  
 コネクション マップの定義を終了します。  
  
```   
END_CONNECTION_MAP()  
```  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="a-nameconnectionparta--connectionpart"></a><a name="connection_part"></a>CONNECTION_PART  
 OLE コントロールのコネクション ポイントを特定のインターフェイス ID にマップします。  
  
```   
CONNECTION_PART(theClass, iid, localClass)   
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 コネクション ポイントを持つコントロール クラスの名前を指定します。  
  
 `iid`  
 接続ポイントによると呼ばれるインターフェイスのインターフェイス ID です。  
  
 *マクロ*  
 接続ポイントを実装するローカル クラスの名前を指定します。  
  
### <a name="remarks"></a>コメント  
 例:  
  
 [!code-cpp[NVC_MFCConnectionPoints&#2;](../../mfc/codesnippet/cpp/connection-maps_2.cpp)]  
  
 呼び出す接続ポイントとの接続のマップを実装、`IID_ISinkInterface`インターフェイスです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="a-nameafxconnectionadvisea--afxconnectionadvise"></a><a name="afxconnectionadvise"></a>AfxConnectionAdvise  
 によって指定された、ソースの間の接続を確立するには、この関数を呼び出す`pUnkSrc`と流しがで指定された`pUnkSink`します。  
  
```   
BOOL AFXAPI AfxConnectionAdvise(
    LPUNKNOWN pUnkSrc, 
    REFIID iid, 
    LPUNKNOWN pUnkSink, 
    BOOL bRefCount, 
    DWORD FAR* pdwCookie);
```  
  
### <a name="parameters"></a>パラメーター  
 `pUnkSrc`  
 インターフェイスを呼び出し、オブジェクトへのポインター。  
  
 `pUnkSink`  
 インターフェイスを実装するオブジェクトへのポインター。  
  
 `iid`  
 接続のインターフェイス ID です。  
  
 `bRefCount`  
 **TRUE**接続を作成するの参照カウントが発生ことを示します`pUnkSink`がインクリメントされます。 **FALSE**参照カウントをインクリメントしないことを示します。  
  
 `pdwCookie`  
 ポインター、`DWORD`接続識別子が返されます。 としてこの値を渡す必要があります、`dwCookie`パラメーターを`AfxConnectionUnadvise`接続を切断するとします。  
  
### <a name="return-value"></a>戻り値  
 接続が確立した場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCConnectionPoints&#8;](../../mfc/codesnippet/cpp/connection-maps_3.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afxctl.h 

##  <a name="a-nameafxconnectionunadvisea--afxconnectionunadvise"></a><a name="afxconnectionunadvise"></a>AfxConnectionUnadvise  
 によって指定された、ソースの間の接続を切断するには、この関数を呼び出す`pUnkSrc`と流しがで指定された`pUnkSink`します。  
  
```   
BOOL AFXAPI AfxConnectionUnadvise(
    LPUNKNOWN pUnkSrc, 
    REFIID iid, 
    LPUNKNOWN pUnkSink, 
    BOOL bRefCount, 
    DWORD dwCookie); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pUnkSrc`  
 インターフェイスを呼び出し、オブジェクトへのポインター。  
  
 `pUnkSink`  
 インターフェイスを実装するオブジェクトへのポインター。  
  
 `iid`  
 コネクション ポイントのインターフェイスのインターフェイス ID です。  
  
 `bRefCount`  
 **TRUE** 、接続を切断するの参照カウントが発生ことを示します`pUnkSink`デクリメントされます。 **FALSE**できないことを示す参照カウントをデクリメントします。  
  
 `dwCookie`  
 によって返される接続識別子`AfxConnectionAdvise`します。  
  
### <a name="return-value"></a>戻り値  
 0 以外の場合、接続が切断されました。それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCConnectionPoints&#9;](../../mfc/codesnippet/cpp/connection-maps_4.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afxctl.h 

## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

