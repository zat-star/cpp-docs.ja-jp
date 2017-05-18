---
title: "CColorDialog クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CColorDialog
- AFXDLGS/CColorDialog
- AFXDLGS/CColorDialog::CColorDialog
- AFXDLGS/CColorDialog::DoModal
- AFXDLGS/CColorDialog::GetColor
- AFXDLGS/CColorDialog::GetSavedCustomColors
- AFXDLGS/CColorDialog::SetCurrentColor
- AFXDLGS/CColorDialog::OnColorOK
- AFXDLGS/CColorDialog::m_cc
dev_langs:
- C++
helpviewer_keywords:
- colors, dialog box
- dialog boxes, colors
- CColorDialog class
ms.assetid: d013dc25-9290-4b5d-a97e-95ad7208e13b
caps.latest.revision: 25
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a8aee088aadbca18acda348c574c8f4b55d1ecbb
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ccolordialog-class"></a>CColorDialog クラス
色の選択 ダイアログ ボックス、アプリケーションに組み込むことができます。  
  
## <a name="syntax"></a>構文  
  
```  
class CColorDialog : public CCommonDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CColorDialog::CColorDialog](#ccolordialog)|`CColorDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CColorDialog::DoModal](#domodal)|色のダイアログ ボックスが表示され、選択を行うことができます。|  
|[CColorDialog::GetColor](#getcolor)|返します。、 **COLORREF**選択した色の値を含む構造体。|  
|[CColorDialog::GetSavedCustomColors](#getsavedcustomcolors)|ユーザーによって作成されたカスタムの色を取得します。|  
|[CColorDialog::SetCurrentColor](#setcurrentcolor)|指定した色に現在の色の選択を強制します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CColorDialog::OnColorOK](#oncolorok)|ダイアログ ボックスに入力された色を検証するためにオーバーライドします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CColorDialog::m_cc](#m_cc)|構造体 ダイアログ ボックスの設定をカスタマイズするために使用します。|  
  
## <a name="remarks"></a>コメント  
 A`CColorDialog`オブジェクトはダイアログ ボックスに表示システムに対して定義されている色の一覧です。 ユーザーでは、選択したりは、報告アプリケーションにダイアログ ボックスの終了時に、一覧から特定の色を作成することができます。  
  
 構築する、`CColorDialog`オブジェクトまたは指定されたコンス トラクターを使用して、新しいクラスを派生、および独自のカスタム コンス トラクターを使用します。  
  
 ダイアログ ボックスを構築すると、設定または任意の値を変更、 [m_cc](#m_cc)  ダイアログ ボックスのコントロールの値を初期化するためにします。 `m_cc`型の構造は、 [CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830)します。  
  
 ダイアログ ボックスのコントロールを初期化した後、`DoModal`メンバー関数 ダイアログ ボックスが表示され、ユーザーが色を選択できるようにします。 `DoModal`いずれかのユーザーの選択 ダイアログ ボックスの ok を返します ( **IDOK**) またはキャンセル ( **IDCANCEL**) ボタンをクリックします。  
  
 場合`DoModal`返します**IDOK**のいずれかを使用する`CColorDialog`のユーザーが入力情報を取得するメンバー関数。  
  
 ウィンドウを使用できます[情報を得る](http://msdn.microsoft.com/library/windows/desktop/ms646916)関数 ダイアログ ボックスの初期化中にエラーが発生したかどうかを確認し、エラーについて説明します。  
  
 `CColorDialog`COMMDLG に依存します。Windows 3.1 以降のバージョンに付属している DLL ファイルです。  
  
 ダイアログ ボックスをカスタマイズするには、派生クラスを`CColorDialog`拡張されたコントロールからの通知メッセージを処理するメッセージ マップを追加、独自のダイアログ テンプレートを使用します。 処理されないメッセージは、基本クラスに渡す必要があります。  
  
 フック関数をカスタマイズする必要はありません。  
  
> [!NOTE]
>  いくつかのインストールで、`CColorDialog`させるその他のフレームワークを使用している場合、オブジェクトは背景が灰色表示されません`CDialog`オブジェクト灰色です。  
  
 使用する方法について`CColorDialog`を参照してください[コモン ダイアログ クラス](../../mfc/common-dialog-classes.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CColorDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdlgs.h  
  
##  <a name="ccolordialog"></a>CColorDialog::CColorDialog  
 `CColorDialog` オブジェクトを構築します。  
  
```  
CColorDialog(
    COLORREF clrInit = 0,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *clrInit*  
 既定色を選択します。 値が指定されていない場合は、既定値は RGB(0,0,0) (黒) にします。  
  
 `dwFlags`  
 関数と、ダイアログ ボックスの外観をカスタマイズするフラグのセットです。 詳細については、次を参照してください。、 [CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `pParentWnd`  
 ダイアログ ボックスの親ウィンドウまたはオーナー ウィンドウへのポインター。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView 番号&49;](../../mfc/codesnippet/cpp/ccolordialog-class_1.cpp)]  
  
##  <a name="domodal"></a>CColorDialog::DoModal  
 この関数では、Windows に共通の [色] ダイアログ ボックスを表示し、ユーザーが色を選択できるようにします。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 **IDOK**または**IDCANCEL**します。 場合**IDCANCEL**は、Windows を呼び出し、返される[情報を得る](http://msdn.microsoft.com/library/windows/desktop/ms646916)エラーが発生したかどうかを判断します。  
  
 **IDOK**と**IDCANCEL**をユーザーが [ok] または [キャンセル] ボタンを選択するかどうかを示す定数です。  
  
### <a name="remarks"></a>コメント  
 メンバーを設定して、さまざまな色 ダイアログ ボックスのオプションを初期化する場合、 [m_cc](#m_cc)構造体、呼び出す前に、これを行う必要があります`DoModal`はダイアログ ボックス オブジェクトを構築します。  
  
 呼び出した後`DoModal`、他のメンバー ダイアログ ボックスに、設定や、ユーザーが入力した情報を取得する関数を呼び出すことができます。  
  
### <a name="example"></a>例  
  例を参照してください[CColorDialog::CColorDialog](#ccolordialog)します。  
  
##  <a name="getcolor"></a>CColorDialog::GetColor  
 この関数を呼び出した後`DoModal`色の選択したユーザーに関する情報を取得します。  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)色 ダイアログ ボックスで選択した色の RGB 情報を含む値。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&50;](../../mfc/codesnippet/cpp/ccolordialog-class_2.cpp)]  
  
##  <a name="getsavedcustomcolors"></a>CColorDialog::GetSavedCustomColors  
 `CColorDialog`オブジェクトは、最大 16 個のカスタム カラーを定義するユーザー、色を選択するだけでなくを許可します。  
  
```  
static COLORREF* PASCAL GetSavedCustomColors();
```  
  
### <a name="return-value"></a>戻り値  
 ユーザーが作成したカスタム カラーを格納する 16 の RGB カラー値の配列を指すポインター。  
  
### <a name="remarks"></a>コメント  
 `GetSavedCustomColors`メンバー関数はこれらの色へのアクセスを提供します。 後にこれらの色を取得できる[DoModal](#domodal)返します**IDOK**します。  
  
 返される配列に 16 の RGB 値は、RGB(255,255,255) (白) に初期化されます。 アプリケーション内でのダイアログ ボックスの呼び出し間でのみ、ユーザーが選択したカスタムの色が保存されます。 呼び出し、アプリケーションの間のこれらの色を保存する場合は、する必要がありますに保存、他の方法など、初期化時に (します。INI) ファイルです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView&51;](../../mfc/codesnippet/cpp/ccolordialog-class_3.cpp)]  
  
##  <a name="m_cc"></a>CColorDialog::m_cc  
 型の構造体[CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830)メンバーの特性と、ダイアログ ボックスの値を格納します。  
  
```  
CHOOSECOLOR m_cc;  
```  
  
### <a name="remarks"></a>コメント  
 構築した後、`CColorDialog`オブジェクトを使用する`m_cc`を呼び出す前に、ダイアログ ボックスのさまざまな側面を設定する、 [DoModal](#domodal)メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&53;](../../mfc/codesnippet/cpp/ccolordialog-class_4.cpp)]  
  
##  <a name="oncolorok"></a>CColorDialog::OnColorOK  
 ダイアログ ボックスに入力された色を検証するためにオーバーライドします。  
  
```  
virtual BOOL OnColorOK();
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、ダイアログ ボックスを消去しない必要があります。入力された色を受け入れるようにそれ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 カラー ダイアログ ボックスで、ユーザーが選択した色のカスタム検証を提供する場合は、この関数をオーバーライドします。  
  
 ユーザーは、次の&2; つのメソッドのいずれかによって、色を選択できます。  
  
-   カラー パレットに色をクリックします。 選択した色の RGB 値は、適切な RGB 編集ボックスに反映されます。  
  
-   エディット ボックスに、RGB 値を入力します。  
  
 オーバーライドする`OnColorOK`ユーザーはアプリケーション固有の何らかの一般的な色のダイアログ ボックスに入力色を拒否することができます。  
  
 通常、フレームワークが色の既定の検証を提供し、無効な色が入力した場合は、メッセージ ボックスを表示するために、この関数を使用する必要はありません。  
  
 呼び出すことができます[SetCurrentColor](#setcurrentcolor)内から`OnColorOK`色の選択を強制します。 1 回`OnColorOK`通知されている (つまり、ユーザーがクリックした**[ok]** 、色の変更を受け入れるように)、呼び出すことができます[GetColor](#getcolor)新しい色の RGB 値を取得します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&52;](../../mfc/codesnippet/cpp/ccolordialog-class_5.cpp)]  
  
##  <a name="setcurrentcolor"></a>CColorDialog::SetCurrentColor  
 この関数を呼び出した後`DoModal`で指定された色の値を現在の色の選択を強制的に`clr`します。  
  
```  
void SetCurrentColor(COLORREF clr);
```  
  
### <a name="parameters"></a>パラメーター  
 `clr`  
 RGB 色の値。  
  
### <a name="remarks"></a>コメント  
 この関数は、メッセージ ハンドラー内から呼び出されるまたは`OnColorOK`です。 ダイアログ ボックスは、ユーザーの選択の値に基づいて自動的に更新、`clr`パラメーター。  
  
### <a name="example"></a>例  
  例を参照してください[CColorDialog::OnColorOK](#oncolorok)します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MDI](../../visual-cpp-samples.md)   
 [MFC サンプル DRAWCLI](../../visual-cpp-samples.md)   
 [CCommonDialog クラス](../../mfc/reference/ccommondialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)


