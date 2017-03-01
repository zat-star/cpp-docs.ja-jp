---
title: "プロパティ ページ (MFC) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- property page data transfer functions in MFC
- property pages, global MFC functions
ms.assetid: 734f88bc-c776-4136-9b0e-f45c761a45c1
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
ms.openlocfilehash: 50888697fe01d3a84d9aa4c6f5f92926e4681535
ms.lasthandoff: 02/24/2017

---
# <a name="property-pages-mfc"></a>プロパティ ページ (MFC)
プロパティ ページでは、表示および編集ダイアログ データ エクス (チェンジ DDX) に基づくデータ マッピング メカニズムをサポートすることで、カスタマイズ可能なグラフィカル インターフェイスで特定の OLE コントロール プロパティの現在の値を表示します。  
  
 このデータ マッピング メカニズムでは、OLE コントロールの個々 のプロパティをプロパティ ページのコントロールをマップします。 コントロールのプロパティの値には、ステータスやプロパティ ページのコントロールの内容が反映されます。 プロパティ ページのコントロールとプロパティ間のマッピングがで指定された**ddp _**関数呼び出しにプロパティ ページの`DoDataExchange`メンバー関数。 次の一覧は、 **ddp _**コントロールのプロパティ ページを使用して入力データを交換する関数。  
  
### <a name="property-page-data-transfer"></a>プロパティ ページのデータ転送  
  
