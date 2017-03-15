---
title: "CWinFormsView クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinFormsView
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- CWinFormsView class
- Windows Forms [C++], MFC support
ms.assetid: d597e397-6529-469b-88f5-7f65a6b9e895
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
translationtype: Machine Translation
ms.sourcegitcommit: 6c49d711da747e4c6cbad0f883d93196b6a98057
ms.openlocfilehash: 7aadcc1aa887cb6be1ddbb8f3797c4a9e1af5b6a
ms.lasthandoff: 02/24/2017

---
# <a name="cwinformsview-class"></a>CWinFormsView クラス
Windows フォーム コントロールのホスティング用の汎用機能を MFC ビューとして提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CWinFormsView : public CView;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CWinFormsView::CWinFormsView](#cwinformsview)|`CWinFormsView` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CWinFormsView::GetControl](#getcontrol)|Windows フォーム コントロールへのポインターを取得します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前||  
|----------|-|  
|[CWinFormsView::operator コントロール ^](#operator_control)|Windows フォーム コントロールへのポインターとして型をキャストします。|  
  
## <a name="remarks"></a>コメント  
 MFC を使用して、 `CWinFormsView` MFC ビュー内で .NET Framework の Windows フォーム コントロールをホストするクラス。 コントロールでは、ネイティブのビューの子である、MFC ビューの全体のクライアント領域を占有しています。 結果は、`CFormView`ビューで、Windows フォーム デザイナーを活用し、実行時に豊富なフォーム ベースのビューを作成することができます。  
  
 Windows フォームの使用に関する詳細については、次を参照してください。 [MFC では、Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)します。  
  
> [!NOTE]
>  MFC Windows フォームの統合は、MFC と動的にリンクするプロジェクトでのみ機能 (プロジェクトの AFXDLL が定義されている場合)。  
  
> [!NOTE]
>  CWinFormsView は MFC 分割ウィンドウをサポートしていません ( [CSplitterWnd クラス](../../mfc/reference/csplitterwnd-class.md))。 現在のみ Windows フォームのスプリッター コントロールはサポートされています。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwinforms.h  
  
##  <a name="a-namecwinformsviewa--cwinformsviewcwinformsview"></a><a name="cwinformsview"></a>CWinFormsView::CWinFormsView  
 `CWinFormsView` オブジェクトを構築します。  
  
```  
CWinFormsView(System::Type^ pManagedViewType);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pManagedViewType`  
 Windows フォーム ユーザー コントロールのデータ型へのポインター。   
  
### <a name="example"></a>例  
 次の例では、`CUserView`クラスから継承`CWinFormsView`の型を渡すと`UserControl1`に、`CWinFormsView`コンス トラクターです。 `UserControl1`ControlLibrary1.dll でカスタム コントロールです。  
  
 [!code-cpp[NVC_MFC_Managed&#1;](../../mfc/reference/codesnippet/cpp/cwinformsview-class_1.h)]  
  
 [!code-cpp[NVC_MFC_Managed&#2;](../../mfc/reference/codesnippet/cpp/cwinformsview-class_2.cpp)]  
  
##  <a name="a-namegetcontrola--cwinformsviewgetcontrol"></a><a name="getcontrol"></a>CWinFormsView::GetControl  
 Windows フォーム コントロールへのポインターを取得します。  
  
```  
System::Windows::Forms::Control^ GetControl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`System.Windows.Forms.Control`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 Windows フォームを使用する方法の例は、次を参照してください。 [MFC では、Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)します。  
  
##  <a name="a-nameoperatorcontrola--cwinformsviewoperator-control"></a><a name="operator_control"></a>CWinFormsView::operator コントロール ^  
 Windows フォーム コントロールへのポインターとして型をキャストします。  
  
```  
operator System::Windows::Forms::Control^() const;  
```  
  
### <a name="remarks"></a>コメント  
 この演算子は、渡すことができます、 `CWinFormsView` <xref:System.Windows.Forms.Control>.</xref:System.Windows.Forms.Control>の種類の Windows フォーム コントロールへのポインターを受け取る関数を表示  
  
### <a name="example"></a>例  
  参照してください[CWinFormsView::GetControl](#getcontrol)します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [関数のクラス](../../mfc/reference/cwinformscontrol-class.md)   
 [CWinFormsDialog クラス](../../mfc/reference/cwinformsdialog-class.md)   
 [CFormView クラス](../../mfc/reference/cformview-class.md)

