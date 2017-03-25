---
title: "OLE コントロールのダイアログ データ エクス関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AFXDISP/DDX_OCBool
- AFXDISP/DDX_OCBoolRO
- AFXDISP/DDX_OCColor
- AFXDISP/DDX_OCColorRO
- AFXDISP/DDX_OCFloat
- AFXDISP/DDX_OCFloatRO
- AFXDISP/DDX_OCInt
- AFXDISP/DDX_OCIntRO
- AFXDISP/DDX_OCShort
- AFXDISP/DDX_OCShortRO
- AFXDISP/DDX_OCText
- AFXDISP/DDX_OCTextRO
dev_langs:
- C++
helpviewer_keywords:
- OLE controls, DDX functions
- DDX (dialog data exchange), OLE support
ms.assetid: 7ef1f288-ff65-40d4-aad2-5497bc00bb27
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 5c50690c1652c4136b7f52f852ddf201c9dd6c9b
ms.lasthandoff: 03/17/2017

---
# <a name="dialog-data-exchange-functions-for-ole-controls"></a>OLE コントロールのダイアログ データ エクスチェンジ (DDX) 関数
このトピックでは、OLE コントロールのプロパティ ダイアログ ボックス、フォーム ビュー、またはオブジェクトのデータ メンバーの間でデータを交換するために使用する DDX_OC 関数を示します。  
  
### <a name="ddxoc-functions"></a>DDX_OC 関数  
  
