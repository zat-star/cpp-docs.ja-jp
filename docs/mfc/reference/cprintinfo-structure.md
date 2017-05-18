---
title: "CPrintInfo 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPrintInfo
dev_langs:
- C++
helpviewer_keywords:
- CPrintInfo structure
ms.assetid: 0b3de849-d050-4386-9a14-f4c1a25684f7
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
ms.openlocfilehash: ffa72acc58e0ac1a387e67e6542abcd466be9640
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cprintinfo-structure"></a>CPrintInfo 構造体
印刷または印刷プレビューのジョブに関する情報を格納します。  
  
## <a name="syntax"></a>構文  
  
```  
struct CPrintInfo  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPrintInfo::GetFromPage](#getfrompage)|印刷されている最初のページ数を返します。|  
|[CPrintInfo::GetMaxPage](#getmaxpage)|ドキュメントの最後のページ数を返します。|  
|[CPrintInfo::GetMinPage](#getminpage)|ドキュメントの最初のページ数を返します。|  
|[CPrintInfo::GetOffsetPage](#getoffsetpage)|結合された DocObject 印刷ジョブで印刷する DocObject 項目の最初のページの前のページ数を返します。|  
|[CPrintInfo::GetToPage](#gettopage)|印刷されている最後のページ数を返します。|  
|[CPrintInfo::SetMaxPage](#setmaxpage)|ドキュメントの最後のページの数を設定します。|  
|[CPrintInfo::SetMinPage](#setminpage)|ドキュメントの最初のページの数を設定します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPrintInfo::m_bContinuePrinting](#m_bcontinueprinting)|フレームワークが印刷ループを続行するかどうかを示すフラグが含まれています。|  
|[CPrintInfo::m_bDirect](#m_bdirect)|使用せずに直接印刷 ダイアログ ボックスを表示する) に文書が印刷されているかどうかを示すフラグが含まれています。|  
|[CPrintInfo::m_bDocObject](#m_bdocobject)|印刷されたドキュメントが DocObject かどうかを示すフラグが含まれています。|  
|[CPrintInfo::m_bPreview](#m_bpreview)|ドキュメントがプレビューされているかどうかを示すフラグが含まれています。|  
|[CPrintInfo::m_dwFlags](#m_dwflags)|DocObject 印刷操作を指定します。|  
|[CPrintInfo::m_lpUserData](#m_lpuserdata)|ユーザーが作成した構造体へのポインターが含まれています。|  
|[CPrintInfo::m_nCurPage](#m_ncurpage)|現在印刷中のページの数を識別します。|  
|[CPrintInfo::m_nJobNumber](#m_njobnumber)|現在の印刷ジョブのオペレーティング システムによって割り当てられたジョブの数を指定します。|  
|[CPrintInfo::m_nNumPreviewPages](#m_nnumpreviewpages)|プレビュー ウィンドウに表示するページの数を指定します。1 または 2 です。|  
|[CPrintInfo::m_nOffsetPage](#m_noffsetpage)|結合 DocObject 印刷ジョブでは、特定の DocObject の最初のページのオフセットを指定します。|  
|[CPrintInfo::m_pPD](#m_ppd)|ポインターを含む、`CPrintDialog`印刷 ダイアログ ボックスに使用するオブジェクト。|  
|[CPrintInfo::m_rectDraw](#m_rectdraw)|現在の使用可能なページ領域を定義する四角形を指定します。|  
|[CPrintInfo::m_strPageDesc](#m_strpagedesc)|ページ番号の表示の書式指定文字列が含まれています。|  
  
## <a name="remarks"></a>コメント  
 `CPrintInfo`構造体は、基本クラスではありません。  
  
 オブジェクトを作成するために、フレームワーク`CPrintInfo`たびに、印刷または印刷プレビュー を選択して、コマンドの完了時に破棄します。  
  
 `CPrintInfo`印刷するページの範囲などの全体の印刷ジョブと現在印刷中のページなどの印刷ジョブの現在の状態の両方の情報が含まれています。 一部の情報が格納されている、関連する[CPrintDialog](../../mfc/reference/cprintdialog-class.md)オブジェクトです。 このオブジェクトには、[印刷] ダイアログ ボックスで、ユーザーが入力した値が含まれています。  
  
 A`CPrintInfo`オブジェクトは、印刷処理中に、フレームワークとビュー クラスの間で渡され、2 つの情報を交換するために使用します。 たとえば、フレームワークに通知ビュー クラスの値を割り当てることによって印刷するドキュメントのどのページ、`m_nCurPage`のメンバー `CPrintInfo`; は、ビュー クラスは、値を取得し、指定したページの印刷を実行します。  
  
 別の例は、印刷されるまで、ドキュメントの長さは認識されません。 このような状況では、ビュー クラスは、ページが印刷されるたびを文書の終わりをテストします。 最後に達すると、ビュー クラスを設定、`m_bContinuePrinting`のメンバー`CPrintInfo`に**FALSE**です。 これにより、印刷のループを停止するフレームワークです。  
  
 `CPrintInfo`メンバー関数によって使用される`CView`表示されている 」も参照"。 Microsoft Foundation Class ライブラリによって提供される印刷のアーキテクチャの詳細については、次を参照してください。[フレーム ウィンドウ](../../mfc/frame-windows.md)と[ドキュメント/ビュー アーキテクチャ](../../mfc/document-view-architecture.md)資料と[印刷](../../mfc/printing.md)と[印刷: マルチページ ドキュメント](../../mfc/multipage-documents.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CPrintInfo`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxext.h  
  
