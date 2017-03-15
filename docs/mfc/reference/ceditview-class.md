---
title: "CEditView クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CEditView
dev_langs:
- C++
helpviewer_keywords:
- text editors, CEditView class
- text editors
- edit controls, classes
- views, classes
- CEditView class
ms.assetid: bf38255c-fcbe-450c-95b2-3c5e35f86c37
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
ms.openlocfilehash: 688a6c0e871a9456b85a8ed02ce43d7fa9ca8180
ms.lasthandoff: 02/24/2017

---
# <a name="ceditview-class"></a>CEditView クラス
Windows のエディット コントロールの機能を提供するビュー クラスの一種であり、シンプルなテキスト編集エディターを実装できます。  
  
## <a name="syntax"></a>構文  
  
```  
class CEditView : public CCtrlView  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CEditView::CEditView](#ceditview)|`CEditView` 型のオブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CEditView::FindText](#findtext)|テキスト内で文字列を検索します。|  
|[CEditView::GetBufferLength](#getbufferlength)|文字バッファーの長さを取得します。|  
|[CEditView::GetEditCtrl](#geteditctrl)|アクセスできるように、`CEdit`の部分、 `CEditView` (Windows のエディット コントロール) オブジェクト。|  
|[CEditView::GetPrinterFont](#getprinterfont)|現在のプリンター フォントを取得します。|  
|[CEditView::GetSelectedText](#getselectedtext)|現在のテキスト範囲を取得します。|  
|[CEditView::LockBuffer](#lockbuffer)|バッファーをロックします。|  
|[CEditView::PrintInsideRect](#printinsiderect)|指定した四角形内のテキストをレンダリングします。|  
|[CEditView::SerializeRaw](#serializeraw)|シリアル化、`CEditView`未加工のテキストとしてディスクにオブジェクトです。|  
|[なかったとき](#setprinterfont)|新しいプリンター フォントを設定します。|  
|[CEditView::SetTabStops](#settabstops)|タブの画面の表示と印刷の位置を設定します。|  
|[CEditView::UnlockBuffer](#unlockbuffer)|バッファーのロックを解除します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CEditView::OnFindNext](#onfindnext)|テキスト文字列の次の出現箇所を検索します。|  
|[CEditView::OnReplaceAll](#onreplaceall)|新しい文字列に指定された文字列のすべての出現を置換します。|  
|[CEditView::OnReplaceSel](#onreplacesel)|現在の選択項目を置き換えます。|  
|[CEditView::OnTextNotFound](#ontextnotfound)|さらに、テキストを照合する検索操作が失敗したときに呼び出されます。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CEditView::dwStyleDefault](#dwstyledefault)|既定の型のオブジェクトのスタイル**CEditView します。**|  
  
## <a name="remarks"></a>コメント  
 `CEditView`クラスは、次の追加機能を提供します。  
  
-   印刷します。  
  
-   検索し、置換します。  
  
 クラス`CEditView`クラスの派生クラスは、 `CView`、クラスのオブジェクト`CEditView`ドキュメントおよびドキュメント テンプレートで使用できます。  
  
 各`CEditView`コントロールのテキストは、独自のグローバル メモリ オブジェクトに保持されます。 アプリケーションが任意の数をある`CEditView`オブジェクトです。  
  
 型のオブジェクトを作成する`CEditView`編集ウィンドウを上に示した機能機能を追加する場合、または単純なテキスト エディターの機能を使用する場合。 A`CEditView`オブジェクトがウィンドウのクライアント全体の領域を占有します。 独自のクラスを派生`CEditView`基本的な機能を追加するか、ドキュメント テンプレートに追加できるクラスを宣言します。  
  
 クラスの既定の実装`CEditView`次のコマンドを処理します。 **ID_EDIT_SELECT_ALL**、 **ID_EDIT_FIND**、 **ID_EDIT_REPLACE**、 **ID_EDIT_REPEAT**、および**ID_FILE_PRINT**します。  
  
 既定の文字制限`CEditView`は (1024 \* 1024-1 = 1048575)。 変更を**EM_LIMITTEXT**基になる関数は、コントロールを編集します。 ただし、制限は、オペレーティング システムによって異なりますしの型は、コントロール (1 つまたは複数行) を編集します。 これらの制限に関する詳細については、次を参照してください。 [EM_LIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761607)します。  
  
 コントロールでは、この制限を変更する、`OnCreate()`の機能、`CEditView`クラスし、次のコード行を挿入します。  
  
 [!code-cpp[NVC_MFCDocView #&65;](../../mfc/codesnippet/cpp/ceditview-class_1.cpp)]  
  
 型のオブジェクト`CEditView`(またはから派生した型の`CEditView`) は次の制限があります。  
  
- `CEditView`true を実装していない表示されるは取得 (WYSIWYG) を編集します。 選択肢では、画面上には、読みやすさと、印刷出力`CEditView`画面の読みやすさを選択します。  
  
- `CEditView`1 つのフォントのみにテキストを表示できます。 特殊文字の書式設定はサポートされません。 クラスを参照して[CRichEditView](../../mfc/reference/cricheditview-class.md)の大きい機能します。  
  
-   テキストの量、`CEditView`含めることができますは制限されています。 制限は同じであるとは、`CEdit`コントロールです。  
  
 詳細については`CEditView`を参照してください[派生ビュー クラスで使用できる MFC](../../mfc/derived-view-classes-available-in-mfc.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CEditView`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxext.h  
  
