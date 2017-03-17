---
title: "COleBusyDialog クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleBusyDialog
- AFXODLGS/COleBusyDialog
- AFXODLGS/COleBusyDialog::COleBusyDialog
- AFXODLGS/COleBusyDialog::DoModal
- AFXODLGS/COleBusyDialog::GetSelectionType
- AFXODLGS/COleBusyDialog::m_bz
dev_langs:
- C++
helpviewer_keywords:
- Server Not Responding dialog box
- Server Busy dialog box
- COleBusyDialog class
ms.assetid: c881a532-9672-4c41-b51b-5ce4a7246a6b
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 0c3ed264cdb83bc97337f13279a20f26b21d454b
ms.lasthandoff: 02/24/2017

---
# <a name="colebusydialog-class"></a>COleBusyDialog クラス
OLE の [サーバーが応答しません] ダイアログ ボックスまたは [サーバーを使用できません] ダイアログ ボックスに使用されます。  
  
## <a name="syntax"></a>構文  
  
```  
class COleBusyDialog : public COleDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleBusyDialog::COleBusyDialog](#colebusydialog)|`COleBusyDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleBusyDialog::DoModal](#domodal)|サーバー使用中のダイアログ ボックスが表示されます。|  
|[COleBusyDialog::GetSelectionType](#getselectiontype)|ダイアログ ボックスで行った選択を決定します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleBusyDialog::m_bz](#m_bz)|型の構造体**OLEUIBUSY**  ダイアログ ボックスの動作を制御します。|  
  
## <a name="remarks"></a>コメント  
 クラスのオブジェクトを作成`COleBusyDialog`これらのダイアログ ボックスを呼び出そうとするとします。 後に、`COleBusyDialog`使用すると、オブジェクトが構築された、[各](#m_bz)値やダイアログ ボックスのコントロールの状態を初期化するためにします。 `m_bz`型の構造は、 **OLEUIBUSY**します。 このダイアログ ボックスの使い方の詳細については、次を参照してください。、 [DoModal](#domodal)メンバー関数。  
  
> [!NOTE]
>  アプリケーション ウィザードで生成されたコンテナーのコードでは、このクラスを使用します。  
  
 詳細については、次を参照してください。、 [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 OLE 固有のダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [関数](../../mfc/reference/coledialog-class.md)  
  
 `COleBusyDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxodlgs.h  
  
##  <a name="colebusydialog"></a>COleBusyDialog::COleBusyDialog  
 この関数は、`COleBusyDialog`オブジェクトです。  
  
```  
explicit COleBusyDialog(
    HTASK htaskBusy,  
    BOOL bNotResponding = FALSE,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *htaskBusy*  
 ビジー状態であるサーバーのタスクへのハンドルします。  
  
 *bNotResponding*  
 場合**TRUE**サーバーがビジー状態のダイアログ ボックスではなく、応答していません ダイアログ ボックスを呼び出します。 応答していません ダイアログ ボックスの内容は、サーバーがビジー状態 ダイアログ ボックスの内容と若干異なると、キャンセル ボタンが無効になっています。  
  
 `dwFlags`  
 作成フラグ。 0 個以上のビットごとの OR 演算子で結合する次の値を含めることができます。  
  
- **BZ_DISABLECANCELBUTTON**  ダイアログ ボックスが呼び出されたときに、キャンセル ボタンを無効にします。  
  
- **BZ_DISABLESWITCHTOBUTTON**  ダイアログ ボックスが呼び出されたときに、切り替え先 ボタンを無効にします。  
  
- **BZ_DISABLERETRYBUTTON**  ダイアログ ボックスが呼び出されたときに、再試行 ボタンを無効にします。  
  
 `pParentWnd`  
 親またはオーナー ウィンドウのオブジェクトを指します (型の`CWnd`) ダイアログ オブジェクトが属しています。 ある場合**NULL**アプリケーションのメイン ウィンドウに、ダイアログ オブジェクトの親ウィンドウが設定されています。  
  
### <a name="remarks"></a>コメント  
 ダイアログ ボックスを表示するには、呼び出す[DoModal](#domodal)します。  
  
 詳細については、次を参照してください。、 [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="domodal"></a>COleBusyDialog::DoModal  
 サーバー ビジー状態であるか、サーバーが応答しません ダイアログ ボックスを表示するには、この関数を呼び出します。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスの終了ステータスです。 次のいずれかの値です。  
  
- **IDOK**  ダイアログ ボックスが正常に表示された場合。  
  
- **IDCANCEL**場合は、ユーザーがダイアログ ボックスをキャンセルします。  
  
- **IDABORT**場合はエラーが発生しました。 場合**IDABORT**は呼び出しが返される、`COleDialog::GetLastError`の詳細については、発生したエラーの種類を取得します。 考えられるエラーの一覧については、次を参照してください。、 [OleUIBusy](http://msdn.microsoft.com/library/windows/desktop/ms680125)で機能、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 メンバーを設定して、さまざまなダイアログ ボックス コントロールを初期化する場合、[各](#m_bz)構造体を呼び出す前に、これを行う必要があります`DoModal`はダイアログ オブジェクトを構築します。  
  
 場合`DoModal`返します**IDOK**、他のメンバーの設定やユーザー ダイアログ ボックスに入力した情報を取得する関数を呼び出すことができます。  
  
##  <a name="getselectiontype"></a>COleBusyDialog::GetSelectionType  
 サーバーがビジー状態のダイアログ ボックスでユーザーが選択した型を取得するには、この関数を呼び出します。  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択内容の種類です。  
  
### <a name="remarks"></a>コメント  
 戻り値の型の値がで指定された、**選択**で宣言された列挙型、`COleBusyDialog`クラスです。  
  
 `enum Selection`  
  
 `{`  
  
 `switchTo,`  
  
 `retry,`  
  
 `callUnblocked`  
  
 `};`  
  
 これらの値の簡単な説明に従ってください。  
  
- **COleBusyDialog::switchTo**切り替えボタンが押されました。  
  
- **COleBusyDialog::retry** [再試行] ボタンが押されました。  
  
- **COleBusyDialog::callUnblocked**サーバーをアクティブ化の呼び出しが、ブロック解除します。  
  
##  <a name="m_bz"></a>COleBusyDialog::m_bz  
 型の構造体**OLEUIBUSY**サーバーがビジー状態のダイアログ ボックスの動作を制御するために使用します。  
  
```  
OLEUIBUSY m_bz;  
```  
  
### <a name="remarks"></a>コメント  
 この構造体のメンバーは、直接またはメンバー関数を使って変更できます。  
  
 詳細については、次を参照してください。、 [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [関数のクラス](../../mfc/reference/coledialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [関数のクラス](../../mfc/reference/coledialog-class.md)

