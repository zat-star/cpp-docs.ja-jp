---
title: "関数クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHtmlEditDoc
- AFXHTML/CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::GetView
- AFXHTML/CHtmlEditDoc::IsModified
- AFXHTML/CHtmlEditDoc::OpenURL
dev_langs:
- C++
helpviewer_keywords:
- CHtmlEditDoc [MFC], CHtmlEditDoc
- CHtmlEditDoc [MFC], GetView
- CHtmlEditDoc [MFC], IsModified
- CHtmlEditDoc [MFC], OpenURL
ms.assetid: b2cca61f-e5d6-4099-b0d1-46bf85f0bd64
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c1e60c3b175346268b2c6b755786adbd8eb86467
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="chtmleditdoc-class"></a>関数クラス
[CHtmlEditView](../../mfc/reference/chtmleditview-class.md)、MFC ドキュメント/ビュー アーキテクチャのコンテキストで WebBrowser 編集プラットフォームの機能を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class AFX_NOVTABLE CHtmlEditDoc : public CDocument  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CHtmlEditDoc::CHtmlEditDoc](#chtmleditdoc)|`CHtmlEditDoc` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CHtmlEditDoc::GetView](#getview)|取得、`CHtmlEditView`オブジェクトはこのドキュメントにアタッチします。|  
|[CHtmlEditDoc::IsModified](#ismodified)|関連するビューの WebBrowser コントロールにユーザーによって変更されているドキュメントが含まれているかどうかを返します。|  
|[CHtmlEditDoc::OpenURL](#openurl)|URL を開きます。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 `CHtmlEditDoc`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxhtml.h  
  
##  <a name="chtmleditdoc"></a>CHtmlEditDoc::CHtmlEditDoc  
 構築、**関数**オブジェクト。  
  
```  
CHtmlEditDoc();
```  
  
##  <a name="getview"></a>CHtmlEditDoc::GetView  
 取得、 [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)オブジェクトはこのドキュメントにアタッチします。  
  
```  
virtual CHtmlEditView* GetView() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ドキュメントへのポインターを返します**CHtmlEditView**オブジェクト。  
  
##  <a name="ismodified"></a>CHtmlEditDoc::IsModified  
 関連するビューの WebBrowser コントロールにユーザーによって変更されているドキュメントが含まれているかどうかを返します。  
  
```  
virtual BOOL IsModified();
```  
  
##  <a name="openurl"></a>CHtmlEditDoc::OpenURL  
 URL を開きます。  
  
```  
virtual BOOL OpenURL(LPCTSTR lpszURL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszURL`  
 開くには URL です。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
## <a name="see-also"></a>参照  
 [HTMLEdit サンプル](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)

