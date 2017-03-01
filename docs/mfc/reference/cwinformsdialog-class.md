---
title: "CWinFormsDialog クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinFormsDialog
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- CWinFormsDialog class
- Windows Forms [C++], MFC support
ms.assetid: e3cec000-a578-448e-b06a-8af256312f61
caps.latest.revision: 26
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
ms.openlocfilehash: 86768a849b0112f7c4f8b6b2a694b80065169575
ms.lasthandoff: 02/24/2017

---
# <a name="cwinformsdialog-class"></a>CWinFormsDialog クラス
Windows フォーム ユーザー コントロールをホストする MFC ダイアログ クラスのラッパーです。  
  
## <a name="syntax"></a>構文  
  
```  
template <typename TManagedControl>  
class CWinFormsDialog :   
    public CDialog  
```  
  
#### <a name="parameters"></a>パラメーター  
 `TManagedControl`  
 MFC アプリケーションに表示される .NET Framework ユーザー コントロール。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CWinFormsDialog::CWinFormsDialog](#cwinformsdialog)|`CWinFormsDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CWinFormsDialog::GetControl](#getcontrol)|Windows フォーム ユーザー コントロールへの参照を取得します。|  
|[CWinFormsDialog::GetControlHandle](#getcontrolhandle)|Windows フォーム ユーザー コントロールにウィンドウ ハンドルを取得します。|  
|[CWinFormsDialog::OnInitDialog](#oninitdialog)|上の Windows フォーム ユーザー コントロールのホストを作成して、MFC ダイアログ ボックスを初期化します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前||  
|----------|-|  
|[CWinFormsDialog::operator-&gt;](#operator_-_gt)|置換[CWinFormsDialog::GetControl](#getcontrol)式にします。|  
|[CWinFormsDialog::operator TManagedControl ^](#operator_tmanagedcontrol)|Windows フォーム ユーザー コントロールへの参照として型をキャストします。|  
  
## <a name="remarks"></a>コメント  
 `CWinFormsDialog`MFC ダイアログ クラスのラッパーです ( [CDialog](../../mfc/reference/cdialog-class.md)) Windows フォーム ユーザー コントロールをホストします。 これにより、.NET Framework、モーダルまたはモードレスの MFC ダイアログ ボックスのコントロールの表示できます。  
  
 Windows フォームの使用に関する詳細については、次を参照してください。 [MFC では、Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)と[MFC ダイアログ ボックスとしての Windows フォーム ユーザー コントロールをホストしている](../../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwinforms.h  
  
##  <a name="a-namecwinformsdialoga--cwinformsdialogcwinformsdialog"></a><a name="cwinformsdialog"></a>CWinFormsDialog::CWinFormsDialog  
 `CWinFormsDialog` オブジェクトを構築します。  
  
```  
CWinFormsDialog(UINT nIDTemplate = IDD);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDTemplate`  
 ダイアログ ボックスのテンプレート リソースの ID が含まれています。 ダイアログ テンプレートを作成し、アプリケーションのリソース スクリプト ファイルに保存するには、ダイアログ エディターを使用します。 ダイアログ テンプレートの詳細については、次を参照してください。 [CDialog クラス](../../mfc/reference/cdialog-class.md)します。  
  
##  <a name="a-namegetcontrola--cwinformsdialoggetcontrol"></a><a name="getcontrol"></a>CWinFormsDialog::GetControl  
 Windows フォーム ユーザー コントロールへの参照を取得します。  
  
```  
inline TManagedControl^ GetControl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 MFC ダイアログ ボックスで、Windows フォーム コントロールへの参照を返します。  
  
##  <a name="a-namegetcontrolhandlea--cwinformsdialoggetcontrolhandle"></a><a name="getcontrolhandle"></a>CWinFormsDialog::GetControlHandle  
 Windows フォーム ユーザー コントロールにウィンドウ ハンドルを取得します。  
  
```  
inline HWND GetControlHandle() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 Windows フォーム ユーザー コントロールにウィンドウ ハンドルを返します。  
  
##  <a name="a-nameoninitdialoga--cwinformsdialogoninitdialog"></a><a name="oninitdialog"></a>CWinFormsDialog::OnInitDialog  
 上の Windows フォーム ユーザー コントロールのホストを作成して、MFC ダイアログ ボックスを初期化します。  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>戻り値  
 アプリケーションがダイアログ ボックスで、コントロールのいずれかに入力フォーカスを設定したかどうかを指定するブール値。 場合`OnInitDialog`戻り値は&0; 以外の値、Windows 入力フォーカスを設定する最初のコントロール ダイアログ ボックス。 このメソッドは、アプリケーションは、ダイアログ ボックスで、コントロールのいずれかに入力フォーカスを明示的に設定が場合にのみ、0 を返すことができます。  
  
### <a name="remarks"></a>コメント  
 MFC ダイアログ ボックスを作成するときに (を使用して、[作成](../../mfc/reference/cdialog-class.md#create)、 [CreateIndirect](../../mfc/reference/cdialog-class.md#createindirect)、または[DoModal](../../mfc/reference/cdialog-class.md#domodal)から継承されたメソッド[CDialog](../../mfc/reference/cdialog-class.md))、`WM_INITDIALOG`メッセージが送信され、このメソッドが呼び出されます。 ダイアログ ボックス上の Windows フォーム コントロールのインスタンスを作成し、ユーザー コントロールのサイズに合わせて調整する ダイアログ ボックスのサイズを調整します。 MFC ダイアログ ボックスで新しいコントロールをホストします。  
  
 ダイアログ ボックスの初期化時に、特別な処理を実行する必要がある場合は、このメンバー関数をオーバーライドします。 このメソッドの使用に関する詳細については、次を参照してください。 [CDialog::OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog)します。  
  
##  <a name="a-nameoperator-gta--cwinformsdialogoperator--gt"></a><a name="operator_-_gt"></a>CWinFormsDialog::operator-&gt;  
 置換[CWinFormsDialog::GetControl](#getcontrol)式にします。  
  
```  
inline TManagedControl^  operator->() const throw();
```  
  
### <a name="remarks"></a>コメント  
 この演算子は、便利な構文を置き換える`GetControl`式にします。  
  
 Windows フォームの使用方法の詳細については、次を参照してください。 [MFC では、Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)します。  
  
##  <a name="a-nameoperatortmanagedcontrolxora--cwinformsdialogoperator-tmanagedcontrol"></a><a name="operator_tmanagedcontrol_xor"></a>CWinFormsDialog::operator TManagedControl ^  
 Windows フォーム ユーザー コントロールへの参照として型をキャストします。  
  
```  
inline operator TManagedControl^() const throw();
```  
  
### <a name="remarks"></a>コメント  
 この演算子は、Windows フォーム コントロールへの参照として型をキャストします。 渡すのに、`CWinFormsDialog<``TManagedControl``>`ダイアログ ボックスで、Windows フォーム ユーザー コントロールのオブジェクトへのポインターを受け取る関数をします。  
  
## <a name="see-also"></a>関連項目  
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [CWinFormsView クラス](../../mfc/reference/cwinformsview-class.md)   
 [CDialog クラス](../../mfc/reference/cdialog-class.md)

