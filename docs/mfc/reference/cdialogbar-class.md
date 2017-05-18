---
title: "CDialogBar クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDialogBar
- AFXEXT/CDialogBar
- AFXEXT/CDialogBar::CDialogBar
- AFXEXT/CDialogBar::Create
dev_langs:
- C++
helpviewer_keywords:
- dialog bars, Windows modeless dialog box
- CDialogBar class
- dialog boxes, modeless
ms.assetid: da2f7a30-970c-44e3-87f0-6094bd002cab
caps.latest.revision: 23
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
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 33dc5f5f4d345745a4b9435e725f411f4387e287
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cdialogbar-class"></a>CDialogBar クラス
コントロール バー内の Windows のモードレス ダイアログ ボックスの機能を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDialogBar : public CControlBar  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDialogBar::CDialogBar](#cdialogbar)|`CDialogBar` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDialogBar::Create](#create)|Windows ダイアログ バーを作成し、それをアタッチ、`CDialogBar`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 ダイアログ バーでは、tab キーでの Windows の標準のコントロールを持つという点で、ダイアログ ボックスに似ています。 もう&1; つの類似性は、ダイアログ バーを表すためのダイアログ テンプレートを作成することです。  
  
 作成して、ダイアログ バーの使い方が作成および使用法のような`CFormView`オブジェクトです。 まず、使用して、[ダイアログ エディター](../../windows/dialog-editor.md)スタイルでダイアログ テンプレートを定義する**WS_CHILD**としないその他のスタイル。 テンプレートには、スタイルが必要ない**WS_VISIBLE**します。 アプリケーション コードで構築するコンス トラクターを呼び出す、`CDialogBar`オブジェクトを呼び出す**作成**ダイアログ バーのウィンドウを作成し、添付、`CDialogBar`オブジェクトです。  
  
 詳細については`CDialogBar`、記事を参照して[ダイアログ バー](../../mfc/dialog-bars.md)と[テクニカル ノート 31](../../mfc/tn031-control-bars.md)、コントロール バーです。  
  
> [!NOTE]
>  現在のリリースで、`CDialogBar`オブジェクトは、Windows フォーム コントロールをホストできません。 Visual C での Windows フォーム コントロールの詳細については、次を参照してください。 [MFC では、Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CDialogBar`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxext.h  
  
##  <a name="cdialogbar"></a>CDialogBar::CDialogBar  
 `CDialogBar` オブジェクトを構築します。  
  
```  
CDialogBar();
```  
  
##  <a name="create"></a>CDialogBar::Create  
 指定したダイアログ ボックス リソース テンプレートを読み込みます`lpszTemplateName`または`nIDTemplate`、ダイアログ バーのウィンドウを作成、そのスタイルを設定および関連付けます、`CDialogBar`オブジェクトです。  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    LPCTSTR lpszTemplateName,  
    UINT nStyle,  
    UINT nID);

 
virtual BOOL Create(
    CWnd* pParentWnd,  
    UINT nIDTemplate,  
    UINT nStyle,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentWnd`  
 親へのポインター`CWnd`オブジェクトです。  
  
 `lpszTemplateName`  
 名前へのポインター、`CDialogBar`オブジェクトのダイアログ ボックス リソースのテンプレートです。  
  
 `nStyle`  
 ツールバーのスタイル。 追加のスタイルは次のとおりです。  
  
- `CBRS_TOP`コントロール バーは、フレーム ウィンドウの上部には。  
  
- `CBRS_BOTTOM`コントロール バーでは、フレーム ウィンドウの下部にあります。  
  
- `CBRS_NOALIGN`コントロール バーは、親のサイズが変更されたときに再配置されません。  
  
- `CBRS_TOOLTIPS`コントロール バーには、ツール ヒントが表示されます。  
  
- **CBRS_SIZE_DYNAMIC**コントロール バーは動的です。  
  
- **CBRS_SIZE_FIXED**コントロール バーを固定します。  
  
- **CBRS_FLOATING**コントロール バーがフローティングします。  
  
- `CBRS_FLYBY`ステータス バーには、ボタンについての情報が表示されます。  
  
- **CBRS_HIDE_INPLACE**コントロール バーがユーザーに表示されません。  
  
 `nID`  
 ダイアログ バーのコントロールの ID。  
  
 `nIDTemplate`  
 リソース ID、`CDialogBar`オブジェクトのダイアログ ボックスのテンプレートです。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 指定した場合、`CBRS_TOP`または`CBRS_BOTTOM`配置スタイル ダイアログ バーの幅は、フレーム ウィンドウの高さで指定されたリソースの`nIDTemplate`です。 指定した場合、`CBRS_LEFT`または`CBRS_RIGHT`配置スタイル ダイアログ バーの高さは、フレーム ウィンドウのその幅で指定されたリソースの`nIDTemplate`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCMessageMaps&#13;](../../mfc/reference/codesnippet/cpp/cdialogbar-class_1.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CTRLBARS](../../visual-cpp-samples.md)   
 [CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFormView クラス](../../mfc/reference/cformview-class.md)   
 [CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)

