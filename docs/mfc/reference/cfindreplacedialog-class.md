---
title: "CFindReplaceDialog クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::Create
- AFXDLGS/CFindReplaceDialog::FindNext
- AFXDLGS/CFindReplaceDialog::GetFindString
- AFXDLGS/CFindReplaceDialog::GetNotifier
- AFXDLGS/CFindReplaceDialog::GetReplaceString
- AFXDLGS/CFindReplaceDialog::IsTerminating
- AFXDLGS/CFindReplaceDialog::MatchCase
- AFXDLGS/CFindReplaceDialog::MatchWholeWord
- AFXDLGS/CFindReplaceDialog::ReplaceAll
- AFXDLGS/CFindReplaceDialog::ReplaceCurrent
- AFXDLGS/CFindReplaceDialog::SearchDown
- AFXDLGS/CFindReplaceDialog::m_fr
dev_langs:
- C++
helpviewer_keywords:
- text searches, replacing text
- text searches, CFindReplaceDialog class
- Find/Replace dialog box
- replacing text, CFindReplaceDialog class
- CFindReplaceDialog class
- replacing text
ms.assetid: 610f0b5d-b398-4ef6-8c05-e9d6641e50a8
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
ms.openlocfilehash: 510f6a763dbacb7d4e1b14ea808a4baaaf3d6bf3
ms.lasthandoff: 02/24/2017

---
# <a name="cfindreplacedialog-class"></a>CFindReplaceDialog クラス
標準の文字列検索と置換 ダイアログ ボックスをアプリケーションに実装できます。  
  
## <a name="syntax"></a>構文  
  
