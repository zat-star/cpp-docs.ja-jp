---
title: "標準的なダイアログ データ エクス ルーチン |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- standard dialog, data exchange routines
ms.assetid: c6adb7f3-f9af-4cc5-a9ea-315c5b60ad1a
caps.latest.revision: 13
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
ms.openlocfilehash: 15bd88000a7a035ed416b7e1c0640488039079ab
ms.lasthandoff: 02/24/2017

---
# <a name="standard-dialog-data-exchange-routines"></a>標準的なダイアログ データ エクスチェンジ ルーチン
このトピックでは、共通の MFC ダイアログ コントロールに使用される標準的なダイアログ データ エクス (チェンジ DDX) ルーチンを示します。  
  
> [!NOTE]
>  標準的なダイアログ データ エクス チェンジ ルーチンは、ヘッダー ファイル afxdd_.h で定義されます。 ただし、アプリケーションでは、afxwin.h を含める必要があります。  
  
### <a name="ddx-functions"></a>DDX 関数  
  
|||  
|-|-|  
|[DDX_CBIndex](#ddx_cbindex)|初期化またはコンボ ボックス コントロールの現在の選択範囲のインデックスを取得します。|  
|[DDX_CBString](#ddx_cbstring)|初期化またはコンボ ボックス コントロールの編集 フィールドの現在の内容を取得します。|  
|[DDX_CBStringExact](#ddx_cbstringexact)|初期化またはコンボ ボックス コントロールの編集 フィールドの現在の内容を取得します。|  
|[DDX_Check](#ddx_check)|初期化またはチェック ボックス コントロールの現在の状態を取得します。|  
|[DDX_Control](#ddx_control)|サブクラス ダイアログ ボックス内で指定されたコントロール。|  
|[DDX_DateTimeCtrl](#ddx_datetimectrl)|初期化または日付と時刻の選択コントロールの日付/時刻のデータを取得します。|  
|[DDX_IPAddress](#ddx_ipaddress)|初期化または IP アドレス コントロールの現在の値を取得します。|  
|[DDX_LBIndex](#ddx_lbindex)|初期化またはリスト ボックス コントロールの現在の選択範囲のインデックスを取得します。|  
|[DDX_LBString](#ddx_lbstring)|初期化またはリスト ボックス コントロール内の現在の選択項目を取得します。|  
|[DDX_LBStringExact](#ddx_lbstringexact)|初期化またはリスト ボックス コントロール内の現在の選択項目を取得します。|  
|[DDX_MonthCalCtrl](#ddx_monthcalctrl)|初期化または月間予定表コントロールの現在の値を取得します。|  
|[DDX_Radio](#ddx_radio)|初期化またはオプション ボタン コントロールのグループ内で現在チェックされているオプション ボタン コントロールの 0 から始まるインデックスを取得します。|  
|[DDX_Scroll](#ddx_scroll)|初期化またはスクロール コントロールのスクロール ボックスの現在の位置を取得します。|  
|[DDX_Slider](#ddx_slider)|初期化またはスライダー コントロールのスクロール ボックスの現在の位置を取得します。|  
|[DDX_Text](#ddx_text)|初期化またはエディット コントロールの現在の値を取得します。|  
  
##  <a name="a-nameddxcbindexa--ddxcbindex"></a><a name="ddx_cbindex"></a>DDX_CBIndex  
 `DDX_CBIndex`関数は、コンテンツの転送を管理`int` ダイアログ ボックスでは、コンボ ボックス コントロールの間でデータ ビュー、またはオブジェクトのフォームと`int` ダイアログ ボックス、フォーム ビュー、またはオブジェクトのデータ メンバーです。  
  
```  
void AFXAPI DDX_CBIndex(
    CDataExchange* pDX,  
    int nIDC,  
    int& index);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 コントロールのプロパティに関連付けられているコンボ ボックス コントロールのリソース ID です。  
  
 *インデックス*  
 ダイアログ ボックス、フォーム ビュー、またはデータを交換するオブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 `DDX_CBIndex`が呼び出されると、*インデックス*コンボ ボックスの現在の選択範囲のインデックスに設定されています。 項目が選択されていない場合*インデックス*は 0 に設定します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddxcbstringa--ddxcbstring"></a><a name="ddx_cbstring"></a>DDX_CBString  
 `DDX_CBString`関数は、コンテンツの転送を管理`CString` ダイアログ ボックスでは、コンボ ボックス コントロールのエディット コントロールの間でデータ ビュー、またはオブジェクトのフォームと`CString` ダイアログ ボックス、フォーム ビュー、またはオブジェクトのデータ メンバーです。  
  
```  
void AFXAPI DDX_CBString(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 コントロールのプロパティに関連付けられているコンボ ボックス コントロールのリソース ID です。  
  
 *value*  
 ダイアログ ボックス、フォーム ビュー、またはデータを交換するオブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 `DDX_CBString`が呼び出されると、*値*コンボ ボックスの現在の選択に設定されています。 項目が選択されていない場合*値*が長さ&0; の文字列に設定します。  
  
> [!NOTE]
>  コンボ ボックスがドロップダウン リスト ボックスの場合、交換される値は 255 文字に制限されます。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddxcbstringexacta--ddxcbstringexact"></a><a name="ddx_cbstringexact"></a>DDX_CBStringExact  
 `DDX_CBStringExact`関数は、コンテンツの転送を管理`CString` ダイアログ ボックスでは、コンボ ボックス コントロールのエディット コントロールの間でデータ ビュー、またはオブジェクトのフォームと`CString` ダイアログ ボックス、フォーム ビュー、またはオブジェクトのデータ メンバーです。  
  
```  
void AFXAPI DDX_CBStringExact(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 コントロールのプロパティに関連付けられているコンボ ボックス コントロールのリソース ID です。  
  
 *value*  
 ダイアログ ボックス、フォーム ビュー、またはデータを交換するオブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 `DDX_CBStringExact`が呼び出されると、*値*コンボ ボックスの現在の選択に設定されています。 項目が選択されていない場合*値*が長さ&0; の文字列に設定します。  
  
> [!NOTE]
>  コンボ ボックスがドロップダウン リスト ボックスの場合、交換される値は 255 文字に制限されます。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddxchecka--ddxcheck"></a><a name="ddx_check"></a>DDX_Check  
 `DDX_Check`関数は、コンテンツの転送を管理`int` ダイアログ ボックスでチェック ボックス コントロールの間でデータ ビュー、またはオブジェクトのフォームと`int` ダイアログ ボックス、フォーム ビュー、またはオブジェクトのデータ メンバーです。  
  
```  
void AFXAPI DDX_Check(
    CDataExchange* pDX,  
    int nIDC,  
    int& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 コントロールのプロパティに関連付けられているチェック ボックス コントロールのリソース ID です。  
  
 *value*  
 ダイアログ ボックス、フォーム ビュー、またはデータを交換するオブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 `DDX_Check`が呼び出されると、*値*チェック ボックス コントロールの現在の状態に設定されています。 可能な状態の値の一覧は、次を参照してください。 [BM_GETCHECK](http://msdn.microsoft.com/library/windows/desktop/bb775986)で、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]*します。*  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddxcontrola--ddxcontrol"></a><a name="ddx_control"></a>DDX_Control  
 `DDX_Control`関数で指定されたコントロールのサブクラス`nIDC`、ダイアログ ボックス、フォーム ビュー、またはオブジェクトのです。  
  
```  
void AFXAPI DDX_Control(
    CDataExchange* pDX,  
    int nIDC,  
    CWnd& rControl);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトです。  
  
 `nIDC`  
 サブクラス化されたコントロールのリソース ID です。  
  
 *rControl*  
 ダイアログ ボックス、フォーム ビュー、または指定したコントロールに関連するオブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 `pDX`オブジェクトは、フレームワークによって提供されるときに、`DoDataExchange`関数が呼び出されます。 したがって、`DDX_Control`のオーバーライド内でのみ呼び出す必要があります`DoDataExchange`します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddxdatetimectrla--ddxdatetimectrl"></a><a name="ddx_datetimectrl"></a>DDX_DateTimeCtrl  
 `DDX_DateTimeCtrl`関数は、日付と時刻の選択コントロール間の日付/時刻のデータの転送を管理 ( [CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)) いずれかのダイアログ ボックスやフォーム ビューのオブジェクトで、 [CTime](../../atl-mfc-shared/reference/ctime-class.md)または[時刻](../../atl-mfc-shared/reference/coledatetime-class.md) ダイアログ ボックスやフォーム ビューのオブジェクトのデータ メンバーです。  
  
```  
void AFXAPI DDX_DateTimeCtrl(
    CDataExchange* pDX,  
    int nIDC,  
    CTime& value);

void AFXAPI DDX_DateTimeCtrl(
    CDataExchange* pDX,  
    int nIDC,  
    COleDateTime& value);

void AFXAPI DDX_DateTimeCtrl(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。 このオブジェクトを削除する必要はありません。  
  
 `nIDC`  
 メンバー変数に関連付けられた日時指定コントロールのリソース ID です。  
  
 *value*  
 最初の&2; つのバージョンへの参照、`CTime`または`COleDateTime`メンバー変数、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトを使用するには、データを交換します。 3 番目のバージョンへの参照で、`CString`データ メンバーのコントロールのビュー オブジェクト。  
  
### <a name="remarks"></a>コメント  
 `DDX_DateTimeCtrl`が呼び出されると、*値*現在に設定されている日付と日時選択コントロールまたはコントロールの状態に設定されている*値*exchange の方向に応じて、します。  
  
 上記の&3; 番目の形式で`DDX_DateTimeCtrl`の転送を管理`CString`時間コントロールの日付の間でデータと[CString](../../atl-mfc-shared/reference/cstringt-class.md)コントロールのビュー オブジェクトのデータ メンバーです。 日付と時刻の書式設定の現在のロケールの規則を使用して、文字列が書式設定されます。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddxipaddressa--ddxipaddress"></a><a name="ddx_ipaddress"></a>DDX_IPAddress  
 `DDX_IPAddress`関数は、IP アドレス コントロールおよびコントロールのビュー オブジェクトのデータ メンバーの間でデータの転送を管理します。  
  
```  
void AFXAPI DDX_IPAddress(
    CDataExchange* pDX,  
    int nIDC,  
    DWORD& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 コントロールのプロパティに関連付けられている IP アドレス コントロールのリソース ID です。  
  
 *value*  
 参照、 `DWORD` IP アドレス コントロールの&4; つのフィールドの値を格納します。 フィールドは入力または、次のようです。  
  
|フィールド|ビット フィールドの値を含む|  
|-----------|-------------------------------------|  
|3|0 ~ 7|  
|2|8 ~ 15|  
|1|16 ~ 23|  
|0|24 ~ 31|  
  
 Win32 を使用して[IPM_GETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761378)値の読み取りまたは使用[IPM_SETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761380)値を入力します。 これらのメッセージは「、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 `DDX_IPAddress`が呼び出されると、*値*がいずれかから読み取られる IP アドレス コントロールまたは*値*は、exchange の方向に応じて、コントロールに書き込まれます。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddxlbindexa--ddxlbindex"></a><a name="ddx_lbindex"></a>DDX_LBIndex  
 `DDX_LBIndex`関数は、コンテンツの転送を管理`int` ダイアログ ボックスでは、リスト ボックス コントロールの間でデータ ビュー、またはオブジェクトのフォームと`int` ダイアログ ボックス、フォーム ビュー、またはオブジェクトのデータ メンバーです。  
  
```  
void AFXAPI DDX_LBIndex(
    CDataExchange* pDX,  
    int nIDC,  
    int& index);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 コントロール プロパティに関連付けられたリスト ボックス コントロールのリソース ID です。  
  
 *インデックス*  
 ダイアログ ボックス、フォーム ビュー、またはデータを交換するオブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 `DDX_LBIndex`が呼び出されると、*インデックス*リスト ボックスの現在の選択範囲のインデックスに設定されています。 項目が選択されていない場合*インデックス*が-1 に設定します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddxlbstringa--ddxlbstring"></a><a name="ddx_lbstring"></a>DDX_LBString  
 `DDX_LBString`関数は、コンテンツの転送を管理`CString` ダイアログ ボックスでは、リスト ボックス コントロールの間でデータ ビュー、またはオブジェクトのフォームと`CString` ダイアログ ボックス、フォーム ビュー、またはオブジェクトのデータ メンバーです。  
  
```  
void AFXAPI DDX_LBString(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 コントロール プロパティに関連付けられたリスト ボックス コントロールのリソース ID です。  
  
 *value*  
 ダイアログ ボックス、フォーム ビュー、またはデータを交換するオブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 `DDX_LBString`先頭に一致するコントロールの最初の項目のリスト ボックス コントロールにデータを転送するために呼び出される*値*が選択されています。 (プレフィックスだけではなく、すべての行と一致させる場合、 [DDX_LBStringExact](#ddx_lbstringexact))。一致しない場合は、項目が選択されていません。 一致では区別されません。  
  
 `DDX_LBString`リスト ボックス コントロールからデータを転送するために呼び出される*値*が現在のリスト ボックスの選択に設定します。 項目が選択されていない場合*値*が長さ&0; の文字列に設定します。  
  
> [!NOTE]
>  リスト ボックスがドロップダウン リスト ボックスの場合、交換される値は、255 文字までに制限されます。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddxlbstringexacta--ddxlbstringexact"></a><a name="ddx_lbstringexact"></a>DDX_LBStringExact  
 `DDX_CBStringExact`関数は、コンテンツの転送を管理`CString` ダイアログ ボックスでは、リスト ボックス コントロールのエディット コントロールの間でデータ ビュー、またはオブジェクトのフォームと`CString` ダイアログ ボックス、フォーム ビュー、またはオブジェクトのデータ メンバーです。  
  
```  
void AFXAPI DDX_LBStringExact(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 コントロール プロパティに関連付けられたリスト ボックス コントロールのリソース ID です。  
  
 *value*  
 ダイアログ ボックス、フォーム ビュー、またはデータを交換するオブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 `DDX_LBStringExact`と一致するコントロールの最初の項目のリスト ボックス コントロールにデータを転送するために呼び出される*値*が選択されています。 (項目全体ではなくプレフィックスだけを一致する、 [DDX_LBString](#ddx_lbstring))。一致しない場合は、項目が選択されていません。 一致では区別されません。  
  
 `DDX_CBStringExact`リスト ボックス コントロールからデータを転送するために呼び出される*値*が現在のリスト ボックスの選択に設定します。 項目が選択されていない場合*値*が長さ&0; の文字列に設定します。  
  
> [!NOTE]
>  リスト ボックスがドロップダウン リスト ボックスの場合、交換される値は、255 文字までに制限されます。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddxmonthcalctrla--ddxmonthcalctrl"></a><a name="ddx_monthcalctrl"></a>DDX_MonthCalCtrl  
 `DDX_MonthCalCtrl`月間予定表コントロールの間で日付データの転送を管理 ( [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)) ダイアログ ボックス、フォーム ビュー、またはコントロールのビュー オブジェクトのいずれかに、 [CTime](../../atl-mfc-shared/reference/ctime-class.md)または[時刻](../../atl-mfc-shared/reference/coledatetime-class.md) ダイアログ ボックス、フォーム ビュー、またはオブジェクトのデータ メンバーです。  
  
```  
void AFXAPI DDX_MonthCalCtrl(
    CDataExchange* pDX,  
    int nIDC,  
    CTime& value);

void AFXAPI DDX_MonthCalCtrl(
    CDataExchange* pDX,  
    int nIDC,  
    COleDateTime& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。 このオブジェクトを削除する必要はありません。  
  
 `nIDC`  
 月間予定表コントロールのリソース ID は、メンバー変数に関連付けられています。  
  
 *value*  
 参照、`CTime`または`COleDateTime`ダイアログ ボックス、フォーム ビュー、またはデータを交換するオブジェクトのメンバー変数です。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  コントロールは、日付の値のみを管理します。 時刻フィールド時のオブジェクトには、コントロールのウィンドウの作成日時を反映するように設定または任意の時間を設定してあるコントロールへの呼び出しに`CMonthCalCtrl::SetCurSel`します。  
  
 `DDX_MonthCalCtrl`が呼び出されると、*値*月間予定表コントロールの現在の状態に設定されています。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddxradioa--ddxradio"></a><a name="ddx_radio"></a>DDX_Radio  
 `DDX_Radio`関数は、コンテンツの転送を管理`int` ダイアログ ボックスでオプション ボタン コントロールのグループ間でデータ ビュー、またはオブジェクトのフォームと`int` ダイアログ ボックス、フォーム ビュー、またはオブジェクトのデータ メンバーです。 値、`int`どのオプションに従って、グループ内のボタンが選択されているデータ メンバーが決定されます。  
  
```  
void AFXAPI DDX_Radio(
    CDataExchange* pDX,  
    int nIDC,  
    int& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 グループ内の最初のオプション ボタン コントロールのリソース ID です。  
  
 *value*  
 ダイアログ ボックス、フォーム ビュー、またはデータを交換するオブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 `DDX_Radio`が呼び出されると、*値*オプション ボタン コントロールのグループの現在の状態に設定されています。 現在チェックされているオプション ボタン コントロールの 0 から始まるインデックス値を設定またはないオプションのコントロールの場合は-1 をチェックします。  
  
 グループ内の最初のラジオ ボタンである場合 (WS_GROUP スタイルのボタン) の値をオンになって、`int`メンバーが 0 です。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddxscrolla--ddxscroll"></a><a name="ddx_scroll"></a>DDX_Scroll  
 `DDX_Scroll`関数は、コンテンツの転送を管理`int` ダイアログ ボックスでは、スクロール バー コントロールの間でデータ ビュー、またはオブジェクトのフォームと`int` ダイアログ ボックス、フォーム ビュー、またはオブジェクトのデータ メンバーです。  
  
```  
void AFXAPI DDX_Scroll(
    CDataExchange* pDX,  
    int nIDC,  
    int& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 コントロールのプロパティに関連付けられたスクロール バー コントロールのリソース ID です。  
  
 *value*  
 データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 `DDX_Scroll`が呼び出されると、*値*コントロールのスクロール ボックスの現在の位置に設定されています。 コントロールのスクロール ボックスの現在の位置に関連付けられている値の詳細については、次を参照してください。 [GetScrollPos](http://msdn.microsoft.com/library/windows/desktop/bb787585)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddxslidera--ddxslider"></a><a name="ddx_slider"></a>DDX_Slider  
 `DDX_Slider`関数は、コンテンツの転送を管理`int` ダイアログ ボックスやフォーム ビューのスライダー コントロールの間でデータと`int` ダイアログ ボックスやフォーム ビューのオブジェクトのデータ メンバーです。  
  
```  
void AFXAPI DDX_Slider(
    CDataExchange* pDX,  
    int nIDC,  
    int& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 スライダー コントロールのリソース ID です。  
  
 *value*  
 交換する値への参照。 このパラメーターは、スライダー コントロールの現在位置を設定または保持します。  
  
### <a name="remarks"></a>コメント  
 `DDX_Slider`が呼び出されると、*値*コントロールのスクロール ボックスの現在の位置に設定されている値が、exchange の方向に応じたの位置を送受信します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。 スライダー コントロールの概要については、次を参照してください。[を使用して CSliderCtrl](../../mfc/using-csliderctrl.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddxtexta--ddxtext"></a><a name="ddx_text"></a>DDX_Text  
 `DDX_Text`関数は、コンテンツの転送を管理`int`、 **UINT**、**長い**、 `DWORD`、 `CString`、 **float**、または**二重** ダイアログ ボックスでは、エディット コントロールの間でデータがフォーム ビュー、または表示を制御し、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)  ダイアログ ボックス、フォーム ビュー、またはオブジェクトのデータ メンバーです。  
  
```  
void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    BYTE& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    short& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    int& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    UINT& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    long& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    DWORD& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    float& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    double& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    COleCurrency& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    COleDateTime& value);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 ダイアログ ボックス、フォーム ビュー、またはオブジェクトのエディット コントロールの ID です。  
  
 *value*  
 ダイアログ ボックス、フォーム ビュー、またはオブジェクトのデータ メンバーへの参照。 データ型*値*のオーバー ロードされたバージョンのうちに依存`DDX_Text`を使用します。  
  
### <a name="remarks"></a>コメント  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  

### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  

## <a name="see-also"></a>関連項目  
 [標準的なダイアログ データ バリデーション ルーチン](../../mfc/reference/standard-dialog-data-validation-routines.md)   
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

