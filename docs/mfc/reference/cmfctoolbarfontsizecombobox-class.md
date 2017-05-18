---
title: "CMFCToolBarFontSizeComboBox クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::GetTwipSize
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::RebuildFontSizes
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::SetTwipSize
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarFontSizeComboBox class
ms.assetid: 72e0c44c-6a0e-4194-a71f-ab64e3afb9b5
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 9dddb563617a708bdc8b2193fa5ee8bd10321828
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarfontsizecombobox-class"></a>CMFCToolBarFontSizeComboBox クラス
コンボ ボックス コントロールのフォント サイズを選択することができますを含むツール バー ボタン。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCToolBarFontSizeComboBox : public CMFCToolBarComboBoxButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox](#cmfctoolbarfontsizecombobox)|`CMFCToolBarFontSizeComboBox` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize)|選択したフォント サイズを返します。|  
|[CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes)|指定したフォントのすべてのサポートされているフォント サイズには、コンボ ボックスの一覧を格納します。|  
|[CMFCToolBarFontSizeComboBox::SetTwipSize](#settwipsize)|フォント サイズを設定します。|  
  
## <a name="remarks"></a>コメント  
 使用することができます、`CMFCToolBarFontSizeComboBox`オブジェクトと共に、 [CMFCToolBarFontComboBox クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)フォントとフォント サイズを選択するユーザーを有効にするオブジェクト。  
  
 フォント コンボ ボックス ボタンを追加すると同様に、ツールバーにフォント サイズ コンボ ボックス ボタンを追加できます。 詳細については、次を参照してください。 [CMFCToolBarFontComboBox クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)します。  
  
 ユーザーが新しいフォントを選択すると、`CMFCToolBarFontComboBox`オブジェクトを使用してそのフォントのサイズがサポートされているフォント サイズ コンボ ボックスを入力し、 [CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes)メソッドです。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CMFCToolBarFontSizeComboBox`を構成するクラス、`CMFCToolBarFontSizeComboBox`オブジェクトです。 この例では、テキスト ボックスからの長さのフォント サイズを取得、すべての有効なサイズ指定されたフォント サイズ、フォント コンボ ボックスを塗りつぶすおよびのフォント サイズを指定する方法を示します。 このコード スニペットの一部である、 [Word パッド サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_WordPad&#8;](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontsizecombobox-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
 [CMFCToolBarFontSizeComboBox](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxtoolbarfontcombobox.h  
  
##  <a name="cmfctoolbarfontsizecombobox"></a>CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox  
 `CMFCToolBarFontSizeComboBox` オブジェクトを構築します。  
  
```  
CMFCToolBarFontSizeComboBox();
```  
  
##  <a name="gettwipsize"></a>CMFCToolBarFontSizeComboBox::GetTwipSize  
 フォント サイズのコンボ ボックスのテキスト ボックスからの長さのフォント サイズを取得します。  
  
```  
int GetTwipSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 戻り値が正の場合のフォント サイズを勧めします。 コンボ ボックスのテキスト ボックスが空の場合は-1 になります。 エラーが発生した場合は-2 を返します。  
  
##  <a name="rebuildfontsizes"></a>CMFCToolBarFontSizeComboBox::RebuildFontSizes  
 すべての有効なサイズ指定されたフォントのフォント サイズのコンボ ボックスで塗りつぶします。  
  
```  
void RebuildFontSizes(const CString& strFontName);
```  
  
### <a name="parameters"></a>パラメーター  
 `[in] strFontName`  
 フォント名を指定します。  
  
### <a name="remarks"></a>コメント  
 など、フォント コンボ ボックス内の選択とフォント サイズ コンボ ボックス間で同期するときに、この関数を呼び出して、 [CMFCToolBarFontComboBox クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)します。  
  
##  <a name="settwipsize"></a>CMFCToolBarFontSizeComboBox::SetTwipSize  
 丸められますが、指定したサイズ (twip) ポイント、および単位のサイズを最も近い値をそのコンボ ボックスで選択したサイズです。  
  
```  
void SetTwipSize(int nSize);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nSize`  
 設定するには、twip 単位のフォント サイズを指定します。  
  
### <a name="remarks"></a>コメント  
 呼び出して、前の有効なフォント サイズを後で取得できる、 [CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize)メソッドです。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton クラス](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [CMFCFontInfo クラス](../../mfc/reference/cmfcfontinfo-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [チュートリアル: ツールバーへのコントロールを配置します。](../../mfc/walkthrough-putting-controls-on-toolbars.md)




