---
title: "CMFCRibbonFontComboBox クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonFontComboBox
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonFontComboBox class
ms.assetid: 33b4db50-df4f-45fa-8f05-2e6e73c31435
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 851ef15013ca62012931fd92baf277d5db96033d
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonfontcombobox-class"></a>CMFCRibbonFontComboBox クラス
フォントの一覧を含むコンボ ボックスを実装します。 このコンボ ボックスをリボン パネルに配置できます。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonFontComboBox : public CMFCRibbonComboBox  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCRibbonFontComboBox::~CMFCRibbonFontComboBox`|デストラクターです。|  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonFontComboBox::CMFCRibbonFontComboBox](#cmfcribbonfontcombobox)|`CMFCRibbonFontComboBox` オブジェクトを構築して初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonFontComboBox::BuildFonts](#buildfonts)|リボンのフォント コンボ ボックスに、指定されたフォントの種類、文字セット、ピッチ、ファミリのフォントを設定します。|  
|`CMFCRibbonFontComboBox::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|[CMFCRibbonFontComboBox::GetCharSet](#getcharset)|指定された文字セットを返します。|  
|[CMFCRibbonFontComboBox::GetFontDesc](#getfontdesc)||  
|[CMFCRibbonFontComboBox::GetFontType](#getfonttype)|コンボ ボックスに表示するフォントの種類を返します。 有効なオプションは、DEVICE_FONTTYPE、RASTER_FONTTYPE、TRUETYPE_FONTTYPE、またはそのビットごとの任意の組み合わせです。|  
|[CMFCRibbonFontComboBox::GetPitchAndFamily](#getpitchandfamily)|コンボ ボックスに表示されるフォントのピッチとファミリを返します。|  
|`CMFCRibbonFontComboBox::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCRibbonFontComboBox::RebuildFonts](#rebuildfonts)|リボンのフォント コンボ ボックスに、以前に指定されたフォントの種類、文字セット、ピッチ、ファミリのフォントを設定します。|  
|[CMFCRibbonFontComboBox::SetFont](#setfont)|コンボ ボックスで、指定されたフォントを選択します。|  
  
## <a name="remarks"></a>コメント  
 作成した後、`CMFCRibbonFontComboBox`オブジェクトで呼び出すことによってリボン パネルに追加[CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)  
  
 [CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)  
  
 [CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxRibbonComboBox.h  
  
##  <a name="a-namebuildfontsa--cmfcribbonfontcomboboxbuildfonts"></a><a name="buildfonts"></a>CMFCRibbonFontComboBox::BuildFonts  
 フォントのリボンのコンボ ボックスに表示します。  
  
```  
void BuildFonts(
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    BYTE nPitchAndFamily = DEFAULT_PITCH);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nFontType`  
 追加するフォントのフォントの種類を指定します。  
  
 [入力] `nCharSet`  
 追加するフォントの文字セットを指定します。  
  
 [入力] `nPitchAndFamily`  
 ピッチおよび追加するフォント ファミリを指定します。  
  
##  <a name="a-namecmfcribbonfontcomboboxa--cmfcribbonfontcomboboxcmfcribbonfontcombobox"></a><a name="cmfcribbonfontcombobox"></a>CMFCRibbonFontComboBox::CMFCRibbonFontComboBox  
 構築して初期化、 [CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md)オブジェクトです。  
  
```  
CMFCRibbonFontComboBox(
    UINT nID,  
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    BYTE nPitchAndFamily = DEFAULT_PITCH,  
    int nWidth = -1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 ユーザーがコンボ ボックスから項目を選択したときに実行されるコマンドのコマンド ID。  
  
 [入力] `nFontType`  
 コンボ ボックスに表示するフォントの種類を指定します。 有効なオプションは**DEVICE_FONTTYPE**、 **RASTER_FONTTYPE**、および**TRUETYPE_FONTTYPE**、または、ビットごとの組み合わせ。  
  
 [入力] `nCharSet`  
 指定された文字セットに属するものにコンボ ボックスの一覧のフォントをフィルター処理.  
  
 [入力] `nPitchAndFamily`  
 ピッチ、およびコンボ ボックスに表示されるフォントのファミリを指定します。  
  
 [入力] `nWidth`  
 コンボ ボックスのピクセル単位の幅を指定します。  
  
### <a name="remarks"></a>コメント  
 可能な限りの詳細については`nFontType`パラメーターの値を参照してください[EnumFontFamProc](http://msdn.microsoft.com/library/windows/desktop/dd162621) Windows SDK のドキュメントです。  
  
 割り当てることができる有効な文字セットの詳細については`nCharSet,`と有効な値を割り当てることのできる`nPitchAndFamily`を参照してください[LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) Windows SDK のドキュメントです。  
  
##  <a name="a-namegetfontdesca--cmfcribbonfontcomboboxgetfontdesc"></a><a name="getfontdesc"></a>CMFCRibbonFontComboBox::GetFontDesc  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
const CMFCFontInfo* GetFontDesc(int iIndex = -1) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iIndex`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namerebuildfontsa--cmfcribbonfontcomboboxrebuildfonts"></a><a name="rebuildfonts"></a>CMFCRibbonFontComboBox::RebuildFonts  
 以前に指定したフォントの種類、文字セットとピッチおよびファミリのフォントでリボンのコンボ ボックスに表示します。  
  
```  
void RebuildFonts();
```  
  
### <a name="remarks"></a>コメント  
 フォントの種類、文字セットを指定して、リボンのフォント コンボ ボックスに含めるフォントのピッチとファミリのボックスに、[コンス トラクター](#cmfcribbonfontcombobox)またはを呼び出してこのクラスの[CMFCRibbonFontComboBox::BuildFonts](#buildfonts)します。  
  
##  <a name="a-namesetfonta--cmfcribbonfontcomboboxsetfont"></a><a name="setfont"></a>CMFCRibbonFontComboBox::SetFont  
 コンボ ボックスで、指定されたフォントを選択します。  
  
```  
BOOL SetFont(
    LPCTSTR lpszName,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    BOOL bExact = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 選択するフォントの名前を指定します。  
  
 `nCharSet`  
 選択したフォントの文字セットを指定します。  
  
 `bExact`  
 `TRUE`文字セットと一致するが、フォントを選択する場合を指定するには`FALSE`フォントを選択するときに、文字セットを無視することができることを指定します。  
  
### <a name="return-value"></a>戻り値  
 指定したフォントが見つかり、選択されている場合は&0; 以外それ以外の場合、0 を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetcharseta--cmfcribbonfontcomboboxgetcharset"></a><a name="getcharset"></a>CMFCRibbonFontComboBox::GetCharSet  
 指定された文字セットを返します。  
  
```  
BYTE GetCharSet() const;  
```  
  
### <a name="return-value"></a>戻り値  
 文字セット (Windows SDK ドキュメントでは、LOGFONT を参照してください)。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetfonttypea--cmfcribbonfontcomboboxgetfonttype"></a><a name="getfonttype"></a>CMFCRibbonFontComboBox::GetFontType  
 コンボ ボックスに表示するフォントの種類を返します。 有効なオプションは、DEVICE_FONTTYPE、RASTER_FONTTYPE、TRUETYPE_FONTTYPE、またはそのビットごとの任意の組み合わせです。  
  
```  
int GetFontType() const;  
```  
  
### <a name="return-value"></a>戻り値  
 フォントの種類 (Windows SDK ドキュメントで EnumFontFamProc を参照してください)。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetpitchandfamilya--cmfcribbonfontcomboboxgetpitchandfamily"></a><a name="getpitchandfamily"></a>CMFCRibbonFontComboBox::GetPitchAndFamily  
 コンボ ボックスに表示されるフォントのピッチとファミリを返します。  
  
```  
BYTE GetPitchAndFamily() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ピッチとファミリ (Windows SDK ドキュメントでは、LOGFONT を参照してください)。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonComboBox クラス](../../mfc/reference/cmfcribboncombobox-class.md)

