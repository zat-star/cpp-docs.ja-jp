---
title: "CPropertyPage クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPropertyPage
dev_langs:
- C++
helpviewer_keywords:
- property pages, CPropertyPage class
- dialog boxes, tabs
- CPropertyPage class
- tab dialog boxes
ms.assetid: d9000a21-aa81-4530-85d9-f43432afb4dc
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 13fb9befb6d1549493afa6cbed53ec4d41443c3a
ms.lasthandoff: 02/24/2017

---
# <a name="cpropertypage-class"></a>CPropertyPage クラス
タブ ダイアログ ボックスとして知られているプロパティ シートの各ページを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CPropertyPage : public CDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CPropertyPage::CPropertyPage](#cpropertypage)|`CPropertyPage` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPropertyPage::CancelToClose](#canceltoclose)|[閉じる] ボタンに変更し、モーダル プロパティ シートのページで、回復不可能な変更の後に [キャンセル] ボタンを無効にします。|  
|[CPropertyPage::Construct](#construct)|`CPropertyPage` オブジェクトを構築します。 使用`Construct`、実行時に、パラメーターを指定する場合、または配列を使用している場合。|  
|[CPropertyPage::GetPSP](#getpsp)|Windows の取得[PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548)構造に関連付けられている、`CPropertyPage`オブジェクトです。|  
|[CPropertyPage::OnApply](#onapply)|適用 ボタンがクリックされたときに、フレームワークによって呼び出されます。|  
|[CPropertyPage::OnCancel](#oncancel)|[キャンセル] ボタンがクリックされたときに、フレームワークによって呼び出されます。|  
|[CPropertyPage::OnKillActive](#onkillactive)|現在のページがアクティブでは不要になったときに、フレームワークによって呼び出されます。 ここでデータの検証を実行します。|  
|[送るに](#onok)|Ok、今すぐ適用または 閉じる ボタンがクリックされたときに、フレームワークによって呼び出されます。|  
|[CPropertyPage::OnQueryCancel](#onquerycancel)|[キャンセル] ボタンがクリックされたときに、キャンセルが行われる前に、フレームワークによって呼び出されます。|  
|[CPropertyPage::OnReset](#onreset)|[キャンセル] ボタンがクリックされたときに、フレームワークによって呼び出されます。|  
|[CPropertyPage::OnSetActive](#onsetactive)|ページには、アクティブなページが行われたときに、フレームワークによって呼び出されます。|  
|[CPropertyPage::OnWizardBack](#onwizardback)|ウィザードの種類のプロパティ シートを使用しているときに、[戻る] ボタンがクリックされたときに、フレームワークによって呼び出されます。|  
|[CPropertyPage::OnWizardFinish](#onwizardfinish)|ウィザードの種類のプロパティ シートを使用しているときに、[完了] をクリックすると、フレームワークによって呼び出されます。|  
|[CPropertyPage::OnWizardNext](#onwizardnext)|ウィザード形式のプロパティ シートを使用しているときに、次のボタンがクリックされたときに、フレームワークによって呼び出されます。|  
|[CPropertyPage::QuerySiblings](#querysiblings)|プロパティ シートの各ページにメッセージを転送します。|  
|[CPropertyPage::SetModified](#setmodified)|アクティブ化または適用 ボタンを非アクティブ化を呼び出します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPropertyPage::m_psp](#m_psp)|Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548)構造体。 基本的なプロパティ ページのパラメーターへのアクセスを提供します。|  
  
## <a name="remarks"></a>コメント  
 クラスを派生する標準のダイアログ ボックスで、`CPropertyPage`プロパティ シートのページごとにします。 使用する`CPropertyPage`-派生オブジェクトを作成、 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)オブジェクト、およびプロパティ シートに移動する各ページのオブジェクトを作成します。 呼び出す[が](../../mfc/reference/cpropertysheet-class.md#addpage)ごとに、シートのページし、呼び出すことで、プロパティ シートを表示[する](../../mfc/reference/cpropertysheet-class.md#domodal)、モーダル プロパティ シートのまたは[CPropertySheet::Create](../../mfc/reference/cpropertysheet-class.md#create)モードレス プロパティ シートにします。  
  
 デバイスのセットアップやニュースレターを作成するなどの操作の手順を追ってプロパティ ページのシーケンスを持つプロパティ シートから成る、ウィザードと呼ばれるタブ ダイアログ ボックスの種類を作成できます。 ウィザードの種類 タブのダイアログ ボックスでは、プロパティ ページのタブがないと、一度に&1; つのプロパティ ページが表示されます。 また、ボタンが ok と 今すぐ適用するのではなく、ウィザードの種類 タブ ダイアログには、戻る ボタン、次へ または 完了 ボタン、キャンセル ボタン。  
  
 ウィザードとプロパティ シートを確立する方法の詳細については、次を参照してください。 [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)します。 使用する方法について`CPropertyPage`オブジェクト、記事を参照して[プロパティ シートとプロパティ ページ](../../mfc/property-sheets-and-property-pages-in-mfc.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CPropertyPage`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdlgs.h  
  
##  <a name="a-namecanceltoclosea--cpropertypagecanceltoclose"></a><a name="canceltoclose"></a>CPropertyPage::CancelToClose  
 モーダル プロパティ シートのページ内のデータを回復できない変更が行われた後は、この関数を呼び出します。  
  
```  
void CancelToClose();
```  
  
### <a name="remarks"></a>コメント  
 この関数は、[ok] ボタンを閉じるに変更し、[キャンセル] ボタンを無効にします。 これは、変更、アラートの変更が確定され、変更があるユーザーはキャンセルできません。  
  
 `CancelToClose`モードレス プロパティ シートが既定では [キャンセル] ボタンを持っていないのでメンバー関数は、モードレス プロパティ シートではありません。  
  
### <a name="example"></a>例  
  例を参照してください[CPropertyPage::QuerySiblings](#querysiblings)します。  
  
##  <a name="a-nameconstructa--cpropertypageconstruct"></a><a name="construct"></a>CPropertyPage::Construct  
 作成するには、このメンバー関数を呼び出す、`CPropertyPage`オブジェクトです。  
  
```  
void Construct(
    UINT nIDTemplate,  
    UINT nIDCaption = 0);

 
void Construct(
    LPCTSTR lpszTemplateName,  
    UINT nIDCaption = 0);

 
void Construct(
    UINT nIDTemplate,  
    UINT nIDCaption,  
    UINT nIDHeaderTitle,  
    UINT nIDHeaderSubTitle = 0);

 
void Construct(
    LPCTSTR lpszTemplateName,  
    UINT nIDCaption,  
    UINT nIDHeaderTitle,  
    UINT nIDHeaderSubTitle = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDTemplate`  
 このページで使用するテンプレートの ID です。  
  
 `nIDCaption`  
 このページのタブ内に配置する名前の ID。 0 の場合、名前がこのページのダイアログ テンプレートから取得されます。  
  
 `lpszTemplateName`  
 テンプレート リソースの名前を指定する null で終わる文字列が含まれています。  
  
 `nIDHeaderTitle`  
 プロパティ ページのヘッダーのタイトルの位置に配置する名前の ID です。 既定では 0 です。  
  
 `nIDHeaderSubTitle`  
 プロパティ ページのヘッダーのサブタイトルの場所に配置する名前の ID です。 既定では 0 です。  
  
### <a name="remarks"></a>コメント  
 すべての次の条件が満たされた後、オブジェクトが表示されます。  
  
-   ページを使用してプロパティ シートに追加された[が](../../mfc/reference/cpropertysheet-class.md#addpage)です。  
  
-   プロパティ シートの[DoModal](../../mfc/reference/cpropertysheet-class.md#domodal)または[作成](../../mfc/reference/cpropertysheet-class.md#create)関数が呼び出されました。  
  
-   ユーザーが選択されています (タブ) このページです。  
  
 呼び出す**構築**他のクラス コンス トラクターのいずれかが呼び出されていない場合。 `Construct`パラメーター ステートメントを空白のままにして、コードで複数のパラメーターと任意の時点での構築を指定するので、メンバー関数は柔軟です。  
  
 使用する必要があります`Construct`と配列を使用して、呼び出す必要があります**構築**配列の各メンバーのデータ メンバーには、適切な値が割り当てられるようにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&112;](../../mfc/codesnippet/cpp/cpropertypage-class_1.cpp)]  
  
##  <a name="a-namecpropertypagea--cpropertypagecpropertypage"></a><a name="cpropertypage"></a>CPropertyPage::CPropertyPage  
 `CPropertyPage` オブジェクトを構築します。  
  
```  
CPropertyPage();

 
explicit CPropertyPage(
    UINT nIDTemplate,  
    UINT nIDCaption = 0,  
    DWORD dwSize = sizeof(PROPSHEETPAGE));

 
explicit CPropertyPage(
    LPCTSTR lpszTemplateName,  
    UINT nIDCaption = 0,  
    DWORD dwSize = sizeof(PROPSHEETPAGE));

 
CPropertyPage(
    UINT nIDTemplate,  
    UINT nIDCaption,  
    UINT nIDHeaderTitle,  
    UINT nIDHeaderSubTitle = 0,  
    DWORD dwSize = sizeof(PROPSHEETPAGE));

 
CPropertyPage(
    LPCTSTR lpszTemplateName,  
    UINT nIDCaption,  
    UINT nIDHeaderTitle,  
    UINT nIDHeaderSubTitle = 0,  
    DWORD dwSize = sizeof(PROPSHEETPAGE));
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDTemplate`  
 このページで使用するテンプレートの ID です。  
  
 `nIDCaption`  
 このページのタブ内に配置する名前の ID。 0 の場合、名前がこのページのダイアログ テンプレートから取得されます。  
  
 `dwSize`  
 `lpszTemplateName`  
 このページのテンプレートの名前を含む文字列へのポインター。 ことはできません**NULL**します。  
  
 `nIDHeaderTitle`  
 プロパティ ページのヘッダーのタイトルの位置に配置する名前の ID です。  
  
 `nIDHeaderSubTitle`  
 プロパティ ページのヘッダーのサブタイトルの場所に配置する名前の ID です。  
  
### <a name="remarks"></a>コメント  
 すべての次の条件が満たされた後、オブジェクトが表示されます。  
  
-   ページを使用してプロパティ シートに追加された[が](../../mfc/reference/cpropertysheet-class.md#addpage)です。  
  
-   プロパティ シートの[DoModal](../../mfc/reference/cpropertysheet-class.md#domodal)または[作成](../../mfc/reference/cpropertysheet-class.md#create)関数が呼び出されました。  
  
-   ユーザーが選択されています (タブ) このページです。  
  
 複数のパラメーター (たとえば、配列を使用している場合) があればを使用して[まず、](../../mfc/reference/cpropertysheet-class.md#construct)の代わりに`CPropertyPage`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&113;](../../mfc/codesnippet/cpp/cpropertypage-class_2.cpp)]  
  
##  <a name="a-namegetpspa--cpropertypagegetpsp"></a><a name="getpsp"></a>CPropertyPage::GetPSP  
 Windows の取得[PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548)構造に関連付けられている、`CPropertyPage`オブジェクトです。  
  
```  
const PROPSHEETPAGE& GetPSP() const;  
  
PROPSHEETPAGE& GetPSP();
```  
  
### <a name="return-value"></a>戻り値  
 参照、 **PROPSHEETPAGE**構造体。  
  
##  <a name="a-namempspa--cpropertypagempsp"></a><a name="m_psp"></a>CPropertyPage::m_psp  
 `m_psp`メンバーの特性を格納する構造体は、 [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548)します。  
  
```  
PROPSHEETPAGE m_psp;  
```  
  
### <a name="remarks"></a>コメント  
 この構造体を使用すると、構築した後、プロパティ ページの外観を初期化できます。  
  
 詳細については、そのメンバーの一覧を含む、この構造体を参照してください。 **PROPSHEETPAGE**で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&128;](../../mfc/codesnippet/cpp/cpropertypage-class_3.cpp)]  
  
##  <a name="a-nameonapplya--cpropertypageonapply"></a><a name="onapply"></a>CPropertyPage::OnApply  
 OK または 適用 ボタンを選択すると、このメンバー関数がフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnApply();
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合、変更が受け入れられます。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 フレームワークがこの関数を呼び出すと、プロパティ シートにすべてのプロパティ ページで行った変更が受け入れられた、プロパティ シートが、フォーカスを保持し、`OnApply`を返します**TRUE** (値 1)。 前に`OnApply`呼び出すことができる、フレームワークによって呼び出す必要がありますが[SetModified](#setmodified)にそのパラメーターを設定し、 **TRUE**します。 ユーザーは、プロパティ ページで変更を行うとすぐにこの適用 ボタンをアクティブになります。  
  
 ユーザーに適用 ボタンがクリックしたときのプログラムの動作を指定するには、このメンバー関数をオーバーライドします。 をオーバーライドする関数で返す必要があります**TRUE**の変更を確定し、 **FALSE**を有効になってからの変更を防ぐためにします。  
  
 既定の実装`OnApply`呼び出し`OnOK`します。  
  
 ユーザー プロパティ シートで、今すぐ適用または [ok] ボタンを押したときに送信された通知メッセージの詳細については、次を参照してください。 [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[送るに](#onok)します。  
  
##  <a name="a-nameoncancela--cpropertypageoncancel"></a><a name="oncancel"></a>CPropertyPage::OnCancel  
 [キャンセル] ボタンを選択すると、このメンバー関数がフレームワークによって呼び出されます。  
  
```  
virtual void OnCancel();
```  
  
### <a name="remarks"></a>コメント  
 [キャンセル] ボタンの操作を実行するには、このメンバー関数をオーバーライドします。 既定値は、加えられた変更を否定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&114;](../../mfc/codesnippet/cpp/cpropertypage-class_4.cpp)]  
  
##  <a name="a-nameonkillactivea--cpropertypageonkillactive"></a><a name="onkillactive"></a>CPropertyPage::OnKillActive  
 このメンバー関数は、ページがアクティブでは不要になったときに、framework によって呼び出されます。  
  
```  
virtual BOOL OnKillActive();
```  
  
### <a name="return-value"></a>戻り値  
 データが正常に更新された場合は 0 以外。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 特別なデータの検証タスクを実行するには、この関数をオーバーライドします。  
  
 このメンバー関数の既定の実装では、メンバー変数をプロパティ ページのプロパティ ページのコントロールからの設定をコピーします。 ダイアログ データ バリデーション (DDV) のエラーのため、データが正常に更新されない場合は、ページにフォーカスが保持されます。  
  
 このメンバー関数が正常に返されるが呼び出されます、ページの[OnOK](#onok)関数です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&115;](../../mfc/codesnippet/cpp/cpropertypage-class_5.cpp)]  
  
##  <a name="a-nameonoka--cpropertypageonok"></a><a name="onok"></a>送るに  
 ユーザーが framework 呼び出しの直後に、[ok] または [今すぐ適用] ボタンのいずれかを選択したときに、このメンバー関数がフレームワークによって呼び出されます[OnKillActive](#onkillactive)します。  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>コメント  
 OK または [適用] ボタンを選択すると、とき、フレームワークは、 [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552)プロパティ ページからの通知。 呼び出し`OnOK`を呼び出す場合に行われたしない[CPropertySheet::PressButton](../../mfc/reference/cpropertysheet-class.md#pressbutton)プロパティ ページは、通知をその場合は送信しないためです。  
  
 ユーザーがプロパティ シート全体を閉じる場合に、現在のページに固有の追加動作を実装するには、この関数をオーバーライドします。  
  
 このメンバー関数の既定の実装で、データが更新されたことを反映するには、「クリーン」としてそのページをマークする、`OnKillActive`関数です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView&116; 位](../../mfc/codesnippet/cpp/cpropertypage-class_6.cpp)]  
  
##  <a name="a-nameonquerycancela--cpropertypageonquerycancel"></a><a name="onquerycancel"></a>CPropertyPage::OnQueryCancel  
 [キャンセル] ボタンをクリックし、キャンセルする前に動作が発生したときに、このメンバー関数がフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnQueryCancel();
```  
  
### <a name="return-value"></a>戻り値  
 返します。 **FALSE**取り消し操作または許可する場合は TRUE を防ぐためです。  
  
### <a name="remarks"></a>コメント  
 ユーザーは [キャンセル] ボタンをクリックしたときのプログラムの動作を指定するには、このメンバー関数をオーバーライドします。  
  
 既定の実装`OnQueryCancel`返します**TRUE**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&117;](../../mfc/codesnippet/cpp/cpropertypage-class_7.cpp)]  
  
##  <a name="a-nameonreseta--cpropertypageonreset"></a><a name="onreset"></a>CPropertyPage::OnReset  
 [キャンセル] ボタンを選択すると、このメンバー関数がフレームワークによって呼び出されます。  
  
```  
virtual void OnReset();
```  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、この関数を呼び出すの適用 ボタンを選択したユーザーによって行われたすべてのプロパティ ページに変更を破棄して、プロパティ シートにフォーカスが保持されます。  
  
 ユーザーは [キャンセル] ボタンをクリックしたときのプログラムの動作を指定するには、このメンバー関数をオーバーライドします。  
  
 既定の実装`OnReset`何も行われません。  
  
### <a name="example"></a>例  
  例を参照してください[CPropertyPage::OnCancel](#oncancel)します。  
  
##  <a name="a-nameonsetactivea--cpropertypageonsetactive"></a><a name="onsetactive"></a>CPropertyPage::OnSetActive  
 このメンバー関数は、ページは、ユーザーが選択され、アクティブになったときに、framework によって呼び出されます。  
  
```  
virtual BOOL OnSetActive();
```  
  
### <a name="return-value"></a>戻り値  
 ページを正常にアクティブに設定されている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ページがアクティブになったときにタスクを実行するには、この関数をオーバーライドします。 このメンバー関数のオーバーライドを新しいデータ ページのコントロールを更新できるように、データ メンバーを更新した後、既定のバージョンを呼び出します。  
  
 既定の実装は ページで、ウィンドウを作成しない場合、以前に作成し、作業中のページになります。  
  
### <a name="example"></a>例  
  例を参照してください[CPropertySheet::SetFinishText](../../mfc/reference/cpropertysheet-class.md#setfinishtext)します。  
  
##  <a name="a-nameonwizardbacka--cpropertypageonwizardback"></a><a name="onwizardback"></a>CPropertyPage::OnWizardBack  
 ユーザーが、ウィザードの [戻る] ボタンをクリックすると、このメンバー関数がフレームワークによって呼び出されます。  
  
```  
virtual LRESULT OnWizardBack();
```  
  
### <a name="return-value"></a>戻り値  
 次のページに自動的に進行する場合は&0;ページの変更を禁止する –&1; です。 次のものではないページにジャンプするには、表示されるダイアログ ボックスの id を返します。  
  
### <a name="remarks"></a>コメント  
 [戻る] ボタンがクリックされたときに、ユーザーが操作を指定するには、このメンバー関数をオーバーライドします。  
  
 ウィザードの種類のプロパティ シートを作成する方法の詳細については、次を参照してください。 [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&118;](../../mfc/codesnippet/cpp/cpropertypage-class_8.cpp)]  
  
##  <a name="a-nameonwizardfinisha--cpropertypageonwizardfinish"></a><a name="onwizardfinish"></a>CPropertyPage::OnWizardFinish  
 ユーザーが、ウィザードで、[完了] をクリックすると、このメンバー関数がフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnWizardFinish();
```  
  
### <a name="return-value"></a>戻り値  
 プロパティ シートは、ウィザードが終了したときに破棄される場合は&0; 以外それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 ユーザーがクリックしたとき、**完了** ボタンをクリックして、ウィザードでは、フレームワークでは、この関数を呼び出します; と`OnWizardFinish`を返します**TRUE** (0 以外の値)、プロパティ シートを破壊すること (ただし、実際に破棄されることはありません)。 呼び出す`DestroyWindow`プロパティ シートを破棄します。 呼び出す必要はありません`DestroyWindow`から`OnWizardFinish`; そうは原因ヒープの破損またはその他のエラーです。  
  
 [完了] ボタンがクリックされたときに、ユーザーが操作を指定するには、このメンバー関数をオーバーライドすることができます。 この関数をオーバーライドする場合は、返す**FALSE**をプロパティ シートが破棄されていることを防ぐためにします。  
  
 ウィザードのプロパティ シートで [完了] ボタンを押したときに送信された通知メッセージの詳細については、次を参照してください。 [PSN_WIZFINISH](http://msdn.microsoft.com/library/windows/desktop/bb774571)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 ウィザードの種類のプロパティ シートを作成する方法の詳細については、次を参照してください。 [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&119;](../../mfc/codesnippet/cpp/cpropertypage-class_9.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #&120;](../../mfc/codesnippet/cpp/cpropertypage-class_10.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #&121;](../../mfc/codesnippet/cpp/cpropertypage-class_11.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #&122;](../../mfc/codesnippet/cpp/cpropertypage-class_12.cpp)]  
  
##  <a name="a-nameonwizardnexta--cpropertypageonwizardnext"></a><a name="onwizardnext"></a>CPropertyPage::OnWizardNext  
 ユーザーが、ウィザードの [次へ] ボタンをクリックすると、このメンバー関数がフレームワークによって呼び出されます。  
  
```  
virtual LRESULT OnWizardNext();
```  
  
### <a name="return-value"></a>戻り値  
 次のページに自動的に進行する場合は&0;ページの変更を禁止する –&1; です。 次のものではないページにジャンプするには、表示されるダイアログ ボックスの id を返します。  
  
### <a name="remarks"></a>コメント  
 次へ ボタンがクリックされたときに、ユーザーが操作を指定するには、この関数をオーバーライドします。  
  
 ウィザードの種類のプロパティ シートを作成する方法の詳細については、次を参照してください。 [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView&#123;](../../mfc/codesnippet/cpp/cpropertypage-class_13.cpp)]  
  
##  <a name="a-namequerysiblingsa--cpropertypagequerysiblings"></a><a name="querysiblings"></a>CPropertyPage::QuerySiblings  
 プロパティ シートの各ページにメッセージを転送するには、このメンバー関数を呼び出します。  
  
```  
LRESULT QuerySiblings(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `wParam`  
 追加のメッセージに依存する情報を指定します。  
  
 `lParam`  
 追加のメッセージに依存する情報を指定します。  
  
### <a name="return-value"></a>戻り値  
 0 以外の値 0 の場合、またはプロパティ シート内のページからすべてのページでは、値 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ページが&0; 以外の値を返す場合、プロパティ シートは、後続のページに、メッセージを送信しません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&124;](../../mfc/codesnippet/cpp/cpropertypage-class_14.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #&125;](../../mfc/codesnippet/cpp/cpropertypage-class_15.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #&126;](../../mfc/codesnippet/cpp/cpropertypage-class_16.cpp)]  
  
##  <a name="a-namesetmodifieda--cpropertypagesetmodified"></a><a name="setmodified"></a>CPropertyPage::SetModified  
 有効にするまたは適用 ボタン、適切な外部のオブジェクトにプロパティ ページの設定を適用するかどうかに基づいてを無効にするには、このメンバー関数を呼び出します。  
  
```  
void SetModified(BOOL bChanged = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bChanged`  
 **TRUE**プロパティ ページの設定が適用されたか、前回から変更されたことを示すために**FALSE**プロパティ ページの設定が適用されているか、無視するかを示します。  
  
### <a name="remarks"></a>コメント  
 フレームワークを保持するページは、「ダーティ」、つまり追跡、プロパティ ページを呼び出すが**SetModified (TRUE)**します。 適用 ボタンは常に有効にするを呼び出す場合**SetModified (TRUE)**ページのいずれかです。 呼び出したときに、適用 ボタンが無効になります**SetModified (FALSE)**のみが場合は、他のページのいずれも「ダーティ」のページの&1; つの  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView&#127;](../../mfc/codesnippet/cpp/cpropertypage-class_17.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CMNCTRL1](../../visual-cpp-samples.md)   
 [MFC サンプル CMNCTRL2](../../visual-cpp-samples.md)   
 [MFC サンプル PROPDLG](../../visual-cpp-samples.md)   
 [MFC サンプル SNAPVW](../../visual-cpp-samples.md)   
 [CDialog クラス](../../mfc/reference/cdialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CPropertySheet クラス](../../mfc/reference/cpropertysheet-class.md)   
 [CDialog クラス](../../mfc/reference/cdialog-class.md)

