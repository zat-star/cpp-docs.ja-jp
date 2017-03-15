---
title: "CSnapInPropertyPageImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSnapInPropertyPageImpl
dev_langs:
- C++
helpviewer_keywords:
- snap-ins, property pages
- snap-ins
- property pages, ATL
- CSnapInPropertyPageImpl class
ms.assetid: 75bdce5a-985e-4166-bd44-493132e023c4
caps.latest.revision: 20
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: f5db4d0742a423e9574db2a4268a9376491b2ed2
ms.lasthandoff: 02/24/2017

---
# <a name="csnapinpropertypageimpl-class"></a>CSnapInPropertyPageImpl クラス
このクラスは、スナップインからプロパティ ページ オブジェクトを実装するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
CSnapInPropertyPageImpl : public CDialogImplBase
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::CancelToClose](#canceltoclose)|ステータスを変更、 **OK**と**キャンセル**ボタン。|  
|[CSnapInPropertyPageImpl::Create](#create)|新しく作成した初期化`CSnapInPropertyPageImpl`オブジェクトです。|  
|[CSnapInPropertyPageImpl::OnApply](#onapply)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、**今すぐ適用**ウィザード形式のプロパティ シートを使用しているときにボタンをクリックします。|  
|[CSnapInPropertyPageImpl::OnHelp](#onhelp)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、**ヘルプ**ウィザード形式のプロパティ シートを使用しているときにボタンをクリックします。|  
|[CSnapInPropertyPageImpl::OnKillActive](#onkillactive)|現在のページがアクティブでなくなったときに、フレームワークによって呼び出されます。|  
|[CSnapInPropertyPageImpl::OnQueryCancel](#onquerycancel)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、**キャンセル** ボタンをクリックし、キャンセルが行われる前にします。|  
|[CSnapInPropertyPageImpl::OnReset](#onreset)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、**リセット**ウィザード形式のプロパティ シートを使用しているときにボタンをクリックします。|  
|[CSnapInPropertyPageImpl::OnSetActive](#onsetactive)|現在のページがアクティブになったときに、フレームワークによって呼び出されます。|  
|[CSnapInPropertyPageImpl::OnWizardBack](#onwizardback)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、**戻る**ウィザード形式のプロパティ シートを使用しているときにボタンをクリックします。|  
|[CSnapInPropertyPageImpl::OnWizardFinish](#onwizardfinish)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、**完了**ウィザード形式のプロパティ シートを使用しているときにボタンをクリックします。|  
|[CSnapInPropertyPageImpl::OnWizardNext](#onwizardnext)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、`Next`ウィザード形式のプロパティ シートを使用しているときにボタンをクリックします。|  
|[CSnapInPropertyPageImpl::QuerySiblings](#querysiblings)|プロパティ シートのすべてのページに現在のメッセージを転送します。|  
|[CSnapInPropertyPageImpl::SetModified](#setmodified)|アクティブ化または非アクティブ化を呼び出し、**今すぐ適用** ボタンをクリックします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::m_psp](#m_psp)|Windows **PROPSHEETPAGE**によって使用される構造、`CSnapInPropertyPageImpl`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 `CSnapInPropertyPageImpl`スナップインのプロパティ ページのオブジェクトの基本実装を提供します。 スナップインのプロパティ ページの基本的な機能は、複数のインターフェイスを使用して実装し、型をマップします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CDialogImplBase`  
  
 `CSnapInPropertyPageImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsnap.h  
  
##  <a name="a-namecanceltoclosea--csnapinpropertypageimplcanceltoclose"></a><a name="canceltoclose"></a>CSnapInPropertyPageImpl::CancelToClose  
 モーダル プロパティ シートのページ内のデータを回復できない変更が行われた後は、この関数を呼び出します。  
  
```
void CancelToClose();
```  
  
### <a name="remarks"></a>コメント  
 この関数が変更、 **ok**ボタン**閉じる**を無効にして、**キャンセル** ボタンをクリックします。 これは、変更、アラートの変更が確定され、変更があるユーザーはキャンセルできません。  
  
 `CancelToClose`モードレス プロパティ シートが持っていないので、モードレス プロパティ シートでは nothing メンバー関数は、**キャンセル**既定ではボタンをクリックします。  
  
##  <a name="a-namecsnapinpropertypageimpla--csnapinpropertypageimplcsnapinpropertypageimpl"></a><a name="csnapinpropertypageimpl"></a>CSnapInPropertyPageImpl::CSnapInPropertyPageImpl  
 `CSnapInPropertyPageImpl` オブジェクトを構築します。  
  
```
CSnapInPropertyPageImpl(LPCTSTR lpszTitle = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszTitle`  
 [in]プロパティ ページのタイトルです。  
  
### <a name="remarks"></a>コメント  
 基になる構造を初期化するために呼び出す[CSnapInPropertyPageImpl::Create](#create)します。  
  
##  <a name="a-namecreatea--csnapinpropertypageimplcreate"></a><a name="create"></a>CSnapInPropertyPageImpl::Create  
 この関数では、プロパティ ページの基になる構造体を初期化します。  
  
```
HPROPSHEETPAGE Create();
```  
  
### <a name="return-value"></a>戻り値  
 ハンドル、 **PROPSHEETPAGE**新しく作成されたプロパティ シートの属性を含む構造体。  
  
### <a name="remarks"></a>コメント  
 まずを呼び出して[CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl)この関数を呼び出す前にします。  
  
##  <a name="a-namempspa--csnapinpropertypageimplmpsp"></a><a name="m_psp"></a>CSnapInPropertyPageImpl::m_psp  
 `m_psp`メンバーの特性を格納する構造体は、 **PROPSHEETPAGE**します。  
  
```
PROPSHEETPAGE m_psp;
```  
  
### <a name="remarks"></a>コメント  
 この構造体を使用すると、構築した後、プロパティ ページの外観を初期化できます。  
  
 詳細については、そのメンバーの一覧を含む、この構造体を参照してください。 [PROPSHEETPAGE](http://msdn.microsoft.com/library/aa815151)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameonapplya--csnapinpropertypageimplonapply"></a><a name="onapply"></a>CSnapInPropertyPageImpl::OnApply  
 ユーザーがクリックしたときに、このメンバー関数が呼び出されます、 **OK**または**今すぐ適用** ボタンをクリックします。  
  
```
BOOL OnApply();
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合、変更が受け入れられます。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 前に`OnApply`呼び出すことができる、フレームワークによって呼び出す必要がありますが`SetModified`にそのパラメーターを設定し、 **TRUE**します。 これをアクティブにする、**今すぐ適用**ユーザーは、プロパティ ページで変更を行うとすぐにボタンをクリックします。  
  
 ユーザーがクリックしたときのプログラムの動作を指定するには、この関数をオーバーライド、**今すぐ適用** ボタンをクリックします。 をオーバーライドする関数で返す必要があります**TRUE**の変更を確定し、 **FALSE**を有効になってからの変更を防ぐためにします。  
  
 既定の実装`OnApply`返します**TRUE**します。  
  
##  <a name="a-nameonhelpa--csnapinpropertypageimplonhelp"></a><a name="onhelp"></a>CSnapInPropertyPageImpl::OnHelp  
 ユーザーがクリックしたときに、このメンバー関数が呼び出されます、**ヘルプ**プロパティ ページのボタンをクリックします。  
  
```
void OnHelp();
```  
  
### <a name="remarks"></a>コメント  
 プロパティ ページのヘルプを表示するには、この関数をオーバーライドします。  
  
##  <a name="a-nameonkillactivea--csnapinpropertypageimplonkillactive"></a><a name="onkillactive"></a>CSnapInPropertyPageImpl::OnKillActive  
 ページがアクティブでは不要になったときに呼び出されます。  
  
```
BOOL OnKillActive();
```  
  
### <a name="return-value"></a>戻り値  
 データが正常に更新された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 特別なデータの検証タスクを実行するには、この関数をオーバーライドします。  
  
##  <a name="a-nameonquerycancela--csnapinpropertypageimplonquerycancel"></a><a name="onquerycancel"></a>CSnapInPropertyPageImpl::OnQueryCancel  
 ユーザーがクリックしたときに、このメンバー関数が呼び出されます、**キャンセル**ボタンをクリックし、キャンセルする前に動作が発生しました。  
  
```
BOOL OnQueryCancel();
```  
  
### <a name="return-value"></a>戻り値  
 キャンセル操作を許可するように 0 以外の値それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ユーザーがクリックしたときのプログラムの動作を指定するには、この関数をオーバーライド、**キャンセル** ボタンをクリックします。  
  
 既定の実装`OnQueryCancel`返します**TRUE**します。  
  
##  <a name="a-nameonreseta--csnapinpropertypageimplonreset"></a><a name="onreset"></a>CSnapInPropertyPageImpl::OnReset  
 このメンバー関数は、ユーザーがクリックしたときに、**キャンセル** ボタンをクリックします。  
  
```
void OnReset();
```  
  
### <a name="remarks"></a>コメント  
 この関数が呼び出されると、変更をクリックして、ユーザーによって行われたすべてのプロパティ ページ、**今すぐ適用**ボタンは破棄され、プロパティ シートにフォーカスが保持されます。  
  
 ユーザーがクリックしたときのプログラムの動作を指定するには、この関数をオーバーライド、**キャンセル** ボタンをクリックします。  
  
##  <a name="a-nameonsetactivea--csnapinpropertypageimplonsetactive"></a><a name="onsetactive"></a>CSnapInPropertyPageImpl::OnSetActive  
 ページは、ユーザーが選択され、アクティブになったときに呼び出されます。  
  
```
BOOL OnSetActive();
```  
  
### <a name="return-value"></a>戻り値  
 ページを正常にアクティブに設定されている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ページがアクティブになったときにタスクを実行するには、この関数をオーバーライドします。 このメンバー関数のオーバーライドは、他の処理が行われる前に、既定のバージョンを呼び出す必要があります。  
  
 既定の実装**TRUE**します。  
  
##  <a name="a-nameonwizardbacka--csnapinpropertypageimplonwizardback"></a><a name="onwizardback"></a>CSnapInPropertyPageImpl::OnWizardBack  
 ユーザーがクリックしたときに、このメンバー関数が呼び出されます、**戻る**ウィザード ボタンをクリックします。  
  
```
BOOL OnWizardBack();
```  
  
### <a name="return-value"></a>戻り値  
  
-   前のページに切り替えが自動的に&0; を返します。  
  
-   ページの変更を禁止する –&1; です。  
  
 次のものではないページにジャンプするには、表示されるダイアログ ボックスの id を返します。  
  
### <a name="remarks"></a>コメント  
 ユーザーにするときに実行する必要がありますいくつかのアクションを指定するには、この関数をオーバーライド、**戻る** ボタンをクリックします。  
  
##  <a name="a-nameonwizardfinisha--csnapinpropertypageimplonwizardfinish"></a><a name="onwizardfinish"></a>CSnapInPropertyPageImpl::OnWizardFinish  
 ユーザーがクリックしたときに、このメンバー関数が呼び出されます、**完了**ウィザード ボタンをクリックします。  
  
```
BOOL OnWizardFinish();
```  
  
### <a name="return-value"></a>戻り値  
 プロパティ シートは、ウィザードが終了したときに破棄される場合は&0; 以外それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 ユーザーにするときに実行する必要がありますいくつかのアクションを指定するには、この関数をオーバーライド、**完了** ボタンをクリックします。  
  
##  <a name="a-nameonwizardnexta--csnapinpropertypageimplonwizardnext"></a><a name="onwizardnext"></a>CSnapInPropertyPageImpl::OnWizardNext  
 このメンバー関数は、ユーザーがクリックすると、`Next`ウィザードの。  
  
```
BOOL OnWizardNext();
```  
  
### <a name="return-value"></a>戻り値  
  
-   次のページに切り替えが自動的に&0; を返します。  
  
-   ページの変更を禁止する –&1; です。  
  
 次のものではないページにジャンプするには、表示されるダイアログ ボックスの id を返します。  
  
### <a name="remarks"></a>コメント  
 ユーザーにするときに実行する必要がありますいくつかのアクションを指定するには、この関数をオーバーライド、 `Next`  ボタンをクリックします。  
  
##  <a name="a-namequerysiblingsa--csnapinpropertypageimplquerysiblings"></a><a name="querysiblings"></a>CSnapInPropertyPageImpl::QuerySiblings  
 プロパティ シートの各ページにメッセージを転送するには、このメンバー関数を呼び出します。  
  
```
LRESULT QuerySiblings(WPARAM wParam, LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `wParam`  
 [in]追加のメッセージに依存する情報を指定します。  
  
 `lParam`  
 [in]追加のメッセージに依存する情報を指定します。  
  
### <a name="return-value"></a>戻り値  
 次のプロパティ ページに、メッセージを転送しない場合は&0; 以外それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 ページが&0; 以外の値を返す場合、プロパティ シートは、後続のページに、メッセージを送信しません。  
  
##  <a name="a-namesetmodifieda--csnapinpropertypageimplsetmodified"></a><a name="setmodified"></a>CSnapInPropertyPageImpl::SetModified  
 有効または無効にするには、このメンバー関数を呼び出して、**今すぐ適用**適切な外部のオブジェクトにプロパティ ページの設定を適用するかどうかに基づいて ボタンをクリックします。  
  
```
void SetModified(BOOL bChanged = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bChanged`  
 [in]**TRUE**プロパティ ページの設定が適用されたか、前回から変更されたことを示すために**FALSE**プロパティ ページの設定が適用されているか、無視するかを示します。  
  
### <a name="remarks"></a>コメント  
 プロパティ シートを保持するページは、「ダーティ」、つまり追跡、プロパティ ページを呼び出すが**SetModified (TRUE)**します。 **今すぐ適用**ボタンは常に有効にするを呼び出す場合**SetModified (TRUE)**ページのいずれかです。 **今すぐ適用**を呼び出すと、ボタンが無効にする**SetModified (FALSE)**のみが場合は、他のページのいずれも「ダーティ」のページの&1; つの  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

