---
title: "CCmdUI クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCmdUI
dev_langs:
- C++
helpviewer_keywords:
- user interfaces, updating
- states, updating user interface object
- updating user interfaces for commands
- commands [C++], updating UI
- CCmdUI class
- toolbars [C++], updating
- command user interface
- menus [C++], updating as context changes
- buttons [C++], updating as context changes
ms.assetid: 04eaaaf5-f510-48ab-b425-94665ba24766
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: beb84a0f0f96c7a8acb5c432c7402b3e62b94518
ms.lasthandoff: 02/24/2017

---
# <a name="ccmdui-class"></a>CCmdUI クラス
内でのみ使用されて、`ON_UPDATE_COMMAND_UI`ハンドラーで、 `CCmdTarget`-クラスを派生します。  
  
## <a name="syntax"></a>構文  
  
```  
class CCmdUI  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CCmdUI::ContinueRouting](#continuerouting)|ハンドラーのチェーンに現在のメッセージを渡すようにコマンド ルーティング メカニズムに指示します。|  
|[関数](#enable)|有効または、このコマンドのユーザー インターフェイスの項目を無効にします。|  
|[CCmdUI::SetCheck](#setcheck)|このコマンドのユーザー インターフェイスの項目のチェックの状態を設定します。|  
|[CCmdUI::SetRadio](#setradio)|ように、`SetCheck`メンバー関数の場合は、オプション ボタン グループが動作します。|  
|[CCmdUI::SetText](#settext)|このコマンドのユーザー インターフェイス項目のテキストを設定します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CCmdUI::m_nID](#m_nid)|ユーザー インターフェイス オブジェクトの ID。|  
|[CCmdUI::m_nIndex](#m_nindex)|ユーザー インターフェイス オブジェクトのインデックス。|  
|[CCmdUI::m_pMenu](#m_pmenu)|によって表されるメニューが指す、`CCmdUI`オブジェクトです。|  
|[CCmdUI::m_pOther](#m_pother)|通知を送信したウィンドウ オブジェクトへのポインター。|  
|[CCmdUI::m_pSubMenu](#m_psubmenu)|によって表される包含のサブメニューを指す、`CCmdUI`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 `CCmdUI`基本クラスはありません。  
  
 ときに、アプリケーションのユーザーをプル ダウン メニューの各メニュー項目得る必要があるかどうかが表示されることが有効にした、または無効になっています。 メニュー コマンドのターゲット実装することでこの情報を提供する、`ON_UPDATE_COMMAND_UI`ハンドラー。 アプリケーション内のコマンドのユーザー インターフェイス オブジェクトごとに、各ハンドラについてのメッセージ マップ エントリと関数のプロトタイプを作成するのに [プロパティ] ウィンドウを使用します。  
  
 フレームワークを検索し、ごとに呼び出すとき、メニューがプルダウン`ON_UPDATE_COMMAND_UI`ハンドラー、各ハンドラーが呼び出す`CCmdUI`などのメンバー関数**を有効にする**と**チェック**、framework 適切に、各メニュー項目を表示します。  
  
 メニュー項目は、内のコードを変更することがなく、コントロール バー ボタンやその他のコマンドのユーザー インターフェイス オブジェクトに置き換えることが、`ON_UPDATE_COMMAND_UI`ハンドラー。  
  
 次の表に、効果`CCmdUI`メンバー関数はさまざまなコマンドのユーザー インターフェイスのアイテムができます。  
  
|ユーザー インターフェイスの項目|[有効化]|SetCheck|SetRadio|SetText|  
|--------------------------|------------|--------------|--------------|-------------|  
|メニュー項目|有効または無効化|(×) オンまたはオフに|ドット (•) を使用してチェック|項目テキストの設定|  
|ツール バー ボタン|有効または無効化|選択し、この選択を解除すると、未確定のいずれか|同じ`SetCheck`|(該当なし)|  
|ステータス バー ペイン|表示と非表示テキストは、します。|セットのポップアウトまたは通常の境界線|同じ`SetCheck`|ウィンドウのテキストを設定します。|  
|通常のボタン`CDialogBar`|有効または無効化|確認またはチェック ボックスをオフに|同じ`SetCheck`|ボタン テキストの設定|  
|通常の制御`CDialogBar`|有効または無効化|(該当なし)|(該当なし)|ウィンドウのテキストを設定します。|  
  
 このクラスの使用方法の詳細は、次を参照してください。[ユーザー インターフェイス オブジェクトの更新方法](../../mfc/how-to-update-user-interface-objects.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CCmdUI`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="a-namecontinueroutinga--ccmduicontinuerouting"></a><a name="continuerouting"></a>CCmdUI::ContinueRouting  
 ハンドラーのチェーンに現在のメッセージを渡すようにコマンド ルーティング メカニズムを確認するには、このメンバー関数を呼び出します。  
  
