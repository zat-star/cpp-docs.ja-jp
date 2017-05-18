---
title: "CMFCAcceleratorKey クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::Format
- AFXACCELERATORKEY/CMFCAcceleratorKey::SetAccelerator
dev_langs:
- C++
helpviewer_keywords:
- CMFCAcceleratorKey class
ms.assetid: d140fbf7-23db-45ea-a63e-414a5ec7b3d5
caps.latest.revision: 36
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
ms.openlocfilehash: 7baa210acfabe8f17e2ab747fd98fe463c2907a2
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcacceleratorkey-class"></a>CMFCAcceleratorKey クラス
仮想キーのマッピングおよび書式設定を実装するヘルパー クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCAcceleratorKey : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCAcceleratorKey::CMFCAcceleratorKey](#cmfcacceleratorkey)|`CMFCAcceleratorKey` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCAcceleratorKey::Format](#format)|ビジュアル表現を ACCEL 構造体に変換します。|  
|[CMFCAcceleratorKey::SetAccelerator](#setaccelerator)|ショートカット キーを設定、`CMFCAcceleratorKey`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 アクセラレータ キーは、ショートカット キーとも呼ばれます。 ユーザーが入力するキーボード ショートカットを表示する場合、 [CMFCAcceleratorKeyAssignCtrl クラス](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md)マップ ショートカット キー、alt キーと shift キーを押しながら S など"Alt + Shift + S"などのカスタム テキスト形式にします。 各`CMFCAcceleratorKey`オブジェクトでは、単一のショートカット キーをテキスト形式にマップします。  
  
 アクセラレータ テーブルのショートカット キーとを使用する方法の詳細については、次を参照してください。 [CKeyboardManager クラス](../../mfc/reference/ckeyboardmanager-class.md)します。  
  
## <a name="example"></a>例  
 次の例では、構築、`CMFCAcceleratorKey`オブジェクトと、使用する方法、`Format`メソッドです。  
  
 [!code-cpp[NVC_MFC_RibbonApp #&30;](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkey-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCAcceleratorKey`   
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxacceleratorkey.h  
  
##  <a name="cmfcacceleratorkey"></a>CMFCAcceleratorKey::CMFCAcceleratorKey  
 構築、 [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md)オブジェクトです。  
  
```  
CMFCAcceleratorKey();  
CMFCAcceleratorKey(LPACCEL lpAccel);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpAccel`  
 ショートカット キーへのポインター。  
  
### <a name="remarks"></a>コメント  
 作成するときに、ショートカット キーを指定しないかどうか、`CMFCAccleratorKey`を使用して、 [CMFCAcceleratorKey::SetAccelerator](#setaccelerator)のショートカット キーを関連付けるメソッドを`CMFCAcceleratorKey`オブジェクトです。  
  
##  <a name="format"></a>CMFCAcceleratorKey::Format  
 関連付けられている文字列値に ACCEL 構造体に変換します。  
  
```  
void Format(CString& str) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `str`  
 参照、`CString`メソッドが変換されたショートカット キーを書き込むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、関連付けられているショートカット キーの文字列形式を取得します。 文字列形式を設定することができます、 [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md)オブジェクト コンス トラクターまたはメソッドのいずれかを使用して[CMFCAcceleratorKey::SetAccelerator](#setaccelerator)します。  
  
##  <a name="setaccelerator"></a>CMFCAcceleratorKey::SetAccelerator  
 ショートカット キーを設定、 [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md)オブジェクトです。  
  
```  
void SetAccelerator(LPACCEL lpAccel);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpAccel`  
 ショートカット キーへのポインター。  
  
### <a name="remarks"></a>コメント  
 ショートカット キーを設定するには、このメソッドを使用して、`CMFCAcceleratorKey`の作成時に、ショートカット キーを指定しなかったかどうか、`CMFCAcceleratorKey`です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CKeyboardManager クラス](../../mfc/reference/ckeyboardmanager-class.md)

