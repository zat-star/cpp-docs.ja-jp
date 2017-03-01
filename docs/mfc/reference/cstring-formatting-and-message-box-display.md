---
title: "CString の書式指定とメッセージ ボックスの表示 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.strings
dev_langs:
- C++
helpviewer_keywords:
- CString objects, formatting and message boxes
ms.assetid: d1068cf4-9cc5-4952-b9e7-d612c53cbc28
caps.latest.revision: 14
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 48fc79f74bda10e43807d57fbcd7ed85fbb5d78b
ms.lasthandoff: 02/24/2017

---
# <a name="cstring-formatting-and-message-box-display"></a>CString の書式指定とメッセージ ボックスの表示
書式設定および解析する多くの機能が提供される`CString`オブジェクトです。 これらの関数を使用するには、操作する必要があるたびに`CString`オブジェクトではなくはメッセージ ボックスのテキストに表示される文字列の書式設定に特に便利です。  
  
 この関数のグループには、メッセージ ボックスを表示するためのグローバル関数も含まれています。  
  
### <a name="cstring-functions"></a>CString 関数  
  
|||  
|-|-|  
|[AfxExtractSubString](#afxextractsubstring)|指定された文字列から単一の文字で区切られた部分文字列を抽出します。|  
|[AfxFormatString1](#afxformatstring1)|ストリング テーブルに置換には文字列の書式指定文字"%1"の指定した文字列が含まれています。|  
|[AfxFormatString2](#afxformatstring2)|形式の&2; つの代替文字列は、「1%」と"%2"文字列の文字列テーブルに含まれる文字します。|  
|[AfxMessageBox](#afxmessagebox)|メッセージ ボックスを表示します。|  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="a-nameafxextractsubstringa--afxextractsubstring"></a><a name="afxextractsubstring"></a>AfxExtractSubString  
 指定された文字列から部分文字列を抽出する、このグローバル関数を使用できます。  
  
```   
BOOL AFXAPI AfxExtractSubString (
    CString& rString,  
    LPCTSTR lpszFullString,  
    int iSubString,  
    TCHAR chSep  = '\n'); 
```  
  
### <a name="parameters"></a>パラメーター  
 *rString*  
 -   参照、 [CString](../../atl-mfc-shared/using-cstring.md)個々 の部分文字列を受け取るオブジェクト。  
  
 *lpszFullString*  
 -   抽出する文字列のすべてのテキストを含む文字列です。  
  
 *iSubString*  
 -   抽出する部分文字列の&0; から始まるインデックス*lpszFullString*します。  
  
 *chSep*  
 -   部分文字列を区切るために使用する区切り記号。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**関数は、指定されたインデックスにある部分文字列を正常に展開する場合は、それ以外の場合、 **FALSE**します。  
  
### <a name="remarks"></a>コメント  
 この関数は、既知の単一の文字は、各サブ文字列を区切るときは、ソース文字列から複数の部分文字列を抽出するために便利です。 この関数の先頭からの検索、`lpszFullString`パラメーターが呼び出されるたび。  
  
 いずれかにこの関数が FALSE を返します`lpszFullString`に設定されている**NULL**関数の末尾に到達または`lpszFullString`検索せず`iSubString`+1 出現する指定した区切り記号文字のです。 `rString`場合、パラメーターを元の値から変更されませんが`lpszFullString`に設定されている**NULL**。 そうしないと、、`rString`パラメーターは、指定したインデックスの部分文字列を抽出できませんでした場合、空の文字列に設定されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities #&48;](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_1.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="a-nameafxformatstring1a--afxformatstring1"></a><a name="afxformatstring1"></a>AfxFormatString1  
 指す文字列に置換`lpsz1`で識別されるテンプレート文字列リソースの「1%」文字のすべてのインスタンスの`nIDS`です。  
  
```  
void  AfxFormatString1(
    CString& rString,  
    UINT nIDS,  
    LPCTSTR lpsz1); 
```  
  
### <a name="parameters"></a>パラメーター  
 `rString`  
 参照、`CString`置換が実行された後に結果の文字列を格納するオブジェクト。  
  
 `nIDS`  
 代替の実行対象となるテンプレート文字列のリソース ID です。  
  
 `lpsz1`  
 「1%」は、テンプレート文字列に文字書式で置換される文字列。  
  
### <a name="remarks"></a>コメント  
 新しく生成された文字列が格納されている`rString`します。 たとえば、文字列テーブル内の文字列が「ファイル %1 が見つかりません」と`lpsz1`は"C:\MYFILE します。TXT"し、`rString`文字列"File C:\MYFILE には。TXT not found"です。 この関数は、メッセージ ボックスやその他のウィンドウに送信される文字列の書式を設定するために便利です。  
  
 書式指定文字"%1"は、文字列に複数回表示される、複数の置き換えが行われます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities&#25;](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_2.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="a-nameafxformatstring2a--afxformatstring2"></a><a name="afxformatstring2"></a>AfxFormatString2  
 指す文字列に置換`lpsz1`「1%」文字とが指す文字列のすべてのインスタンスの`lpsz2`で識別されるテンプレート文字列リソース内の文字"%2"のすべてのインスタンスの`nIDS`です。  
  
```   
void AfxFormatString2(
    CString& rString,  
    UINT nIDS,  
    LPCTSTR lpsz1,  
    LPCTSTR lpsz2); 
```  
  
### <a name="parameters"></a>パラメーター  
 `rString`  
 参照、`CString`結果の文字列が含まれる置換が実行された後です。  
  
 `nIDS`  
 代替の実行対象となるテンプレート文字列の文字列テーブルの ID。  
  
 `lpsz1`  
 「1%」は、テンプレート文字列に文字書式で置換される文字列。  
  
 `lpsz2`  
 "%2"は、テンプレート文字列に文字書式で置換される文字列。  
  
### <a name="remarks"></a>コメント  
 新しく生成された文字列が格納されている`rString`します。 たとえば、文字列テーブル内の文字列が「ファイル %1 がディレクトリ %2 で見つかりません」`lpsz1`が指す myfile をポイントします。TXT"、および`lpsz2`"C:\MYDIR"が、指す`rString`は文字列"File myfile をポイントします。TXT C:\MYDIR ディレクトリに見つかりませんでした"  
  
 書式指定文字「1%」または"%2"は文字列に複数回表示される、複数の置き換えになります。 数値の順序でそれらがありません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities #&26;](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_3.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="a-nameafxmessageboxa--afxmessagebox"></a><a name="afxmessagebox"></a>AfxMessageBox  
 画面にメッセージ ボックスを表示します。  
  
```  
int AfxMessageBox(
    LPCTSTR lpszText,  
    UINT nType = MB_OK,  
    UINT nIDHelp = 0);

int AFXAPI AfxMessageBox(
    UINT nIDPrompt,  
    UINT nType = MB_OK,  
    UINT nIDHelp = (UINT) -1); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszText`  
 `CString` オブジェクト、またはメッセージ ボックスに表示されるメッセージを含む null で終了する文字列をポイントします。  
  
 `nType`  
 メッセージ ボックスのスタイル。 任意の適用、[メッセージ ボックス スタイル](../../mfc/reference/message-box-styles.md)をボックスにします。  
  
 `nIDHelp`  
 メッセージのヘルプ コンテキスト ID。0 は、アプリケーションの既定のヘルプ コンテキストが使用されることを示します。  
  
 `nIDPrompt`  
 文字列テーブル内の文字列の参照に使用される一意の ID。  
  
### <a name="return-value"></a>戻り値  
 メッセージ ボックスを表示する十分なメモリがない場合は&0;。それ以外の場合、次のいずれかの値が返されます。  
  
- **IDABORT** [中止] ボタンを選択します。  
  
- **IDCANCEL** [キャンセル] ボタンを選択します。  
  
- **IDIGNORE** [無視] ボタンを選択します。  
  
- **IDNO**ボタンが選択されません。  
  
- **IDOK** [ok] ボタンが選択されました。  
  
- **IDRETRY** [再試行] ボタンを選択します。  
  
- **IDYES** [はい] ボタンが選択されました。  
  
 メッセージ ボックスに、[キャンセル] ボタンがある場合、 **IDCANCEL** ESC キーが押されるか、または [キャンセル] ボタンが選択されている場合、値が返されます。 メッセージ ボックスに [キャンセル] ボタンがない場合、Esc キーを押しても効果はありません。  
  
 関数は、 [AfxFormatString1](#afxformatstring1)と[AfxFormatString2](#afxformatstring2)メッセージ ボックスに表示されるテキストの書式設定で役に立ちます。  
  
### <a name="remarks"></a>コメント  
 このオーバーロード関数の最初の形式には、メッセージ ボックスの `lpszText` がポイントする文字列が表示され、`nIDHelp` を使用してヘルプ コンテキストが記述されます。 ヘルプ コンテキストは、ユーザーがヘルプ キー (通常は F1 キー) を押したときに関連するヘルプ トピックにジャンプするために使用されます。  
  
 関数の&2; 番目の形式では、ID `nIDPrompt` を持つ文字列リソースを使用してメッセージ ボックスにメッセージが表示されます。 関連するヘルプ ページは、`nIDHelp` の値を使用して検出されます。 場合、既定値の`nIDHelp`を使用 (â €"1)、文字列リソース ID `nIDPrompt`、ヘルプ コンテキストに使用されます。 ヘルプ コンテキストの定義の詳細については、次を参照してください。[テクニカル ノート 28:](../../mfc/tn028-context-sensitive-help-support.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&133;](../../mfc/reference/codesnippet/cpp/cstring-formatting-and-message-box-display_4.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)   
 [CStringT クラス](../../atl-mfc-shared/reference/cstringt-class.md)

