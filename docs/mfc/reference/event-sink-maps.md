---
title: "イベント シンク マップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.maps
dev_langs:
- C++
helpviewer_keywords:
- event sink maps
ms.assetid: a9757eb2-5f4a-45ec-a2cd-ce5eec85b16f
caps.latest.revision: 14
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 33bf66d18b499787a34b2da501bb3e8ead255459
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="event-sink-maps"></a>イベント シンク マップ
埋め込み OLE コントロールは、イベントを発生させる、コントロールのコンテナーは、「イベント シンク マップ」MFC によって提供されるメカニズムを使用して、イベントを受信します。 このイベント シンク マップは、それぞれの特定のイベントだけでなくそれらのイベントのパラメーター用のハンドラー関数を指定します。 イベント シンク マップの詳細については、記事を参照してください。 [ActiveX コントロール コンテナー](../../mfc/activex-control-containers.md)します。  
  
### <a name="event-sink-maps"></a>イベント シンク マップ  
  
|||  
|-|-|  
|[BEGIN_EVENTSINK_MAP](#begin_eventsink_map)|イベント シンク マップの定義を開始します。|  
|[DECLARE_EVENTSINK_MAP](#declare_eventsink_map)|イベント シンク マップを宣言します。|  
|[END_EVENTSINK_MAP](#end_eventsink_map)|イベント シンク マップの定義を終了します。|  
|[ON_EVENT](#on_event)|特定のイベントのイベント ハンドラーを定義します。|  
|[ON_EVENT_RANGE](#on_event_range)|OLE コントロールのセットから発生した特定のイベントのイベント ハンドラーを定義します。|  
|[ON_EVENT_REFLECT](#on_event_reflect)|コントロールのコンテナーによって処理される前に、コントロールによって発生したイベントを受信します。|  
|[ON_PROPNOTIFY](#on_propnotify)|OLE コントロールからプロパティの通知を処理するためのハンドラーを定義します。|  
|[ON_PROPNOTIFY_RANGE](#on_propnotify_range)|OLE コントロールのセットからのプロパティの通知を処理するためのハンドラーを定義します。|  
|[ON_PROPNOTIFY_REFLECT](#on_propnotify_reflect)|コントロールのコンテナーによって処理される前に、コントロールから送信されたプロパティの通知を受信します。|  
  
##  <a name="begin_eventsink_map"></a>BEGIN_EVENTSINK_MAP  
 イベント シンク マップの定義を開始します。  
  
```   
BEGIN_EVENTSINK_MAP(theClass, baseClass)  
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 イベント シンク マップ コントロール クラスの名前を指定します。  
  
 `baseClass`  
 基本クラスの名前を指定`theClass`します。  
  
### <a name="remarks"></a>コメント  
 クラスのメンバー関数を定義する実装 (.cpp) ファイル、起動とイベント シンク マップ、`BEGIN_EVENTSINK_MAP`マクロの通知を受信するには、各イベントのマクロのエントリを追加し、完了とイベント シンク マップ、`END_EVENTSINK_MAP`マクロです。  
  
 イベント シンク マップと OLE コントロールのコンテナーの詳細については、記事を参照してください。 [ActiveX コントロール コンテナー](../../mfc/activex-control-containers.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="declare_eventsink_map"></a>DECLARE_EVENTSINK_MAP  
 OLE コンテナーのコンテナーに通知するイベントを指定するイベント シンク マップを提供できます。  
  
```   
DECLARE_EVENTSINK_MAP()   
```  
  
### <a name="remarks"></a>コメント  
 使用して、`DECLARE_EVENTSINK_MAP`クラス宣言の末尾のマクロです。 次に、します。クラスのメンバーを定義する CPP ファイルの機能を使用して、`BEGIN_EVENTSINK_MAP`の通知を受信するイベントの各マクロと`END_EVENTSINK_MAP`イベント シンクの一覧の末尾を宣言するマクロ。  
  
 イベント シンク マップの詳細については、記事を参照してください。 [ActiveX コントロール コンテナー](../../mfc/activex-control-containers.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="end_eventsink_map"></a>END_EVENTSINK_MAP  
 イベント シンク マップの定義を終了します。  
  
```   
END_EVENTSINK_MAP()   
```  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="on_event"></a>ON_EVENT  
 使用して、 `ON_EVENT` OLE コントロールによって発生したイベントのイベント ハンドラー関数を定義するマクロ。  
  
```   
ON_EVENT(theClass, id, dispid, pfnHandler,  vtsParams) 
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 このイベント シンク マップが所属するクラスです。  
  
 `id`  
 OLE コントロールのコントロールの ID。  
  
 `dispid`  
 コントロールによって発生したイベントのディスパッチの ID。  
  
 `pfnHandler`  
 イベントを処理するメンバー関数へのポインター。 この関数が必要です、 **BOOL**型、およびイベントのパラメーターと一致するパラメーターの型を返す (を参照してください`vtsParams`)。 関数が返す必要があります**TRUE**イベントが処理済み以外の場合を示す**FALSE**します。  
  
 `vtsParams`  
 一連の**vts _**イベントのパラメーターの型を指定する定数。 これらなどのディスパッチ マップ エントリで使用される同じ定数`DISP_FUNCTION`します。  
  
### <a name="remarks"></a>コメント  
 `vtsParams`引数がスペースで区切られた一連の値から、 **vts _**定数です。 1 つ以上のスペース (コンマではなく) で区切られたこれらの値は、関数のパラメーター リストを指定します。 例:  
  
 [!code-cpp[NVC_MFCAutomation&#11;](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 続いて短整数を含む一覧を示す、 **BOOL**します。  
  
 一覧については、 **vts _**定数を参照してください[EVENT_CUSTOM](event-maps.md#event_custom)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="on_event_range"></a>ON_EVENT_RANGE  
 使用して、 `ON_EVENT_RANGE` Id の連続した範囲内のコントロール ID を持つ任意の OLE コントロールによって発生したイベントのイベント ハンドラー関数を定義するマクロ。  
  
```   
ON_EVENT_RANGE(theClass, idFirst, idLast, dispid, pfnHandler,  vtsParams)   
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 このイベント シンク マップが所属するクラスです。  
  
 `idFirst`  
 範囲の最初の OLE コントロールのコントロールの ID。  
  
 `idLast`  
 範囲の最後の OLE コントロールのコントロールの ID。  
  
 `dispid`  
 コントロールによって発生したイベントのディスパッチの ID。  
  
 `pfnHandler`  
 イベントを処理するメンバー関数へのポインター。 この関数が必要です、 **BOOL**型の最初のパラメーターの型を取得**UINT** (のコントロールの ID)、およびイベントのパラメーターと一致する追加のパラメーターの型 (を参照してください`vtsParams`)。 関数が返す必要があります**TRUE**イベントが処理済み以外の場合を示す**FALSE**します。  
  
 `vtsParams`  
 一連の**vts _**イベントのパラメーターの型を指定する定数。 最初の定数は、型でなければなりません**VTS_I4**コントロールの id これらなどのディスパッチ マップ エントリで使用される同じ定数`DISP_FUNCTION`します。  
  
### <a name="remarks"></a>コメント  
 `vtsParams`引数がスペースで区切られた一連の値から、 **vts _**定数です。 1 つ以上のスペース (コンマではなく) で区切られたこれらの値は、関数のパラメーター リストを指定します。 例:  
  
 [!code-cpp[NVC_MFCAutomation&#11;](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 続いて短整数を含む一覧を示す、 **BOOL**します。  
  
 一覧については、 **vts _**定数を参照してください[EVENT_CUSTOM](event-maps.md#event_custom)します。  
  
### <a name="example"></a>例  
 次の例では、次の&3; つのコントロールの実装、MouseDown イベントのイベント ハンドラー (`IDC_MYCTRL1`を通じて`IDC_MYCTRL3`)。 イベント ハンドラー関数の`OnRangeMouseDown`、ダイアログ クラスのヘッダー ファイルで宣言された ( `CMyDlg`) として。  
  
 [!code-cpp[NVC_MFCAutomation&#12;](../../mfc/codesnippet/cpp/event-sink-maps_2.h)]  
  
 次のコードは、ダイアログ クラスの実装ファイルで定義されます。  
  
 [!code-cpp[NVC_MFCAutomation&#13;](../../mfc/codesnippet/cpp/event-sink-maps_3.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="on_event_reflect"></a>ON_EVENT_REFLECT  
 `ON_EVENT_REFLECT`イベント シンク マップ OLE コントロールのラッパー クラスを使用すると、マクロがコントロールのコンテナーによって処理される前に、コントロールによって発生したイベントを受信します。  
  
```   
ON_EVENT_REFLECT(theClass,  dispid, pfnHandler,  vtsParams) 
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 このイベント シンク マップが所属するクラスです。  
  
 dispid  
 コントロールによって発生したイベントのディスパッチの ID。  
  
 `pfnHandler`  
 イベントを処理するメンバー関数へのポインター。 この関数が必要です、 **BOOL**型と、イベントのパラメーターと一致するパラメーターの型を返す (を参照してください`vtsParams`)。 関数が返す必要があります**TRUE**イベントが処理済み以外の場合を示す**FALSE**します。  
  
 `vtsParams`  
 一連の**vts _**イベントのパラメーターの型を指定する定数。 これらなどのディスパッチ マップ エントリで使用される同じ定数`DISP_FUNCTION`します。  
  
### <a name="remarks"></a>コメント  
 `vtsParams`引数がスペースで区切られた一連の値から、 **vts _**定数です。  
  
 1 つ以上のスペース (コンマではなく) で区切られたこれらの値は、関数のパラメーター リストを指定します。 例:  
  
 [!code-cpp[NVC_MFCAutomation&#11;](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 続いて短整数を含む一覧を示す、 **BOOL**します。  
  
 一覧については、 **vts _**定数を参照してください[EVENT_CUSTOM](event-maps.md#event_custom)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="on_propnotify"></a>ON_PROPNOTIFY  
 使用して、`ON_PROPNOTIFY`マクロ OLE コントロールからプロパティの通知を処理するためのイベント シンク マップ エントリを定義します。  
  
```   
ON_PROPNOTIFY(theClass, id, dispid, pfnRequest, pfnChanged)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 このイベント シンク マップが所属するクラスです。  
  
 `id`  
 OLE コントロールのコントロールの ID。  
  
 `dispid`  
 通知に関連するプロパティのディスパッチの ID。  
  
 `pfnRequest`  
 処理するメンバー関数へのポインター、 **OnRequestEdit**このプロパティに通知します。 この関数が必要です、 **BOOL**型を返すと、 **BOOL\* **パラメーター。 この関数は、パラメーターを設定する必要があります**TRUE**プロパティの変更を許可するように、 **FALSE**を許可しないようにします。 関数が返す必要があります**TRUE**通知された以外の処理を示す**FALSE**します。  
  
 `pfnChanged`  
 処理するメンバー関数へのポインター、 **OnChanged**このプロパティに通知します。 関数を**BOOL**型を返すと**UINT**パラメーター。 関数が返す必要があります**TRUE**通知が処理される、それ以外のことを示す**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 `vtsParams`引数がスペースで区切られた一連の値から、 **vts _**定数です。 1 つ以上のスペース (コンマではなく) で区切られたこれらの値は、関数のパラメーター リストを指定します。 例:  
  
 [!code-cpp[NVC_MFCAutomation&#11;](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 続いて短整数を含む一覧を示す、 **BOOL**します。  
  
 一覧については、 **vts _**定数を参照してください[EVENT_CUSTOM](event-maps.md#event_custom)します。  
  
##  <a name="on_propnotify_range"></a>ON_PROPNOTIFY_RANGE  
 使用して、`ON_PROPNOTIFY_RANGE`マクロ Id の連続した範囲内のコントロール ID を持つ任意の OLE コントロールからプロパティの通知を処理するためのイベント シンク マップ エントリを定義します。  
  
```  
 
ON_PROPNOTIFY_RANGE(theClass, idFirst, idLast, dispid, pfnRequest, pfnChanged)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 このイベント シンク マップが所属するクラスです。  
  
 `idFirst`  
 範囲の最初の OLE コントロールのコントロールの ID。  
  
 `idLast`  
 範囲の最後の OLE コントロールのコントロールの ID。  
  
 `dispid`  
 通知に関連するプロパティのディスパッチの ID。  
  
 `pfnRequest`  
 処理するメンバー関数へのポインター、 **OnRequestEdit**このプロパティに通知します。 この関数が必要です、 **BOOL**型を返すと**UINT**と**BOOL\* **パラメーター。 関数は、パラメーターを設定する必要があります**TRUE**プロパティの変更を許可するように、 **FALSE**を許可しないようにします。 関数が返す必要があります**TRUE**通知が処理される、それ以外のことを示す**FALSE**します。  
  
 `pfnChanged`  
 処理するメンバー関数へのポインター、 **OnChanged**このプロパティに通知します。 関数を**BOOL**型を返すと**UINT**パラメーター。 関数が返す必要があります**TRUE**通知が処理される、それ以外のことを示す**FALSE**します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="on_propnotify_reflect"></a>ON_PROPNOTIFY_REFLECT  
 `ON_PROPNOTIFY_REFLECT`マクロ、イベント シンク マップ OLE コントロールのラッパー クラスを使用する場合がコントロールのコンテナーによって処理される前に、コントロールから送信されたプロパティの通知を受信します。  
  
```  
 
ON_PROPNOTIFY_REFLECT(theClass, dispid, pfnRequest, pfnChanged)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 このイベント シンク マップが所属するクラスです。  
  
 `dispid`  
 通知に関連するプロパティのディスパッチの ID。  
  
 `pfnRequest`  
 処理するメンバー関数へのポインター、 **OnRequestEdit**このプロパティに通知します。 この関数が必要です、 **BOOL**型を返すと、 **BOOL\* **パラメーター。 この関数は、パラメーターを設定する必要があります**TRUE**プロパティの変更を許可するように、 **FALSE**を許可しないようにします。 関数が返す必要があります**TRUE**通知された以外の処理を示す**FALSE**します。  
  
 `pfnChanged`  
 処理するメンバー関数へのポインター、 **OnChanged**このプロパティに通知します。 関数を**BOOL**型およびパラメーターを返します。 関数が返す必要があります**TRUE**通知された以外の処理を示す**FALSE**します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
    
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

