---
title: "CMFCRibbonContextCaption クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetColor
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetRightTabX
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonContextCaption class
ms.assetid: cce2c0a2-8370-4266-997e-f8d0eeb3d616
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
ms.openlocfilehash: 54f71af5ec46a8ddac4459e9ffdbc5b10f3106d4
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribboncontextcaption-class"></a>CMFCRibbonContextCaption クラス
リボン カテゴリまたはコンテキスト カテゴリの最上位に表示される色付きのキャプションを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonContextCaption : public CMFCRibbonButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCRibbonContextCaption::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|[CMFCRibbonContextCaption::GetColor](#getcolor)|キャプションの色を返します。|  
|[CMFCRibbonContextCaption::GetRightTabX](#getrighttabx)||  
|`CMFCRibbonContextCaption::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
  
## <a name="remarks"></a>コメント  
 このクラスを直接インスタンス化することはできません。 [CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)クラスを使用してこのクラスに、内部的にリボン カテゴリに色を追加します。  
  
 リボン カテゴリの色を設定するには、呼び出す[CMFCRibbonCategory::SetTabColor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor)します。 コンテキスト カテゴリの色を設定するには、呼び出す[CMFCRibbonBar::AddContextCategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonContextCaption](../../mfc/reference/cmfcribboncontextcaption-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxRibbonBar.h  
  
##  <a name="getcolor"></a>CMFCRibbonContextCaption::GetColor  
 キャプションの背景色を返します。  
  
```  
AFX_RibbonCategoryColor GetColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 返される値は、次の列挙値のいずれかになります。  
  
- `AFX_CategoryColor_None`  
  
- `AFX_CategoryColor_Red`  
  
- `AFX_CategoryColor_Orange`  
  
- `AFX_CategoryColor_Yellow`  
  
- `AFX_CategoryColor_Green`  
  
- `AFX_CategoryColor_Blue`  
  
- `AFX_CategoryColor_Indigo`  
  
- `AFX_CategoryColor_Violet`  
  
### <a name="remarks"></a>コメント  
 キャプションの色を呼び出すことによって設定できる[CMFCRibbonCategory::SetTabColor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor)または[CMFCRibbonBar::AddContextCategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory)します。  
  
##  <a name="getrighttabx"></a>CMFCRibbonContextCaption::GetRightTabX  
 カテゴリのリボン タブの右側のエッジの位置を取得します。  
  
```  
int GetRightTabX() const;  
```  
  
### <a name="return-value"></a>戻り値  
 それを囲む四角形の X の右辺値を返す、`CMFCRibbonCategory`オブジェクトのリボン タブまたはタブが切り捨てられる場合は-1 の値。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonCategory クラス](../../mfc/reference/cmfcribboncategory-class.md)   
 [CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)

