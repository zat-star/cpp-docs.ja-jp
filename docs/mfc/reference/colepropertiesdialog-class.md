---
title: "メンバー クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COlePropertiesDialog
dev_langs:
- C++
helpviewer_keywords:
- OLE Object Properties dialog box
- Object Properties dialog box
- dialog boxes, OLE
- OLE documents, modifying properties
- property pages, OLE
- COlePropertiesDialog class
ms.assetid: a54dbc89-1447-4329-bd01-00e98ec9e935
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 0c07766bca6bbc546f877e10255d80bd388d30d7
ms.lasthandoff: 02/24/2017

---
# <a name="colepropertiesdialog-class"></a>メンバー クラス
Windows に共通の [OLE プロジェクト プロパティ] ダイアログ ボックスをカプセル化します。  
  
## <a name="syntax"></a>構文  
  
```  
class COlePropertiesDialog : public COleDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COlePropertiesDialog::COlePropertiesDialog](#colepropertiesdialog)|`COlePropertiesDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COlePropertiesDialog::DoModal](#domodal)|ダイアログ ボックスを表示および選択を行うことができます。|  
|[COlePropertiesDialog::OnApplyScale](#onapplyscale)|ドキュメント アイテムの表示スケールが変更されたときに、フレームワークによって呼び出されます。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COlePropertiesDialog::m_gp](#m_gp)|[全般] ページを初期化するために使用される構造体、`COlePropertiesDialog`オブジェクトです。|  
|[COlePropertiesDialog::m_lp](#m_lp)|「リンク」ページを初期化するために使用される構造体、`COlePropertiesDialog`オブジェクトです。|  
|[COlePropertiesDialog::m_op](#m_op)|初期化するために使用される構造体、`COlePropertiesDialog`オブジェクトです。|  
|[COlePropertiesDialog::m_psh](#m_psh)|追加のカスタム プロパティ ページを追加するために使用する構造体。|  
|[COlePropertiesDialog::m_vp](#m_vp)|[表示] ページをカスタマイズするために使用する構造体、`COlePropertiesDialog`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 共通の OLE オブジェクトのプロパティ ダイアログ ボックスは、表示し、Windows の標準に準拠した方法で OLE ドキュメント アイテムのプロパティを変更する簡単な方法を提供します。 これらのプロパティには、文書の項目 (項目がリンクされている) 場合に、項目のリンクをアイコンとイメージのスケーリングと情報を表示するオプションによって表されるファイルに関する情報が、他のユーザー間で含まれます。  
  
 使用する、`COlePropertiesDialog`オブジェクトは、まずを使用してオブジェクトを作成、`COlePropertiesDialog`コンス トラクターです。 ダイアログ ボックスが構築された後、`DoModal`メンバー関数 ダイアログ ボックスが表示され、ユーザーが項目のプロパティを変更できるようにします。 `DoModal`ユーザーが [ok] を選択するかどうかを返します ( **IDOK**) または [キャンセル] ( **IDCANCEL**) ボタンをクリックします。 だけでなく、[ok] と [キャンセル] ボタン、[適用] ボタンがあります。 ユーザーは、適用を選択するドキュメント項目のプロパティに加えられた変更は、項目に適用されると、そのイメージに自動的に更新されますが、アクティブなままです。  
  
 [M_psh](#m_psh)データ メンバーへのポインターは、 **PROPSHEETHEADER**構造体、およびほとんどの場合に明示的にアクセスする必要はありません。 既定の一般的なビュー、およびリンクのページを超える追加のプロパティ ページを必要がある場合は例外です。 この場合、変更することができます、`m_psh`データ メンバーを呼び出す前に、カスタム ページを含める、`DoModal`メンバー関数。  
  
 OLE ダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [関数](../../mfc/reference/coledialog-class.md)  
  
 `COlePropertiesDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxodlgs.h  
  
##  <a name="a-namecolepropertiesdialoga--colepropertiesdialogcolepropertiesdialog"></a><a name="colepropertiesdialog"></a>COlePropertiesDialog::COlePropertiesDialog  
 
          `COlePropertiesDialog` オブジェクトを作成します。  
  
```  
COlePropertiesDialog(
    COleClientItem* pItem,  
    UINT nScaleMin = 10,  
    UINT nScaleMax = 500,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 プロパティにアクセスしているドキュメントの項目へのポインター。  
  
 *nScaleMin*  
 最小のアイテムのドキュメントのイメージの倍率します。  
  
 *nScaleMax*  
 ドキュメント アイテムのイメージの倍率を最大値。  
  
 `pParentWnd`  
 ダイアログ ボックスの親または所有者へのポインター。  
  
### <a name="remarks"></a>コメント  
 共通の OLE オブジェクトのプロパティ ダイアログのクラスを派生`COlePropertiesDialog`ドキュメント アイテムのスケーリングを実装するためにします。 このクラスのインスタンスによって実装されるすべてのダイアログ ボックスは、ドキュメント項目のスケーリングをサポートしていません。  
  
 既定では、共通の OLE オブジェクトのプロパティ ダイアログ ボックスでは、次の&3; つの既定のページがあります。  
  
-   全般  
  
     このページには、ドキュメントを選択した項目によって表されるファイルのシステム情報が含まれています。 このページから、ユーザーは、別の種類を選択した項目を変換できます。  
  
-   表示  
  
     このページには、アイテムを表示する、アイコンの変更、およびイメージのスケーリングを変更するためのオプションが含まれています。  
  
-   Link  
  
     このページには、リンクされた項目の場所を変更して、リンク アイテムの更新のオプションが含まれています。 このページから、ユーザーが選択された項目のリンクを中断できます。  
  
 既定で提供されていないページを追加するには、変更、 [m_psh](#m_psh)メンバー変数のコンス トラクターを終了する前に、 `COlePropertiesDialog`-クラスを派生します。 これは、高度な実装の`COlePropertiesDialog`コンス トラクターです。  
  
##  <a name="a-namedomodala--colepropertiesdialogdomodal"></a><a name="domodal"></a>COlePropertiesDialog::DoModal  
 Windows に共通の [OLE プロジェクト プロパティ] ダイアログ ボックスを表示し、ユーザーが閲覧またはドキュメント項目のさまざまなプロパティを変更できるようにするには、このメンバー関数を呼び出します。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 **IDOK**または**IDCANCEL**成功。 それ以外の場合 0 の場合。 **IDOK**と**IDCANCEL**をユーザーが [ok] または [キャンセル] ボタンを選択するかどうかを示す定数です。  
  
 場合**IDCANCEL**返されるか、Windows を呼び出すことができます[情報を得る](http://msdn.microsoft.com/library/windows/desktop/ms646916)エラーが発生したかどうかを判断します。  
  
##  <a name="a-namemgpa--colepropertiesdialogmgp"></a><a name="m_gp"></a>COlePropertiesDialog::m_gp  
 型の構造体[OLEUIGNRLPROPS](http://msdn.microsoft.com/library/windows/desktop/ms687297), OLE オブジェクトのプロパティダイアログ ボックスの [全般] ページを初期化するために使用されます。  
  
```  
OLEUIGNRLPROPS m_gp;  
```  
  
### <a name="remarks"></a>コメント  
 このページは、埋め込まれたアイテムのサイズと種類を表示し、[変換] ダイアログ ボックスへのアクセスを許可します。 このページには、かどうか、オブジェクトは、リンクのリンク先も表示されます。  
  
 詳細については、 **OLEUIGNRLPROPS**構造体を参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namemlpa--colepropertiesdialogmlp"></a><a name="m_lp"></a>COlePropertiesDialog::m_lp  
 型の構造体[OLEUILINKPROPS](http://msdn.microsoft.com/library/windows/desktop/ms680735), OLE オブジェクトのプロパティダイアログ ボックスの [リンク] ページを初期化するために使用されます。  
  
```  
OLEUILINKPROPS m_lp;  
```  
  
### <a name="remarks"></a>コメント  
 このページは、リンク アイテムの場所を表示し、更新、またはアイテムへのリンクを解除することができます。  
  
 詳細については、 **OLEUILINKPROPS**構造体を参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namemopa--colepropertiesdialogmop"></a><a name="m_op"></a>COlePropertiesDialog::m_op  
 型の構造体[OLEUIOBJECTPROPS](http://msdn.microsoft.com/library/windows/desktop/ms687199)、共通の OLE オブジェクトのプロパティ ダイアログ ボックスを初期化するために使用します。  
  
```  
OLEUIOBJECTPROPS m_op;  
```  
  
### <a name="remarks"></a>コメント  
 この構造体には、一般的なリンク、およびビューのページを初期化するために使用されるメンバーが含まれています。  
  
 詳細については、次を参照してください。、 **OLEUIOBJECTPROPS**と[OLEUILINKPROPS](http://msdn.microsoft.com/library/windows/desktop/ms680735)構造体に、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namempsha--colepropertiesdialogmpsh"></a><a name="m_psh"></a>COlePropertiesDialog::m_psh  
 型の構造体[PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546)、そのメンバーはダイアログ オブジェクトの特性を格納します。  
  
```  
PROPSHEETHEADER m_psh;  
```  
  
### <a name="remarks"></a>コメント  
 構築した後、`COlePropertiesDialog`オブジェクトを使用する`m_psh`を呼び出す前に、ダイアログ ボックスのさまざまな側面を設定する、`DoModal`メンバー関数。  
  
 変更した場合、`m_psh`データ メンバーを直接、既定の動作をオーバーライドします。  
  
 詳細については、 **PROPSHEETHEADER**構造体を参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namemvpa--colepropertiesdialogmvp"></a><a name="m_vp"></a>COlePropertiesDialog::m_vp  
 型の構造体[OLEUIVIEWPROPS](http://msdn.microsoft.com/library/windows/desktop/ms693751), OLE オブジェクトのプロパティダイアログ ボックスの [表示] ページを初期化するために使用されます。  
  
```  
OLEUIVIEWPROPS m_vp;  
```  
  
### <a name="remarks"></a>コメント  
 このページでは、ユーザーが"content"と「伝説的な」ビューのオブジェクトの間で切り替えるし、コンテナー内でスケールを変更します。 アイコンの変更 ダイアログ ボックスへのユーザー アクセスは、オブジェクトがアイコンとして表示されているときにこともできます。  
  
 詳細については、 **OLEUIVIEWPROPS**構造体を参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameonapplyscalea--colepropertiesdialogonapplyscale"></a><a name="onapplyscale"></a>COlePropertiesDialog::OnApplyScale  
 スケールの値が変更され、ok または 適用が選択されたときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnApplyScale(
    COleClientItem* pItem,  
    int nCurrentScale,  
    BOOL bRelativeToOrig);
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 プロパティにアクセスしているドキュメントの項目へのポインター。  
  
 `nCurrentScale`  
 ダイアログの小数点以下桁数の数値を設定します。  
  
 *bRelativeToOrig*  
 ドキュメント アイテムの元のサイズにスケーリングを適用するかどうかを示します。  
  
### <a name="return-value"></a>戻り値  
 0 以外の値を処理します。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、何も行われません。 スケーリングの制御を有効にするには、この関数をオーバーライドする必要があります。  
  
> [!NOTE]
>  共通の OLE オブジェクトのプロパティ ダイアログ ボックスが表示される前に、フレームワークでこの関数を**NULL**の`pItem`の場合は、– 1`nCurrentScale`します。 これを行うにが拡大縮小のコントロールを有効にするかどうかを決定します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル円](../../visual-cpp-samples.md)   
 [関数のクラス](../../mfc/reference/coledialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [関数のクラス](../../mfc/reference/coledialog-class.md)   
 [CPropertyPage クラス](../../mfc/reference/cpropertypage-class.md)

