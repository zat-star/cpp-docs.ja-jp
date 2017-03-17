---
title: "CDynamicChain クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDynamicChain
- ATLWIN/ATL::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CallChain
- ATLWIN/ATL::CDynamicChain::RemoveChainEntry
- ATLWIN/ATL::CDynamicChain::SetChainEntry
dev_langs:
- C++
helpviewer_keywords:
- message maps, chaining
- chaining message maps
- CDynamicChain class
ms.assetid: f084b2be-0e77-4836-973d-ae278a1e9da8
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
ms.openlocfilehash: 4da97d0b3d72400d7e285fde187e6860759900af
ms.lasthandoff: 02/24/2017

---
# <a name="cdynamicchain-class"></a>CDynamicChain クラス
このクラスは、メッセージ マップの動的なチェーンをサポートするメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CDynamicChain
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDynamicChain::CDynamicChain](#cdynamicchain)|コンストラクターです。|  
|[CDynamicChain:: ~ CDynamicChain](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDynamicChain::CallChain](#callchain)|Windows メッセージを別のオブジェクトのメッセージ マップを送ります。|  
|[CDynamicChain::RemoveChainEntry](#removechainentry)|コレクションからのメッセージ マップ エントリを削除します。|  
|[CDynamicChain::SetChainEntry](#setchainentry)|メッセージ マップ エントリをコレクションに追加または既存のエントリを変更します。|  
  
## <a name="remarks"></a>コメント  
 `CDynamicChain`Windows メッセージを送るには、別のオブジェクトのメッセージ マップに、実行時に有効にすると、メッセージ マップのコレクションを管理します。  
  
 メッセージ マップの動的なチェーンのサポートを追加するには、次の操作を行います。  
  
-   クラスを派生`CDynamicChain`します。 メッセージ マップに指定、[場合](http://msdn.microsoft.com/library/7e5c72b7-cb31-4f3b-8a1b-6293804af220)を別のオブジェクトの既定のメッセージ マップ マクロです。  
  
-   チェーンするすべてのクラスを派生[CMessageMap](../../atl/reference/cmessagemap-class.md)します。 `CMessageMap`他のオブジェクトへのメッセージ マップを公開するオブジェクトを許可します。  
  
-   呼び出す`CDynamicChain::SetChainEntry`オブジェクトとどのようなメッセージにマップするには連鎖の対象を特定するのにします。  
  
 たとえば、クラスが次のように定義されているとします。  
  
 [!code-cpp[NVC_ATL_Windowing #&88;](../../atl/codesnippet/cpp/cdynamicchain-class_1.h)]  
  
 クライアントは、 `CMyWindow::SetChainEntry`:  
  
 [!code-cpp[NVC_ATL_Windowing #&89;](../../atl/codesnippet/cpp/cdynamicchain-class_2.cpp)]  
  
 ここで`chainedObj`チェーン オブジェクトから派生したクラスのインスタンスは、`CMessageMap`です。 これで場合、`myCtl`によって処理されていないメッセージを受信`OnPaint`または`OnSetFocus`、ウィンドウ プロシージャにメッセージを送信する`chainedObj`の既定のメッセージ マップです。  
  
 メッセージ マップのチェインの詳細については、次を参照してください[メッセージ マップ](../../atl/message-maps-atl.md)"ATL ウィンドウ クラス"記事の内容。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
  
##  <a name="callchain"></a>CDynamicChain::CallChain  
 Windows メッセージを別のオブジェクトのメッセージのマップに指示します。  
  
```
BOOL CallChain(  
    DWORD dwChainID,
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT& lResult);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwChainID`  
 [in]チェーンのオブジェクトとそのメッセージ マップに関連付けられている一意の識別子。  
  
 `hWnd`  
 [in]メッセージを受信するウィンドウ ハンドル。  
  
 `uMsg`  
 [in]ウィンドウに送信するメッセージ。  
  
 `wParam`  
 [in]その他のメッセージに固有の情報です。  
  
 `lParam`  
 [in]その他のメッセージに固有の情報です。  
  
 `lResult`  
 [out]メッセージの処理の結果。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**場合は、メッセージが完全に処理済みでない場合は**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 ウィンドウ プロシージャを呼び出す`CallChain`を指定する必要があります、[場合](http://msdn.microsoft.com/library/7e5c72b7-cb31-4f3b-8a1b-6293804af220)メッセージ マップにマクロです。 例については、次を参照してください。、 [CDynamicChain](../../atl/reference/cdynamicchain-class.md)の概要です。  
  
 `CallChain`以前の呼び出しを必要と[SetChainEntry](#setchainentry)に関連付けるには、`dwChainID`値、オブジェクトと、メッセージ マップを使用します。  
  
##  <a name="cdynamicchain"></a>CDynamicChain::CDynamicChain  
 コンストラクターです。  
  
```
CDynamicChain();
```  
  
##  <a name="dtor"></a>CDynamicChain:: ~ CDynamicChain  
 デストラクターです。  
  
```
~CDynamicChain();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられているすべてのリソースを解放します。  
  
##  <a name="removechainentry"></a>CDynamicChain::RemoveChainEntry  
 コレクションから指定されたメッセージ マップを削除します。  
  
```
BOOL RemoveChainEntry(DWORD dwChainID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwChainID`  
 [in]チェーンのオブジェクトとそのメッセージ マップに関連付けられている一意の識別子。 最初の呼び出しを使用してこの値を定義する[SetChainEntry](#setchainentry)します。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**メッセージ マップは、コレクションから正常に削除された場合。 それ以外の場合、 **FALSE**します。  
  
##  <a name="setchainentry"></a>CDynamicChain::SetChainEntry  
 指定されたメッセージ マップをコレクションに追加します。  
  
```
BOOL SetChainEntry(  
    DWORD dwChainID,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwChainID`  
 [in]チェーンのオブジェクトとそのメッセージ マップに関連付けられている一意の識別子。  
  
 `pObject`  
 [in]メッセージ マップを宣言するチェーン オブジェクトへのポインター。 このオブジェクトから派生する必要があります[CMessageMap](../../atl/reference/cmessagemap-class.md)します。  
  
 `dwMsgMapID`  
 [in]メッセージ マップのチェーン オブジェクトの識別子です。 既定値は 0 で、既定のメッセージ マップを使用して宣言を識別する[送るに](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554)します。 宣言された代替のメッセージ マップを指定する[ALT_MSG_MAP(msgMapID)](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8)、渡す`msgMapID`します。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**メッセージ マップが正しく、コレクションに追加された場合。 それ以外の場合、 **FALSE**します。  
  
### <a name="remarks"></a>コメント  
 場合、`dwChainID`値がコレクションに既に存在する、関連付けられているオブジェクトに、メッセージ マップは置き換え`pObject`と`dwMsgMapID`、それぞれします。 それ以外の場合、新しいエントリが追加されます。  
  
## <a name="see-also"></a>関連項目  
 [CWindowImpl クラス](../../atl/reference/cwindowimpl-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