```  
class CFindReplaceDialog : public CCommonDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog)|作成するには、この関数を呼び出して、`CFindReplaceDialog`オブジェクトです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFindReplaceDialog::Create](#create)|作成し、表示、 `CFindReplaceDialog`  ダイアログ ボックス。|  
|[CFindReplaceDialog::FindNext](#findnext)|ユーザーが検索文字列の次の出現箇所を検索するかどうかを判断するには、この関数を呼び出します。|  
|[CFindReplaceDialog::GetFindString](#getfindstring)|この関数では、現在の検索文字列を取得します。|  
|[CFindReplaceDialog::GetNotifier](#getnotifier)|取得するには、この関数を呼び出して、 **FINDREPLACE**登録済みのメッセージ ハンドラーで構造体。|  
|[CFindReplaceDialog::GetReplaceString](#getreplacestring)|この関数では、現在の置換文字列を取得します。|  
|[CFindReplaceDialog::IsTerminating](#isterminating)|ダイアログ ボックスが終了したかどうかを判断するには、この関数を呼び出します。|  
|[CFindReplaceDialog::MatchCase](#matchcase)|検索文字列の大文字小文字を正確に一致するかどうかを判断するには、この関数を呼び出します。|  
|[CFindReplaceDialog::MatchWholeWord](#matchwholeword)|ユーザーが単語だけを一致するかどうかを判断するには、この関数を呼び出します。|  
|[CFindReplaceDialog::ReplaceAll](#replaceall)|ユーザーが置換される文字列のすべての出現回数をかどうかを判断するには、この関数を呼び出します。|  
|[CFindReplaceDialog::ReplaceCurrent](#replacecurrent)|現在の単語を置換するかどうかを調べますを呼び出します。|  
|[CFindReplaceDialog::SearchDown](#searchdown)|下方向へ検索するかどうかを調べますを呼び出します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CFindReplaceDialog::m_fr](#m_fr)|カスタマイズに使用する構造体、`CFindReplaceDialog`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 その他の Windows コモン ダイアログ ボックスとは異なり`CFindReplaceDialog`オブジェクトは、モードレス、ユーザーが画面上にある他のウィンドウと対話できるようにします。 2 種類の`CFindReplaceDialog`オブジェクト: ダイアログ ボックスおよび検索と置換 ダイアログ ボックスを検索します。 ダイアログ ボックスには、ユーザーが入力された検索と検索/置換文字列ができるように、これらは実行しません、検索や置換用の関数のいずれか。 このアプリケーションに追加する必要があります。  
  
 構築する、`CFindReplaceDialog`オブジェクトを指定されたコンス トラクター (引数を持ちません) を使用します。 これはモードレス ダイアログ ボックスであるため、ヒープを使用して、オブジェクトの割り当て、**新しい**演算子、スタックではなく。  
  
 1 回、`CFindReplaceDialog`オブジェクトが構築された、呼び出す必要があります、[作成](#create)メンバー関数を作成し、ダイアログ ボックスを表示します。  
  
 使用して、 [m_fr](#m_fr)呼び出す前に、ダイアログ ボックスを初期化するために**作成**します。 `m_fr`型の構造は、 [FINDREPLACE](http://msdn.microsoft.com/library/windows/desktop/ms646835)します。 この構造体の詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] を参照してください。  
  
 親ウィンドウ検索/置換要求の通知を受信するためには、Windows を使用する必要があります[を通じて](http://msdn.microsoft.com/library/windows/desktop/ms644947)機能し、使用して、 [ON_REGISTERED_MESSAGE](http://msdn.microsoft.com/library/93c1c068-ae8c-4e04-8a60-a603800ab57d)を登録したメッセージを処理するフレーム ウィンドウ内のメッセージ マップ マクロです。  
  
 ダイアログ ボックスを終了したかどうかを指定できます、`IsTerminating`メンバー関数。  
  
 `CFindReplaceDialog`COMMDLG に依存します。Windows 3.1 以降のバージョンに付属している DLL ファイルです。  
  
 ダイアログ ボックスをカスタマイズするには、派生クラスを`CFindReplaceDialog`拡張されたコントロールからの通知メッセージを処理するメッセージ マップを追加、独自のダイアログ テンプレートを使用します。 処理されないメッセージは、基本クラスに渡す必要があります。  
  
 フック関数をカスタマイズする必要はありません。  
  
 使用する方法について`CFindReplaceDialog`を参照してください[コモン ダイアログ クラス](../../mfc/common-dialog-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFindReplaceDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdlgs.h  
  
##  <a name="cfindreplacedialog"></a>CFindReplaceDialog::CFindReplaceDialog  
 `CFindReplaceDialog` オブジェクトを構築します。  
  
```  
CFindReplaceDialog();
```  
  
### <a name="remarks"></a>コメント  
 `CFindReplaceDialog`オブジェクトは、モードレス ダイアログ ボックスを使用して、ヒープを作成する必要があります、`new`演算子。  
  
 破棄、中には、フレームワークを実行、 `delete this`  ダイアログ ボックスへのポインターにします。 スタックで、ダイアログ ボックスを作成した場合、`this`ポインターが存在しないと、未定義の動作が発生する可能性があります。  
  
 構築の詳細については`CFindReplaceDialog`オブジェクトを参照してください、 [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md)の概要です。 使用して、 [CFindReplaceDialog::Create](#create)  ダイアログ ボックスを表示するメンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&170;](../../mfc/codesnippet/cpp/cfindreplacedialog-class_1.cpp)]  
  
##  <a name="create"></a>CFindReplaceDialog::Create  
 作成し、検索や検索と置換 ダイアログ ボックス オブジェクトの表示の値に応じて`bFindDialogOnly`します。  
  
```  
virtual BOOL Create(
    BOOL bFindDialogOnly,  
    LPCTSTR lpszFindWhat,  
    LPCTSTR lpszReplaceWith = NULL,  
    DWORD dwFlags = FR_DOWN,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `bFindDialogOnly`  
 このパラメーターを設定`TRUE`を表示する、**検索** ダイアログ ボックス。 設定`FALSE`を表示する、**検索/置換** ダイアログ ボックス。  
  
 `lpszFindWhat`  
 ダイアログ ボックスが表示されたら、既定の検索文字列へのポインター。 場合`NULL`、ダイアログ ボックスに既定の検索文字列が含まれていません。  
  
 `lpszReplaceWith`  
 ダイアログ ボックスが表示されたら、既定の置換文字列へのポインター。 場合`NULL`、ダイアログ ボックスに、既定値の置換文字列が含まれていません。  
  
 `dwFlags`  
 ビットごとの OR 演算子を使用して結合 ダイアログ ボックスの設定をカスタマイズに使用できる&1; つまたは複数のフラグです。 既定値は`FR_DOWN`検索を下方向に続行することを指定します。 参照してください、 [FINDREPLACE](http://msdn.microsoft.com/library/windows/desktop/ms646835)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]詳細については、これらのフラグ。  
  
 `pParentWnd`  
 ダイアログ ボックスの親ウィンドウまたはオーナー ウィンドウへのポインター。 これは、検索と置換の操作が要求されたことを示す特別なメッセージを受信するウィンドウです。 場合`NULL`アプリケーションのメイン ウィンドウを使用します。  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスのオブジェクトが正常に作成された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 親ウィンドウ検索/置換要求の通知を受信するためには、Windows を使用する必要があります[を通じて](http://msdn.microsoft.com/library/windows/desktop/ms644947)関数の戻り値は、アプリケーションのインスタンスに固有のメッセージ番号。 フレーム ウィンドウは、コールバック関数を宣言するメッセージ マップ エントリを持つ必要があります (`OnFindReplace`に続く例では) この登録済みのメッセージを処理します。 次のコード フラグメントは、これを行うという名前のフレーム ウィンドウ クラスの方法の例`CMyRichEditView`:  
  
 [!code-cpp[NVC_MFCDocView #&171;。](../../mfc/codesnippet/cpp/cfindreplacedialog-class_2.h)]  
  
 [!code-cpp[NVC_MFCDocView #&172;](../../mfc/codesnippet/cpp/cfindreplacedialog-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #&173;](../../mfc/codesnippet/cpp/cfindreplacedialog-class_4.cpp)]  
  
 内で、`OnFindReplace`関数を使用して、ユーザーの意図を解釈する、 [CFindReplaceDialog::FindNext](#findnext)と[CFindReplaceDialog::IsTerminating](#isterminating)メソッドとする検索/置換の操作のコードを作成します。  
  
### <a name="example"></a>例  
  例を参照してください[CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog)します。  
  
##  <a name="findnext"></a>CFindReplaceDialog::FindNext  
 コールバック関数、ユーザーが検索文字列の次の出現箇所を検索するかどうかを判断するのには、この関数を呼び出します。  
  
```  
BOOL FindNext() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ユーザーが検索文字列の次の出現箇所を検索する場合は 0 以外それ以外の場合 0 を返します。  
  
##  <a name="getfindstring"></a>CFindReplaceDialog::GetFindString  
 コールバック関数を検索する既定の文字列を取得するのには、この関数を呼び出します。  
  
```  
CString GetFindString() const;  
```  
  
### <a name="return-value"></a>戻り値  
 検索する既定の文字列。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&69;](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]  
  
##  <a name="getnotifier"></a>CFindReplaceDialog::GetNotifier  
 現在の検索置換 ダイアログ ボックスへのポインターを取得するには、この関数を呼び出します。  
  
```  
static CFindReplaceDialog* PASCAL GetNotifier(LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `lParam`  
 **Lparam**フレーム ウィンドウの値が渡される**次 OnFindReplace**メンバー関数。  
  
### <a name="return-value"></a>戻り値  
 現在のダイアログ ボックスへのポインター。  
  
### <a name="remarks"></a>コメント  
 現在のダイアログ ボックスを表示するには、関数、およびアクセスは、そのメンバーを呼び出し、コールバック関数内で使用する必要があります、`m_fr`構造体。  
  
### <a name="example"></a>例  
 参照してください[CFindReplaceDialog::Create](#create)検索置換 ダイアログ ボックスから通知を受け取る次の OnFindReplace ハンドラーを登録する方法の例です。  
  
 [!code-cpp[NVC_MFCDocView #&69;](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]  
  
##  <a name="getreplacestring"></a>CFindReplaceDialog::GetReplaceString  
 この関数では、現在の置換文字列を取得します。  
  
```  
CString GetReplaceString() const;  
```  
  
### <a name="return-value"></a>戻り値  
 検索した文字列の置換に使用する既定の文字列。  
  
### <a name="example"></a>例  
  例を参照してください[CFindReplaceDialog::GetFindString](#getfindstring)します。  
  
##  <a name="isterminating"></a>CFindReplaceDialog::IsTerminating  
 ダイアログ ボックスを終了したかどうかを決定するコールバック関数内でこの関数を呼び出します。  
  
```  
BOOL IsTerminating() const;  
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、ユーザーがダイアログ ボックスを終了することにしましたそれ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は&0; 以外の値を返す場合を呼び出す必要があります、`DestroyWindow`の現在のダイアログ ボックスおよび任意のダイアログ ボックスへのポインター変数セットのメンバー関数**NULL**します。 必要に応じて、最後に入力された検索/置換テキストを格納し、次の検索と置換 ダイアログ ボックスを初期化するために使用することができますもします。  
  
### <a name="example"></a>例  
  例を参照してください[CFindReplaceDialog::GetFindString](#getfindstring)します。  
  
##  <a name="m_fr"></a>CFindReplaceDialog::m_fr  
 カスタマイズに使用される、`CFindReplaceDialog`オブジェクトです。  
  
```  
FINDREPLACE m_fr;  
```  
  
### <a name="remarks"></a>コメント  
 `m_fr`型の構造体は、 [FINDREPLACE](http://msdn.microsoft.com/library/windows/desktop/ms646835)します。 そのメンバーは、ダイアログ ボックスのオブジェクトの特性を格納します。 構築した後、`CFindReplaceDialog`オブジェクトを使用する`m_fr` ダイアログ ボックスのさまざまな値を変更します。  
  
 この構造体の詳細については、次を参照してください。、 **FINDREPLACE**構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog)します。  
  
##  <a name="matchcase"></a>CFindReplaceDialog::MatchCase  
 検索文字列の大文字小文字を正確に一致するかどうかを判断するには、この関数を呼び出します。  
  
```  
BOOL MatchCase() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ユーザーが検索文字列の大文字と小文字を正確に一致する検索文字列の出現箇所が検出する場合は 0 以外それ以外の場合 0 を返します。  
  
##  <a name="matchwholeword"></a>CFindReplaceDialog::MatchWholeWord  
 ユーザーが単語だけを一致するかどうかを判断するには、この関数を呼び出します。  
  
```  
BOOL MatchWholeWord() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ユーザーが検索文字列の全体の単語のみが一致する場合は 0 以外それ以外の場合 0 を返します。  
  
##  <a name="replaceall"></a>CFindReplaceDialog::ReplaceAll  
 ユーザーが置換される文字列のすべての出現回数をかどうかを判断するには、この関数を呼び出します。  
  
```  
BOOL ReplaceAll() const;  
```  
  
### <a name="return-value"></a>戻り値  
 置換文字列に一致するすべての文字列が置き換えられることは、ユーザーが要求した場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="replacecurrent"></a>CFindReplaceDialog::ReplaceCurrent  
 現在の単語を置換するかどうかを調べますを呼び出します。  
  
```  
BOOL ReplaceCurrent() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ユーザーが現在選択されている文字列を置換文字列に置き換えることを要求した場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="searchdown"></a>CFindReplaceDialog::SearchDown  
 下方向へ検索するかどうかを調べますを呼び出します。  
  
```  
BOOL SearchDown() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ユーザーは、下方向へ検索を望んでいる場合は 0 以外。上方向へ検索する場合は 0 を返します。  
  
## <a name="see-also"></a>関連項目  
 [CCommonDialog クラス](../../mfc/reference/ccommondialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)  

