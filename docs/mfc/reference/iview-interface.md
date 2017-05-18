---
title: "IView インターフェイス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IView
- No header/IView
- No header/IView::OnActivateView
- No header/IView::OnInitialUpdate
- No header/IView::OnUpdate
dev_langs:
- C++
helpviewer_keywords:
- views [MFC]
- IView class
- views, classes
ms.assetid: 9321f299-486e-4551-bee9-d2c4a7b91548
caps.latest.revision: 23
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
ms.openlocfilehash: 9a8b5f2d9d123aa3032cb30ecdbdd1cd380b32f8
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="iview-interface"></a>IView インターフェイス
さまざまなメソッド実装を[CWinFormsView](../../mfc/reference/cwinformsview-class.md)を使用してマネージ コントロールをビューの通知を送信します。  
  
## <a name="syntax"></a>構文  
  
```  
interface class IView  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IView::OnActivateView](#onactivateview)|ビューがアクティブ化または非アクティブ化されたときに、MFC によって呼び出されます。|  
|[IView::OnInitialUpdate](#oninitialupdate)|ドキュメントにビューを最初にアタッチ後、ビューが最初に表示される前に、フレームワークによって呼び出されます。|  
|[IView::OnUpdate](#onupdate)|ビューのドキュメントが変更された後に、MFC によって呼び出されますこの関数は、ビューの変更を反映するように表示を更新できます。|  
  
## <a name="remarks"></a>コメント  
 `IView`いくつかのメソッドを実装する`CWinFormsView`を使用してホストされるマネージ コントロールを一般的な通知の表示を転送します。 これらは[OnInitialUpdate](#oninitialupdate)、 [OnUpdate](#onupdate)と[OnActivateView](#onactivateview)します。  
  
 `IView`ような[CView](../../mfc/reference/cview-class.md)が、管理ビューおよびコントロールでのみ使用されます。  
  
 Windows フォームの使用に関する詳細については、次を参照してください。 [MFC では、Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)します。  
  

## <a name="requirements"></a>要件  
 ヘッダー: afxwinforms.h (アセンブリ atlmfc\lib\mfcmifc80.dll で定義)  

## <a name="onactivateview"></a>IView::OnActivateView  
ビューがアクティブ化または非アクティブ化されたときに、MFC によって呼び出されます。
```
void OnActivateView(bool activate);
```
## <a name="parameters"></a>パラメーター
`activate`  
表示されているかどうかを示しますがアクティブまたは非アクティブ化します。  

## <a name="oninitialupdate"></a>IView::OnInitialUpdate
ドキュメントにビューを最初にアタッチ後、ビューが最初に表示される前に、フレームワークによって呼び出されます。
```
void OnInitialUpdate();
```

## <a name="onupdate"></a>IView::OnUpdate 
ビューのドキュメントが変更された後に、MFC によって呼び出されます。  
```
void OnUpdate();
```
## <a name="remarks"></a>コメント  
この関数は、ビューの変更を反映するように表示を更新できます。

## <a name="see-also"></a>関連項目  
 [CWinFormsView クラス](../../mfc/reference/cwinformsview-class.md)   
 [CView クラス](../../mfc/reference/cview-class.md)