##  <a name="getfrompage"></a>CPrintInfo::GetFromPage  
 この関数では、印刷する最初のページの数を取得します。  
  
```  
UINT GetFromPage() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 印刷する最初のページの数。  
  
### <a name="remarks"></a>コメント  
 これは、[印刷] ダイアログ ボックスでユーザーが指定した値に格納されている、`CPrintDialog`によって参照されるオブジェクト、`m_pPD`メンバーです。 ユーザーが値を指定していない場合は、既定では、ドキュメントの最初のページです。  
  
##  <a name="getmaxpage"></a>CPrintInfo::GetMaxPage  
 この関数では、ドキュメントの最後のページの数を取得します。  
  
```  
UINT GetMaxPage() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 ドキュメントの最後のページの数。  
  
### <a name="remarks"></a>コメント  
 この値は、`CPrintDialog`によって参照されるオブジェクト、`m_pPD`メンバーです。  
  
##  <a name="getminpage"></a>CPrintInfo::GetMinPage  
 この関数では、ドキュメントの最初のページの数を取得します。  
  
```  
UINT GetMinPage() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 ドキュメントの最初のページの数。  
  
### <a name="remarks"></a>コメント  
 この値は、`CPrintDialog`によって参照されるオブジェクト、`m_pPD`メンバーです。  
  
##  <a name="getoffsetpage"></a>CPrintInfo::GetOffsetPage  
 DocObject クライアントから複数の DocObject アイテムを印刷する場合は、オフセットを取得するには、この関数を呼び出します。  
  
```  
UINT GetOffsetPage() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 結合された DocObject 印刷ジョブで印刷する DocObject 項目の最初のページの前にページの数。  
  
### <a name="remarks"></a>コメント  
 この値は、によって参照される、**される場合**メンバーです。 ドキュメントの最初のページ番号になります、**される場合**値 + 他のアクティブなドキュメント DocObject として印刷する場合は 1 です。 **される場合**メンバーは有効な場合にのみ、 **m_bDocObject**値は**TRUE**します。  
  
##  <a name="gettopage"></a>CPrintInfo::GetToPage  
 この関数では、印刷する最後のページの数を取得します。  
  
