---
title: "CMFCPropertyGridFileProperty クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyGridFileProperty class
- CMFCPropertyGridFileProperty::OnClickButton method
ms.assetid: 2bb8b8b4-47fc-4798-bd5e-dc8ea0b4cd9d
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 56e9d258f5d608b03497632bef84cf73611f2e9a
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpropertygridfileproperty-class"></a>CMFCPropertyGridFileProperty クラス
`CMFCPropertyGridFileProperty`クラスは、ファイルの選択 ダイアログ ボックスを開くプロパティ リスト コントロール項目をサポートしています。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCPropertyGridFileProperty : public CMFCPropertyGridProperty  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty](#cmfcpropertygridfileproperty)|`CMFCPropertyGridFileProperty` オブジェクトを構築します。|  
|`CMFCPropertyGridFileProperty::~CMFCPropertyGridFileProperty`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCPropertyGridFileProperty::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|`CMFCPropertyGridFileProperty::OnClickButton`|(上書き[CMFCPropertyGridProperty::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton))。|  
  
### <a name="remarks"></a>コメント  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridFileProperty](../../mfc/reference/cmfcpropertygridfileproperty-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxpropertygridctrl.h  
  
##  <a name="cmfcpropertygridfileproperty"></a>CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty  
 `CMFCPropertyGridFileProperty` オブジェクトを構築します。  
  
```  
CMFCPropertyGridFileProperty(
    const CString& strName,  
    BOOL bOpenFileDialog,  
    const CString& strFileName,  
    LPCTSTR lpszDefExt=NULL,  
    DWORD dwFlags=OFN_HIDEREADONLY|OFN_OVERWRITEPROMPT,  
    LPCTSTR lpszFilter=NULL,  
    LPCTSTR lpszDescr=NULL,  
    DWORD_PTR dwData=0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `strName`  
 プロパティ名。  
  
 [入力] `bOpenFileDialog`  
 `TRUE`開くには、**ファイルを開く** ダイアログ ボックス`FALSE`を開くには、**ファイルを保存** ダイアログ ボックス。  
  
 [入力] `strFileName`  
 初期ファイル名。  
  
 [入力] `lpszDefExt`  
 1 つ以上のファイル名拡張子の文字列。 既定値は `NULL` です。  
  
 [入力] `dwFlags`  
 ダイアログ ボックスのフラグ。 既定値は、`OFN_HIDEREADONLY` と `OFN_OVERWRITEPROMPT` のビットごとの組み合わせ (OR) です。  
  
 [入力] `lpszFilter`  
 1 つ以上のファイル フィルターの文字列。 既定値は `NULL` です。  
  
 [入力] `lpszDescr`  
 プロパティ項目の説明。 既定値は `NULL` です。  
  
 [入力] `dwData`  
 プロパティ項目に関連付けられたアプリケーション固有のデータ。 たとえば、32 ビット整数またはその他のデータへのポインター。 既定値は 0 です。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 使用可能なフラグの一覧については、次を参照してください。 [OPENFILENAME 構造](https://msdn.microsoft.com/library/ms646839.aspx)します。  
  
### <a name="example"></a>例  
 次の例では、`CMFCPropertyGridFileProperty` クラスのコンストラクターを使用してオブジェクトを作成する方法を示します。 この例は、 [Visual Studio のデモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&22;](../../mfc/codesnippet/cpp/cmfcpropertygridfileproperty-class_1.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyGridCtrl クラス](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [CMFCPropertyGridProperty クラス](../../mfc/reference/cmfcpropertygridproperty-class.md)

