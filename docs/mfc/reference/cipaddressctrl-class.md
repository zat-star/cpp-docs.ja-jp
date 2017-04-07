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
- CIPAddressCtrl
- AFXCMN/CIPAddressCtrl
- AFXCMN/CIPAddressCtrl::CIPAddressCtrl
- AFXCMN/CIPAddressCtrl::ClearAddress
- AFXCMN/CIPAddressCtrl::Create
- AFXCMN/CIPAddressCtrl::CreateEx
- AFXCMN/CIPAddressCtrl::GetAddress
- AFXCMN/CIPAddressCtrl::IsBlank
- AFXCMN/CIPAddressCtrl::SetAddress
- AFXCMN/CIPAddressCtrl::SetFieldFocus
- AFXCMN/CIPAddressCtrl::SetFieldRange
dev_langs:
- C++
helpviewer_keywords:
- IP address control
- Internet address edit box
- CIPAddressCtrl class
- Internet protocol address box
- common controls, Internet Explorer 4.0
- Internet Explorer 4.0 common controls
ms.assetid: 9764d2f4-cb14-4ba8-b799-7f57a55a47c6
caps.latest.revision: 22
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
ms.openlocfilehash: b3849580c7bfd07f241e55cc48144959566d7d09
ms.lasthandoff: 02/24/2017

