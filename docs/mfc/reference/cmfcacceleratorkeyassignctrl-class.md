---
title: "CMFCAcceleratorKeyAssignCtrl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::GetAccel
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::IsFocused
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::IsKeyDefined
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::ResetKey
dev_langs:
- C++
helpviewer_keywords:
- CMFCAcceleratorKeyAssignCtrl class
ms.assetid: 89fb8e62-596e-4e71-8c9a-32740347aaab
caps.latest.revision: 33
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
ms.openlocfilehash: 23687cf4c13881293d10a5f816a2c825180df49c
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcacceleratorkeyassignctrl-class"></a>CMFCAcceleratorKeyAssignCtrl クラス
`CMFCAcceleratorKeyAssignCtrl`クラスを拡張、 [CEdit クラス](../../mfc/reference/cedit-class.md)alt キーを押し、コントロール、および SHIFT などの追加のシステム ボタンをサポートするためにします。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCAcceleratorKeyAssignCtrl : public CEdit  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl](#cmfcacceleratorkeyassignctrl)|`CMFCAcceleratorKeyAssignCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCAcceleratorKeyAssignCtrl::GetAccel](#getaccel)|`CMFCAcceleratorKeyAssignCtrl` オブジェクトで押されるショートカット キーの `ACCEL` 構造体を取得します。|  
|[CMFCAcceleratorKeyAssignCtrl::IsFocused](#isfocused)||  
|[CMFCAcceleratorKeyAssignCtrl::IsKeyDefined](#iskeydefined)|ショートカット キーが定義されているかどうかを判断します。|  
|[CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage](#pretranslatemessage)|クラスで使用される[CWinApp](../../mfc/reference/cwinapp-class.md)にディスパッチされる前に、ウィンドウ メッセージを変換する、 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 関数です。 (上書き[CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage))。|  
|[CMFCAcceleratorKeyAssignCtrl::ResetKey](#resetkey)|ショートカット キーをリセットします。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、ショートカット キー (アクセラレータ キーとも呼ばれます) をサポートすることで、`CEdit` クラスの機能を拡張します。 `CMFCAcceleratorKeyAssignCtrl`クラスの関数として、 [CEdit クラス](../../mfc/reference/cedit-class.md)とシステム ボタンを認識できます。  
  
 このクラスは、物理的なショートカット キーの組み合わせを文字列値にマップします。 たとえば、キーの組み合わせ Alt + B が文字列 "Alt + B" にマップされている場合、 ユーザーが `CMFCAcceleratorKeyAssignCtrl` オブジェクト内でこのキーの組み合わせを押すと、"Alt + B" が表示されます。 ショートカット キーと文字列の形式の間のマッピングの詳細については、次を参照してください。 [CMFCAcceleratorKey クラス](../../mfc/reference/cmfcacceleratorkey-class.md)します。  
  
## <a name="example"></a>例  
 次の例は、`CMFCAcceleratorKeyAssignCtrl` オブジェクトを構築し、その `ResetKey` メソッドを使用してショートカット キーをリセットする方法について説明しています。  
  
 [!code-cpp[NVC_MFC_RibbonApp #&31;](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkeyassignctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 `CMFCAcceleratorKeyAssignCtrl`   
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxacceleratorkeyassignctrl.h  
  
##  <a name="cmfcacceleratorkeyassignctrl"></a>CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl  
 構築、 [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md)オブジェクトです。  
  
```  
CMFCAcceleratorKeyAssignCtrl();
```  
  
##  <a name="getaccel"></a>CMFCAcceleratorKeyAssignCtrl::GetAccel  
 取得、`ACCEL`のショートカット キーが押されるを構造体、 [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md)オブジェクトです。  
  
```  
ACCEL const* GetAccel() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `ACCEL`ショートカット キーを表す構造体。  
  
### <a name="remarks"></a>コメント  
 この関数を使用して取得、 `ACCEL` 、ユーザーに入力したショートカット キーの構造、`CMFCAcceleratorKeyAssignCtrl`オブジェクトです。  
  
##  <a name="isfocused"></a>CMFCAcceleratorKeyAssignCtrl::IsFocused  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsFocused() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="iskeydefined"></a>CMFCAcceleratorKeyAssignCtrl::IsKeyDefined  
 ショートカット キーが定義されているかどうかを判断、 [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md)オブジェクトです。  
  
```  
BOOL IsKeyDefined() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ユーザーが既にショートカット キーを定義するキーの有効な組み合わせを押した場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ユーザーが有効なショートカット キーを入力するかどうかを判断するこの関数を使用して、`CMFCAcceleratorKeyAssignCtrl`オブジェクトです。 ショートカット キーが存在する場合を使用できます[CMFCAcceleratorKeyAssignCtrl::GetAccel](#getaccel)を入手する方法、`ACCEL`このショートカット キーに関連付けられている構造体。  
  
##  <a name="pretranslatemessage"></a>CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMsg`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="resetkey"></a>CMFCAcceleratorKeyAssignCtrl::ResetKey  
 ショートカット キーをリセットします。  
  
```  
void ResetKey();
```  
  
### <a name="remarks"></a>コメント  
 この関数では、エディット コントロールのテキストを消去します。 これには、ユーザーが押された任意のショートカット キーが含まれます。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCAcceleratorKey クラス](../../mfc/reference/cmfcacceleratorkey-class.md)

