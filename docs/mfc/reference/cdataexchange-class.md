---
title: "CDataExchange クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDataExchange
- AFXWIN/CDataExchange
- AFXWIN/CDataExchange::CDataExchange
- AFXWIN/CDataExchange::Fail
- AFXWIN/CDataExchange::PrepareCtrl
- AFXWIN/CDataExchange::PrepareEditCtrl
- AFXWIN/CDataExchange::PrepareOleCtrl
- AFXWIN/CDataExchange::m_bSaveAndValidate
- AFXWIN/CDataExchange::m_pDlgWnd
dev_langs:
- C++
helpviewer_keywords:
- DDX/DDV, Technical Note 26
- DDX/DDV, CDataExchange class
- DDX (dialog data exchange), direction of exchange
- DDX (dialog data exchange), between dialog and CDialog
- DDX (dialog data exchange), custom DDX routines
- DDV (dialog data validation)
- m_bSaveAndValidate
- CDataExchange class
- exchanging data between dialogs and CDialogs
- DDV (dialog data validation), custom DDV routines
- DDX/DDV
- DDX (dialog data exchange)
- validating data, dialog box data entry
ms.assetid: 84ed6113-325d-493e-a75d-223f03a992b8
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 8f35e87d562a894411401755ccd4fdd54e43b58a
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cdataexchange-class"></a>CDataExchange クラス
MFC で使われているダイアログ データ エクスチェンジ (DDX) およびダイアログ データ検証 (DDV) の両ルーチンをサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CDataExchange  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDataExchange::CDataExchange](#cdataexchange)|`CDataExchange` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDataExchange::Fail](#fail)|検証が失敗したときに呼び出されます。 前のコントロールにフォーカスをリセットし、例外をスローします。|  
|[CDataExchange::PrepareCtrl](#preparectrl)|データ交換または検証のためには、指定したコントロールを準備します。 エディット コントロールに使用します。|  
|[CDataExchange::PrepareEditCtrl](#prepareeditctrl)|データ交換または検証のためには、指定されたエディット コントロールを準備します。|  
|[CDataExchange::PrepareOleCtrl](#prepareolectrl)|データ交換または検証のためには、指定した OLE コントロールを準備します。 エディット コントロールに使用します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDataExchange::m_bSaveAndValidate](#m_bsaveandvalidate)|DDX ルーチンおよび DDV の方向を示すフラグします。|  
|[CDataExchange::m_pDlgWnd](#m_pdlgwnd)|データ交換がダイアログ ボックスまたはウィンドウが行われます。|  
  
## <a name="remarks"></a>コメント  
 `CDataExchange`基本クラスはありません。  
  
 カスタム データ型またはコントロールのデータ エクス チェンジ ルーチンを記述する場合は、このクラスを使用して、またはデータの検証ルーチンを作成している場合。 独自の DDX ルーチンおよび DDV ルーチンを記述の詳細については、次を参照してください。[テクニカル ノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)します。 DDX ルーチンおよび DDV の概要については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)と[ダイアログ ボックス](../../mfc/dialog-boxes.md)します。  
  
 A`CDataExchange`オブジェクト DDX ルーチンおよび DDV を配置に必要なコンテキスト情報を提供します。 フラグ`m_bSaveAndValidate`は**FALSE**ダイアログ コントロールのデータ メンバーからの初期値を入力する DDX を使用する場合。 フラグ`m_bSaveAndValidate`は**TRUE**データ メンバーおよびデータ値を検証する DDV を使用する場合にダイアログ コントロールの現在の値を設定する DDX を使用する場合。 DDV 検証が失敗した場合、ddv によって入力エラーを示すメッセージ ボックスが表示されます。 DDV プロシージャが呼び出され、**失敗**問題が発生したコントロールにフォーカスをリセットし、検証プロセスを停止する例外をスローします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CDataExchange`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cdataexchange"></a>CDataExchange::CDataExchange  
 作成するには、このメンバー関数を呼び出す、`CDataExchange`オブジェクトです。  
  
```  
CDataExchange(
    CWnd* pDlgWnd,  
    BOOL bSaveAndValidate);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDlgWnd*  
 コントロールを含む親ウィンドウへのポインター。 これは通常、 [CDialog](../../mfc/reference/cdialog-class.md)-派生オブジェクト。  
  
 `bSaveAndValidate`  
 場合**TRUE**、このオブジェクトは、データを検証し、メンバーに、コントロールからデータを書き込みます。 場合**FALSE**、このオブジェクトは、メンバーのデータをコントロールに移動されます。  
  
### <a name="remarks"></a>コメント  
 構築、`CDataExchange`オブジェクトに渡す、ウィンドウのデータの exchange オブジェクトに追加情報を格納する自分で[CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange)メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog #&70;](../../mfc/codesnippet/cpp/cdataexchange-class_1.cpp)]  
  
##  <a name="fail"></a>CDataExchange::Fail  
 フレームワークは、ダイアログ データ バリデーション (DDV) 操作が失敗したときに、このメンバー関数を呼び出します。  
  
```  
void Fail();
```  
  
### <a name="remarks"></a>コメント  
 **失敗**が検証には、(復元するためのコントロールがある場合) が失敗しました。 コントロールにフォーカスと選択を復元します。 **失敗**型の例外をスロー[チェック](../../mfc/reference/cuserexception-class.md)検証プロセスを停止します。 例外により、メッセージ ボックスが表示されるエラーの説明。 DDV 検証が失敗した後、ユーザーは、問題が発生したコントロールのデータの再入できます。  
  
 カスタムの DDV ルーチンの実装を呼び出すことができます**失敗**検証が失敗したときに、ルーチンからです。  
  
 独自の DDX ルーチンおよび DDV ルーチンを記述の詳細については、次を参照してください。[テクニカル ノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)します。 DDX ルーチンおよび DDV の概要については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)と[ダイアログ ボックスに関するトピック](../../mfc/dialog-boxes.md)します。  
  
##  <a name="m_bsaveandvalidate"></a>CDataExchange::m_bSaveAndValidate  
 このフラグは、ダイアログ データ エクス (チェンジ DDX) 操作の方向を示します。  
  
```  
BOOL m_bSaveAndValidate;  
```  
  
### <a name="remarks"></a>コメント  
 フラグがゼロ以外場合、`CDataExchange`ユーザー コントロールの編集後は、ダイアログ クラスのデータ メンバーに、ダイアログ コントロールからデータを移動するオブジェクトを使用します。 ダイアログ クラスのデータ メンバーからダイアログ コントロールを初期化するために、オブジェクトを使用する場合、このフラグは&0; です。  
  
 ダイアログ データ バリデーション (DDV) の中には、フラグを&0; 以外の値もです。  
  
 独自の DDX ルーチンおよび DDV ルーチンを記述の詳細については、次を参照してください。[テクニカル ノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)します。 DDX ルーチンおよび DDV の概要については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)と[ダイアログ ボックスに関するトピック](../../mfc/dialog-boxes.md)します。  
  
##  <a name="m_pdlgwnd"></a>CDataExchange::m_pDlgWnd  
 ポインターを含む、 [CWnd](../../mfc/reference/cwnd-class.md)オブジェクト ダイアログ データ エクス (チェンジ DDX) またはバリデーション (DDV) が行われています。  
  
```  
CWnd* m_pDlgWnd;  
```  
  
### <a name="remarks"></a>コメント  
 このオブジェクトは、通常、 [CDialog](../../mfc/reference/cdialog-class.md)オブジェクトです。 独自の DDX または DDV ルーチンを記述するときは、このポインターを使用して、操作するコントロールを格納しているダイアログ ウィンドウにアクセス権を取得します。  
  
 独自の DDX ルーチンおよび DDV ルーチンを記述の詳細については、次を参照してください。[テクニカル ノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)します。 DDX ルーチンおよび DDV の概要については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)と[ダイアログ ボックスに関するトピック](../../mfc/dialog-boxes.md)します。  
  
##  <a name="preparectrl"></a>CDataExchange::PrepareCtrl  
 ダイアログ データ エクス (チェンジ DDX) とバリデーション (DDV) の指定したコントロールを準備する、フレームワークが呼び出します。  
  
```  
HWND PrepareCtrl(int nIDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDC`  
 DDX または DDV 用の準備、コントロールの ID。  
  
### <a name="return-value"></a>戻り値  
 `HWND` DDX または DDV 用に準備されているコントロールのです。  
  
### <a name="remarks"></a>コメント  
 使用して[性チェックされる](#prepareeditctrl)代わりにエディット コントロールを他のすべてのコントロールのこのメンバー関数を使用します。  
  
 コントロールを格納するは、準備`HWND`で、`CDataExchange`クラスです。 フレームワークでは、このハンドルを使用して、DDX または DDV 障害発生時のフォーカスがあったのコントロールにフォーカスを戻します。  
  
 独自の DDX または DDV ルーチンを記述するときに呼び出す必要があります`PrepareCtrl`すべての非編集コントロールをする DDX を使ってデータを交換するか、DDV を使ってデータを検証します。  
  
 独自の DDX ルーチンおよび DDV ルーチンを記述の詳細については、次を参照してください。[テクニカル ノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)します。 DDX ルーチンおよび DDV の概要については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)と[ダイアログ ボックスに関するトピック](../../mfc/dialog-boxes.md)します。  
  
##  <a name="prepareeditctrl"></a>CDataExchange::PrepareEditCtrl  
 ダイアログ データ エクス (チェンジ DDX) とバリデーション (DDV) の指定されたエディット コントロールを準備する、フレームワークが呼び出します。  
  
```  
HWND PrepareEditCtrl(int nIDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDC`  
 DDX または DDV のための準備がエディット コントロールの ID。  
  
### <a name="return-value"></a>戻り値  
 `HWND` DDX または DDV の準備中エディット コントロールのです。  
  
### <a name="remarks"></a>コメント  
 使用[記述](#preparectrl)代わりにすべての非編集コントロールです。  
  
 準備は、次の&2; つで構成されます。 まず、 `PrepareEditCtrl` 、コントロールを格納`HWND`で、`CDataExchange`クラスです。 フレームワークでは、このハンドルを使用して、DDX または DDV 障害発生時のフォーカスがあったのコントロールにフォーカスを戻します。 2 番目、`PrepareEditCtrl`にフラグを設定、`CDataExchange`ことを示すデータが交換またはエディット コントロールは、検証コントロールです。  
  
 独自の DDX または DDV ルーチンを記述するときに呼び出す必要があります`PrepareEditCtrl`のすべてのエディット コントロールをする DDX を使ってデータを交換するか、DDV を使ってデータを検証します。  
  
 独自の DDX ルーチンおよび DDV ルーチンを記述の詳細については、次を参照してください。[テクニカル ノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)します。 DDX ルーチンおよび DDV の概要については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)と[ダイアログ ボックスに関するトピック](../../mfc/dialog-boxes.md)します。  
  
##  <a name="prepareolectrl"></a>CDataExchange::PrepareOleCtrl  
 ダイアログ データ エクス (チェンジ DDX) とバリデーション (DDV) の指定した OLE コントロールを準備する、フレームワークが呼び出します。  
  
```  
COleControlSite* PrepareOleCtrl(int nIDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDC`  
 DDX または DDV 用の準備の OLE コントロールの ID。  
  
### <a name="return-value"></a>戻り値  
 OLE コントロール サイトへのポインター。  
  
### <a name="remarks"></a>コメント  
 使用[性チェックされる](#prepareeditctrl)代わりに編集コントロールのまたは[記述](#preparectrl)他のすべての非 OLE コントロールです。  
  
 独自の DDX または DDV ルーチンを記述するときに呼び出す必要があります`PrepareOleCtrl`のすべての OLE コントロールをする DDX を使ってデータを交換するか、DDV を使ってデータを検証します。  
  
 独自の DDX ルーチンおよび DDV ルーチンを記述の詳細については、次を参照してください。[テクニカル ノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)します。 DDX ルーチンおよび DDV の概要については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)と[ダイアログ ボックスに関するトピック](../../mfc/dialog-boxes.md)します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル VIEWEX](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange)   
 [:Updatedata](../../mfc/reference/cwnd-class.md#updatedata)


