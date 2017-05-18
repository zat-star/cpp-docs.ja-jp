---
title: "複合コントロール マクロ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- composite controls, macros
ms.assetid: 17f2dd5e-07e6-4aa6-b965-7a361c78c45e
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 8cdedc5cfac9d49df812ae6fcfcc548201b1edb5
ms.openlocfilehash: 9fb8a907c8052c9816d6b87247e903a63f34a5be
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="composite-control-macros"></a>複合コントロール マクロ
これらのマクロは、イベント シンク マップとエントリを定義します。  
  
|||  
|-|-|  
|[BEGIN_SINK_MAP](#begin_sink_map)|複合コントロールのイベント シンク マップの先頭をマークします。|  
|[END_SINK_MAP](#end_sink_map)|複合コントロールのイベント シンク マップの最後をマークします。|  
|[SINK_ENTRY](#sink_entry)|イベント シンク マップ エントリ。|  
|[SINK_ENTRY_EX](#sink_entry_ex)|その他のパラメーターを持つイベント シンク マップ エントリ。| 
|[SINK_ENTRY_EX_P](#sink_entry_ex)| (Visual Studio 2017)Iid へのポインターを受け取る点を除いて、SINK_ENTRY_EX 同様です。|  
|[SINK_ENTRY_INFO](#sink_entry_info)|使用するための手動で指定された型情報を持つイベント シンク マップへのエントリ[されます](../../atl/reference/idispeventsimpleimpl-class.md)します。|  
|[SINK_ENTRY_INFO_P](#sink_entry_info)| (Visual Studio 2017)Iid へのポインターを受け取る点を除いて、SINK_ENTRY_INFO 同様です。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  

##  <a name="begin_sink_map"></a>BEGIN_SINK_MAP  
 複合コントロールのイベント シンク マップの先頭を宣言します。  
  
```
BEGIN_SINK_MAP(_class)
```  
  
### <a name="parameters"></a>パラメーター  
 `_class`  
 [in]コントロールを指定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&104;](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>コメント  
 ActiveX イベント シンクのみサポートの戻り値の HRESULT の種類や、イベント ハンドラー メソッドは void の CE ATL の実装その他の戻り値はサポートされていませんし、その動作は未定義です。  
  
##  <a name="end_sink_map"></a>END_SINK_MAP  
 複合コントロールのイベント シンク マップの最後を宣言します。  
  
```
END_SINK_MAP()
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&104;](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>コメント  
 ActiveX イベント シンクのみサポートの戻り値の HRESULT の種類や、イベント ハンドラー メソッドは void の CE ATL の実装その他の戻り値はサポートされていませんし、その動作は未定義です。  
  
##  <a name="sink_entry"></a>SINK_ENTRY  
 ハンドラー関数を宣言 ( `fn`) 指定したイベント ( `dispid`) で指定されたコントロールの`id`です。  
  
```
SINK_ENTRY( id, dispid, fn )
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]コントロールを識別します。  
  
 `dispid`  
 [in]指定したイベントを識別します。  
  
 `fn`  
 [in]イベント ハンドラー関数の名前です。 この関数を使用する必要があります、 **_stdcall**呼び出し規約および適切なディスパッチ インターフェイス スタイルの署名があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&104;](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>コメント  
 ActiveX イベント シンクのみサポートの戻り値の HRESULT の種類や、イベント ハンドラー メソッドは void の CE ATL の実装その他の戻り値はサポートされていませんし、その動作は未定義です。  
  
##  <a name="sink_entry_ex"></a>SINK_ENTRY_EX と SINK_ENTRY_EX_P
 ハンドラー関数を宣言 ( `fn`) 指定したイベント ( `dispid`)、ディスパッチ インターフェイスの ( *iid)*、によって識別されるコントロールの`id`です。  
  
```
SINK_ENTRY_EX( id, iid, dispid, fn )
SINK_ENTRY_EX_P( id, piid, dispid, fn ) // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]コントロールを識別します。  
  
 `iid`  
 [in]ディスパッチ インターフェイスを識別します。  

 `piid`  
 [in]ディスパッチ インターフェイスへのポインター。  
  
 `dispid`  
 [in]指定したイベントを識別します。  
  
 `fn`  
 [in]イベント ハンドラー関数の名前です。 この関数を使用する必要があります、 **_stdcall**呼び出し規約および適切なディスパッチ インターフェイス スタイルの署名があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&136;](../../atl/codesnippet/cpp/composite-control-macros_2.h)]  
  
### <a name="remarks"></a>コメント  
 ActiveX イベント シンクのみサポートの戻り値の HRESULT の種類や、イベント ハンドラー メソッドは void の CE ATL の実装その他の戻り値はサポートされていませんし、その動作は未定義です。  
  
##  <a name="sink_entry_info"></a>SINK_ENTRY_INFO と SINK_ENTRY_INFO_P  
 使用して、`SINK_ENTRY_INFO`で必要な情報を提供するイベント シンク マップ内のマクロ[されます](../../atl/reference/idispeventsimpleimpl-class.md)関連するハンドラー関数にイベントをルーティングします。  
  
```
SINK_ENTRY_INFO( id, iid, dispid, fn, info )
SINK_ENTRY_INFO_P( id, piid, dispid, fn, info ) // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]イベント ソースを識別する符号なし整数。 この値に一致する必要があります、`nID`関連するのに使用されるテンプレート パラメーター[されます](../../atl/reference/idispeventsimpleimpl-class.md)基本クラスです。  
  
 `iid`  
 [in]ディスパッチ インターフェイスを識別する IID です。  

 `piid`  
 [in]ディスパッチ インターフェイスを識別する IID へのポインター。
  
 `dispid`  
 [in]指定したイベントを識別するように DISPID します。  
  
 `fn`  
 [in]イベント ハンドラー関数の名前です。 この関数を使用する必要があります、 **_stdcall**呼び出し規約および適切なディスパッチ インターフェイス スタイルの署名があります。  
  
 `info`  
 [in]イベント ハンドラー関数の情報を入力します。 この型情報がへのポインターの形で提供される、`_ATL_FUNC_INFO`構造体。 `CC_CDECL`Windows ce のサポートされている唯一のオプションは、`CALLCONV`のフィールド、`_ATL_FUNC_INFO`構造体。 その他の値はサポートされていませんので、動作が定義されていません。  
  
### <a name="remarks"></a>コメント  
 最初の&4; つのマクロのパラメーターは場合と同じ、 [SINK_ENTRY_EX](#sink_entry_ex)マクロです。 最後のパラメーターは、イベントの種類の情報を提供します。 ActiveX イベント シンクのみサポートの戻り値の HRESULT の種類や、イベント ハンドラー メソッドは void の CE ATL の実装その他の戻り値はサポートされていませんし、その動作は未定義です。  
  

## <a name="see-also"></a>関連項目  
 [マクロ](../../atl/reference/atl-macros.md)   
 [複合コントロールのグローバル関数](../../atl/reference/composite-control-global-functions.md)

