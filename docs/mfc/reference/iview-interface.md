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
- AFXWINFORMS/IView
- AFXWINFORMS/IView::OnActivateView
- AFXWINFORMS/IView::OnInitialUpdate
- AFXWINFORMS/IView::OnUpdate
dev_langs:
- C++
helpviewer_keywords:
- views [MFC]
- IView class [MFC]
- views [MFC], classes
ms.assetid: 9321f299-486e-4551-bee9-d2c4a7b91548
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a4266d8f5ec564dac67d7167c6c9bab4768a0276
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="iview-interface"></a>IView インターフェイス
いくつかのメソッドを実装する[CWinFormsView](../../mfc/reference/cwinformsview-class.md)を使用してマネージ コントロールを表示通知を送信します。  
  
## <a name="syntax"></a>構文  
  
```  
interface class IView  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IView::OnActivateView](#onactivateview)|ビューがアクティブまたは非アクティブ化されたときに、MFC によって呼び出されます。|  
|[IView::OnInitialUpdate](#oninitialupdate)|ビューが最初に表示される前に、ビューが最初に、ドキュメントにアタッチされている後に、フレームワークによって呼び出されます。|  
|[IView::OnUpdate](#onupdate)|ビューのドキュメントが変更された後に、MFC によって呼び出されますこの機能は、変更を反映するには、その表示を更新するビューを使用します。|  
  
## <a name="remarks"></a>コメント  
 `IView`いくつかのメソッドを実装する`CWinFormsView`を使用してホストされるマネージ コントロールに共通の通知の表示を転送します。 これらは[フィルターと並べ替え順序](#oninitialupdate)、 [OnUpdate](#onupdate)と[OnActivateView](#onactivateview)です。  
  
 `IView`ような[CView](../../mfc/reference/cview-class.md)が管理対象のビューおよびコントロールでのみ使用されます。  
  
 Windows フォームを使用する方法については、次を参照してください。 [MFC における Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)です。  
  

## <a name="requirements"></a>必要条件  
 ヘッダー: afxwinforms.h (アセンブリ atlmfc\lib\mfcmifc80.dll で定義)  

## <a name="onactivateview"></a>IView::OnActivateView  
ビューがアクティブまたは非アクティブ化されたときに、MFC によって呼び出されます。
```
void OnActivateView(bool activate);
```
## <a name="parameters"></a>パラメーター
`activate`  
表示されているかどうかを示しますがアクティブまたは非アクティブ化します。  

## <a name="oninitialupdate"></a>IView::OnInitialUpdate
ビューが最初に表示される前に、ビューが最初に、ドキュメントにアタッチされている後に、フレームワークによって呼び出されます。
```
void OnInitialUpdate();
```

## <a name="onupdate"></a>IView::OnUpdate 
ビューのドキュメントが変更された後に、MFC によって呼び出されます。  
```
void OnUpdate();
```
## <a name="remarks"></a>コメント  
この機能は、変更を反映するには、その表示を更新するビューを使用します。

## <a name="see-also"></a>参照  
 [CWinFormsView クラス](../../mfc/reference/cwinformsview-class.md)   
 [CView クラス](../../mfc/reference/cview-class.md)