|||  
|-|-|  
|[DDP_CBIndex](#ddp_cbindex)|コントロールのプロパティを持つコンボ ボックスで選択した文字列のインデックスをリンクします。|  
|[DDP_CBString](#ddp_cbstring)|コントロールのプロパティを持つコンボ ボックスで選択された文字列をリンクします。 選択した文字列は、プロパティの値と同じ文字で始まることができますが、完全に一致する必要はありません。|  
|[DDP_CBStringExact](#ddp_cbstringexact)|コントロールのプロパティを持つコンボ ボックスで選択された文字列をリンクします。 選択した文字列と、このプロパティの文字列値が正確に一致する必要があります。|  
|[DDP_Check](#ddp_check)|コントロールのプロパティを使用して、コントロールのプロパティ ページでチェック ボックスをリンクします。|  
|[DDP_LBIndex](#ddp_lbindex)|コントロールのプロパティを使用してリスト ボックスで選択した文字列のインデックスをリンクします。|  
|[DDP_LBString](#ddp_lbstring)|コントロールのプロパティを使用してリスト ボックスで選択された文字列をリンクします。 選択した文字列は、プロパティの値と同じ文字で始まることができますが、一致しなくても、完全に。|  
|[DDP_LBStringExact](#ddp_lbstringexact)|コントロールのプロパティを使用してリスト ボックスで選択された文字列をリンクします。 選択した文字列と、このプロパティの文字列値が正確に一致する必要があります。|  
|[DDP_PostProcessing](#ddp_postprocessing)|コントロールからプロパティ値の転送を完了します。|  
|[DDP_Radio](#ddp_radio)|リンク コントロールのプロパティを使用して、コントロールのプロパティ ページのオプション ボタン グループです。|  
|[DDP_Text](#ddp_text)|コントロールのプロパティを使用して、コントロールのプロパティ ページのコントロールにリンクします。 この関数はさまざまな種類のプロパティの処理など**二重**、**短い**、 `BSTR`、および**長い**します。|  
  
 詳細については、`DoDataExchange`関数やプロパティ ページでは、記事を参照して[ActiveX コントロール: プロパティ ページ](../../mfc/mfc-activex-controls-property-pages.md)します。  
  
 作成し、OLE コントロールのプロパティ ページの管理に使用されるマクロの一覧を次に示します。  
  
### <a name="property-pages"></a>プロパティ ページ  
  
|||  
|-|-|  
|[BEGIN_PROPPAGEIDS](#begin_proppageids)|プロパティ ページ Id のリストを開始します。|  
|[END_PROPPAGEIDS](#end_proppageids)|プロパティ ページ Id の一覧を終了します。|  
|[PROPPAGEID](#proppageid)|コントロール クラスのプロパティ ページを宣言します。|  
  
##  <a name="a-nameddpcbindexa--ddpcbindex"></a><a name="ddp_cbindex"></a>DDP_CBIndex  
 プロパティ ページの この関数を呼び出す`DoDataExchange`プロパティ ページにあるコンボ ボックスの現在の選択項目のインデックスの整数型のプロパティの値を同期する関数。  
  
```   
void AFXAPI DDP_CBIndex(
    CDataExchange* pDX,  
    int id,  
    int& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、`CDataExchange`オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `id`  
 コンボ ボックスのリソース ID で指定されたコントロール プロパティに関連付けられたコントロールのボックス`pszPropName`します。  
  
 `member`  
 指定されたプロパティ ページのコントロールに関連付けられているメンバー変数`id`で指定されたプロパティと`pszPropName`です。  
  
 `pszPropName`  
 指定されたコンボ ボックス コントロールと交換するコントロール プロパティのプロパティ名`id`します。  
  
### <a name="remarks"></a>コメント  
 この関数は、対応する前に呼び出す必要があります`DDX_CBIndex`関数の呼び出しです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="a-nameddpcbstringa--ddpcbstring"></a><a name="ddp_cbstring"></a>DDP_CBString  
 プロパティ ページの この関数を呼び出す`DoDataExchange`文字列プロパティの値をプロパティ ページにあるコンボ ボックスの現在の選択と同期します。  
  
```  
void AFXAPI DDP_CBString(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、`CDataExchange`オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `id`  
 コンボ ボックスのリソース ID で指定されたコントロール プロパティに関連付けられたコントロールのボックス`pszPropName`します。  
  
 `member`  
 指定されたプロパティ ページのコントロールに関連付けられているメンバー変数`id`で指定されたプロパティと`pszPropName`です。  
  
 `pszPropName`  
 指定されたコンボ ボックスの文字列と交換するコントロール プロパティのプロパティ名`id`します。  
  
### <a name="remarks"></a>コメント  
 この関数は、対応する前に呼び出す必要があります`DDX_CBString`関数の呼び出しです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="a-nameddpcbstringexacta--ddpcbstringexact"></a><a name="ddp_cbstringexact"></a>DDP_CBStringExact  
 プロパティ ページの この関数を呼び出す`DoDataExchange`プロパティ ページにあるコンボ ボックスの現在の選択内容を正確に一致する文字列プロパティの値を同期する関数。  
  
```  
void AFXAPI DDP_CBStringExact(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、`CDataExchange`オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `id`  
 コンボ ボックスのリソース ID で指定されたコントロール プロパティに関連付けられたコントロールのボックス`pszPropName`します。  
  
 `member`  
 指定されたプロパティ ページのコントロールに関連付けられているメンバー変数`id`で指定されたプロパティと`pszPropName`です。  
  
 `pszPropName`  
 指定されたコンボ ボックスの文字列と交換するコントロール プロパティのプロパティ名`id`します。  
  
### <a name="remarks"></a>コメント  
 この関数は、対応する前に呼び出す必要があります`DDX_CBStringExact`関数の呼び出しです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="a-nameddpchecka--ddpcheck"></a><a name="ddp_check"></a>DDP_Check  
 プロパティ ページの [この関数を呼び出す`DoDataExchange`関連付けられたプロパティ ページ] チェック ボックス コントロールとプロパティの値を同期する関数。  
  
```   
void AFXAPI DDP_Check(
    CDataExchange* pDX,  
    int id,  
    int & member,  
    LPCSTR pszPropName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、`CDataExchange`オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `id`  
 指定されたコントロール プロパティに関連付けられているチェック ボックス コントロールのリソース ID`pszPropName`します。  
  
 `member`  
 指定されたプロパティ ページのコントロールに関連付けられているメンバー変数`id`で指定されたプロパティと`pszPropName`です。  
  
 `pszPropName`  
 指定された チェック ボックス コントロールと交換するコントロール プロパティのプロパティ名`id`します。  
  
### <a name="remarks"></a>コメント  
 この関数は、対応する前に呼び出す必要があります`DDX_Check`関数の呼び出しです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="a-nameddplbindexa--ddplbindex"></a><a name="ddp_lbindex"></a>DDP_LBIndex  
 プロパティ ページの この関数を呼び出す`DoDataExchange`プロパティ ページにあるリスト ボックスの現在の選択項目のインデックスの整数型のプロパティの値を同期する関数。  
  
```   
void AFXAPI DDP_LBIndex(
    CDataExchange* pDX,  
    int id,  
    int& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、`CDataExchange`オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `id`  
 リストのリソース ID で指定されたコントロール プロパティに関連付けられたコントロールのボックス`pszPropName`します。  
  
 `member`  
 指定されたプロパティ ページのコントロールに関連付けられているメンバー変数`id`で指定されたプロパティと`pszPropName`です。  
  
 `pszPropName`  
 指定されたリスト ボックスの文字列と交換するコントロール プロパティのプロパティ名`id`します。  
  
### <a name="remarks"></a>コメント  
 この関数は、対応する前に呼び出す必要があります`DDX_LBIndex`関数の呼び出しです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="a-nameddplbstringa--ddplbstring"></a><a name="ddp_lbstring"></a>DDP_LBString  
 プロパティ ページの この関数を呼び出す`DoDataExchange`文字列プロパティの値をプロパティ ページにあるリスト ボックスの現在の選択と同期します。  
  
```   
void AFXAPI DDP_LBString(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、`CDataExchange`オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `id`  
 リストのリソース ID で指定されたコントロール プロパティに関連付けられたコントロールのボックス`pszPropName`します。  
  
 `member`  
 指定されたプロパティ ページのコントロールに関連付けられているメンバー変数`id`で指定されたプロパティと`pszPropName`です。  
  
 `pszPropName`  
 指定されたリスト ボックスの文字列と交換するコントロール プロパティのプロパティ名`id`します。  
  
### <a name="remarks"></a>コメント  
 この関数は、対応する前に呼び出す必要があります`DDX_LBString`関数の呼び出しです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="a-nameddplbstringexacta--ddplbstringexact"></a><a name="ddp_lbstringexact"></a>DDP_LBStringExact  
 プロパティ ページの この関数を呼び出す`DoDataExchange`プロパティ ページにあるリスト ボックスの現在の選択内容を正確に一致する文字列プロパティの値を同期する関数。  
  
```   
void AFXAPI DDP_LBStringExact(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、`CDataExchange`オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `id`  
 リストのリソース ID で指定されたコントロール プロパティに関連付けられたコントロールのボックス`pszPropName`します。  
  
 `member`  
 指定されたプロパティ ページのコントロールに関連付けられているメンバー変数`id`で指定されたプロパティと`pszPropName`です。  
  
 `pszPropName`  
 指定されたリスト ボックスの文字列と交換するコントロール プロパティのプロパティ名`id`します。  
  
### <a name="remarks"></a>コメント  
 この関数は、対応する前に呼び出す必要があります`DDX_LBStringExact`関数の呼び出しです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="a-nameddppostprocessinga--ddppostprocessing"></a><a name="ddp_postprocessing"></a>DDP_PostProcessing  
 プロパティ ページの この関数を呼び出す`DoDataExchange`関数、プロパティの値は、保存されているときに、プロパティ ページから、コントロールへのプロパティの値の転送を完了します。  
  
```   
void AFXAPI DDP_PostProcessing(CDataExchange * pDX);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、`CDataExchange`オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
### <a name="remarks"></a>コメント  
 すべてのデータ交換関数が完了した後、この関数を呼び出す必要があります。 例:  
  
 [!code-cpp[NVC_MFCAxCtl&#15;](../../mfc/reference/codesnippet/cpp/property-pages-mfc_1.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="a-nameddpradioa--ddpradio"></a><a name="ddp_radio"></a>DDP_Radio  
 コントロールのこの関数を呼び出す`DoPropExchange`関連付けられたプロパティ ページのオプション ボタン コントロールとプロパティの値を同期する関数。  
  
```   
void AFXAPI DDP_Radio(
    CDataExchange* pDX,  
    int id,  
    int & member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、`CDataExchange`オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `id`  
 無線のリソース ID で指定されたコントロール プロパティに関連付けられたコントロールのボタン`pszPropName`します。  
  
 `member`  
 指定されたプロパティ ページのコントロールに関連付けられているメンバー変数`id`で指定されたプロパティと`pszPropName`です。  
  
 `pszPropName`  
 指定したオプション ボタン コントロールと交換するコントロール プロパティのプロパティ名`id`します。  
  
### <a name="remarks"></a>コメント  
 この関数は、対応する前に呼び出す必要があります`DDX_Radio`関数の呼び出しです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="a-nameddptexta--ddptext"></a><a name="ddp_text"></a>DDP_Text  
 コントロールのこの関数を呼び出す`DoDataExchange`関連付けられたプロパティ ページのコントロールとプロパティの値を同期する関数。  
  
```   
void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    BYTE & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    int & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    UINT & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    long & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    DWORD & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    float & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    double & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    CString & member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、`CDataExchange`オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `id`  
 指定されたコントロール プロパティに関連付けられたコントロールのリソース ID`pszPropName`します。  
  
 `member`  
 指定されたプロパティ ページのコントロールに関連付けられているメンバー変数`id`で指定されたプロパティと`pszPropName`です。  
  
 `pszPropName`  
 指定されたコントロールと交換するコントロール プロパティのプロパティ名`id`します。  
  
### <a name="remarks"></a>コメント  
 この関数は、対応する前に呼び出す必要があります`DDX_Text`関数の呼び出しです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="a-namebeginproppageidsa--beginproppageids"></a><a name="begin_proppageids"></a>BEGIN_PROPPAGEIDS  
 コントロールのプロパティ ページ Id のリストの定義を開始します。  
  
```   
BEGIN_PROPPAGEIDS(class_name,  count)   
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 プロパティ ページが指定されているコントロール クラスの名前。  
  
 *count*  
 コントロール クラスによって使用されるプロパティ ページの数。  
  
### <a name="remarks"></a>コメント  
 クラスのメンバー関数を定義する実装 (.cpp) ファイルでのプロパティ ページの一覧を開始、`BEGIN_PROPPAGEIDS`マクロの各プロパティ ページで、マクロのエントリを追加し、しし、プロパティ ページの一覧で、`END_PROPPAGEIDS`マクロです。  
  
 プロパティ ページの詳細については、記事を参照してください。 [ActiveX コントロール: プロパティ ページ](../../mfc/mfc-activex-controls-property-pages.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="a-nameendproppageidsa--endproppageids"></a><a name="end_proppageids"></a>END_PROPPAGEIDS  
 プロパティ ページの ID のリストの定義を終了します。  
  
```   
END_PROPPAGEIDS(class_name)   
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 プロパティ ページを所有するコントロール クラスの名前。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="a-nameproppageida--proppageid"></a><a name="proppageid"></a>PROPPAGEID  
 OLE コントロールで使用するためのプロパティ ページを追加します。  
  
```   
PROPPAGEID(clsid)   
```  
  
### <a name="parameters"></a>パラメーター  
 `clsid`  
 プロパティ ページの一意のクラス ID。  
  
### <a name="remarks"></a>コメント  
 すべて`PROPPAGEID`マクロは、間に配置する必要があります、`BEGIN_PROPPAGEIDS`と`END_PROPPAGEIDS`コントロールの実装ファイル内のマクロです。  

### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
    
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