```  
UINT GetToPage() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 印刷する最後のページの数。  
  
### <a name="remarks"></a>コメント  
 これは、[印刷] ダイアログ ボックスでユーザーが指定した値に格納されている、`CPrintDialog`によって参照されるオブジェクト、`m_pPD`メンバーです。 ユーザーが値を指定していない場合は、既定では、ドキュメントの最後のページです。  
  
##  <a name="m_bcontinueprinting"></a>CPrintInfo::m_bContinuePrinting  
 フレームワークが印刷ループを続行するかどうかを示すフラグが含まれています。  
  
### <a name="remarks"></a>コメント  
 印刷時の改ページ調整を行う場合このメンバーを設定することができます**FALSE**のオーバーライドで`CView::OnPrepareDC`ドキュメントの末尾に到達したとします。 使用して、印刷ジョブの先頭にあるドキュメントの長さを指定した場合、この変数を変更する必要はありません、`SetMaxPage`メンバー関数。 `m_bContinuePrinting`メンバーは型のパブリック変数**BOOL**します。  
  
##  <a name="m_bdirect"></a>CPrintInfo::m_bDirect  
 フレームワークでは、このメンバーを設定**TRUE**場合は直接印刷するために、[印刷] ダイアログ ボックスがバイパスされます**FALSE**それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 シェルから、または印刷プロセスを印刷するときに、印刷 ダイアログ ボックスがバイパスされる通常のコマンド ID を使用して**ID_FILE_PRINT_DIRECT**します。  
  
 通常、このメンバーは変わりませんが、これを変更する場合は、変更する前に呼び出し[しません](../../mfc/reference/cview-class.md#doprepareprinting)のオーバーライドで[き](../../mfc/reference/cview-class.md#onprepareprinting)します。  
  
##  <a name="m_bdocobject"></a>CPrintInfo::m_bDocObject  
 印刷されたドキュメントが DocObject かどうかを示すフラグが含まれています。  
  
### <a name="remarks"></a>コメント  
 データ メンバー`m_dwFlags`と**される場合**は、このフラグがない限り、有効な**TRUE**します。  
  
##  <a name="m_bpreview"></a>CPrintInfo::m_bPreview  
 ドキュメントがプレビューされているかどうかを示すフラグが含まれています。  
  
### <a name="remarks"></a>コメント  
 これは、ユーザーのコマンドを実行するに応じてフレームワークによって設定されます。 印刷プレビューのジョブでは、印刷 ダイアログ ボックスは表示されません。 **されます**メンバーは型のパブリック変数**BOOL**します。  
  
##  <a name="m_dwflags"></a>CPrintInfo::m_dwFlags  
 DocObject 印刷操作を指定するフラグの組み合わせが含まれています。  
  
### <a name="remarks"></a>コメント  
 有効な場合にのみデータ メンバー **m_bDocObject**は**TRUE**します。  
  
 フラグは、次の値の&1; つ以上になります。  
  
- **PRINTFLAG_MAYBOTHERUSER**  
  
- **PRINTFLAG_PROMPTUSER**  
  
- **PRINTFLAG_USERMAYCHANGEPRINTER**  
  
- **PRINTFLAG_RECOMPOSETODEVICE**  
  
- **PRINTFLAG_DONTACTUALLYPRINT**  
  
- **PRINTFLAG_FORCEPROPERTIES**  
  
- **PRINTFLAG_PRINTTOFILE**  
  
##  <a name="m_lpuserdata"></a>CPrintInfo::m_lpUserData  
 ユーザーが作成した構造体へのポインターが含まれています。  
  
### <a name="remarks"></a>コメント  
 ビュー クラスに格納したくない印刷固有のデータを格納するのにには、これを使用できます。 **M_lpUserData**メンバーは型のパブリック変数**LPVOID**します。  
  
##  <a name="m_ncurpage"></a>CPrintInfo::m_nCurPage  
 現在のページの数が含まれています。  
  
### <a name="remarks"></a>コメント  
 Framework 呼び出し`CView::OnPrepareDC`と`CView::OnPrint`回たびに、このメンバーの別の値を指定するドキュメントの各ページの範囲の値によって返される値`GetFromPage`により返された`GetToPage`です。 このメンバーを使用して`CView::OnPrepareDC`と`CView::OnPrint`ドキュメントの指定したページを印刷します。  
  
 プレビュー モードが最初に呼び出されたときに、フレームワークは、最初に、ドキュメントのどのページをプレビューを判断するには、このメンバーの値を読み取ります。 このメンバーの値を設定するには、オーバーライド`CView::OnPreparePrinting`プレビュー モードに入るときに、ドキュメント内のユーザーの現在位置を維持します。 `m_nCurPage`メンバーは型のパブリック変数**UINT**します。  
  
##  <a name="m_njobnumber"></a>CPrintInfo::m_nJobNumber  
 現在の印刷ジョブのオペレーティング システムによって割り当てられたジョブの数を示します。  
  
### <a name="remarks"></a>コメント  
 この値は、 **SP_ERROR**場合は、ジョブがまだ印刷 (されている場合、`CPrintInfo`オブジェクトが新しく構築され、印刷に使用されていない)、またはジョブの開始時にエラーが発生しました。  
  
##  <a name="m_nnumpreviewpages"></a>CPrintInfo::m_nNumPreviewPages  
 プレビュー モードで表示するページの数が含まれています1 または 2 のいずれかを指定できます。  
  
### <a name="remarks"></a>コメント  
 **M_nNumPreviewPages**メンバーは型のパブリック変数**UINT**します。  
  
##  <a name="m_noffsetpage"></a>CPrintInfo::m_nOffsetPage  
 結合された DocObject 印刷ジョブ内の特定の DocObject の最初のページの前のページ数が含まれています。  
  
##  <a name="m_ppd"></a>CPrintInfo::m_pPD  
 ポインターを含む、`CPrintDialog`の印刷ジョブの印刷 ダイアログ ボックスを表示するために使用します。  
  
### <a name="remarks"></a>コメント  
 `m_pPD`メンバーはパブリック変数へのポインターとして宣言されている`CPrintDialog`します。  
  
##  <a name="m_rectdraw"></a>CPrintInfo::m_rectDraw  
 論理座標で、ページの使用可能な描画領域を指定します。  
  
### <a name="remarks"></a>コメント  
 オーバーライドでこれを参照することも`CView::OnPrint`です。 このメンバーは、ヘッダーとフッターを印刷した後、どのような領域が使えるの追跡に使用できます。 **M_rectDraw**メンバーは型のパブリック変数`CRect`します。  
  
##  <a name="m_strpagedesc"></a>CPrintInfo::m_strPageDesc  
 印刷プレビュー中にページ番号を表示するために使用する書式指定文字列が含まれていますこの文字列は、単一ページの表示と"\n"文字で終了それぞれ二重ページ表示用の&2; つの部分文字列で構成されます。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、既定値として"ページ %u\npages%u-%u\n"を使用します。 ページ番号の別の形式が必要な場合は、書式指定文字列を指定のオーバーライドで`CView::OnPreparePrinting`します。 **関数**メンバーは型のパブリック変数`CString`します。  
  
##  <a name="setmaxpage"></a>CPrintInfo::SetMaxPage  
 この関数では、ドキュメントの最後のページの数を指定します。  
  
```  
void SetMaxPage(UINT nMaxPage);
```  
  
### <a name="parameters"></a>パラメーター  
 *nMaxPage*  
 ドキュメントの最後のページの数です。  
  
### <a name="remarks"></a>コメント  
 この値は、`CPrintDialog`によって参照されるオブジェクト、`m_pPD`メンバーです。 印刷前に、ドキュメントの長さがわかっている場合は、この関数をオーバーライドから呼び出す`CView::OnPreparePrinting`します。 ドキュメントの長さは、[印刷] ダイアログ ボックスで、ユーザーが指定されている設定に依存する場合は、この関数をオーバーライドから呼び出す`CView::OnBeginPrinting`します。 不明な場合、ドキュメントの長さが印刷されるまでを使用して、`m_bContinuePrinting`印刷ループを制御するメンバー。  
  
### <a name="example"></a>例  
  例を参照してください[き](../../mfc/reference/cview-class.md#onprepareprinting)します。  
  
##  <a name="setminpage"></a>CPrintInfo::SetMinPage  
 この関数では、ドキュメントの最初のページの数を指定します。  
  
```  
void SetMinPage(UINT nMinPage);
```  
  
### <a name="parameters"></a>パラメーター  
 *nMinPage*  
 ドキュメントの最初のページの数です。  
  
### <a name="remarks"></a>コメント  
 通常、ページ番号は 1 から始まります。 この値は、`CPrintDialog`によって参照されるオブジェクト、`m_pPD`メンバーです。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル DIBLOOK](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [値](../../mfc/reference/cview-class.md#onbeginprinting)   
 [CView::OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting)   
 [CView::OnEndPrintPreview](../../mfc/reference/cview-class.md#onendprintpreview)   
 [付け](../../mfc/reference/cview-class.md#onpreparedc)   
 [関数](../../mfc/reference/cview-class.md#onprepareprinting)   
 [のみ](../../mfc/reference/cview-class.md#onprint)