---
# <a name="cipaddressctrl-class"></a>関数のクラス
Windows コモン IP アドレス コントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CIPAddressCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CIPAddressCtrl::CIPAddressCtrl](#cipaddressctrl)|`CIPAddressCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CIPAddressCtrl::ClearAddress](#clearaddress)|IP アドレス コントロールの内容を消去します。|  
|[CIPAddressCtrl::Create](#create)|IP アドレス コントロールを作成し、それにアタッチ、`CIPAddressCtrl`オブジェクトです。|  
|[CIPAddressCtrl::CreateEx](#createex)|指定した Windows 拡張スタイルを使用して IP アドレス コントロールを作成し、それにアタッチ、`CIPAddressCtrl`オブジェクトです。|  
|[CIPAddressCtrl::GetAddress](#getaddress)|IP アドレス コントロール内のすべての&4; つのフィールドのアドレス値を取得します。|  
|[CIPAddressCtrl::IsBlank](#isblank)|IP アドレス コントロールのすべてのフィールドを空にするかどうかを判断します。|  
|[CIPAddressCtrl::SetAddress](#setaddress)|IP アドレス コントロールのすべての&4; つのフィールドのアドレス値を設定します。|  
|[CIPAddressCtrl::SetFieldFocus](#setfieldfocus)|キーボード フォーカスを IP アドレス コントロールの指定したフィールドに設定します。|  
|[CIPAddressCtrl::SetFieldRange](#setfieldrange)|IP アドレス コントロールの指定したフィールドに範囲を設定します。|  
  
## <a name="remarks"></a>コメント  
 エディット コントロールのようなコントロールは IP アドレス コントロールを使用すると、入力およびインターネット プロトコル (IP) 形式の数値のアドレスを操作できます。  
  
 このコントロール (つまり、`CIPAddressCtrl`クラス) で Microsoft Internet Explorer 4.0 以降を実行中のプログラムにのみ有効です。 Windows および Windows NT の将来のバージョンで使用可能なユーザーはもできます。  
  
 IP アドレス コントロールの概要については、次を参照してください。 [IP アドレス コントロール](http://msdn.microsoft.com/library/windows/desktop/bb761372)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CIPAddressCtrl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="cipaddressctrl"></a>CIPAddressCtrl::CIPAddressCtrl  
 
          `CIPAddressCtrl` オブジェクトを作成します。  
  
```  
CIPAddressCtrl();
```  
  
##  <a name="clearaddress"></a>CIPAddressCtrl::ClearAddress  
 IP アドレス コントロールの内容を消去します。  
  
```  
void ClearAddress();
```  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[IPM_CLEARADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761377)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="create"></a>CIPAddressCtrl::Create  
 IP アドレス コントロールを作成し、それにアタッチ、`CIPAddressCtrl`オブジェクトです。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 IP アドレス コントロールのスタイル。 ウィンドウ スタイルの組み合わせを適用します。 含める必要があります、 **WS_CHILD**コントロールは、子ウィンドウを指定する必要がありますのでのスタイルを設定します。 参照してください[CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)で、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] windows スタイルの一覧にします。  
  
 `rect`  
 IP アドレス コントロールのサイズと位置への参照。 いずれかになります、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体。  
  
 `pParentWnd`  
 IP アドレス コントロールの親ウィンドウへのポインター。 ことはできません**NULL です。**  
  
 `nID`  
 IP アドレス コントロールの id。  
  
### <a name="return-value"></a>戻り値  
 初期化が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 構築する、 `CIPAddressCtrl`&2; つのステップ内のオブジェクト。  
  
1.  作成するコンス トラクターを呼び出し、`CIPAddressCtrl`オブジェクトです。  
  
2.  呼び出す**作成**、IP アドレス コントロールを作成します。  
  
 コントロールで拡張ウィンドウ スタイルを使用する場合は、呼び出す[CreateEx](#createex)の代わりに**作成**します。  
  
##  <a name="createex"></a>CIPAddressCtrl::CreateEx  
 コントロール (子ウィンドウ) を作成し、関連付けることは、この関数を呼び出して、`CIPAddressCtrl`オブジェクトです。  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwExStyle`  
 作成されるコントロールの拡張スタイルを指定します。 拡張ウィンドウ スタイルの一覧は、次を参照してください。、`dwExStyle`パラメーター [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `dwStyle`  
 IP アドレス コントロールのスタイル。 ウィンドウ スタイルの組み合わせを適用します。 含める必要があります、 **WS_CHILD**コントロールは、子ウィンドウを指定する必要がありますのでのスタイルを設定します。 参照してください[CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)で、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] windows スタイルの一覧にします。  
  
 `rect`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体のサイズとのクライアント座標で、作成するウィンドウの位置を表す`pParentWnd`します。  
  
 `pParentWnd`  
 コントロールの親ウィンドウへのポインター。  
  
 `nID`  
 コントロールの子ウィンドウの id。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用`CreateEx`の代わりに[作成](#create)、Windows 拡張スタイルの先頭で指定された、Windows の拡張スタイルを適用する**WS_EX**します。  
  
##  <a name="getaddress"></a>CIPAddressCtrl::GetAddress  
 IP アドレス コントロール内のすべての&4; つのフィールドのアドレス値を取得します。  
  
```  
int GetAddress(
    BYTE& nField0,  
    BYTE& nField1,  
    BYTE& nField2,  
    BYTE& nField3);  
  
int GetAddress(DWORD& dwAddress);
```  
  
### <a name="parameters"></a>パラメーター  
 `nField0`  
 パックされた IP アドレスからフィールド 0 の値への参照。  
  
 `nField1`  
 パックされた IP アドレスから 1 フィールドの値への参照。  
  
 `nField2`  
 パックされた IP アドレスからフィールド 2 の値への参照。  
  
 `nField3`  
 パックされた IP アドレスからフィールド 3 の値への参照。  
  
 `dwAddress`  
 アドレスへの参照、 `DWORD` IP アドレスを受信した値です。 参照してください**解説**を表示するテーブルの方法`dwAddress`入力されます。  
  
### <a name="return-value"></a>戻り値  
 IP アドレス コントロール内の空白でないフィールドの数。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[IPM_GETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761378)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 最初のプロトタイプでは、番号は、0 ~ 3 で、コントロールのフィールドを読み取るそれぞれ左から右、4 つのパラメーターを設定します。 上記の&2; つ目のプロトタイプで`dwAddress`は次のように設定されます。  
  
|フィールド|ビット フィールドの値を含む|  
|-----------|-------------------------------------|  
|0|24 ~ 31|  
|1|16 ~ 23|  
|2|8 ~ 15|  
|3|0 ~ 7|  
  
##  <a name="isblank"></a>CIPAddressCtrl::IsBlank  
 IP アドレス コントロールのすべてのフィールドを空にするかどうかを判断します。  
  
```  
BOOL IsBlank() const;  
```  
  
### <a name="return-value"></a>戻り値  
 すべての場合は 0 以外の IP アドレス コントロールのフィールドは空です。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[IPM_ISBLANK](http://msdn.microsoft.com/library/windows/desktop/bb761379)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="setaddress"></a>CIPAddressCtrl::SetAddress  
 IP アドレス コントロールのすべての&4; つのフィールドのアドレス値を設定します。  
  
```  
void SetAddress(
    BYTE nField0,  
    BYTE nField1,  
    BYTE nField2,  
    BYTE nField3);  
  
void SetAddress(DWORD dwAddress);
```  
  
### <a name="parameters"></a>パラメーター  
 `nField0`  
 フィールド 0 の値は、パックされた IP アドレスです。  
  
 `nField1`  
 パックされた IP アドレスから 1 フィールドの値。  
  
 `nField2`  
 パックされた IP アドレスから 2 フィールドの値。  
  
 `nField3`  
 パックされた IP アドレスからフィールド 3 の値。  
  
 `dwAddress`  
 A`DWORD`新しい IP アドレスを表す値。 参照してください**解説**を表示するテーブルの方法、`DWORD`値が自動的に入力します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[IPM_SETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761380)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 最初のプロトタイプでは、番号は、0 ~ 3 で、コントロールのフィールドを読み取るそれぞれ左から右、4 つのパラメーターを設定します。 上記の&2; つ目のプロトタイプで`dwAddress`は次のように設定されます。  
  
|フィールド|ビット フィールドの値を含む|  
|-----------|-------------------------------------|  
|0|24 ~ 31|  
|1|16 ~ 23|  
|2|8 ~ 15|  
|3|0 ~ 7|  
  
##  <a name="setfieldfocus"></a>CIPAddressCtrl::SetFieldFocus  
 キーボード フォーカスを IP アドレス コントロールの指定したフィールドに設定します。  
  
```  
void SetFieldFocus(WORD nField);
```  
  
### <a name="parameters"></a>パラメーター  
 `nField`  
 0 から始まるフィールドのインデックスがフォーカスを設定する必要があります。 この値がフィールドの数よりも大きい場合は、最初の空白のフィールドにフォーカスが設定されます。 すべてのフィールドが空白以外の場合は、最初のフィールドにフォーカスが設定されます。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[IPM_SETFOCUS](http://msdn.microsoft.com/library/windows/desktop/bb761381)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="setfieldrange"></a>CIPAddressCtrl::SetFieldRange  
 IP アドレス コントロールの指定したフィールドに範囲を設定します。  
  
```  
void SetFieldRange(
    int nField,  
    BYTE nLower,  
    BYTE nUpper);
```  
  
### <a name="parameters"></a>パラメーター  
 `nField`  
 範囲の適用先となるフィールドを&0; から始まるインデックス。  
  
 `nLower`  
 この IP アドレス コントロールの指定したフィールドの下限値を受け取る整数への参照。  
  
 `nUpper`  
 この IP アドレス コントロールの指定したフィールドの上限値を受け取る整数への参照。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[IPM_SETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761382)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 2 つのパラメーターを使用して`nLower`と`nUpper`の代わりに、フィールドの上限と下限の制限を示すために、 *wRange* Win32 メッセージで使用されるパラメーターです。  
  
## <a name="see-also"></a>関連項目  
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)