|||  
|-|-|  
|[DDX_OCBool](#ddx_ocbool)|データの転送を管理**BOOL** OLE コントロールのプロパティの間でデータと**BOOL**データ メンバーです。|  
|[DDX_OCBoolRO](#ddx_ocboolro)|データの転送を管理**BOOL** OLE コントロールの読み取り専用プロパティの間でデータと**BOOL**データ メンバーです。|  
|[DDX_OCColor](#ddx_occolor)|データの転送を管理**OLE_COLOR** OLE コントロールのプロパティの間でデータと**OLE_COLOR**データ メンバーです。|  
|[DDX_OCColorRO](#ddx_occolorro)|データの転送を管理**OLE_COLOR** OLE コントロールの読み取り専用プロパティの間でデータと**OLE_COLOR**データ メンバーです。|  
|[DDX_OCFloat](#ddx_ocfloat)|データの転送を管理**float** (または**二重**) OLE コントロールのプロパティの間でデータと**float** (または**二重**) データ メンバーです。|  
|[DDX_OCFloatRO](#ddx_ocfloatro)|データの転送を管理**float** (または**二重**) OLE コントロールの読み取り専用プロパティの間でデータと**float** (または**二重**) データ メンバーです。|  
|[DDX_OCInt](#ddx_ocint)|データの転送を管理`int`(または**長い**) OLE コントロールのプロパティの間でデータと`int`(または**長い**) データ メンバーです。|  
|[DDX_OCIntRO](#ddx_ocintro)|データの転送を管理`int`(または**長い**) OLE コントロールの読み取り専用プロパティの間でデータと`int`(または**長い**) データ メンバーです。|  
|[DDX_OCShort](#ddx_ocshort)|データの転送を管理**短い**OLE コントロールのプロパティの間でデータと**短い**データ メンバーです。|  
|[DDX_OCShortRO](#ddx_ocshortro)|データの転送を管理**短い**OLE コントロールの読み取り専用プロパティの間でデータと**短い**データ メンバーです。|  
|[DDX_OCText](#ddx_octext)|データの転送を管理**CString** OLE コントロールのプロパティの間でデータと**CString**データ メンバーです。|  
|[DDX_OCTextRO](#ddx_octextro)|データの転送を管理**CString** OLE コントロールの読み取り専用プロパティの間でデータと**CString**データ メンバーです。|  
  
##  <a name="ddx_ocbool"></a>DDX_OCBool  
 `DDX_OCBool`関数は、コンテンツの転送を管理**BOOL**  ダイアログ ボックスでは、OLE コントロールのプロパティの間でデータ ビュー、またはオブジェクトのフォームと**BOOL**  ダイアログ ボックス、フォーム ビュー、またはオブジェクトのデータ メンバーです。  
  
```   
void AFXAPI DDX_OCBool(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    BOOL& value);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。  
  
 `dispid`  
 コントロールのプロパティのディスパッチ ID。  
  
 *value*  
 データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー :** afxdisp.h  
  
##  <a name="ddx_ocboolro"></a>DDX_OCBoolRO  
 `DDX_OCBoolRO`関数は、コンテンツの転送を管理**BOOL**  ダイアログ ボックスでは、OLE コントロールの読み取り専用プロパティの間でデータ ビュー、またはオブジェクトのフォームと**BOOL**  ダイアログ ボックス、フォーム ビュー、またはオブジェクトのデータ メンバーです。  
  
```   
void AFXAPI DDX_OCBoolRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    BOOL& value);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。  
  
 `dispid`  
 コントロールのプロパティのディスパッチ ID。  
  
 *value*  
 データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="ddx_occolor"></a>DDX_OCColor  
 `DDX_OCColor`関数は、コンテンツの転送を管理**OLE_COLOR**  ダイアログ ボックスでは、OLE コントロールのプロパティの間でデータ ビュー、またはオブジェクトのフォームと**OLE_COLOR**  ダイアログ ボックス、フォーム ビュー、またはオブジェクトのデータ メンバーです。  
  
```   
void AFXAPI DDX_OCColor(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    OLE_COLOR& value);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。  
  
 `dispid`  
 コントロールのプロパティのディスパッチ ID。  
  
 *value*  
 データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="ddx_occolorro"></a>DDX_OCColorRO  
 `DDX_OCColorRO`関数は、コンテンツの転送を管理**OLE_COLOR**  ダイアログ ボックスでは、OLE コントロールの読み取り専用プロパティの間でデータ ビュー、またはオブジェクトのフォームと**OLE_COLOR**  ダイアログ ボックス、フォーム ビュー、またはオブジェクトのデータ メンバーです。  
  
```   
void AFXAPI DDX_OCColorRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    OLE_COLOR& value);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。  
  
 `dispid`  
 コントロールのプロパティのディスパッチ ID。  
  
 *value*  
 データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="ddx_ocfloat"></a>DDX_OCFloat  
 `DDX_OCFloat`関数は、コンテンツの転送を管理**float** (または**二重**) ダイアログ ボックスでは、OLE コントロールのプロパティの間でデータ ビュー、またはオブジェクトのフォームと**float** (または**二重**) ダイアログ ボックス、フォーム ビュー、またはオブジェクトのデータ メンバーです。  
  
```   
void AFXAPI DDX_OCFloat(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    float& value);

void AFXAPI DDX_OCFloat(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    double& value);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。  
  
 `dispid`  
 コントロールのプロパティのディスパッチ ID。  
  
 *value*  
 データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="ddx_ocfloatro"></a>DDX_OCFloatRO  
 `DDX_OCFloatRO`関数は、コンテンツの転送を管理**float** (または**二重**) ダイアログ ボックスでは、OLE コントロールの読み取り専用プロパティの間でデータ ビュー、またはオブジェクトのフォームと**float** (または**二重**) ダイアログ ボックス、フォーム ビュー、またはオブジェクトのデータ メンバーです。  
  
```   
void AFXAPI DDX_OCFloatRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    float& value);

void AFXAPI DDX_OCFloatRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    double& value);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。  
  
 `dispid`  
 コントロールのプロパティのディスパッチ ID。  
  
 *value*  
 データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="ddx_ocint"></a>DDX_OCInt  
 `DDX_OCInt`関数は、コンテンツの転送を管理`int`(または**長い**) ダイアログ ボックスでは、OLE コントロールのプロパティの間でデータ ビュー、またはオブジェクトのフォームと`int`(または**長い**) ダイアログ ボックス、フォーム ビュー、またはオブジェクトのデータ メンバーです。  
  
```   
void AFXAPI DDX_OCInt(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    int& value);

void AFXAPI DDX_OCInt(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    long& value);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。  
  
 `dispid`  
 コントロールのプロパティのディスパッチ ID。  
  
 *value*  
 データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="ddx_ocintro"></a>DDX_OCIntRO  
 `DDX_OCIntRO`関数は、コンテンツの転送を管理`int`(または**長い**) ダイアログ ボックスでは、OLE コントロールの読み取り専用プロパティの間でデータ ビュー、またはオブジェクトのフォームと`int`(または**長い**) ダイアログ ボックス、フォーム ビュー、またはオブジェクトのデータ メンバーです。  
  
```   
void AFXAPI DDX_OCIntRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    int& value);

void AFXAPI DDX_OCIntRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    long& value);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。  
  
 `dispid`  
 コントロールのプロパティのディスパッチ ID。  
  
 *value*  
 データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="ddx_ocshort"></a>DDX_OCShort  
 `DDX_OCShort`関数は、ダイアログ ボックスで、フォーム ビューでの OLE コントロールのプロパティ間の短いデータの転送を管理またはフォーム ビュー、オブジェクトと、ダイアログ ボックスの短いデータ メンバー、またはオブジェクトの表示を制御します。  
  
```   
void AFXAPI DDX_OCShort(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    short& value);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。  
  
 `dispid`  
 コントロールのプロパティのディスパッチ ID。  
  
 *value*  
 データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="ddx_ocshortro"></a>DDX_OCShortRO  
 `DDX_OCShortRO`関数は、読み取り専用のプロパティ ダイアログ ボックスで、フォーム ビューの OLE コントロールの間の短いデータの転送を管理またはフォーム ビュー、オブジェクトと、ダイアログ ボックスの短いデータ メンバー、またはオブジェクトの表示を制御します。  
  
```   
void AFXAPI DDX_OCShortRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    short& value);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。  
  
 `dispid`  
 コントロールのプロパティのディスパッチ ID。  
  
 *value*  
 データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="ddx_octext"></a>DDX_OCText  
 **DDX_OCText**関数は、コンテンツの転送を管理**CString**  ダイアログ ボックスでは、OLE コントロールのプロパティの間でデータ ビュー、またはオブジェクトのフォームと**CString**  ダイアログ ボックス、フォーム ビュー、またはオブジェクトのデータ メンバーです。  
  
```   
void AFXAPI DDX_OCText(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    CString& value); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 **CDataExchange**オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。  
  
 `dispid`  
 コントロールのプロパティのディスパッチ ID。  
  
 *value*  
 データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="ddx_octextro"></a>DDX_OCTextRO  
 `DDX_OCTextRO` 関数は、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの読み取り専用プロパティと、ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの `CString` データ メンバーの間の `CString` データ転送を管理します。  
  
```  
void AFXAPI DDX_OCTextRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    CString& value); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 ダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトの OLE コントロールの ID。  
  
 `dispid`  
 コントロールのプロパティのディスパッチ ID。  
  
 *value*  
 データの交換相手になるダイアログ ボックス、フォーム ビュー、またはコントロール ビュー オブジェクトのメンバー変数への参照。  
  
### <a name="remarks"></a>コメント  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  

### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h
    
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

