---
title: "クラスの関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinFormsControl
- AFXWINFORMS/CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CreateManagedControl
- AFXWINFORMS/CWinFormsControl::GetControl
- AFXWINFORMS/CWinFormsControl::GetControlHandle
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- CWinFormsControl class
- Windows Forms [C++], MFC support
ms.assetid: 6406dd7b-fb89-4a18-ac3a-c010d6b6289a
caps.latest.revision: 28
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
ms.openlocfilehash: 49e24c04deda3df5683908fa9ca485cf7802214b
ms.lasthandoff: 02/24/2017

---
# <a name="cwinformscontrol-class"></a>関数のクラス
Windows フォーム コントロールのホスティング用の基本機能を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
template<class TManagedControl>  
class CWinFormsControl : public CWnd  
```  
  
#### <a name="parameters"></a>パラメーター  
 `TManagedControl`  
 MFC アプリケーションに表示される .NET Framework の Windows フォーム コントロール。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CWinFormsControl::CWinFormsControl](#cwinformscontrol)|MFC Windows フォーム コントロールのラッパー オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CWinFormsControl::CreateManagedControl](#createmanagedcontrol)|MFC コンテナー内には、Windows フォーム コントロールを作成します。|  
|[CWinFormsControl::GetControl](#getcontrol)|Windows フォーム コントロールへのポインターを取得します。|  
|[CWinFormsControl::GetControlHandle](#getcontrolhandle)|Windows フォーム コントロールへのハンドルを取得します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CWinFormsControl::operator-&gt;](#operator_-_gt)|置換[CWinFormsControl::GetControl](#getcontrol)式にします。|  
|[CWinFormsControl::operator TManagedControl ^](#operator_tmanagedcontrol)|Windows フォーム コントロールへのポインターとして型をキャストします。|  
  
## <a name="remarks"></a>コメント  
 `CWinFormsControl`クラスには、Windows フォーム コントロールのホスティングの基本的な機能が用意されています。  
  
 Windows フォームの使用に関する詳細については、次を参照してください。 [MFC では、Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)します。  
  
 MFC コードは、ウィンドウ ハンドルをキャッシュする必要があります (通常`m_hWnd`)。 一部の Windows フォーム コントロールのプロパティを必要とする、基になる Win32`Window`が破棄され、使用して再作成`DestroyWindow`と`CreateWindow`です。 MFC Windows フォームの実装のハンドル、`Destroy`と`Create`を更新するコントロールのイベント、`m_hWnd`メンバーです。  
  
> [!NOTE]
>  MFC Windows フォームの統合は、MFC (AFXDLL が定義されている) を動的にリンクしているプロジェクトでのみ動作します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwinforms.h  
  
##  <a name="createmanagedcontrol"></a>CWinFormsControl::CreateManagedControl  
 MFC コンテナー内には、Windows フォーム コントロールを作成します。  
  
```  
inline BOOL CreateManagedControl(
    System::Type^ pType,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID)  
inline BOOL CreateManagedControl(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID);

 
inline BOOL CreateManagedControl(
    DWORD dwStyle,  
    int nPlaceHolderID,  
    CWnd* pParentWnd);

 
