---
title: "CSimpleDialog クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleDialog
- ATLWIN/ATL::CSimpleDialog
- ATLWIN/ATL::CSimpleDialog::DoModal
dev_langs:
- C++
helpviewer_keywords:
- CSimpleDialog class
- CSimpleDialog class, modal dialog boxes in ATL
- dialog boxes, modal
- modal dialog boxes, ATL
ms.assetid: 2ae65cc9-4f32-4168-aecd-200b4a480fdf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5e497d5f1646ab890b7dafa3e1fb7e1c711a8a09
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="csimpledialog-class"></a>CSimpleDialog クラス
このクラスは、基本のモーダル ダイアログ ボックスを実装します。  
  
## <a name="syntax"></a>構文  
  
```
template <WORD t_wDlgTemplateID, BOOL t_bCenter = TRUE>  
class CSimpleDialog : public CDialogImplBase
```  
  
#### <a name="parameters"></a>パラメーター  
 *t_wDlgTemplateID*  
  
 ダイアログ テンプレート リソースのリソース ID です。  
  
 *t_bCenter*  
 **TRUE**ダイアログ オブジェクトする場合は、オーナー ウィンドウの中央に配置します。 それ以外の**FALSE**です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleDialog::DoModal](#domodal)|モーダル ダイアログ ボックスを作成します。|  
  
## <a name="remarks"></a>コメント  
 基本的な機能を持つモーダル ダイアログ ボックスを実装します。 `CSimpleDialog`Windows コモン コントロールのみのサポートを提供します。 作成、モーダル ダイアログ ボックスを表示するには、ダイアログ ボックスの既存のリソース テンプレートの名前を提供する、このクラスのインスタンスを作成します。 ユーザー (IDOK、IDCANCEL など) の定義済みの値を持つ任意のコントロールがクリックしたときに、ダイアログ ボックスのオブジェクトを閉じます。  
  
 `CSimpleDialog`モーダル ダイアログ ボックスのみを作成できます。 `CSimpleDialog`既定のメッセージ マップを使用して、適切なハンドラーへのメッセージを送信するためのダイアログ ボックス プロシージャを提供します。  
  
 参照してください[ ダイアログ ボックスを実装する](../../atl/implementing-a-dialog-box.md)詳細についてはします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CDialogImplBase`  
  
 `CSimpleDialog`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h  
  
##  <a name="domodal"></a>CSimpleDialog::DoModal  
 モーダル ダイアログ ボックスの呼び出しを完了ダイアログ ボックスの結果を返します。  
  
```
INT_PTR DoModal(HWND hWndParent = ::GetActiveWindow());
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndParent`  
 ダイアログ ボックスの親へのハンドル。 値が指定されていない場合は、親が現在アクティブなウィンドウに設定されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、戻り値は、ダイアログ ボックスを閉じて、コントロールのリソース ID です。  
  
 関数が失敗した場合、戻り値は-1 です。 拡張されたエラー情報を取得するには、`GetLastError` を呼び出します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ダイアログ ボックスがアクティブな間に、ユーザーとすべての対話を処理します。 モーダル ダイアログ ボックスは、します。ユーザーは、ダイアログ ボックスが閉じられるまで、他のウィンドウを操作できません。  
  
## <a name="see-also"></a>参照  
 [クラスの概要](../../atl/atl-class-overview.md)