##  <a name="a-nameceditviewa--ceditviewceditview"></a><a name="ceditview"></a>CEditView::CEditView  
 `CEditView` 型のオブジェクトを構築します。  
  
```  
CEditView();
```  
  
### <a name="remarks"></a>コメント  
 オブジェクトを構築後に呼び出す必要があります、 [cwnd::create](../../mfc/reference/cwnd-class.md#create)エディット コントロールを使用する前に機能します。 クラスを派生させる場合`CEditView`を使用してテンプレートに追加`CWinApp::AddDocTemplate`、フレームワークがこの両方のコンス トラクターを呼び出すと、**作成**関数です。  
  
##  <a name="a-namedwstyledefaulta--ceditviewdwstyledefault"></a><a name="dwstyledefault"></a>CEditView::dwStyleDefault  
 既定のスタイルを含む、`CEditView`オブジェクトです。  
  
```  
static const DWORD dwStyleDefault;  
```  
  
### <a name="remarks"></a>コメント  
 この静的メンバーとして渡す、`dwStyle`のパラメーター、**作成**の既定のスタイルを取得する関数、`CEditView`オブジェクトです。  
  
##  <a name="a-namefindtexta--ceditviewfindtext"></a><a name="findtext"></a>CEditView::FindText  
 呼び出す、`FindText`を検索する関数、`CEditView`オブジェクトの文字列バッファー。  
  
```  
BOOL FindText(
    LPCTSTR lpszFind,  
    BOOL bNext = TRUE,  
    BOOL bCase = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFind`  
 検索するテキスト。  
  
 `bNext`  
 検索の方向を指定します。 場合**TRUE**バッファーの末尾方向検索の方向です。 場合**FALSE**バッファーの先頭方向検索の方向です。  
  
 `bCase`  
 検索では、大文字小文字を区別するかどうかを指定します。 場合**TRUE**検索では、大文字小文字を区別します。 場合**FALSE**検索では大文字小文字が区別されません。  
  
### <a name="return-value"></a>戻り値  
 検索テキストが見つかった場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は、指定した文字列のバッファーにテキストを検索`lpszFind`を開始位置で指定した方向での現在の選択項目として`bNext`で指定された大文字小文字の区別を使用して`bCase`します。 テキストが見つかった場合は、見つかったテキストを選択範囲を設定し、0 以外の値を返します。 テキストが見つからなかった場合は、0 を返します。  
  
 通常必要はありませんを呼び出して、`FindText`オーバーライドする必要がない限り、機能`OnFindNext`、どの呼び出し`FindText`します。  
  
##  <a name="a-namegetbufferlengtha--ceditviewgetbufferlength"></a><a name="getbufferlength"></a>CEditView::GetBufferLength  
 Null 終端文字を含まない、エディット コントロールのバッファーの現在の文字数を取得するには、このメンバー関数を呼び出します。  
  
```  
UINT GetBufferLength() const;  
```  
  
### <a name="return-value"></a>戻り値  
 バッファー内の文字列の長さ。  
  
##  <a name="a-namegeteditctrla--ceditviewgeteditctrl"></a><a name="geteditctrl"></a>CEditView::GetEditCtrl  
 呼び出す`GetEditCtrl`編集ビューで使用されるエディット コントロールへの参照を取得します。  
  
```  
CEdit& GetEditCtrl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `CEdit` オブジェクトへの参照。  
  
### <a name="remarks"></a>コメント  
 このコントロールは、型の[CEdit](../../mfc/reference/cedit-class.md)を使用して直接、Windows のエディット コントロールを操作できるように、`CEdit`メンバー関数。  
  
> [!CAUTION]
>  使用して、`CEdit`オブジェクトの基になるウィンドウの状態の変更は、コントロールを編集できます。 たとえば、タブの設定を使用して変更しないで、 [CEdit::SetTabStops](../../mfc/reference/cedit-class.md#settabstops)ために機能`CEditView`エディット コントロールと印刷の両方に使用するため、これらの設定をキャッシュします。 代わりに、 [CEditView::SetTabStops](#settabstops)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&66;](../../mfc/codesnippet/cpp/ceditview-class_2.cpp)]  
  
##  <a name="a-namegetprinterfonta--ceditviewgetprinterfont"></a><a name="getprinterfont"></a>CEditView::GetPrinterFont  
 呼び出す`GetPrinterFont`へのポインターを取得する、 [CFont](../../mfc/reference/cfont-class.md)を現在のプリンター フォントを記述するオブジェクト。  
  
```  
CFont* GetPrinterFont() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CFont`現在のプリンター フォントを指定するオブジェクト**NULL**プリンター フォントが設定されていない場合。 ポインターは一時的である可能性があり、後で使用するために格納しないでください。  
  
### <a name="remarks"></a>コメント  
 プリンター フォントが設定されていないかどうか、既定の動作の印刷、`CEditView`クラスは、表示するために使用する同じフォントを使用して印刷します。  
  
 現在プリンター フォントを判断するのにには、この関数を使用します。 目的のプリンター フォントでない場合は使用[なかったとき](#setprinterfont)を変更します。  
  
##  <a name="a-namegetselectedtexta--ceditviewgetselectedtext"></a><a name="getselectedtext"></a>CEditView::GetSelectedText  
 呼び出す`GetSelectedText`に選択したテキストをコピーする、`CString`選択または選択範囲の先頭のキャリッジ リターン文字の直前の文字の末尾までのオブジェクト。  
  
```  
void GetSelectedText(CString& strResult) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `strResult`  
 参照、`CString`を選択したテキストを受け取るオブジェクト。  
  
##  <a name="a-namelockbuffera--ceditviewlockbuffer"></a><a name="lockbuffer"></a>CEditView::LockBuffer  
 このメンバー関数を呼び出してバッファーへのポインターを取得します。 バッファーを変更する必要があります。  
  
```  
LPCTSTR LockBuffer() const;  
```  
  
### <a name="return-value"></a>戻り値  
 エディット コントロールのバッファーへのポインター。  
  
##  <a name="a-nameonfindnexta--ceditviewonfindnext"></a><a name="onfindnext"></a>CEditView::OnFindNext  
 指定した文字列のバッファーにテキストを検索`lpszFind`で指定した方向で`bNext`で指定された大文字と小文字の区別`bCase`します。  
  
```  
virtual void OnFindNext(
    LPCTSTR lpszFind,  
    BOOL bNext,  
    BOOL bCase);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFind`  
 検索するテキスト。  
  
 `bNext`  
 検索の方向を指定します。 場合**TRUE**バッファーの末尾方向検索の方向です。 場合**FALSE**バッファーの先頭方向検索の方向です。  
  
 `bCase`  
 検索では、大文字小文字を区別するかどうかを指定します。 場合**TRUE**検索では、大文字小文字を区別します。 場合**FALSE**検索では大文字小文字が区別されません。  
  
### <a name="remarks"></a>コメント  
 検索は現在の選択範囲の先頭に開始しを呼び出すことによって実現[FindText](#findtext)します。 既定の実装で`OnFindNext`呼び出し[見つからなかったとき](#ontextnotfound)テキストが見つからなかった場合。  
  
 オーバーライド`OnFindNext`方法を変更する、 `CEditView`-派生オブジェクトがテキストを検索します。 `CEditView`呼び出し`OnFindNext`ユーザーが標準の検索 ダイアログ ボックスで、次を検索 ボタンを選択するとします。  
  
##  <a name="a-nameonreplacealla--ceditviewonreplaceall"></a><a name="onreplaceall"></a>CEditView::OnReplaceAll  
 `CEditView`呼び出し`OnReplaceAll`ユーザーが標準の置換 ダイアログ ボックスで、すべて置換 ボタンを選択するとします。  
  
```  
virtual void OnReplaceAll(
    LPCTSTR lpszFind,  
    LPCTSTR lpszReplace,  
    BOOL bCase);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFind`  
 検索するテキスト。  
  
 `lpszReplace`  
 検索テキストを置換するテキスト。  
  
 `bCase`  
 検索は大文字小文字を区別するかどうかを指定します。 場合**TRUE**検索では、大文字小文字を区別します。 場合**FALSE**検索では大文字小文字が区別されません。  
  
### <a name="remarks"></a>コメント  
 `OnReplaceAll`指定した文字列のバッファーにテキストを検索`lpszFind`で指定された大文字と小文字の区別`bCase`します。 現在の選択範囲の先頭から検索を開始します。 指定されたテキストで、検索テキストが見つかるたびこの関数の置換その出現する位置のテキストの`lpszReplace`です。 呼び出すことによって、検索を行う[FindText](#findtext)します。 既定の実装で[見つからなかったとき](#ontextnotfound)テキストが見つからなかった場合に呼び出されます。  
  
 現在の選択範囲が一致しない場合`lpszFind`、最初に見つかった位置で指定したテキストに、選択内容が更新`lpszFind`置換が実行されていません。 これにより、ユーザーにこれは、選択範囲が置き換えられるテキストと一致しない場合のために必要なことを確認できます。  
  
 オーバーライド`OnReplaceAll`方法を変更する、 `CEditView`-派生オブジェクトには、テキストが置き換えられます。  
  
##  <a name="a-nameonreplacesela--ceditviewonreplacesel"></a><a name="onreplacesel"></a>CEditView::OnReplaceSel  
 `CEditView`呼び出し`OnReplaceSel`ユーザーが標準の置換 ダイアログ ボックスで、置換 ボタンを選択するとします。  
  
```  
virtual void OnReplaceSel(
    LPCTSTR lpszFind,  
    BOOL bNext,  
    BOOL bCase,  
    LPCTSTR lpszReplace);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFind`  
 検索するテキスト。  
  
 `bNext`  
 検索の方向を指定します。 場合**TRUE**バッファーの末尾方向検索の方向です。 場合**FALSE**バッファーの先頭方向検索の方向です。  
  
 `bCase`  
 検索では、大文字小文字を区別するかどうかを指定します。 場合**TRUE**検索では、大文字小文字を区別します。 場合**FALSE**検索では大文字小文字が区別されません。  
  
 `lpszReplace`  
 検出の文字列を置換するテキスト。  
  
### <a name="remarks"></a>コメント  
 選択範囲を交換した後にこの関数は、バッファーで指定したテキストの次のインスタンスのテキストを検索`lpszFind`で指定した方向で`bNext`で指定された大文字と小文字の区別`bCase`します。 呼び出すことによって、検索を行う[FindText](#findtext)します。 テキストが見つからなかった場合[見つからなかったとき](#ontextnotfound)が呼び出されます。  
  
 オーバーライド`OnReplaceSel`方法を変更する、 `CEditView`-派生オブジェクトには、選択したテキストが置き換えられます。  
  
##  <a name="a-nameontextnotfounda--ceditviewontextnotfound"></a><a name="ontextnotfound"></a>CEditView::OnTextNotFound  
 既定の実装では、Windows 関数を変更するには、この関数をオーバーライド**MessageBeep**します。  
  
```  
virtual void OnTextNotFound(LPCTSTR lpszFind);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFind`  
 検索するテキスト。  
  
##  <a name="a-nameprintinsiderecta--ceditviewprintinsiderect"></a><a name="printinsiderect"></a>CEditView::PrintInsideRect  
 呼び出す`PrintInsideRect`で指定された四角形内のテキストを印刷する*rectLayout*します。  
  
```  
UINT PrintInsideRect(
    CDC *pDC,  
    RECT& rectLayout,  
    UINT nIndexStart,  
    UINT nIndexStop);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 プリンター デバイス コンテキストへのポインター。  
  
 *rectLayout*  
 参照、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT 構造体](../../mfc/reference/rect-structure1.md)テキストがレンダリングされる四角形を指定します。  
  
 `nIndexStart`  
 表示する最初の文字のバッファー内のインデックスします。  
  
 `nIndexStop`  
 表示する最後の文字を次の文字のバッファー内のインデックスします。  
  
### <a name="return-value"></a>戻り値  
 印刷するのには、次の文字のインデックス (最後の文字が表示される文字)。  
  
### <a name="remarks"></a>コメント  
 場合、`CEditView`コントロールにスタイルがない**ES_AUTOHSCROLL**レンダリングの四角形内でテキストをラップします。 コントロールにスタイルがある場合**ES_AUTOHSCROLL**、四角形の右端でのテキストが切り取られます。  
  
 **に**の要素、 *rectLayout*オブジェクトは、四角形の寸法がテキストで使用されている元の四角形の部分を定義するように変更します。  
  
##  <a name="a-nameserializerawa--ceditviewserializeraw"></a><a name="serializeraw"></a>CEditView::SerializeRaw  
 呼び出す`SerializeRaw`が、`CArchive`オブジェクトの読み取りまたはテキストを作成、`CEditView`オブジェクトがテキスト ファイルにします。  
  
```  
void SerializeRaw(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 `ar`  
 参照、`CArchive`シリアル化されたテキストを格納するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 `SerializeRaw`異なる`CEditView`の内部実装の`Serialize`を読み取り、オブジェクトの説明のデータの前にせず、テキストのみを書き込みますという点でします。  
  
##  <a name="a-namesetprinterfonta--ceditviewsetprinterfont"></a><a name="setprinterfont"></a>なかったとき  
 呼び出す`SetPrinterFont`で指定されたフォントにプリンター フォントを設定する`pFont`です。  
  
```  
void SetPrinterFont(CFont* pFont);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFont`  
 型のオブジェクトへのポインター`CFont`します。 場合**NULL**印刷に使用するフォントがディスプレイのフォントに基づいています。  
  
### <a name="remarks"></a>コメント  
 呼び出しをビューに常に特定のフォントを印刷に使用する場合は、含める`SetPrinterFont`クラスの`OnPreparePrinting`関数です。 フォントは、変更、ビューの内容が印刷される前に、印刷が行われる前にこの仮想関数が呼び出されます。  
  
##  <a name="a-namesettabstopsa--ceditviewsettabstops"></a><a name="settabstops"></a>CEditView::SetTabStops  
 この関数では、表示および印刷するためのタブ ストップを設定します。  
  
```  
void SetTabStops(int nTabStops);
```  
  
### <a name="parameters"></a>パラメーター  
 `nTabStops`  
 ダイアログ単位で各タブ ストップの幅。  
  
### <a name="remarks"></a>コメント  
 1 つのタブ ストップ幅のみがサポートされています。 (`CEdit`オブジェクトは複数のタブ幅をサポートします)。幅は、ダイアログ単位は、印刷または表示するときに使用するフォントの平均の文字幅 (大文字と小文字の英字のみに基づく) の&4; 分の&1; と同じです。 使用しないで`CEdit::SetTabStops`ため`CEditView`タブ ストップの値をキャッシュする必要があります。  
  
 この関数では、呼び出しのオブジェクトのタブだけを変更します。 タブは変更を各停止`CEditView`オブジェクトのアプリケーションで、各オブジェクトの`SetTabStops`関数です。  
  
### <a name="example"></a>例  
 次のコード片は、コントロールを使用するフォントを慎重に測定することにより、4 文字ごとに、コントロールのタブ ストップを設定します。  
  
 [!code-cpp[NVC_MFCDocView #&67;](../../mfc/codesnippet/cpp/ceditview-class_3.cpp)]  
  
##  <a name="a-nameunlockbuffera--ceditviewunlockbuffer"></a><a name="unlockbuffer"></a>CEditView::UnlockBuffer  
 バッファーのロックを解除するには、このメンバー関数を呼び出します。  
  
```  
void UnlockBuffer() const;  
```  
  
### <a name="remarks"></a>コメント  
 呼び出す`UnlockBuffer`によって返されたポインターの使用が完了した後[LockBuffer](#lockbuffer)します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル SUPERPAD](../../visual-cpp-samples.md)   
 [CCtrlView クラス](../../mfc/reference/cctrlview-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CEdit クラス](../../mfc/reference/cedit-class.md)   
 [CDocument クラス](../../mfc/reference/cdocument-class.md)   
 [CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)   
 [CCtrlView クラス](../../mfc/reference/cctrlview-class.md)   
 [CRichEditView クラス](../../mfc/reference/cricheditview-class.md)

