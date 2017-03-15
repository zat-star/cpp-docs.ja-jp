---
title: "CMFCFontInfo クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCFontInfo
dev_langs:
- C++
helpviewer_keywords:
- CMFCFontInfo class
- CMFCFontInfo::CMFCFontInfo constructor
ms.assetid: f88329b2-d74e-4921-9441-a3bb6536a049
caps.latest.revision: 26
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
ms.openlocfilehash: ac1409bcfce389cbc334edd2b864f7505d7443c7
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcfontinfo-class"></a>CMFCFontInfo クラス
`CMFCFontInfo`クラスは、名前とその他のフォントの属性を記述します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCFontInfo : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCFontInfo`|
          `CMFCFontInfo` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCFontInfo::GetFullName](#getfullname)|フォントとその文字の連結された名前のセット (スクリプト) を取得します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCFontInfo::m_nCharSet](#m_ncharset)|フォントに関連付けられている文字セット (スクリプト) を指定する値。|  
|[CMFCFontInfo::m_nPitchAndFamily](#m_npitchandfamily)|ピッチとフォントのファミリを指定する値。|  
|[CMFCFontInfo::m_nType](#m_ntype)|フォントの種類を指定する値。|  
|[CMFCFontInfo::m_strName](#m_strname)|フォントの名前たとえば、 **Arial**します。|  
|[CMFCFontInfo::m_strScript](#m_strscript)|フォントに関連付けられている文字セット (スクリプト) の名前。|  
  
## <a name="remarks"></a>コメント  
 アタッチすることができます、`CMFCFontInfo`オブジェクトの項目を[CMFCToolBarFontComboBox クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)クラスです。 呼び出す、 [CMFCToolBarFontComboBox::GetFontDesc](../../mfc/reference/cmfctoolbarfontcombobox-class.md#getfontdesc)へのポインターを取得するメソッドを`CMFCFontInfo`オブジェクトです。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメンバーを使用して、`CMFCFontInfo`クラスです。 取得する方法の例、`CMFCFontInfo`オブジェクトから、 `CMFCRibbonFontComboBox`、および、ローカル変数にアクセスする方法です。 この例は、 [MSOffice 2007 デモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo&6;](../../mfc/reference/codesnippet/cpp/cmfcfontinfo-class_1.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxtoolbarfontcombobox.h  
  
##  <a name="a-namecmfcfontinfoa--cmfcfontinfocmfcfontinfo"></a><a name="cmfcfontinfo"></a>CMFCFontInfo::CMFCFontInfo  
 `CMFCFontInfo` オブジェクトを構築します。  
  
```  
CMFCFontInfo(
    LPCTSTR lpszName,  
    LPCTSTR lpszScript,  
    BYTE nCharSet,  
    BYTE nPitchAndFamily,  
    int nType);  
  
CMFCFontInfo(const CMFCFontInfo& src);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszName`  
 フォントの名前。 詳細については、次を参照してください。、`lfFaceName`のメンバー、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)構造体。  
  
 [入力] `lpszScript`  
 フォントのスクリプト (文字セット) の名前。  
  
 [入力] `nCharSet`  
 フォントの文字セット (スクリプト) を指定する値。 詳細については、次を参照してください。、`lfCharSet`のメンバー、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)構造体。  
  
 [入力] `nPitchAndFamily`  
 ピッチとフォントのファミリを指定する値。 詳細については、次を参照してください。、`lfPitchAndFamily`のメンバー、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)構造体。  
  
 [入力] `nType`  
 フォントの種類を指定する値。 このパラメーターは、DEVICE_FONTTYPE、RASTER_FONTTYPE、および TRUETYPE_FONTTYPE のビットごとの組み合わせ (OR) を指定できます。  
  
 [入力] `src`  
 既存の`CMFCFontInfo`オブジェクトのメンバーが、これを構築するために使用`CMFCFontInfo`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 このドキュメントでは、用語*文字セット*と*スクリプト*同義です。 A*スクリプト*、文字および&1; つまたは複数の言語でこれらの文字を書き込むようにルールのコレクションには、書記体系であるとも呼ばれます。 文字のコレクションには、アルファベットとそのスクリプトで使用される区切り記号が含まれています。 たとえば、ラテン語のスクリプトは英語用として使用は、米国で使用されて、されのアルファベットには、a ~ Z の文字が含まれています。`lfCharSet`のメンバー、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)構造体は、文字セットを指定します。 たとえば、値`ANSI_CHARSET`指定、[!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)]文字セットは、ラテン文字のアルファベットが含まれています。  
  
##  <a name="a-namegetfullnamea--cmfcfontinfogetfullname"></a><a name="getfullname"></a>CMFCFontInfo::GetFullName  
 フォントとその文字の連結された名前のセット (スクリプト) を取得します。  
  
```  
CString GetFullName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 スクリプトとフォントの名前を表す文字列。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、フォントの完全な名前を取得できます。 たとえば、フォント名がある場合は`Arial`、およびフォント スクリプトが`Cyrillic`、このメソッドは、Arial (キリル文字) を返します。  
  
##  <a name="a-namemncharseta--cmfcfontinfomncharset"></a><a name="m_ncharset"></a>CMFCFontInfo::m_nCharSet  
 フォントに関連付けられている文字セット (スクリプト) を指定する値。  
  
```  
const BYTE m_nCharSet;  
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。、`nCharSet`のパラメーター、 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo)コンス トラクターです。  
  
##  <a name="a-namemnpitchandfamilya--cmfcfontinfomnpitchandfamily"></a><a name="m_npitchandfamily"></a>CMFCFontInfo::m_nPitchAndFamily  
 声の高さ (ポイント サイズ) とフォントのファミリ (serif、sans-serif、および固定幅など) を指定する値。  
  
```  
const BYTE m_nPitchAndFamily;  
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。、`nPitchAndFamily`のパラメーター、 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo)コンス トラクターです。  
  
##  <a name="a-namemntypea--cmfcfontinfomntype"></a><a name="m_ntype"></a>CMFCFontInfo::m_nType  
 フォントの種類を指定する値。  
  
```  
const int m_nType;  
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。、`nType`のパラメーター、 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo)コンス トラクターです。  
  
##  <a name="a-namemstrnamea--cmfcfontinfomstrname"></a><a name="m_strname"></a>CMFCFontInfo::m_strName  
 フォントの名前: たとえば、 **Arial**します。  
  
```  
const CString m_strName;  
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。、`lpszName`のパラメーター、 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo)コンス トラクターです。  
  
##  <a name="a-namemstrscripta--cmfcfontinfomstrscript"></a><a name="m_strscript"></a>CMFCFontInfo::m_strScript  
 フォントに関連付けられている文字セット (スクリプト) の名前。  
  
```  
const CString m_strScript;  
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。、`lpszScript`のパラメーター、 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo)コンス トラクターです。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarFontComboBox クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [CMFCToolBarFontSizeComboBox クラス](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)

