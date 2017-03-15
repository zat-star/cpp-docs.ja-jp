---
title: "クラスの関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMultiPageDHtmlDialog
dev_langs:
- C++
helpviewer_keywords:
- CMultiPageDHtmlDialog class
ms.assetid: 971accc1-824d-4df4-b4c1-b1a20e0f7e4f
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
ms.openlocfilehash: c00af20731b2c47a0074366722da3f4a0711ef85
ms.lasthandoff: 02/24/2017

---
# <a name="cmultipagedhtmldialog-class"></a>関数のクラス
マルチページ ダイアログは、複数の HTML ページを順番に表示し、各ページのイベントを処理します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMultiPageDHtmlDialog : public CDHtmlDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMultiPageDHtmlDialog::CMultiPageDHtmlDialog](#cmultipagedhtmldialog)|マルチページ (ウィザード スタイル) DHTML ダイアログ オブジェクトを構築します。|  
|[関数:: ~ 関数](#cmultipagedhtmldialog__~cmultipagedhtmldialog)|マルチページ DHTML ダイアログ オブジェクトを破棄します。|  
  
## <a name="remarks"></a>コメント  
 これを行うためのメカニズムは、 [DHTML および URL のイベント マップ](http://msdn.microsoft.com/en-us/2a7332f0-79d7-46e4-b816-0a618c46777a)を含む[イベント マップの埋め込み](http://msdn.microsoft.com/library/5346210f-f8b7-4e28-9d2c-d9d7fd42421d)ページごとにします。  
  
## <a name="example"></a>例  
 このマルチページ ダイアログは、単純なウィザードのような機能を定義する&3; つの HTML リソースを想定しています。 最初のページには、`Next`ボタン、もう&1; つ、 **前へ**と`Next` ボタン、および&3; 番目、 **Prev**  ボタンをクリックします。 ハンドラー関数を呼び出すボタンが押されると[CDHtmlDialog::LoadFromResource](../../mfc/reference/cdhtmldialog-class.md#loadfromresource)適切な新しいページを読み込みます。  
  
 (CMyMultiPageDlg.h) で、クラス宣言の関連部分。  
  
 [!code-cpp[NVC_MFCDocView #&181;](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_1.h)]  
  
 クラスの実装 (CMyMultipageDlg.cpp) 内の関連部分。  
  
 [!code-cpp[NVC_MFCDocView #&182;](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDHtmlSinkHandlerBase2`  
  
 `CDHtmlSinkHandlerBase1`  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDHtmlSinkHandler`  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDHtmlEventSink`  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)  
  
 `CMultiPageDHtmlDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdhtml.h  
  
##  <a name="a-namecmultipagedhtmldialoga--cmultipagedhtmldialogcmultipagedhtmldialog"></a><a name="cmultipagedhtmldialog"></a>CMultiPageDHtmlDialog::CMultiPageDHtmlDialog  
 マルチページ (ウィザード スタイル) DHTML ダイアログ オブジェクトを構築します。  
  
```  
CMultiPageDHtmlDialog(
    LPCTSTR lpszTemplateName,  
    LPCTSTR szHtmlResID = NULL,  
    CWnd* pParentWnd = NULL);

 
CMultiPageDHtmlDialog(
    UINT nIDTemplate,  
    UINT nHtmlResID = 0,  
    CWnd* pParentWnd = NULL);  
  
CMultiPageDHtmlDialog();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszTemplateName`  
 ダイアログ テンプレート リソースの名前を表す null で終わる文字列。  
  
 `szHtmlResID`  
 HTML のリソースの名前を表す null で終わる文字列。  
  
 `pParentWnd`  
 親またはオーナー ウィンドウ オブジェクトへのポインター (型の[CWnd](../../mfc/reference/cwnd-class.md)) ダイアログ オブジェクトが属しています。 ある場合**NULL**、ダイアログ オブジェクトの親ウィンドウがアプリケーションのメイン ウィンドウに設定します。  
  
 `nIDTemplate`  
 ダイアログ テンプレート リソースの ID 番号が含まれています。  
  
 `nHtmlResID`  
 HTML リソースの ID 番号が含まれています。  
  
##  <a name="a-namedtorcmultipagedhtmldialoga--cmultipagedhtmldialogcmultipagedhtmldialog"></a><a name="_dtorcmultipagedhtmldialog"></a>関数:: ~ 関数  
 マルチページ DHTML ダイアログ オブジェクトを破棄します。  
  
```  
virtual ~CMultiPageDHtmlDialog();
```  
  
## <a name="see-also"></a>関連項目  
 [CDHtmlDialog クラス](../../mfc/reference/cdhtmldialog-class.md)

