---
title: "CMFCRibbonApplicationButton クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton::CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton::SetImage
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonApplicationButton class
ms.assetid: beb81757-fabd-4641-9130-876ba8505b78
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a6fc19c2af854f3cd4ee3dc3a3008abcb4714ba3
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonapplicationbutton-class"></a>CMFCRibbonApplicationButton クラス
アプリケーション ウィンドウの左上隅に表示される特殊なボタンを実装します。 このボタンがクリックされると、通常は、一般的な **[ファイル]** メニューのコマンド ( **[開く]**、 **[上書き保存]**、 **[終了]**など) を含むメニューが開かれます。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonApplicationButton : public CMFCRibbonButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonApplicationButton::CMFCRibbonApplicationButton](#cmfcribbonapplicationbutton)|`CMFCRibbonApplicationButton` オブジェクトを構築して初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCRibbonApplicationButton::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|`CMFCRibbonApplicationButton::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCRibbonApplicationButton::SetImage](#setimage)|リボン アプリケーション ボタンにイメージを割り当てます。|  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CMFCRibbonApplicationButton`クラスです。 この例では、アプリケーション ボタンにイメージを割り当てる方法と、ツールヒントを設定する方法を示します。 このコード スニペットの一部である、[クライアントの描画のサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_DrawClient&4;](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_1.h)]  
[!code-cpp[NVC_MFC_DrawClient&#5;](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxRibbonBar.h  
  
##  <a name="cmfcribbonapplicationbutton"></a>CMFCRibbonApplicationButton::CMFCRibbonApplicationButton  
 構築して初期化、 [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md)オブジェクトです。  
  
```  
CMFCRibbonApplicationButton();  
CMFCRibbonApplicationButton(UINT uiBmpResID);  
  CMFCRibbonApplicationButton(HBITMAP hBmp);
```  
  
### <a name="parameters"></a>パラメーター  
 `uiBmpResID`  
 アプリケーション ボタンを表示するイメージのリソース ID です。  
  
 `hBmp`  
 アプリケーション ボタンを表示するビットマップへのハンドル。  
  
### <a name="remarks"></a>コメント  
 リボン アプリケーション ボタンは、アプリケーション ウィンドウの左上隅にある特殊なボタンです。 アプリケーションが通常を含む一般的なメニューを開き、ユーザーには、このボタンがクリックすると、**ファイル**などのコマンド**開く**、**保存**、および**終了**します。  
  
##  <a name="setimage"></a>CMFCRibbonApplicationButton::SetImage  
 アプリケーション ボタンにイメージを割り当てます。  
  
```  
void SetImage(UINT uiBmpResID);  
void SetImage(HBITMAP hBmp);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiBmpResID`  
 アプリケーション ボタンを表示するイメージのリソース ID です。  
  
 [入力] `hBmp`  
 アプリケーション ボタンを表示するビットマップへのハンドル。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して、ボタンを作成した後に、リボン アプリケーション ボタンに新しいイメージを割り当てます。 アプリケーション ボタンは、アプリケーション ウィンドウの左上隅にあります。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)

