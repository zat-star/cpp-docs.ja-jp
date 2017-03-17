---
title: "CD2DTextLayout クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout::CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout::Create
- AFXRENDERTARGET/CD2DTextLayout::Destroy
- AFXRENDERTARGET/CD2DTextLayout::Get
- AFXRENDERTARGET/CD2DTextLayout::GetFontFamilyName
- AFXRENDERTARGET/CD2DTextLayout::GetLocaleName
- AFXRENDERTARGET/CD2DTextLayout::IsValid
- AFXRENDERTARGET/CD2DTextLayout::ReCreate
- AFXRENDERTARGET/CD2DTextLayout::SetFontFamilyName
- AFXRENDERTARGET/CD2DTextLayout::SetLocaleName
- AFXRENDERTARGET/CD2DTextLayout::m_pTextLayout
dev_langs:
- C++
helpviewer_keywords:
- CD2DTextLayout class
ms.assetid: 724bd13c-f2ef-4e55-a775-8cb04b7b7908
caps.latest.revision: 16
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
ms.openlocfilehash: b9d3873058613041042857b7edf213d207f058c5
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dtextlayout-class"></a>CD2DTextLayout クラス
IDWriteTextLayout のラッパーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DTextLayout : public CD2DResource;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DTextLayout::CD2DTextLayout](#cd2dtextlayout)|CD2DTextLayout オブジェクトを構築します。|  
|[CD2DTextLayout:: ~ CD2DTextLayout](#cd2dtextlayout__~cd2dtextlayout)|デストラクターです。 D2D テキスト レイアウト オブジェクトが破棄されるときに呼び出されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DTextLayout::Create](#create)|CD2DTextLayout を作成します。 (上書き[CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create))。|  
|[CD2DTextLayout::Destroy](#destroy)|CD2DTextLayout オブジェクトを破棄します。 (上書き[CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy))。|  
|[CD2DTextLayout::Get](#get)|返します。 IDWriteTextLayout インターフェイス|  
|[CD2DTextLayout::GetFontFamilyName](#getfontfamilyname)|指定した位置にあるテキストのフォント ファミリ名をコピーします。|  
|[CD2DTextLayout::GetLocaleName](#getlocalename)|指定した位置にあるテキストのロケール名を取得します。|  
|[CD2DTextLayout::IsValid](#isvalid)|リソースの有効性をチェックする (上書き[CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid))。|  
|[CD2DTextLayout::ReCreate](#recreate)|CD2DTextLayout を再作成されます。 (上書き[CD2DResource::ReCreate](../../mfc/reference/cd2dresource-class.md#recreate))。|  
|[CD2DTextLayout::SetFontFamilyName](#setfontfamilyname)|指定したテキスト範囲内のテキストの null で終わるフォント ファミリ名を設定|  
|[CD2DTextLayout::SetLocaleName](#setlocalename)|指定したテキスト範囲内のテキストのロケール名を設定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DTextLayout::operator IDWriteTextLayout *](#operator_idwritetextlayout_star)|返します。 IDWriteTextLayout インターフェイス|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DTextLayout::m_pTextLayout](#m_ptextlayout)|IDWriteTextLayout へのポインター。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DTextLayout](../../mfc/reference/cd2dtextlayout-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="_dtorcd2dtextlayout"></a>CD2DTextLayout:: ~ CD2DTextLayout  
 デストラクターです。 D2D テキスト レイアウト オブジェクトが破棄されるときに呼び出されます。  
  
```  
virtual ~CD2DTextLayout();
```  
  
##  <a name="cd2dtextlayout"></a>CD2DTextLayout::CD2DTextLayout  
 CD2DTextLayout オブジェクトを構築します。  
  
```  
CD2DTextLayout(
    CRenderTarget* pParentTarget,  
    const CString& strText,  
    CD2DTextFormat& textFormat,  
    const CD2DSizeF& sizeMax,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentTarget`  
 レンダー ターゲットへのポインター。  
  
 `strText`  
 新しい CD2DTextLayout オブジェクトを作成するための文字列を格納する CString オブジェクト。  
  
 `textFormat`  
 文字列に適用する書式を含む CString オブジェクト。  
  
 `sizeMax`  
 [レイアウト] ボックスのサイズ。  
  
 `bAutoDestroy`  
 所有者 (pParentTarget) によって、オブジェクトが破棄されることを示します。  
  
##  <a name="create"></a>CD2DTextLayout::Create  
 CD2DTextLayout を作成します。  
  
```  
virtual HRESULT Create(CRenderTarget* */);
```  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。  
  
##  <a name="destroy"></a>CD2DTextLayout::Destroy  
 CD2DTextLayout オブジェクトを破棄します。  
  
```  
virtual void Destroy();
```  
  
##  <a name="get"></a>CD2DTextLayout::Get  
 返します。 IDWriteTextLayout インターフェイス  
  
```  
IDWriteTextLayout* Get();
```  
  
### <a name="return-value"></a>戻り値  
 IDWriteTextLayout インターフェイスまたはオブジェクトがまだ初期化されていない場合は NULL へのポインター。  
  
##  <a name="getfontfamilyname"></a>CD2DTextLayout::GetFontFamilyName  
 指定した位置にあるテキストのフォント ファミリ名をコピーします。  
  
```  
CString GetFontFamilyName(
    UINT32 currentPosition,  
    DWRITE_TEXT_RANGE* textRange = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `currentPosition`  
 確認するテキストの位置。  
  
 `textRange`  
 同じテキストの範囲は、現在位置で指定した位置のテキストとして書式設定できます。 これは、実行がフォント ファミリ名など、指定した位置と書式をそのままことを意味します。  
  
### <a name="return-value"></a>戻り値  
 現在のフォント ファミリ名を含む CString オブジェクト。  
  
##  <a name="getlocalename"></a>CD2DTextLayout::GetLocaleName  
 指定した位置にあるテキストのロケール名を取得します。  
  
```  
CString GetLocaleName(
    UINT32 currentPosition,  
    DWRITE_TEXT_RANGE* textRange = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `currentPosition`  
 検査するテキストの位置。  
  
 `textRange`  
 同じテキストの範囲は、現在位置で指定した位置のテキストとして書式設定できます。 これは、実行が指定すると、位置をロケール名などと書式をそのままことを意味します。  
  
### <a name="return-value"></a>戻り値  
 現在のロケール名を含む CString オブジェクト。  
  
##  <a name="isvalid"></a>CD2DTextLayout::IsValid  
 リソースの有効性のチェック  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リソースが無効である場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="m_ptextlayout"></a>CD2DTextLayout::m_pTextLayout  
 IDWriteTextLayout へのポインター。  
  
```  
IDWriteTextLayout* m_pTextLayout;  
```  
  
##  <a name="operator_idwritetextlayout_star"></a>CD2DTextLayout::operator IDWriteTextLayout *  
 返します。 IDWriteTextLayout インターフェイス  
  
```  
operator IDWriteTextLayout*();
```   
  
### <a name="return-value"></a>戻り値  
 IDWriteTextLayout インターフェイスまたはオブジェクトがまだ初期化されていない場合は NULL へのポインター。  
  
##  <a name="recreate"></a>CD2DTextLayout::ReCreate  
 CD2DTextLayout を再作成されます。  
  
```  
virtual HRESULT ReCreate(CRenderTarget* */);
```  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。  
  
##  <a name="setfontfamilyname"></a>CD2DTextLayout::SetFontFamilyName  
 指定したテキスト範囲内のテキストの null で終わるフォント ファミリ名を設定  
  
```  
BOOL SetFontFamilyName(
    LPCWSTR pwzFontFamilyName,  
    DWRITE_TEXT_RANGE textRange);
```  
  
### <a name="parameters"></a>パラメーター  
 `pwzFontFamilyName`  
 TextRange で指定された範囲内で文字列全体に適用されるフォント ファミリ名  
  
 `textRange`  
 この変更を適用するテキスト範囲  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、TRUE を返します。 それ以外の場合は FALSE を返します  
  
##  <a name="setlocalename"></a>CD2DTextLayout::SetLocaleName  
 指定したテキスト範囲内のテキストのロケール名を設定します。  
  
```  
BOOL SetLocaleName(
    LPCWSTR pwzLocaleName,  
    DWRITE_TEXT_RANGE textRange);
```  
  
### <a name="parameters"></a>パラメーター  
 `pwzLocaleName`  
 Null で終わるロケール名の文字列  
  
 `textRange`  
 この変更を適用するテキスト範囲  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、TRUE を返します。 それ以外の場合は FALSE を返します  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

