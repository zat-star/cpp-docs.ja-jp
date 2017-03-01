---
title: "CRecordView と CDaoRecordView のダイアログ データ エクス関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.data
dev_langs:
- C++
helpviewer_keywords:
- DDX_Field functions
- ODBC [C++], dialog data exchange (DDX) support
- DDX (dialog data exchange) [C++], database support
- DDX (dialog data exchange) [C++], functions
- databases [C++], dialog data exchange (DDX) support
- DAO [C++], dialog data exchange (DDX) support
ms.assetid: 0d8cde38-3a2c-4100-9589-ac80a7b1ce91
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
ms.openlocfilehash: 682c845aa2c915be69aee0d5e95f820573cd6084
ms.lasthandoff: 02/24/2017

---
# <a name="dialog-data-exchange-functions-for-crecordview-and-cdaorecordview"></a>CRecordView と CDaoRecordView のダイアログ データ エクスチェンジ (DDX) 関数
このトピックの一覧の間でデータを交換するために使用 DDX_Field 関数、 [CRecordset](../../mfc/reference/crecordset-class.md)と[CRecordView](../../mfc/reference/crecordview-class.md)フォームまたは[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フォームです。  
  
> [!NOTE]
>  DDX_Field 関数は、DDX 関数と同様に、フォームのコントロールにデータを交換します。 DDX とは異なり、レコード ビュー自体のフィールドではなく、ビューの関連するレコード セット オブジェクトのフィールドでデータを交換します。 詳細については、クラスを参照してください。`CRecordView`と`CDaoRecordView`です。  
  
### <a name="ddxfield-functions"></a>DDX_Field 関数  
  
|||  
|-|-|  
|[DDX_FieldCBIndex](#ddx_fieldcbindex)|レコード セット フィールド データ メンバーと、現在の選択コンボ ボックス内のインデックスの間で整数データ転送、 [CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)します。|  
|[DDX_FieldCBString](#ddx_fieldcbstring)|転送`CString`コンボのエディット コントロールとレコード セット フィールド データ メンバーの間でデータのボックスに、`CRecordView`または`CDaoRecordView`です。 レコード セットからコントロールにデータを移動する場合、この関数は、指定した文字列内の文字で始まるコンボ ボックスで項目を選択します。|  
|[DDX_FieldCBStringExact](#ddx_fieldcbstringexact)|転送`CString`コンボのエディット コントロールとレコード セット フィールド データ メンバーの間でデータのボックスに、`CRecordView`または`CDaoRecordView`です。 レコード セットからコントロールにデータを移動する場合、この関数は、指定した文字列を正確に一致するコンボ ボックスで項目を選択します。|  
|[DDX_FieldCheck](#ddx_fieldcheck)|レコード セット フィールド データ メンバーとのチェック ボックス間でのブール型のデータの転送、`CRecordView`または`CDaoRecordView`です。|  
|[DDX_FieldLBIndex](#ddx_fieldlbindex)|レコード セット フィールド データ メンバーと、リスト ボックスで現在の選択範囲のインデックスの間で整数データ転送、`CRecordView`または`CDaoRecordView`です。|  
|[DDX_FieldLBString](#ddx_fieldlbstring)|データの転送を管理[CString](../../atl-mfc-shared/reference/cstringt-class.md)リスト ボックス コントロールとレコード セットのフィールド データ メンバーの間のデータです。 レコード セットからコントロールにデータを移動する場合、この関数は、指定した文字列内の文字で始まるリスト ボックスで、項目を選択します。|  
|[DDX_FieldLBStringExact](#ddx_fieldlbstringexact)|データの転送を管理`CString`リスト ボックス コントロールとレコード セットのフィールド データ メンバーの間のデータです。 レコード セットからコントロールにデータを移動する場合、この関数は、指定した文字列を正確に一致する最初の項目を選択します。|  
|[DDX_FieldRadio](#ddx_fieldradio)|レコード セット フィールド データ メンバーとのラジオ ボタンのグループ間で整数型のデータを転送する`CRecordView`または`CDaoRecordView`です。|  
|[DDX_FieldScroll](#ddx_fieldscroll)|スクロール バー コントロールのスクロール位置を取得または設定、`CRecordView`または`CDaoRecordView`です。 呼び出し、 [DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange)関数です。|  
|[DDX_FieldText](#ddx_fieldtext)|オーバー ロードされたバージョンが転送するために使用できる`int`、 **UINT**、**長い**、 `DWORD`、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)、 **float**、 **double**、**短い**、[時刻](../../atl-mfc-shared/reference/coledatetime-class.md)、および[COleCurrency](../../mfc/reference/colecurrency-class.md)レコード セット フィールド データ メンバーと編集の間でデータのボックスに、`CRecordView`または`CDaoRecordView`です。|  
  
##  <a name="a-nameddxfieldcbindexa--ddxfieldcbindex"></a><a name="ddx_fieldcbindex"></a>DDX_FieldCBIndex  
 `DDX_FieldCBIndex`関数は、レコード ビュー内のコンボ ボックス コントロールのリスト ボックス コントロールで選択した項目のインデックスを同期し、`int`レコード ビューに関連付けられているレコード セットのフィールド データ メンバーです。  
  
```  
void AFXAPI DDX_FieldCBIndex(
    CDataExchange* pDX,    
    int nIDC,   
    int& index,  
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBIndex(
    CDataExchange* pDX,    
    int nIDC,   
    int& index,  
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 内のコントロールの ID、 [CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクトです。  
  
 *インデックス*  
 関連付けられたフィールドのデータ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクトです。  
  
 `pRecordset`  
 ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを使用するには、データを交換します。  
  
### <a name="remarks"></a>コメント  
 レコード セットからコントロールにデータを移動する場合に指定された値に基づいてコントロールの選択範囲を設定します*インデックス*します。 レコード セットからコントロールへの転送にレコード セット フィールドが Null の場合 MFC 設定インデックスの値を 0 にします。 コントロールからレコード セットへの転送時にコントロールが空の場合、または項目が選択されていない場合は、レコード セット フィールドは 0 に設定します。  
  
 ODBC ベースのクラスを使用している場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用している場合は、2 番目のバージョンを使用します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールド、記事を参照して[レコード ビュー](../../data/record-views-mfc-data-access.md)します。  
  
### <a name="example"></a>例  
 参照してください[DDX_FieldText](#ddx_fieldtext)全般 DDX_Field などです。 この例はのようになります`DDX_FieldCBIndex`します。  

### <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  

##  <a name="a-nameddxfieldcbstringa--ddxfieldcbstring"></a><a name="ddx_fieldcbstring"></a>DDX_FieldCBString  
 `DDX_FieldCBString`関数は、コンテンツの転送を管理[CString](../../atl-mfc-shared/reference/cstringt-class.md)レコード ビュー内のコンボ ボックス コントロールのエディット コントロールの間でデータと`CString`レコード ビューに関連付けられているレコード セットのフィールド データ メンバーです。  
  
```  
void AFXAPI DDX_FieldCBString(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBString(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 内のコントロールの ID、 [CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクトです。  
  
 *value*  
 関連付けられたフィールドのデータ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクトです。  
  
 `pRecordset`  
 ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを使用するには、データを交換します。  
  
### <a name="remarks"></a>コメント  
 レコード セットからコントロールにデータを移動する場合に指定された文字列内の文字で始まる最初の行にコンボ ボックスの現在の選択範囲を設定します*値*です。 レコード セットから、コントロールへの転送時にレコード セット フィールドが Null の場合は、コンボ ボックスからの選択は解除し、コンボ ボックスのエディット コントロールの設定を空にします。 コントロールからレコード セットへの転送時にコントロールが空である場合、レコード セット フィールドは Null に設定フィールドが許可している場合。  
  
 ODBC ベースのクラスを使用している場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用している場合は、2 番目のバージョンを使用します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールド、記事を参照して[レコード ビュー](../../data/record-views-mfc-data-access.md)します。  
  
### <a name="example"></a>例  
 参照してください[DDX_FieldText](#ddx_fieldtext)全般 DDX_Field などです。 この例では呼び出しを`DDX_FieldCBString`します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdao.h  
  
## <a name="a-nameddxfieldcbstringexacta--ddxfieldcbstringexact"></a><a name="ddx_fieldcbstringexact"></a>DDX_FieldCBStringExact  
 `DDX_FieldCBStringExact`関数は、コンテンツの転送を管理[CString](../../atl-mfc-shared/reference/cstringt-class.md)レコード ビュー内のコンボ ボックス コントロールのエディット コントロールの間でデータと`CString`レコード ビューに関連付けられているレコード セットのフィールド データ メンバーです。  
  
```  
void AFXAPI DDX_FieldCBStringExact(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBStringExact(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 内のコントロールの ID、 [CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクトです。  
  
 *value*  
 関連付けられたフィールドのデータ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクトです。  
  
 `pRecordset`  
 ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを使用するには、データを交換します。  
  
### <a name="remarks"></a>コメント  
 レコード セットからコントロールにデータを移動する場合に指定された文字列を正確に一致する最初の行にコンボ ボックスの現在の選択範囲を設定します*値*です。 レコード セットから、コントロールへの転送時にレコード セット フィールドが NULL の場合は、コンボ ボックスからの選択は解除し、コンボ ボックスの編集ボックスの設定を空にします。 コントロールからレコード セットへの転送時に、コントロールが空である場合は、レコード セット フィールドは NULL に設定します。  
  
 ODBC ベースのクラスを使用している場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用している場合は、2 番目のバージョンを使用します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールド、記事を参照して[レコード ビュー](../../data/record-views-mfc-data-access.md)します。  
  
### <a name="example"></a>例  
 参照してください[DDX_FieldText](#ddx_fieldtext)全般 DDX_Field などです。 呼び出す`DDX_FieldCBStringExact`ようになります。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdao.h  
  
##  <a name="a-nameddxfieldchecka--ddxfieldcheck"></a><a name="ddx_fieldcheck"></a>DDX_FieldCheck  
 `DDX_FieldCheck`関数は、コンテンツの転送を管理`int` ダイアログ ボックスでチェック ボックス コントロールの間でデータ ビュー、またはオブジェクトのフォームと`int` ダイアログ ボックス、フォーム ビュー、またはオブジェクトのデータ メンバーです。  
  
```  
void AFXAPI DDX_FieldCheck(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCheck(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 コントロールのプロパティに関連付けられているチェック ボックス コントロールのリソース ID です。  
  
 *value*  
 ダイアログ ボックス、フォーム ビューまたは使用するには、データを交換オブジェクトのメンバー変数への参照。  
  
 `pRecordset`  
 ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを使用するには、データを交換します。  
  
### <a name="remarks"></a>コメント  
 ときに`DDX_FieldCheck`が呼び出されると、*値* チェック ボックス コントロールの現在の状態に設定されているコントロールの状態に設定されている、または*値*転送の方向に応じて、します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdao.h  
  
##  <a name="a-nameddxfieldlbindexa--ddxfieldlbindex"></a><a name="ddx_fieldlbindex"></a>DDX_FieldLBIndex  
 `DDX_FieldLBIndex`関数は、レコード ビュー内のリスト ボックス コントロールで選択した項目のインデックスを同期し、`int`レコード ビューに関連付けられているレコード セットのフィールド データ メンバーです。  
  
```  
void AFXAPI DDX_FieldLBIndex(
    CDataExchange* pDX,    
    int nIDC,   
    int& index,  
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBIndex(
    CDataExchange* pDX,    
    int nIDC,   
    int& index,  
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 内のコントロールの ID、 [CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクトです。  
  
 *インデックス*  
 関連付けられたフィールドのデータ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクトです。  
  
 `pRecordset`  
 ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを使用するには、データを交換します。  
  
### <a name="remarks"></a>コメント  
 レコード セットからコントロールにデータを移動する場合に指定された値に基づいてコントロールの選択範囲を設定します*インデックス*します。 レコード セットからコントロールへの転送にレコード セット フィールドが Null の場合 MFC 設定インデックスの値を 0 にします。 コントロールからレコード セットへの転送時に、コントロールが空である場合は、レコード セット フィールドは 0 に設定します。  
  
 ODBC ベースのクラスを使用している場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用している場合は、2 番目のバージョンを使用します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールド、記事を参照して[レコード ビュー](../../data/record-views-mfc-data-access.md)します。  
  
### <a name="example"></a>例  
 参照してください[DDX_FieldText](#ddx_fieldtext)全般 DDX_Field などです。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdao.h  
  
##  <a name="a-nameddxfieldlbstringa--ddxfieldlbstring"></a><a name="ddx_fieldlbstring"></a>DDX_FieldLBString  
 `DDX_FieldLBString`にレコード ビュー内のリスト ボックス コントロールの現在の選択部分をコピー、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)レコード ビューに関連付けられているレコード セットのフィールド データ メンバーです。  
  
```  
void AFXAPI DDX_FieldLBString(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBString(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 内のコントロールの ID、 [CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクトです。  
  
 *value*  
 関連付けられたフィールドのデータ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクトです。  
  
 `pRecordset`  
 ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを使用するには、データを交換します。  
  
### <a name="remarks"></a>コメント  
 逆方向にこの関数は、リスト ボックスで指定された文字列内の文字で始まる最初の行の現在の選択範囲を設定*値*です。 レコード セットからコントロールへの転送にはレコード セット フィールドが Null の場合、選択内容がリスト ボックスから削除されます。 コントロールからレコード セットへの転送時に、コントロールが空である場合は、レコード セット フィールドは Null に設定します。  
  
 ODBC ベースのクラスを使用している場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用している場合は、2 番目のバージョンを使用します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールド、記事を参照して[レコード ビュー](../../data/record-views-mfc-data-access.md)します。  
  
### <a name="example"></a>例  
 参照してください[DDX_FieldText](#ddx_fieldtext)全般 DDX_Field などです。 呼び出す`DDX_FieldLBString`ようになります。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdao.h  
  
##  <a name="a-nameddxfieldlbstringexacta--ddxfieldlbstringexact"></a><a name="ddx_fieldlbstringexact"></a>DDX_FieldLBStringExact  
 `DDX_FieldLBStringExact`関数では、リスト ボックス コントロールの現在の選択項目をコピーするレコード ビュー内で、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)レコード ビューに関連付けられているレコード セットのフィールド データ メンバーです。  
  
```  
void AFXAPI DDX_FieldLBStringExact(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBStringExact(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 内のコントロールの ID、 [CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクトです。  
  
 *value*  
 関連付けられたフィールドのデータ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクトです。  
  
 `pRecordset`  
 ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを使用するには、データを交換します。  
  
### <a name="remarks"></a>コメント  
 逆方向にこの関数は、リスト ボックスに指定された文字列を正確に一致する最初の行の現在の選択範囲を設定*値*です。 レコード セットからコントロールへの転送にはレコード セット フィールドが Null の場合、選択内容がリスト ボックスから削除されます。 コントロールからレコード セットへの転送時に、コントロールが空である場合は、レコード セット フィールドは Null に設定します。  
  
 ODBC ベースのクラスを使用している場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用している場合は、2 番目のバージョンを使用します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールド、記事を参照して[レコード ビュー](../../data/record-views-mfc-data-access.md)します。  
  
### <a name="example"></a>例  
 参照してください[DDX_FieldText](#ddx_fieldtext)全般 DDX_Field などです。 呼び出す`DDX_FieldLBStringExact`ようになります。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdao.h  
  
##  <a name="a-nameddxfieldradioa--ddxfieldradio"></a><a name="ddx_fieldradio"></a>DDX_FieldRadio  
 `DDX_FieldRadio`関数は、0 から始まる`int`レコード ビューのオプション ボタンのグループ内の現在選択されているオプション ボタンとレコード ビューのレコード セットのメンバー変数を指定します。  
  
```  
void AFXAPI DDX_FieldRadio(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldRadio(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 最初の ID、グループ内 (スタイルで**WS_GROUP**) にある隣接するラジオ ボタン コントロールの[CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクトです。  
  
 *value*  
 関連付けられたフィールドのデータ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクトです。  
  
 `pRecordset`  
 ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを使用するには、データを交換します。  
  
### <a name="remarks"></a>コメント  
 この関数をオンにレコード セット フィールドからビューに転送する際、 *n 番目*(0 から始まる) オプション ボタンをクリックし、その他のボタンをオフにします。 逆方向には、この関数は、現在 (チェック) 上にあるラジオ ボタンの序数をレコード セット フィールドを設定します。 レコード セットからコントロールへの転送にレコード セット フィールドが Null の場合 ボタンが選択されていません。 コントロールからレコード セットへの転送時にコントロールが選択されていない場合、レコード セット フィールドは Null に設定、フィールドが許可されている場合。  
  
 ODBC ベースのクラスを使用している場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用している場合は、2 番目のバージョンを使用します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールド、記事を参照して[レコード ビュー](../../data/record-views-mfc-data-access.md)します。  
  
### <a name="example"></a>例  
 参照してください[DDX_FieldText](#ddx_fieldtext)全般 DDX_Field などです。 呼び出す`DDX_FieldRadio`ようになります。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdao.h  
  
##  <a name="a-nameddxfieldscrolla--ddxfieldscroll"></a><a name="ddx_fieldscroll"></a>DDX_FieldScroll  
 `DDX_FieldScroll`関数は、レコード ビューにスクロール バー コントロールのスクロール位置を同期し、`int`レコード ビュー (またはに関連付けられた整数変数にマップする) レコード セットのフィールド データ メンバーです。  
  
```  
void AFXAPI DDX_FieldScroll(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldScroll(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *各\**  
 最初の ID、グループ内 (スタイルで**WS_GROUP**) にある隣接するラジオ ボタン コントロールの[CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクトです。  
  
 *value*  
 関連付けられたフィールドのデータ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクトです。  
  
 `pRecordset`  
 ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを使用するには、データを交換します。  
  
### <a name="remarks"></a>コメント  
 この関数がで指定された値に、スクロール バー コントロールのスクロール位置を設定するコントロールをレコード セットからデータを移動する場合*値*です。 レコード セットからコントロールへの転送にレコード セット フィールドが Null の場合は、スクロール バー コントロールは 0 に設定します。 コントロールからレコード セットへの転送時に、コントロールが空である場合、レコード セット フィールドの値は 0 です。  
  
 ODBC ベースのクラスを使用している場合は、最初のバージョンを使用します。 DAO ベースのクラスを使用している場合は、2 番目のバージョンを使用します。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールド、記事を参照して[レコード ビュー](../../data/record-views-mfc-data-access.md)します。  
  
### <a name="example"></a>例  
 参照してください[DDX_FieldText](#ddx_fieldtext)全般 DDX_Field などです。 呼び出す`DDX_FieldScroll`ようになります。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdao.h  
  
##  <a name="a-nameddxfieldtexta--ddxfieldtext"></a><a name="ddx_fieldtext"></a>DDX_FieldText  
 `DDX_FieldText`関数は、コンテンツの転送を管理`int`、**短い**、**長い**、 `DWORD`、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)、 **float**、**二重**、 **BOOL**、または**バイト**エディット ボックス コントロールとレコード セットのフィールド データ メンバーの間でのデータです。  
  
```  
void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    BYTE& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    UINT& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    long& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    DWORD& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    float& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    double& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    short& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    BOOL& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    BYTE& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    long& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    DWORD& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    float& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    double& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    COleDateTime& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    COleCurrency& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 `nIDC`  
 内のコントロールの ID、 [CRecordView](../../mfc/reference/crecordview-class.md)または[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)オブジェクトです。  
  
 *value*  
 関連付けられたフィールドのデータ メンバーへの参照を`CRecordset`または`CDaoRecordset`オブジェクトです。 値のデータ型のオーバー ロードされたバージョンのうちに依存`DDX_FieldText`を使用します。  
  
 `pRecordset`  
 ポインター、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトを使用するには、データを交換します。 このポインターにより`DDX_FieldText`を検出し、Null 値を設定します。  
  
### <a name="remarks"></a>コメント  
 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクト、`DDX_FieldText`転送も管理[時刻](../../atl-mfc-shared/reference/coledatetime-class.md)、および[COleCurrency](../../mfc/reference/colecurrency-class.md)値。 空の編集ボックス コントロールでは、Null 値を示します。 レコード セットからコントロールへの転送では、レコード セット フィールドが Null の場合、編集ボックスが設定を空にします。 コントロールからレコード セットへの転送時に、コントロールが空である場合は、レコード セット フィールドは Null に設定します。  
  
 バージョンを使用して[CRecordset](../../mfc/reference/crecordset-class.md) ODBC ベースのクラスを使用している場合のパラメーターです。 バージョンを使用して[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) DAO ベースのクラスを使用している場合のパラメーターです。  
  
 DDX の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。 例との DDX の詳細について[CRecordView](../../mfc/reference/crecordview-class.md)と[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)フィールド、記事を参照して[レコード ビュー](../../data/record-views-mfc-data-access.md)します。  
  
### <a name="example"></a>例  
 次`DoDataExchange`の機能、 [CRecordView](../../mfc/reference/crecordview-class.md)が含まれています`DDX_FieldText`3 つのデータ型の関数を呼び出します:`IDC_COURSELIST`コンボ ボックスは、他の&2; つのコントロールは、エディット ボックス。 DAO プログラミング、 *m_pSet*パラメーターへのポインターは、 [CRecordset](../../mfc/reference/crecordset-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)します。  
  
 [!code-cpp[NVC_MFCDatabase #&43;](../../mfc/codesnippet/cpp/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview_1.cpp)]  

  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdao.h  
    
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

