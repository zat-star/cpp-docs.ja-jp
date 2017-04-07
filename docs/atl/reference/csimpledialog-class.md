---
title: "CSimpleDialog クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
caps.latest.revision: 19
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: a4c17a1da8d1be00ebff171af09bc6c8eb81ed44
ms.lasthandoff: 02/24/2017

---
# <a name="csimpledialog-class"></a>CSimpleDialog クラス
このクラスは、基本的なモーダル ダイアログ ボックスを実装します。  
  
## <a name="syntax"></a>構文  
  
```
template <WORD t_wDlgTemplateID, BOOL t_bCenter = TRUE>  
class CSimpleDialog : public CDialogImplBase
```  
  
#### <a name="parameters"></a>パラメーター  
 *t_wDlgTemplateID*  
  
 ダイアログ テンプレート リソースのリソース ID。  
  
 *t_bCenter*  
 **TRUE**ダイアログ オブジェクトは、オーナー ウィンドウを中心とした、それ以外の場合**FALSE**します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleDialog::DoModal](#domodal)|モーダル ダイアログ ボックスを作成します。|  
  
## <a name="remarks"></a>コメント  
 基本的な機能を持つモーダル ダイアログ ボックスを実装します。 `CSimpleDialog`Windows コモン コントロールのみのサポートを提供します。 作成し、モーダル ダイアログ ボックスを表示して、ダイアログ ボックスの既存のリソース テンプレートの名前を指定して、このクラスのインスタンスを作成します。 ユーザー (IDOK、IDCANCEL など) の定義済みの値を持つ任意のコントロールがクリックしたときにダイアログ ボックスのオブジェクトを閉じます。  
  
 `CSimpleDialog`モーダル ダイアログ ボックスのみを作成できます。 `CSimpleDialog`適切なハンドラーにメッセージを既定のメッセージ マップを使用して、ダイアログ ボックス プロシージャを提供します。  
  
 参照してください[ ダイアログ ボックスを実装する](../../atl/implementing-a-dialog-box.md)の詳細。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CDialogImplBase`  
  
 `CSimpleDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
  
##  <a name="domodal"></a>CSimpleDialog::DoModal  
 モーダル ダイアログ ボックスの呼び出しを実行時にダイアログ ボックスの結果を返します。  
  
```
INT_PTR DoModal(HWND hWndParent = ::GetActiveWindow());
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndParent`  
 ダイアログ ボックスの親へのハンドル。 値が指定されていない場合は、親が、現在アクティブなウィンドウに設定されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、戻り値は、ダイアログ ボックスを閉じて、コントロールのリソース ID です。  
  
 関数が失敗した場合は、–&1; を返します。 拡張されたエラー情報を取得するには、`GetLastError` を呼び出します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ダイアログ ボックスがアクティブなときに、ユーザーとすべての対話を処理します。 これは、こそが、ダイアログ ボックスをモーダルになります。つまり、ユーザーは、ダイアログ ボックスが閉じられるまで、他のウィンドウを操作できません。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

