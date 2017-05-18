---
title: "クラスの関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDataPathProperty
- AFXCTL/CDataPathProperty
- AFXCTL/CDataPathProperty::CDataPathProperty
- AFXCTL/CDataPathProperty::GetControl
- AFXCTL/CDataPathProperty::GetPath
- AFXCTL/CDataPathProperty::Open
- AFXCTL/CDataPathProperty::ResetData
- AFXCTL/CDataPathProperty::SetControl
- AFXCTL/CDataPathProperty::SetPath
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], asynchronous
- OLE controls [C++], asynchronous
- CDataPathProperty class
- asynchronous controls [C++]
ms.assetid: 1f96efdb-54e4-460b-862c-eba5d4103488
caps.latest.revision: 24
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: d767cf950d8b86959aadc2fd4d77401134a6dc75
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cdatapathproperty-class"></a>関数のクラス
非同期で読み込める OLE コントロール プロパティを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDataPathProperty : public CAsyncMonikerFile  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDataPathProperty::CDataPathProperty](#cdatapathproperty)|`CDataPathProperty` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDataPathProperty::GetControl](#getcontrol)|関連付けられている非同期 OLE コントロールを取得、`CDataPathProperty`オブジェクトです。|  
|[CDataPathProperty::GetPath](#getpath)|プロパティのパス名を取得します。|  
|[CDataPathProperty::Open](#open)|関連付けられた ActiveX (OLE) コントロールの非同期のプロパティの読み込みを開始します。|  
|[CDataPathProperty::ResetData](#resetdata)|呼び出し`CAsyncMonikerFile::OnDataAvailable`コンテナー コントロールのプロパティが変更されたことを通知します。|  
|[CDataPathProperty::SetControl](#setcontrol)|プロパティに関連付けられた非同期 ActiveX (OLE) コントロールを設定します。|  
|[CDataPathProperty::SetPath](#setpath)|プロパティのパス名を設定します。|  
  
## <a name="remarks"></a>コメント  
 同期の開始に使用した後は、非同期のプロパティが読み込まれます。  
  
 クラス`CDataPathProperty`から派生した**CAysncMonikerFile**します。 OLE コントロールでは、非同期プロパティを実装するには、派生クラスを`CDataPathProperty`、させ[OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable)します。  
  
 インターネット アプリケーションで非同期モニカーと ActiveX コントロールを使用する方法の詳細については、次の記事を参照してください。  
  
- [インターネット最初のステップ: ActiveX コントロール](../../mfc/activex-controls-on-the-internet.md)  
  
- [インターネット最初のステップ: 非同期モニカー](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [関数](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 `CDataPathProperty`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxctl.h  
  
##  <a name="cdatapathproperty"></a>CDataPathProperty::CDataPathProperty  
 `CDataPathProperty` オブジェクトを構築します。  
  
```  
CDataPathProperty(COleControl* pControl = NULL);  
CDataPathProperty(LPCTSTR lpszPath, COleControl* pControl = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pControl`  
 これに関連する OLE コントロールのオブジェクトへのポインター`CDataPathProperty`オブジェクトです。  
  
 `lpszPath`  
 可能性のある絶対または相対パス、パスは、プロパティの実際の絶対位置を参照する非同期モニカーの作成に使用します。 `CDataPathProperty`Url はファイル名を使用します。 場合は、`CDataPathProperty`ファイルのオブジェクト、先頭に追加`file://`パスにします。  
  
### <a name="remarks"></a>コメント  
 `COleControl`によって指されるオブジェクト`pControl`によって使用される**開く**派生クラスによって取得します。 場合`pControl`は**NULL**で使用されるコントロール**開く**で設定する必要があります`SetControl`します。 場合`lpszPath`は**NULL**を使用してパスを渡すことができます**開く**を設定または`SetPath`です。  
  
##  <a name="getcontrol"></a>CDataPathProperty::GetControl  
 取得するには、このメンバー関数を呼び出す、`COleControl`オブジェクトに関連付けられている、`CDataPathProperty`オブジェクトです。  
  
```  
COleControl* GetControl();
```  
  
### <a name="return-value"></a>戻り値  
 OLE コントロールへのポインターに関連付けられている返します、`CDataPathProperty`オブジェクトです。 **NULL**コントロールではなくが関連付けられている場合。  
  
##  <a name="getpath"></a>CDataPathProperty::GetPath  
 パスを取得する、時に設定するには、このメンバー関数を呼び出して、`CDataPathProperty`オブジェクトが構築すると、やで指定された**開く**、または以前の呼び出しで指定された、`SetPath`メンバー関数。  
  
```  
CString GetPath() const;  
```  
  
### <a name="return-value"></a>戻り値  
 プロパティ自体へのパス名を返します。 パスが指定されていない場合は空にすることができます。  
  
##  <a name="open"></a>CDataPathProperty::Open  
 関連付けられたコントロールの非同期のプロパティの読み込みを開始するには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL Open(
    COleControl* pControl,  
    CFileException* pError = NULL);

 
virtual BOOL Open(
    LPCTSTR lpszPath,  
    COleControl* pControl,
    CFileException* pError = NULL);

 
virtual BOOL Open(
    LPCTSTR lpszPath,  
    CFileException* pError = NULL);  
  
virtual BOOL Open(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pControl`  
 これに関連する OLE コントロールのオブジェクトへのポインター`CDataPathProperty`オブジェクトです。  
  
 `pError`  
 ファイルの例外へのポインター。 エラーが発生した場合は、原因に設定されます。  
  
 `lpszPath`  
 可能性のある絶対または相対パス、パスは、プロパティの実際の絶対位置を参照する非同期モニカーの作成に使用します。 `CDataPathProperty`Url はファイル名を使用します。 場合は、`CDataPathProperty`ファイルのオブジェクト、先頭に追加`file://`パスにします。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 取得しようと、関数、`IBindHost`コントロールからのインターフェイスです。  
  
 呼び出しの前に**開く**パスを使用せず、このプロパティのパスの値を設定する必要があります。 これは、ため、オブジェクトが構築、またはを呼び出して、`SetPath`メンバー関数。  
  
 呼び出しの前に**開く**コントロールを使用しない (旧称 OLE コントロール) ActiveX コントロールは、オブジェクトに関連付けできます。 これは、ため、オブジェクトが構築、またはを呼び出して`SetControl`します。  
  
 すべてのオーバー ロード[CAsyncMonikerFile::Open](../../mfc/reference/casyncmonikerfile-class.md#open)からも入手できます`CDataPathProperty`します。  
  
##  <a name="resetdata"></a>CDataPathProperty::ResetData  
 取得するには、この関数を呼び出す`CAsyncMonikerFile::OnDataAvailable`いるコントロールのプロパティが変更され、非同期的に読み込まれるすべての情報は役に立たなくなったコンテナーに通知します。  
  
```  
virtual void ResetData();
```  
  
### <a name="remarks"></a>コメント  
 開くを再起動する必要があります。 派生クラスでは、この関数はそれぞれ異なる既定値をオーバーライドできます。  
  
##  <a name="setcontrol"></a>CDataPathProperty::SetControl  
 このメンバー関数を呼び出して非同期の OLE コントロールと関連付ける、`CDataPathProperty`オブジェクトです。  
  
```  
void SetControl(COleControl* pControl);
```  
  
### <a name="parameters"></a>パラメーター  
 `pControl`  
 プロパティに関連する非同期の OLE コントロールへのポインター。  
  
##  <a name="setpath"></a>CDataPathProperty::SetPath  
 プロパティのパス名を設定するには、このメンバー関数を呼び出します。  
  
```  
void SetPath(LPCTSTR lpszPath);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszPath`  
 パスであり、絶対または相対プロパティを非同期的に読み込まれる場合があります。 `CDataPathProperty`Url はファイル名を使用します。 場合は、`CDataPathProperty`ファイルのオブジェクト、先頭に追加`file://`パスにします。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル イメージ](../../visual-cpp-samples.md)   
 [CAsyncMonikerFile クラス](../../mfc/reference/casyncmonikerfile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CAsyncMonikerFile クラス](../../mfc/reference/casyncmonikerfile-class.md)