```  
void ContinueRouting();
```  
  
### <a name="remarks"></a>コメント  
 これは、高度なメンバー関数と組み合わせて使用する必要がありますが、`ON_COMMAND_EX`を返すハンドラー **FALSE**します。 詳細については、次を参照してください。[テクニカル ノート 6](../../mfc/tn006-message-maps.md)します。  
  
##  <a name="a-nameenablea--ccmduienable"></a><a name="enable"></a>関数  
 有効にするか、このコマンドのユーザー インターフェイスの項目を無効にするには、このメンバー関数を呼び出します。  
  
```  
virtual void Enable(BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bOn`  
 **TRUE** 、項目を有効にする**FALSE**を無効にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView&#46;](../../mfc/codesnippet/cpp/ccmdui-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #&47;](../../mfc/codesnippet/cpp/ccmdui-class_2.cpp)]  
  
##  <a name="a-namemnida--ccmduimnid"></a><a name="m_nid"></a>CCmdUI::m_nID  
 メニュー項目、ツール バー ボタンによって表されるその他のユーザー インターフェイス オブジェクトの ID、`CCmdUI`オブジェクトです。  
  
```  
UINT m_nID;  
```  
  
##  <a name="a-namemnindexa--ccmduimnindex"></a><a name="m_nindex"></a>CCmdUI::m_nIndex  
 メニュー項目、ツール バー ボタンまたはによって表されるその他のユーザー インターフェイス オブジェクトのインデックス、`CCmdUI`オブジェクトです。  
  
```  
UINT m_nIndex;  
```  
  
##  <a name="a-namempmenua--ccmduimpmenu"></a><a name="m_pmenu"></a>CCmdUI::m_pMenu  
 ポインター (の`CMenu`型) で表されるメニューに、`CCmdUI`オブジェクトです。  
  
```  
CMenu* m_pMenu;  
```  
  
### <a name="remarks"></a>コメント  
 **NULL**場合は、アイテムは、メニューではありません。  
  
##  <a name="a-namempsubmenua--ccmduimpsubmenu"></a><a name="m_psubmenu"></a>CCmdUI::m_pSubMenu  
 ポインター (の`CMenu`型) で表される包含のサブメニューを`CCmdUI`オブジェクトです。  
  
```  
CMenu* m_pSubMenu;  
```  
  
### <a name="remarks"></a>コメント  
 **NULL**場合は、アイテムは、メニューではありません。 Sub メニューがポップアップ ウィンドウ、ウィンドウの場合`m_nID`ポップアップ メニューの最初の項目の ID が含まれています。 詳細については、次を参照してください。[テクニカル ノート 21](../../mfc/tn021-command-and-message-routing.md)します。  
  
##  <a name="a-namempothera--ccmduimpother"></a><a name="m_pother"></a>CCmdUI::m_pOther  
 ポインター (型の`CWnd`) ツールバーやステータス バーなどのウィンドウ オブジェクトへの通知を送信しました。  
  
```  
CWnd* m_pOther;  
```  
  
### <a name="remarks"></a>コメント  
 **NULL**メニューまたは以外のかどうか、項目は`CWnd`オブジェクトです。  
  
##  <a name="a-namesetchecka--ccmduisetcheck"></a><a name="setcheck"></a>CCmdUI::SetCheck  
 このコマンドのユーザー インターフェイスの項目を適切なチェックの状態に設定するには、このメンバー関数を呼び出します。  
  
```  
virtual void SetCheck(int nCheck = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `nCheck`  
 設定する状態の確認を指定します。 場合は 0、オフにします。場合 1 をチェックします。2 の場合、不確定なを設定します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、メニュー項目とツール バー ボタンに動作します。 不確定な状態は、ツール バー ボタンにのみ適用されます。  
  
##  <a name="a-namesetradioa--ccmduisetradio"></a><a name="setradio"></a>CCmdUI::SetRadio  
 このコマンドのユーザー インターフェイスの項目を適切なチェックの状態に設定するには、このメンバー関数を呼び出します。  
  
```  
virtual void SetRadio(BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bOn`  
 **TRUE**アイテムを有効にするそれ以外の場合**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数のように動作する`SetCheck`オプション グループの一部として機能するユーザー インターフェイス項目上で動作する点を除いて、します。 項目自体は、オプション ボタン グループの動作を保持しない限り、グループ内の他の項目をオフにする自動はありません。  
  
##  <a name="a-namesettexta--ccmduisettext"></a><a name="settext"></a>CCmdUI::SetText  
 このコマンドのユーザー インターフェイスの項目のテキストを設定するには、このメンバー関数を呼び出します。  
  
```  
virtual void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszText`  
 テキスト文字列へのポインター。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&48;](../../mfc/codesnippet/cpp/ccmdui-class_3.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MDI](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)

