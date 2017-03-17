---
title: "CFormView クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFormView
- AFXEXT/CFormView
- AFXEXT/CFormView::CFormView
- AFXEXT/CFormView::IsInitDlgCompleted
dev_langs:
- C++
helpviewer_keywords:
- views, containing controls
- CFormView class
- form views
ms.assetid: a99ec313-36f0-4f28-9d2b-de11de14ac19
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 82b38b04aa3cf2368d41ee20847c952c3082d4e4
ms.lasthandoff: 02/24/2017

---
# <a name="cformview-class"></a>CFormView クラス
フォーム ビューの基底クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class CFormView : public CScrollView  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CFormView::CFormView](#cformview)|`CFormView` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFormView::IsInitDlgCompleted](#isinitdlgcompleted)|初期化中に同期に使用されます。|  
  
## <a name="remarks"></a>コメント  
 フォーム ビューは、基本的には、コントロールを含むビューです。 これらのコントロールは、ダイアログ テンプレート リソースに基づいて配置されます。 アプリケーションでフォームが必要な場合は、`CFormView` を使用します。 これらのビューをサポートして、スクロールを使用して、必要に応じて、 [CScrollView](../../mfc/reference/cscrollview-class.md)機能します。  
  
 できたら[フォーム ベースのアプリケーションを作成する](../../mfc/reference/creating-a-forms-based-mfc-application.md)、ビュー クラスの基`CFormView`、フォーム ベースのアプリケーションを作成します。  
  
 挿入することも新しい[フォームに関するトピック](../../mfc/form-views-mfc.md)ドキュメント/ビュー ベースのアプリケーションにします。 アプリケーションで最初はフォームをサポートしていなかった場合でも、新しいフォームを挿入するときに、Visual C++ によってフォームのサポートが追加されます。  
  
 MFC アプリケーション ウィザードと [クラスの追加] コマンドは、フォーム ベースのアプリケーションを作成する方法として推奨されています。 これらのメソッドを使用せず、フォーム ベース アプリケーションを作成する必要がある場合[フォーム ベースのアプリケーションを作成する](../../mfc/reference/creating-a-forms-based-mfc-application.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 `CFormView`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxext.h  
  
##  <a name="cformview"></a>CFormView::CFormView  
 `CFormView` オブジェクトを構築します。  
  
```  
CFormView(LPCTSTR lpszTemplateName);  
CFormView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszTemplateName`  
 ダイアログ テンプレート リソースの名前を表す null で終わる文字列が含まれています。  
  
 `nIDTemplate`  
 ダイアログ テンプレート リソースの ID 番号が含まれています。  
  
### <a name="remarks"></a>コメント  
 派生した型のオブジェクトを作成する場合`CFormView`、ビュー オブジェクトを作成し、ビューの基になるダイアログ リソースを識別するコンス トラクターの&1; つを呼び出します。 (コンス トラクターの引数として文字列を渡す) の名前または ID (パスの引数として符号なし整数) では、リソースを識別できます。  
  
 まで、フォーム ビュー ウィンドウおよび子コントロールを作成しない`CWnd::Create`が呼び出されます。 `CWnd::Create`ドキュメント テンプレートによっては、ドキュメントとビューの作成プロセスの一環として、フレームワークによって呼び出されます。  
  
> [!NOTE]
>  派生クラス*必要があります*独自のコンス トラクターを指定します。 コンス トラクターで、コンス トラクターを呼び出す`CFormView::CFormView`リソース名またはクラスの概要を前述のように、引数としての ID を指定しています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&90;](../../mfc/codesnippet/cpp/cformview-class_1.h)]  
  
 [!code-cpp[NVC_MFCDocView #&91;](../../mfc/codesnippet/cpp/cformview-class_2.cpp)]  
  
##  <a name="isinitdlgcompleted"></a>CFormView::IsInitDlgCompleted  
 他の操作が実行される前に初期化が完了したことを確認するために MFC によって使用されます。  
  
```  
BOOL IsInitDlgCompleted() const;  
```  
  
### <a name="return-value"></a>戻り値  
 このダイアログの初期化関数が完了している場合は true。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル SNAPVW](../../visual-cpp-samples.md)   
 [MFC サンプル VIEWEX](../../visual-cpp-samples.md)   
 [CScrollView クラス](../../mfc/reference/cscrollview-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDialog クラス](../../mfc/reference/cdialog-class.md)   
 [CScrollView クラス](../../mfc/reference/cscrollview-class.md)

