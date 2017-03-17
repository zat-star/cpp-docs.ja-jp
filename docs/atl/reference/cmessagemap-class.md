---
title: "CMessageMap クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMessageMap
- ATLWIN/ATL::CMessageMap
- ATLWIN/ATL::CMessageMap::ProcessWindowMessage
dev_langs:
- C++
helpviewer_keywords:
- CMessageMap class
- message maps, ATL
- ATL, message handlers
ms.assetid: 1f97bc16-a8a0-4cf0-b90f-1778813a5c8e
caps.latest.revision: 22
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
ms.openlocfilehash: f0b40c73101463b934e3fcf299171bea142fe838
ms.lasthandoff: 02/24/2017

---
# <a name="cmessagemap-class"></a>CMessageMap クラス
このクラスにより、オブジェクトのメッセージ マップに別のオブジェクトからアクセスできます。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class ATL_NO_VTABLE CMessageMap
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMessageMap::ProcessWindowMessage](#processwindowmessage)|メッセージ マップにアクセスする、 `CMessageMap`-クラスを派生します。|  
  
## <a name="remarks"></a>コメント  
 `CMessageMap`抽象基本クラスでオブジェクトのメッセージ マップに別のオブジェクトによってアクセスできます。 派生する必要があります、クラス、オブジェクトのメッセージ マップを公開するためには、`CMessageMap`です。  
  
 ATL では、`CMessageMap`サポートが含まれている windows および動的メッセージ マップのチェインにします。 たとえば、すべてを含むクラスを[CContainedWindow](../../atl/reference/ccontainedwindowt-class.md)オブジェクトから派生しなければなりません`CMessageMap`します。 次のコードの抜粋、 [SUBEDIT](../../visual-cpp-samples.md)サンプルです。 を通じて[CComControl](../../atl/reference/ccomcontrol-class.md)、`CAtlEdit`から自動的に派生`CMessageMap`します。  
  
 [!code-cpp[NVC_ATL_Windowing #&90;](../../atl/codesnippet/cpp/cmessagemap-class_1.h)]  
  
 コンテナー内のウィンドウ`m_EditCtrl`、外側のクラスでメッセージ マップを使用して、`CAtlEdit`から派生した`CMessageMap`します。  
  
 メッセージ マップの詳細については、次を参照してください[メッセージ マップ](../../atl/message-maps-atl.md)"ATL ウィンドウ クラス"記事の内容。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
  
##  <a name="processwindowmessage"></a>CMessageMap::ProcessWindowMessage  
 識別されるメッセージ マップにアクセスする`dwMsgMapID`で、 `CMessageMap`-クラスを派生します。  
  
```
virtual BOOL ProcessWindowMessage(  
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT& lResult,
    DWORD dwMsgMapID) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
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
  
 `dwMsgMapID`  
 [in]メッセージを処理するメッセージ マップの識別子です。 宣言された既定のメッセージ マップ[送るに](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554)0 で識別されます。 宣言された、代替のメッセージ マップ[ALT_MSG_MAP(msgMapID)](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8)、によって識別される`msgMapID`します。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**場合は、メッセージが完全に処理済みでない場合は**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 ウィンドウ プロシージャによって呼び出される、 [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md)オブジェクトまたはオブジェクトのことを動的にチェーンをメッセージ マップです。  
  
## <a name="see-also"></a>関連項目  
 [CDynamicChain クラス](../../atl/reference/cdynamicchain-class.md)   
 [送るに](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554)   
 [ALT_MSG_MAP](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8)   
 [クラスの概要](../../atl/atl-class-overview.md)