inline BOOL CreateManagedControl(
    typename TManagedControl^ pControl,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `pType`  
 作成されるコントロールのデータ型。 必要があります、[型](https://msdn.microsoft.com/en-us/library/system.type)データ型。  
  
 `dwStyle`  
 コントロールに適用するウィンドウ スタイル。 組み合わせを指定[ウィンドウ スタイル](../../mfc/reference/window-styles.md)します。 現時点では、次のスタイルのみがサポートされている: WS_TABSTOP、WS_VISIBLE、WS_DISABLED および WS_GROUP します。  
  
 `rect`  
 A [RECT 構造体](../../mfc/reference/rect-structure1.md)コントロールの左上隅および右下隅の座標を定義する (最初のオーバー ロードだけ)。  
  
 `nPlaceHolderID`  
 静的なプレース ホルダー コントロールのハンドルでは、リソース エディターで配置されます。 新しく作成された Windows フォーム コントロールの位置、z オーダーとスタイルと仮定した場合、静的コントロールが置き換えられます (2 つ目のオーバー ロードだけ)。  
  
 `pParentWnd`  
 親ウィンドウへのポインター。  
  
 `nID`  
 新しく作成されたコントロールに割り当てられるリソース ID 番号。  
  
 `pControl`  
 関連付けられる Windows フォーム コントロールのインスタンス、[関数](../../mfc/reference/cwinformscontrol-class.md)(4 番目のオーバー ロードだけ) のオブジェクトします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、0 以外の値を返します。 失敗した場合は、0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、MFC コンテナー内の .NET Framework の Windows フォーム コントロールをインスタンス化します。  
  
 メソッドの最初のオーバー ロードは、.NET Framework データ型を受け入れる`pType`MFC は、この型の新しいオブジェクトをインスタンス化できるようにします。 `pType`必要があります、[型](https://msdn.microsoft.com/en-us/library/system.type)データ型。  
  
 メソッドの&2; 番目のオーバー ロードに基づき、Windows フォーム コントロールの作成、`TManagedControl`のテンプレート パラメーター、`CWinFormsControl`クラスです。 コントロールの位置とサイズがに基づいて、`RECT`メソッドに渡された構造体。 のみ`dwStyle`スタイルの順序は重要です。  
  
 3 番目のオーバー ロード メソッドでは、破棄して、その位置、z オーダー、およびスタイルを仮定して、静的コントロールを置換する Windows フォーム コントロールを作成します。 静的コントロールは、Windows フォーム コントロールのプレース ホルダーとしてのみ機能します。 このオーバー ロードがからスタイルを組み合わせて、コントロールを作成するときに`dwStyle`静的コントロールのリソースのスタイルを使用します。  
  
 メソッドの&4; 番目のオーバー ロードは、既にインスタンス化された Windows フォーム コントロールに渡すことができる`pControl`MFC をラップします。 同じ型でなければなりません、`TManagedControl`のテンプレート パラメーター、`CWinFormsControl`クラスです。  
  
 参照してください[MFC では、Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)Windows フォームを使用するサンプルを制御します。  
  
##  <a name="cwinformscontrol"></a>CWinFormsControl::CWinFormsControl  
 MFC Windows フォーム コントロールのラッパー オブジェクトを構築します。  
  
```  
CWinFormsControl();
```  
  
### <a name="remarks"></a>コメント  
 呼び出したときに、Windows フォーム コントロールがインスタンス化される[CWinFormsControl::CreateManagedControl](#createmanagedcontrol)します。  
  
##  <a name="getcontrol"></a>CWinFormsControl::GetControl  
 Windows フォーム コントロールへのポインターを取得します。  
  
```  
inline TManagedControl^ GetControl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 Windows フォーム コントロールへのポインターを返します。  
  
### <a name="example"></a>例  
  参照してください[CWinFormsControl::CreateManagedControl](#createmanagedcontrol)します。  
  
##  <a name="getcontrolhandle"></a>CWinFormsControl::GetControlHandle  
 Windows フォーム コントロールへのハンドルを取得します。  
  
```  
inline HWND GetControlHandle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 Windows フォーム コントロールのハンドルを返します。  
  
### <a name="remarks"></a>コメント  
 `GetControlHandle`.NET Framework のコントロールのプロパティに格納されているウィンドウ ハンドルを返すヘルパー メソッド。 ウィンドウ ハンドルの値にコピー [CWnd::m_hWnd](../../mfc/reference/cwnd-class.md#m_hwnd)呼び出し中に[CWnd::Attach](../../mfc/reference/cwnd-class.md#attach)します。  
  
##  <a name="operator_-_gt"></a>CWinFormsControl::operator-&gt;  
 置換[CWinFormsControl::GetControl](#getcontrol)式にします。  
  
```  
inline TManagedControl^  operator->() const;  
```  
  
### <a name="remarks"></a>コメント  
 この演算子は、便利な構文を置き換える`GetControl`式にします。  
  
 Windows フォームの詳細については、次を参照してください。 [MFC では、Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)します。  
  
##  <a name="operator_tmanagedcontrol"></a>CWinFormsControl::operator TManagedControl ^  
 Windows フォーム コントロールへのポインターとして型をキャストします。  
  
```  
inline operator TManagedControl^() const;  
```  
  
### <a name="remarks"></a>コメント  
 この演算子は渡します`CWinFormsControl<``TManagedControl``>`を Windows フォーム コントロールへのポインターを受け取る関数にします。  
  
## <a name="see-also"></a>関連項目  
 [CWinFormsDialog クラス](../../mfc/reference/cwinformsdialog-class.md)   
 [CWinFormsView クラス](../../mfc/reference/cwinformsview-class.md)

