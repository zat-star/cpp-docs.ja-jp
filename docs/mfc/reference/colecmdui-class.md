---
title: "COleCmdUI クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleCmdUI
- AFXDOCOBJ/COleCmdUI
- AFXDOCOBJ/COleCmdUI::COleCmdUI
- AFXDOCOBJ/COleCmdUI::Enable
- AFXDOCOBJ/COleCmdUI::SetCheck
- AFXDOCOBJ/COleCmdUI::SetText
dev_langs:
- C++
helpviewer_keywords:
- document object server
- COleCmdUI class
- servers [C++], ActiveX documents
- docobject server
- servers [C++], doc objects
- ActiveX documents [C++], document server
ms.assetid: a2d5ce08-6657-45d3-8673-2a9f32d50eec
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 38e7019d7636166262028d955455cee675824f8b
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="colecmdui-class"></a>COleCmdUI クラス
アプリケーションの `IOleCommandTarget`ドリブンの機能に関連するユーザー インターフェイス オブジェクトの状態を更新するメソッドを MFC に提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class COleCmdUI : public CCmdUI  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleCmdUI::COleCmdUI](#colecmdui)|`COleCmdUI` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleCmdUI::Enable](#enable)|設定または有効にするコマンドのフラグをクリアします。|  
|[COleCmdUI::SetCheck](#setcheck)|オン/オフ切り替えの状態を設定するコマンドです。|  
|[COleCmdUI::SetText](#settext)|コマンドのテキストの名前またはステータス文字列を返します。|  
  
## <a name="remarks"></a>コメント  
 有効になっていない DocObjects、ユーザーは、MFC プロセス、アプリケーションでメニューを表示すると、アプリケーションで**UPDATE_COMMAND_UI**通知します。 各通知、 [CCmdUI](../../mfc/reference/ccmdui-class.md)特定のコマンドの状態を反映するように操作できるオブジェクト。 ただし、アプリケーションは DocObjects の有効な場合、MFC 処理**UPDATE_OLE_COMMAND_UI**通知と割り当てます`COleCmdUI`オブジェクトです。  
  
 `COleCmdUI`コマンド (という名前、開く、印刷、およびなど) などのコンテナーのユーザー インターフェイスを受信する DocObject をでき、DocObject のユーザー インターフェイスで発生するコマンドを受信するためのコンテナーです。 `IDispatch`同じコマンドがディスパッチされる可能性があります`IOleCommandTarget`を照会し、標準的な一連の引数を指定せずに通常のコマンドに依存し、型情報が関与していないために、実行する簡単な方法を提供します。 `COleCmdUI`有効にする、更新、および DocObject ユーザー インターフェイスのコマンドの他のプロパティを設定するために使用します。 コマンドを呼び出す場合は、呼び出す[COleServerDoc::OnExecOleCmd](../../mfc/reference/coleserverdoc-class.md#onexecolecmd)します。  
  
 DocObjects については、次を参照してください。[関数](../../mfc/reference/cdocobjectserver-class.md)と[CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md)します。 参照してください[インターネットの最初の手順: アクティブなドキュメント](../../mfc/active-documents-on-the-internet.md)と[アクティブ ドキュメント](../../mfc/active-documents-on-the-internet.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CCmdUI](../../mfc/reference/ccmdui-class.md)  
  
 `COleCmdUI`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdocobj.h  
  
##  <a name="colecmdui"></a>COleCmdUI::COleCmdUI  
 構築、`COleCmdUI`特定のユーザー インターフェイス コマンドに関連付けられたオブジェクト。  
  
```  
COleCmdUI(
    OLECMD* rgCmds,  
    ULONG cCmds,  
    const GUID* m_pGroup);
```  
  
### <a name="parameters"></a>パラメーター  
 `rgCmds`  
 指定された GUID に関連付けられている、サポートされているコマンドの一覧。 **OLECMD**構造体は、コマンドのフラグでコマンドを関連付けます。  
  
 *cCmds*  
 コマンド数`rgCmds`します。  
  
 `pGroup`  
 コマンドのセットを識別する GUID へのポインター。  
  
### <a name="remarks"></a>コメント  
 `COleCmdUI`オブジェクトは、メニュー項目やコントロール バーのボタンなどの DocObject ユーザー インターフェイス オブジェクトを更新するためのプログラム インターフェイスを提供します。 ユーザー インターフェイス オブジェクトを有効になっている、無効になっている、オンになっているおよびをオフになって、`COleCmdUI`オブジェクトです。  
  
##  <a name="enable"></a>COleCmdUI::Enable  
 コマンド フラグを設定するには、この関数を呼び出す、`COleCmdUI`オブジェクトを**OLECOMDF_ENABLED**インターフェイスを指定すると、コマンドは、利用可能で、有効になっている、またはコマンドのフラグをクリアします。  
  
```  
virtual void Enable(BOOL bOn);
```  
  
### <a name="parameters"></a>パラメーター  
 `bOn`  
 コマンドに関連付けられているかどうかを示す、`COleCmdUI`オブジェクトを有効または無効にする必要があります。 0 以外、コマンドを使用します。0 は、コマンドを無効にします。  
  
##  <a name="setcheck"></a>COleCmdUI::SetCheck  
 この関数のオン/オフ切り替えの状態を設定するコマンドです。  
  
```  
virtual void SetCheck(int nCheck);
```  
  
### <a name="parameters"></a>パラメーター  
 `nCheck`  
 オン/オフ切り替えを設定する状態を決定する値コマンドです。 値は次のとおりです。  
  
|値|説明|  
|-----------|-----------------|  
|**1**|オン に、コマンドを設定します。|  
|**2**|不確定コマンドを設定します。両方の内外で関連する選択項目の状態、コマンドの属性がであるために、状態を特定できません。|  
|その他の値|コマンドをオフに設定します。|  
  
##  <a name="settext"></a>COleCmdUI::SetText  
 この関数では、コマンドのテキストの名前または状態文字列を取得します。  
  
```  
virtual void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszText`  
 コマンドを使用して使用するテキストへのポインター。  
  
## <a name="see-also"></a>関連項目  
 [CCmdUI クラス](../../mfc/reference/ccmdui-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)




