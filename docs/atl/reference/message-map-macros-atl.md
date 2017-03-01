---
title: "メッセージ マップ マクロ (ATL) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: eefdd546-8934-4a30-b263-9c06a8addcbd
caps.latest.revision: 16
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
ms.openlocfilehash: 8097982d6574af2ce1ba592dbead8abf6f6433df
ms.lasthandoff: 02/24/2017

---
# <a name="message-map-macros-atl"></a>メッセージ マップ マクロ (ATL)
これらのマクロは、メッセージ マップとエントリを定義します。  
  
|||  
|-|-|  
|[ALT_MSG_MAP](#alt_msg_map)|代替のメッセージ マップの先頭をマークします。|  
|[送るに](#begin_msg_map)|既定のメッセージ マップの先頭をマークします。|  
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|基本クラスのマップに代替のメッセージをチェインします。|  
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|クラスのデータ メンバーのマップに代替のメッセージをチェインします。|  
|[CHAIN_MSG_MAP](#chain_msg_map)|基本クラスの既定のメッセージ マップへのチェーン。|  
|[場合](#chain_msg_map_dynamic)|実行時に別のクラス内のメッセージ マップへのチェーン。|  
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|クラスのデータ メンバーの既定のメッセージ マップへのチェーン。|  
|[COMMAND_CODE_HANDLER](#command_code_handler)|マップ、 **WM_COMMAND**メッセージ ハンドラー関数の場合、通知のコードに基づいています。|  
|[COMMAND_HANDLER](#command_handler)|マップ、 **WM_COMMAND**メッセージ ハンドラー関数の場合、通知コードとメニュー項目、コントロール、またはアクセラレータの id を基にします。|  
|[COMMAND_ID_HANDLER](#command_id_handler)|マップ、 **WM_COMMAND**メッセージ ハンドラー関数の場合、メニュー項目、コントロール、またはアクセラレータの id に基づいています。|  
|[COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler)|マップ、 **WM_COMMAND**メッセージ ハンドラー関数の場合、通知コードとコントロール id の連続した範囲に基づいてをします。|  
|[COMMAND_RANGE_HANDLER](#command_range_handler)|マップ、 **WM_COMMAND**メッセージ ハンドラー関数の場合、連続した範囲のコントロール id に基づいています。|  
|[DECLARE_EMPTY_MSG_MAP](#declare_empty_msg_map)|空のメッセージ マップを実装します。|  
|[DEFAULT_REFLECTION_HANDLER](#default_reflection_handler)|それ以外の場合は処理されない返送されたメッセージの既定のハンドラーを提供します。|  
|[も](#end_msg_map)|メッセージ マップの最後をマークします。|  
|[FORWARD_NOTIFICATIONS](#forward_notifications)|親ウィンドウへの通知メッセージを転送します。|  
|[MESSAGE_HANDLER](#message_handler)|Windows メッセージをハンドラー関数にマップします。|  
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Windows の連続したメッセージをハンドラー関数にマップします。|  
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|マップ、 **WM_NOTIFY**メッセージ ハンドラー関数の場合、通知のコードに基づいています。|  
|[NOTIFY_HANDLER](#notify_handler)|マップ、 **WM_NOTIFY**メッセージ ハンドラー関数の場合、通知コードとコントロール id を基にします。|  
|[NOTIFY_ID_HANDLER](#notify_id_handler)|マップ、 **WM_NOTIFY**メッセージ ハンドラー関数の場合、コントロールの id に基づいています。|  
|[NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler)|マップ、 **WM_NOTIFY**メッセージ ハンドラー関数の場合、通知コードとコントロール id の連続した範囲に基づいてをします。|  
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|マップ、 **WM_NOTIFY**メッセージ ハンドラー関数の場合、連続した範囲のコントロール id に基づいています。|  
|[REFLECT_NOTIFICATIONS](#reflect_notifications)|通知メッセージを送信元ウィンドウに反映されます。|  
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|反射マップ**WM_COMMAND**メッセージ ハンドラー関数の場合、通知のコードに基づいています。|  
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|反射マップ**WM_COMMAND**メッセージ ハンドラー関数の場合、通知コードとメニュー項目、コントロール、またはアクセラレータの id を基にします。|  
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|反射マップ**WM_COMMAND**メッセージ ハンドラー関数の場合、メニュー項目、コントロール、またはアクセラレータの id に基づいています。|  
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|反射マップ**WM_COMMAND**メッセージ ハンドラー関数の場合、通知コードとコントロール id の連続した範囲に基づいてをします。|  
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|反射マップ**WM_COMMAND**メッセージ ハンドラー関数の場合、コントロールの id の連続した範囲に基づいて決まります。|  
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|反射マップ**WM_NOTIFY**メッセージ ハンドラー関数の場合、通知のコードに基づいています。|  
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|反射マップ**WM_NOTIFY**メッセージ ハンドラー関数の場合、通知コードとコントロール id を基にします。|  
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|反射マップ**WM_NOTIFY**メッセージ ハンドラー関数の場合、コントロールの id に基づいています。|  
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|反射マップ**WM_NOTIFY**メッセージ ハンドラー関数の場合、通知コードとコントロール id の連続した範囲に基づいてをします。|  
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|反射マップ**WM_NOTIFY**メッセージ ハンドラー関数の場合、コントロールの id の連続した範囲に基づいて決まります。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  

##  <a name="a-namealtmsgmapa--altmsgmap"></a><a name="alt_msg_map"></a>ALT_MSG_MAP  
 代替のメッセージ マップの先頭をマークします。  
  
```
ALT_MSG_MAP(msgMapID)
```  
  
### <a name="parameters"></a>パラメーター  
 `msgMapID`  
 [in]メッセージ マップの識別子。  
  
### <a name="remarks"></a>コメント  
 ATL では、各メッセージ マップを数値を識別します。 既定のメッセージ マップ (で宣言された、`BEGIN_MSG_MAP`マクロ) は 0 で識別します。 代替のメッセージ マップがで識別される`msgMapID`します。  
  
 メッセージ マップは、ウィンドウに送信されるメッセージの処理に使用されます。 たとえば、 [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md)親オブジェクトでメッセージ マップの識別子を指定することができます。 [CContainedWindow::WindowProc](ccontainedwindowt-class.md#windowproc)このメッセージ マップを使用して、適切なハンドラー関数または別のメッセージ マップのいずれかに含まれているウィンドウのメッセージを送信します。 ハンドラー関数を宣言するマクロの一覧は、次を参照してください。[送るに](#begin_msg_map)します。  
  
 メッセージ マップは常に開始`BEGIN_MSG_MAP`します。 代替の後続のメッセージ マップを宣言することができます。  
  
 [も](#end_msg_map)マクロは、メッセージ マップの最後をマークします。 メモの&1; つのインスタンスは常に`BEGIN_MSG_MAP`と`END_MSG_MAP`です。  
  
 ATL でのメッセージ マップの使用に関する詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)します。  
  
### <a name="example"></a>例  
 次の例では、既定のメッセージ マップと、それぞれ&1; つのハンドラー関数を含む&1; つの代替のメッセージ マップを示します。  
  
 [!code-cpp[NVC_ATL_Windowing #&98;](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 次の例では、2 つの代替のメッセージ マップを示します。 既定のメッセージ マップが空です。  
  
 [!code-cpp[NVC_ATL_Windowing&#99;](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   

##  <a name="a-namebeginmsgmapa--beginmsgmap"></a><a name="begin_msg_map"></a>送るに  
 既定のメッセージ マップの先頭をマークします。  
  
```
BEGIN_MSG_MAP(theClass)
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 [in]メッセージ マップを含むクラスの名前。  
  
### <a name="remarks"></a>コメント  
 [CWindowImpl::WindowProc](cwindowimpl-class.md#windowproc)既定のメッセージ マップを使用して、ウィンドウに送信されたメッセージを処理します。 メッセージ マップは、適切なハンドラー関数または別のメッセージ マップのいずれかのメッセージを送信します。  

  
 次のマクロは、メッセージをハンドラー関数にマップします。 この関数を定義する必要があります`theClass`します。  
  
|マクロ|説明|  
|-----------|-----------------|  
|[MESSAGE_HANDLER](#message_handler)|Windows メッセージをハンドラー関数にマップします。|  
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Windows の連続したメッセージをハンドラー関数にマップします。|  
|[COMMAND_HANDLER](#command_handler)|マップ、 **WM_COMMAND**メッセージ ハンドラー関数の場合、通知コードとメニュー項目、コントロール、またはアクセラレータの id を基にします。|  
|[COMMAND_ID_HANDLER](#command_id_handler)|マップ、 **WM_COMMAND**メッセージ ハンドラー関数の場合、メニュー項目、コントロール、またはアクセラレータの id に基づいています。|  
|[COMMAND_CODE_HANDLER](#command_handler)|マップ、 **WM_COMMAND**メッセージ ハンドラー関数の場合、通知のコードに基づいています。|  
|[COMMAND_RANGE_HANDLER](#command_range_handler)|連続した範囲の**WM_COMMAND**メニュー項目、コントロール、またはアクセラレータの識別子に基づいて、メッセージ ハンドラー関数をします。|  
|[NOTIFY_HANDLER](#notify_handler)|マップ、 **WM_NOTIFY**メッセージ ハンドラー関数の場合、通知コードとコントロール id を基にします。|  
|[NOTIFY_ID_HANDLER](#notify_id_handler)|マップ、 **WM_NOTIFY**メッセージ ハンドラー関数の場合、コントロールの id に基づいています。|  
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|マップ、 **WM_NOTIFY**メッセージ ハンドラー関数の場合、通知のコードに基づいています。|  
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|連続した範囲の**WM_NOTIFY**コントロール id に基づいて、メッセージ ハンドラー関数をします。|  
  
 次のマクロは、別のメッセージ マップへのメッセージを送ります。 このプロセスでは、「チェーン」と呼ばれます  
  
|マクロ|説明|  
|-----------|-----------------|  
|[CHAIN_MSG_MAP](#chain_msg_map)|基本クラスの既定のメッセージ マップへのチェーン。|  
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|クラスのデータ メンバーの既定のメッセージ マップへのチェーン。|  
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|基本クラスのマップに代替のメッセージをチェインします。|  
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|クラスのデータ メンバーのマップに代替のメッセージをチェインします。|  
|[場合](#chain_msg_map_dynamic)|実行時に別のクラスの既定のメッセージ マップへのチェーン。|  
  
 次のマクロは、親ウィンドウから「反映」のメッセージを送ります。 たとえば、コントロール通常送信します通知メッセージを親ウィンドウの処理しますが、親ウィンドウは、コントロールにメッセージを反映できます。  
  
|マクロ|説明|  
|-----------|-----------------|  
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|反射マップ**WM_COMMAND**メッセージ ハンドラー関数の場合、通知コードとメニュー項目、コントロール、またはアクセラレータの id を基にします。|  
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|反射マップ**WM_COMMAND**メッセージ ハンドラー関数の場合、メニュー項目、コントロール、またはアクセラレータの id に基づいています。|  
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|反射マップ**WM_COMMAND**メッセージ ハンドラー関数の場合、通知のコードに基づいています。|  
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|反射マップ**WM_COMMAND**メッセージ ハンドラー関数の場合、コントロールの id の連続した範囲に基づいて決まります。|  
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|反射マップ**WM_COMMAND**メッセージ ハンドラー関数の場合、通知コードとコントロール id の連続した範囲に基づいてをします。|  
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|反射マップ**WM_NOTIFY**メッセージ ハンドラー関数の場合、通知コードとコントロール id を基にします。|  
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|反射マップ**WM_NOTIFY**メッセージ ハンドラー関数の場合、コントロールの id に基づいています。|  
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|反射マップ**WM_NOTIFY**メッセージ ハンドラー関数の場合、通知のコードに基づいています。|  
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|反射マップ**WM_NOTIFY**メッセージ ハンドラー関数の場合、コントロールの id の連続した範囲に基づいて決まります。|  
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|反射マップ**WM_NOTIFY**メッセージ ハンドラー関数の場合、通知コードとコントロール id の連続した範囲に基づいてをします。|  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&102;](../../atl/codesnippet/cpp/message-map-macros-atl_3.h)]  
  
 ときに、`CMyExtWindow`オブジェクトを受け取る、`WM_PAINT`メッセージにメッセージが送信先`CMyExtWindow::OnPaint`実際の処理です。 場合`OnPaint`メッセージでは、さらに処理、メッセージはする必要がありますし、既定のメッセージ マップに送られる`CMyBaseWindow`です。  
  
 代替のメッセージ マップを定義するだけでなく既定のメッセージ マップ[ALT_MSG_MAP](#alt_msg_map)します。 メッセージ マップは常に開始`BEGIN_MSG_MAP`します。 代替の後続のメッセージ マップを宣言することができます。 次の例では、既定のメッセージ マップと、それぞれ&1; つのハンドラー関数を含む&1; つの代替のメッセージ マップを示します。  
  
 [!code-cpp[NVC_ATL_Windowing #&98;](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 次の例では、2 つの代替のメッセージ マップを示します。 既定のメッセージ マップが空です。  
  
 [!code-cpp[NVC_ATL_Windowing&#99;](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
 [も](#end_msg_map)マクロは、メッセージ マップの最後をマークします。 メモの&1; つのインスタンスは常に`BEGIN_MSG_MAP`と`END_MSG_MAP`です。  
  
 ATL でのメッセージ マップの使用に関する詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)します。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="a-namechainmsgmapalta--chainmsgmapalt"></a><a name="chain_msg_map_alt"></a>CHAIN_MSG_MAP_ALT  
 メッセージ マップのエントリを定義します。  
  
```
CHAIN_MSG_MAP_ALT(theChainClass, msgMapID)
```  
  
### <a name="parameters"></a>パラメーター  
 `theChainClass`  
 [in]メッセージ マップを含む基本クラスの名前。  
  
 `msgMapID`  
 [in]メッセージ マップの識別子。  
  
### <a name="remarks"></a>コメント  
 `CHAIN_MSG_MAP_ALT`基本クラスの代替のメッセージ マップにメッセージを送信します。 この代替のメッセージ マップが宣言されている必要があります[ALT_MSG_MAP(msgMapID)](#alt_msg_map)します。 基本クラスの既定のメッセージ マップへのメッセージを送信する (を使用して宣言[送るに](#begin_msg_map)) を使用して`CHAIN_MSG_MAP`します。 例については、次を参照してください。 [CHAIN_MSG_MAP](#chain_msg_map)します。  
  
> [!NOTE]
>  メッセージ マップは常に開始`BEGIN_MSG_MAP`します。 使って、代替メッセージ マップを宣言することができますし、`ALT_MSG_MAP`です。 [も](#end_msg_map)マクロは、メッセージ マップの最後をマークします。 すべてのメッセージ マップが正確に&1; つのインスタンスを持つ必要があります`BEGIN_MSG_MAP`と`END_MSG_MAP`です。  
  
 ATL でのメッセージ マップの使用に関する詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)します。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="a-namechainmsgmapaltmembera--chainmsgmapaltmember"></a><a name="chain_msg_map_alt_member"></a>CHAIN_MSG_MAP_ALT_MEMBER  
 メッセージ マップのエントリを定義します。  
  
```
CHAIN_MSG_MAP_ALT_MEMBER(theChainMember, msgMapID)
```  
  
### <a name="parameters"></a>パラメーター  
 `theChainMember`  
 [in]メッセージ マップを含むデータ メンバーの名前。  
  
 `msgMapID`  
 [in]メッセージ マップの識別子。  
  
### <a name="remarks"></a>コメント  
 `CHAIN_MSG_MAP_ALT_MEMBER`データ メンバーの代替のメッセージ マップにメッセージを送信します。 この代替のメッセージ マップが宣言されている必要があります[ALT_MSG_MAP(msgMapID)](#alt_msg_map)します。 データ メンバーの既定のメッセージ マップへのメッセージを送信する (を使用して宣言[送るに](#begin_msg_map)) を使用して`CHAIN_MSG_MAP_MEMBER`します。 例については、次を参照してください。 [CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)します。  
  
> [!NOTE]
>  メッセージ マップは常に開始`BEGIN_MSG_MAP`します。 使って、代替メッセージ マップを宣言することができますし、`ALT_MSG_MAP`です。 [も](#end_msg_map)マクロは、メッセージ マップの最後をマークします。 すべてのメッセージ マップが正確に&1; つのインスタンスを持つ必要があります`BEGIN_MSG_MAP`と`END_MSG_MAP`です。  
  
 ATL でのメッセージ マップの使用に関する詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)します。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="a-namechainmsgmapa--chainmsgmap"></a><a name="chain_msg_map"></a>CHAIN_MSG_MAP  
 メッセージ マップのエントリを定義します。  
  
```
CHAIN_MSG_MAP(theChainClass)
```  
  
### <a name="parameters"></a>パラメーター  
 `theChainClass`  
 [in]メッセージ マップを含む基本クラスの名前。  
  
### <a name="remarks"></a>コメント  
 `CHAIN_MSG_MAP`基本クラスの既定のメッセージ マップへのメッセージを送信 (を使用して宣言[送るに](#begin_msg_map))。 基本クラスの代替のメッセージ マップにメッセージを送信する (を使用して宣言[ALT_MSG_MAP](#alt_msg_map)) を使用して[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)します。  
  
> [!NOTE]
>  メッセージ マップは常に開始`BEGIN_MSG_MAP`します。 使って、代替メッセージ マップを宣言することができますし、`ALT_MSG_MAP`です。 [も](#end_msg_map)マクロは、メッセージ マップの最後をマークします。 すべてのメッセージ マップが正確に&1; つのインスタンスを持つ必要があります`BEGIN_MSG_MAP`と`END_MSG_MAP`です。  
  
 ATL でのメッセージ マップの使用に関する詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&107;](../../atl/codesnippet/cpp/message-map-macros-atl_4.h)]  
  
 この例は、次のいずれかを示します。  
  
-   ウィンドウ プロシージャが使用されている場合`CMyClass`の既定のメッセージ マップと`OnPaint`メッセージ、メッセージ送信先ハンドル以外は`CMyBaseClass`の処理のための既定のメッセージ マップです。  
  
-   ウィンドウ プロシージャが最初の代替のメッセージ マップを使用している`CMyClass`、すべてのメッセージが宛て`CMyBaseClass`の既定のメッセージ マップです。  
  
-   ウィンドウ プロシージャが使用されている場合`CMyClass`の&2; つ目の代替のメッセージにマップし、`OnChar`メッセージ、メッセージは指定した代替のメッセージ マップに送られますハンドル以外は`CMyBaseClass`です。 `CMyBaseClass`このメッセージ マップが宣言されている必要があります`ALT_MSG_MAP(1)`します。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="a-namechainmsgmapdynamica--chainmsgmapdynamic"></a><a name="chain_msg_map_dynamic"></a>場合  
 メッセージ マップのエントリを定義します。  
  
```
CHAIN_MSG_MAP_DYNAMIC(dynaChainID)
```  
  
### <a name="parameters"></a>パラメーター  
 *dynaChainID*  
 [in]オブジェクトのメッセージ マップの一意の識別子。  
  
### <a name="remarks"></a>コメント  
 `CHAIN_MSG_MAP_DYNAMIC`別のオブジェクトの既定のメッセージ マップへの実行時に、メッセージを出力します。 オブジェクトとそのメッセージ マップが関連付けられている*dynaChainID*を使用して定義される[CDynamicChain::SetChainEntry](cdynamicchain-class.md#setchainentry)します。 クラスを派生させる必要があります`CDynamicChain`を使用するために`CHAIN_MSG_MAP_DYNAMIC`します。 例については、次を参照してください。、 [CDynamicChain](../../atl/reference/cdynamicchain-class.md)の概要です。  

  
> [!NOTE]
>  メッセージ マップは常に開始[送るに](#begin_msg_map)します。 使って、代替メッセージ マップを宣言することができますし、`ALT_MSG_MAP`です。 [も](#end_msg_map)マクロは、メッセージ マップの最後をマークします。 すべてのメッセージ マップが正確に&1; つのインスタンスを持つ必要があります`BEGIN_MSG_MAP`と`END_MSG_MAP`です。  
  
 ATL でのメッセージ マップの使用に関する詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)します。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="a-namechainmsgmapmembera--chainmsgmapmember"></a><a name="chain_msg_map_member"></a>CHAIN_MSG_MAP_MEMBER  
 メッセージ マップのエントリを定義します。  
  
```
CHAIN_MSG_MAP_MEMBER(theChainMember)
```  
  
### <a name="parameters"></a>パラメーター  
 `theChainMember`  
 [in]メッセージ マップを含むデータ メンバーの名前。  
  
### <a name="remarks"></a>コメント  
 `CHAIN_MSG_MAP_MEMBER`データ メンバーの既定のメッセージ マップへのメッセージを送信 (を使用して宣言[送るに](#begin_msg_map))。 データ メンバーの代替のメッセージ マップにメッセージを送信する (を使用して宣言[ALT_MSG_MAP](#alt_msg_map)) を使用して[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)します。  
  
> [!NOTE]
>  メッセージ マップは常に開始`BEGIN_MSG_MAP`します。 使って、代替メッセージ マップを宣言することができますし、`ALT_MSG_MAP`です。 [も](#end_msg_map)マクロは、メッセージ マップの最後をマークします。 すべてのメッセージ マップが正確に&1; つのインスタンスを持つ必要があります`BEGIN_MSG_MAP`と`END_MSG_MAP`です。  
  
 ATL でのメッセージ マップの使用に関する詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&108;](../../atl/codesnippet/cpp/message-map-macros-atl_5.h)]  
  
 この例は、次のいずれかを示します。  
  
-   ウィンドウ プロシージャが使用されている場合`CMyClass`の既定のメッセージ マップと`OnPaint`メッセージ、メッセージ送信先ハンドル以外は`m_obj`の処理のための既定のメッセージ マップです。  
  
-   ウィンドウ プロシージャが最初の代替のメッセージ マップを使用している`CMyClass`、すべてのメッセージが宛て`m_obj`の既定のメッセージ マップです。  
  
-   ウィンドウ プロシージャが使用されている場合`CMyClass`の&2; つ目の代替のメッセージにマップし、`OnChar`メッセージ、メッセージは、指定した代替のメッセージ マップに送られますハンドル以外は`m_obj`です。 クラス`CMyContainedClass`では、このメッセージ マップが宣言されている必要があります`ALT_MSG_MAP(1)`します。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="a-namecommandcodehandlera--commandcodehandler"></a><a name="command_code_handler"></a>COMMAND_CODE_HANDLER  
 ような[COMMAND_HANDLER](#command_handler)、マップが、 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)メッセージが通知コードにのみ基づいています。  
  
```
COMMAND_CODE_HANDLER(code, func)
```  
  
### <a name="parameters"></a>パラメーター  
 `code`  
 [in]通知コード。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="a-namecommandhandlera--commandhandler"></a><a name="command_handler"></a>COMMAND_HANDLER  
 メッセージ マップのエントリを定義します。  
  
```
COMMAND_HANDLER(id, code, func)
```    
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]メニュー項目、コントロール、またはアクセラレータの識別子。  
  
 `code`  
 [in]通知コード。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 `COMMAND_HANDLER`マップ、 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)通知コードとコントロール id に基づいて、指定されたハンドラー関数にメッセージです。 例:  
  
 [!code-cpp[NVC_ATL_Windowing #&119;](../../atl/codesnippet/cpp/message-map-macros-atl_6.h)]  
  
 指定された関数、`COMMAND_HANDLER`マクロは次のように定義する必要があります。  
  
 `LRESULT CommandHandler(WORD wNotifyCode, WORD wID, HWND hWndCtl, BOOL& bHandled);`  
  
 メッセージ マップ セット`bHandled`に**TRUE**する前に`CommandHandler`が呼び出されます。 場合`CommandHandler`、メッセージを完全に処理しませんに設定する必要があります`bHandled`に**FALSE**を示す、メッセージは、さらに処理を必要があります。  
  
> [!NOTE]
>  メッセージ マップは常に開始[送るに](#begin_msg_map)します。 使って、代替メッセージ マップを宣言することができますし、 [ALT_MSG_MAP](#alt_msg_map)します。 [も](#end_msg_map)マクロは、メッセージ マップの最後をマークします。 すべてのメッセージ マップが正確に&1; つのインスタンスを持つ必要があります`BEGIN_MSG_MAP`と`END_MSG_MAP`です。  
  
 他に、 `COMMAND_HANDLER`、使用することができます[MESSAGE_HANDLER](#message_handler)にマップする、 **WM_COMMAND**識別子またはコードには関係なくメッセージです。 この場合、`MESSAGE_HANDLER(WM_COMMAND, OnHandlerFunction)`すべてを指示する**WM_COMMAND**へのメッセージ`OnHandlerFunction`します。  
  
 ATL でのメッセージ マップの使用に関する詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)します。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="a-namecommandidhandlera--commandidhandler"></a><a name="command_id_handler"></a>COMMAND_ID_HANDLER  
 ような[COMMAND_HANDLER](#command_handler)、マップしますが、 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)メッセージはメニュー項目、コントロール、またはアクセラレータの識別子にのみ基づいています。  
  
```
COMMAND_ID_HANDLER(id, func)
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]メニュー項目、コントロール、またはメッセージを送信するアクセラレータの識別子。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="a-namecommandrangecodehandlera--commandrangecodehandler"></a><a name="command_range_code_handler"></a>COMMAND_RANGE_CODE_HANDLER  
 ような[COMMAND_RANGE_HANDLER](#command_range_handler)、マップが、 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)コントロールの範囲から特定の通知コードを&1; つのハンドラー関数を持つメッセージ。  
  
```
COMMAND_RANGE_CODE_HANDLER(idFirst, idLast, code, func)
```    
  
### <a name="parameters"></a>パラメーター  
 `idFirst`  
 [in]コントロール id は連続した範囲の先頭をマークします。  
  
 `idLast`  
 [in]コントロール id の連続した範囲の末尾をマークします。  
  
 `code`  
 [in]通知コード。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 この範囲は、メニュー項目、コントロール、またはメッセージを送信するアクセラレータの識別子に基づきます。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="a-namecommandrangehandlera--commandrangehandler"></a><a name="command_range_handler"></a>COMMAND_RANGE_HANDLER  
 ような[COMMAND_HANDLER](#command_handler)、マップが、 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)コントロールの範囲から&1; つのハンドラー関数へのメッセージ。  
  
```
COMMAND_RANGE_HANDLER( idFirst, idLast, func)
```    
  
### <a name="parameters"></a>パラメーター  
 `idFirst`  
 [in]コントロール id は連続した範囲の先頭をマークします。  
  
 `idLast`  
 [in]コントロール id の連続した範囲の末尾をマークします。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 この範囲は、メニュー項目、コントロール、またはメッセージを送信するアクセラレータの識別子に基づきます。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="a-namedeclareemptymsgmapa--declareemptymsgmap"></a><a name="declare_empty_msg_map"></a>DECLARE_EMPTY_MSG_MAP  
 空のメッセージ マップを宣言します。  
  
```
DECLARE_EMPTY_MSG_MAP()
```  
  
### <a name="remarks"></a>コメント  
 `DECLARE_EMPTY_MSG_MAP`マクロを呼び出すための便利なマクロです[送るに](#begin_msg_map)と[も](#end_msg_map)空のメッセージ マップを作成します。  
  
 [!code-cpp[NVC_ATL_Windowing #&122;](../../atl/codesnippet/cpp/message-map-macros-atl_7.h)]  
  
##  <a name="a-namedefaultreflectionhandlera--defaultreflectionhandler"></a><a name="default_reflection_handler"></a>DEFAULT_REFLECTION_HANDLER  
 戻されたメッセージを受信する子ウィンドウ (コントロール) の既定のハンドラーを提供します。ハンドラーで適切に処理不能なメッセージを渡す`DefWindowProc`します。  
  
```
DEFAULT_REFLECTION_HANDLER()
```  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="a-nameendmsgmapa--endmsgmap"></a><a name="end_msg_map"></a>も  
 メッセージ マップの最後をマークします。  
  
```
END_MSG_MAP()
```  
  
### <a name="remarks"></a>コメント  
 常に使用する、[送るに](#begin_msg_map)マクロをメッセージ マップの先頭をマークします。 使用[ALT_MSG_MAP](#alt_msg_map)代替メッセージ マップを宣言します。  
  
 メモの&1; つのインスタンスは常に`BEGIN_MSG_MAP`と`END_MSG_MAP`です。  
  
 ATL でのメッセージ マップの使用に関する詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)します。  
  
### <a name="example"></a>例  
 次の例では、既定のメッセージ マップと、それぞれ&1; つのハンドラー関数を含む&1; つの代替のメッセージ マップを示します。  
  
 [!code-cpp[NVC_ATL_Windowing #&98;](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]  
  
 次の例では、2 つの代替のメッセージ マップを示します。 既定のメッセージ マップが空です。  
  
 [!code-cpp[NVC_ATL_Windowing&#99;](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="a-nameforwardnotificationsa--forwardnotifications"></a><a name="forward_notifications"></a>FORWARD_NOTIFICATIONS  
 親ウィンドウへの通知メッセージを転送します。  
  
```
FORWARD_NOTIFICATIONS()
```  
  
### <a name="remarks"></a>コメント  
 このマクロをメッセージ マップの一部として指定します。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="a-namemessagehandlera--messagehandler"></a><a name="message_handler"></a>MESSAGE_HANDLER  
 メッセージ マップのエントリを定義します。  
  
```
MESSAGE_HANDLER( msg, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `msg`  
 [in]Windows メッセージ。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 `MESSAGE_HANDLER`Windows メッセージを指定されたハンドラー関数にマップします。  
  
 指定された関数、`MESSAGE_HANDLER`マクロは次のように定義する必要があります。  
  
 `LRESULT MessageHandler(UINT uMsg, WPARAM wParam, LPARAM lParam, BOOL& bHandled);`  
  
 メッセージ マップ セット`bHandled`に**TRUE**する前に`MessageHandler`が呼び出されます。 場合`MessageHandler`、メッセージを完全に処理しませんに設定する必要があります`bHandled`に**FALSE**を示す、メッセージは、さらに処理を必要があります。  
  
> [!NOTE]
>  メッセージ マップは常に開始[送るに](#begin_msg_map)します。 使って、代替メッセージ マップを宣言することができますし、 [ALT_MSG_MAP](#alt_msg_map)します。 [も](#end_msg_map)マクロは、メッセージ マップの最後をマークします。 すべてのメッセージ マップが正確に&1; つのインスタンスを持つ必要があります`BEGIN_MSG_MAP`と`END_MSG_MAP`です。  
  
 加え`MESSAGE_HANDLER`、使用することができます[COMMAND_HANDLER](#command_handler)と[NOTIFY_HANDLER](#notify_handler)にマップする[WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)と[WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)メッセージそれぞれします。  
  
 ATL でのメッセージ マップの使用に関する詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&129;](../../atl/codesnippet/cpp/message-map-macros-atl_8.h)]  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="a-namemessagerangehandlera--messagerangehandler"></a><a name="message_range_handler"></a>MESSAGE_RANGE_HANDLER  
 ような[MESSAGE_HANDLER](#message_handler)が、多くの Windows メッセージの&1; つのハンドラー関数にマップします。  
  
```
MESSAGE_RANGE_HANDLER( msgFirst, msgLast, func )
```  
  
### <a name="parameters"></a>パラメーター  
 *msgFirst*  
 [in]メッセージの連続した範囲の先頭をマークします。  
  
 *msgLast*  
 [in]メッセージの連続した範囲の末尾をマークします。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="a-namenotifycodehandlera--notifycodehandler"></a><a name="notify_code_handler"></a>NOTIFY_CODE_HANDLER  
 ような[NOTIFY_HANDLER](#notify_handler)、マップが、 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)メッセージが通知コードにのみ基づいています。  
  
```
NOTIFY_CODE_HANDLER(cd, func)
```  
  
### <a name="parameters"></a>パラメーター  
 `cd`  
 [in]通知コード。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="a-namenotifyhandlera--notifyhandler"></a><a name="notify_handler"></a>NOTIFY_HANDLER  
 メッセージ マップのエントリを定義します。  
  
```
NOTIFY_HANDLER( id, cd, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]メッセージを送信するコントロールの識別子です。  
  
 `cd`  
 [in]通知コード。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 `NOTIFY_HANDLER`マップ、 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)通知コードとコントロール id に基づいて、指定されたハンドラー関数にメッセージです。  
  
 指定された関数、`NOTIFY_HANDLER`マクロは次のように定義する必要があります。  
  
 `LRESULT NotifyHandler(int idCtrl, LPNMHDR pnmh, BOOL& bHandled);`  
  
 メッセージ マップ セット`bHandled`に**TRUE**する前に`NotifyHandler`が呼び出されます。 場合`NotifyHandler`、メッセージを完全に処理しませんに設定する必要があります`bHandled`に**FALSE**を示す、メッセージは、さらに処理を必要があります。  
  
> [!NOTE]
>  メッセージ マップは常に開始[送るに](#begin_msg_map)します。 使って、代替メッセージ マップを宣言することができますし、 [ALT_MSG_MAP](#alt_msg_map)します。 [も](#end_msg_map)マクロは、メッセージ マップの最後をマークします。 すべてのメッセージ マップが正確に&1; つのインスタンスを持つ必要があります`BEGIN_MSG_MAP`と`END_MSG_MAP`です。  
  
 他に、 `NOTIFY_HANDLER`、使用することができます[MESSAGE_HANDLER](#message_handler)にマップする、 **WM_NOTIFY**識別子またはコードには関係なくメッセージです。 この場合、`MESSAGE_HANDLER(WM_NOTIFY, OnHandlerFunction)`すべてを指示する**WM_NOTIFY**へのメッセージ`OnHandlerFunction`します。  
  
 ATL でのメッセージ マップの使用に関する詳細については、次を参照してください。[メッセージ マップ](../../atl/message-maps-atl.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing #&130;](../../atl/codesnippet/cpp/message-map-macros-atl_9.h)]  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="a-namenotifyidhandlera--notifyidhandler"></a><a name="notify_id_handler"></a>NOTIFY_ID_HANDLER  
 ような[NOTIFY_HANDLER](#notify_handler)、マップしますが、 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)メッセージがコントロールの識別子にのみ基づいています。  
  
```
NOTIFY_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]メッセージを送信するコントロールの識別子です。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="a-namenotifyrangecodehandlera--notifyrangecodehandler"></a><a name="notify_range_code_handler"></a>NOTIFY_RANGE_CODE_HANDLER  
 ような[NOTIFY_RANGE_HANDLER](#notify_range_handler)、マップが、 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)コントロールの範囲から特定の通知コードを&1; つのハンドラー関数を持つメッセージ。  
  
```
NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `idFirst`  
 [in]コントロール id は連続した範囲の先頭をマークします。  
  
 `idLast`  
 [in]コントロール id の連続した範囲の末尾をマークします。  
  
 `cd`  
 [in]通知コード。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 この範囲は、メッセージを送信するコントロールの識別子に基づきます。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="a-namenotifyrangehandlera--notifyrangehandler"></a><a name="notify_range_handler"></a>NOTIFY_RANGE_HANDLER  
 ような[NOTIFY_HANDLER](#notify_handler)、マップが、 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)コントロールの範囲から&1; つのハンドラー関数へのメッセージ。  
  
```
NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `idFirst`  
 [in]コントロール id は連続した範囲の先頭をマークします。  
  
 `idLast`  
 [in]コントロール id の連続した範囲の末尾をマークします。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 この範囲は、メッセージを送信するコントロールの識別子に基づきます。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="a-namereflectnotificationsa--reflectnotifications"></a><a name="reflect_notifications"></a>REFLECT_NOTIFICATIONS  
 通知メッセージを送信する子ウィンドウ (コントロール) に戻しますが反映されます。  
  
```
REFLECT_NOTIFICATIONS()
```  
  
### <a name="remarks"></a>コメント  
 このマクロは、親ウィンドウのメッセージ マップの一部として指定します。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="a-namereflectedcommandcodehandlera--reflectedcommandcodehandler"></a><a name="reflected_command_code_handler"></a>REFLECTED_COMMAND_CODE_HANDLER  
 ような[COMMAND_CODE_HANDLER](#command_code_handler)、親ウィンドウからコマンドにマッピングします。  
  
```
REFLECTED_COMMAND_CODE_HANDLER( code, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `code`  
 [in]通知コード。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
   
##  <a name="a-namereflectedcommandhandlera--reflectedcommandhandler"></a><a name="reflected_command_handler"></a>REFLECTED_COMMAND_HANDLER  
 ような[COMMAND_HANDLER](#command_handler)、親ウィンドウからコマンドにマッピングします。  
  
```
REFLECTED_COMMAND_HANDLER( id, code, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]メニュー項目、コントロール、またはアクセラレータの識別子。  
  
 `code`  
 [in]通知コード。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  

##  <a name="a-namereflectedcommandidhandlera--reflectedcommandidhandler"></a><a name="reflected_command_id_handler"></a>REFLECTED_COMMAND_ID_HANDLER  
 ような[COMMAND_ID_HANDLER](#command_id_handler)、親ウィンドウからコマンドにマッピングします。  
  
```
REFLECTED_COMMAND_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]メニュー項目、コントロール、またはアクセラレータの識別子。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  

##  <a name="a-namereflectedcommandrangecodehandlera--reflectedcommandrangecodehandler"></a><a name="reflected_command_range_code_handler"></a>REFLECTED_COMMAND_RANGE_CODE_HANDLER  
 ような[COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler)、親ウィンドウからコマンドにマッピングします。  
  
```
REFLECTED_COMMAND_RANGE_CODE_HANDLER( idFirst, idLast, code, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `idFirst`  
 [in]コントロール id は連続した範囲の先頭をマークします。  
  
 `idLast`  
 [in]コントロール id の連続した範囲の末尾をマークします。  
  
 `code`  
 [in]通知コード。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  

##  <a name="a-namereflectedcommandrangehandlera--reflectedcommandrangehandler"></a><a name="reflected_command_range_handler"></a>REFLECTED_COMMAND_RANGE_HANDLER  
 ような[COMMAND_RANGE_HANDLER](#command_range_handler)、親ウィンドウからコマンドにマッピングします。  
  
```
REFLECTED_COMMAND_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `idFirst`  
 [in]コントロール id は連続した範囲の先頭をマークします。  
  
 `idLast`  
 [in]コントロール id の連続した範囲の末尾をマークします。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  

##  <a name="a-namereflectednotifycodehandlera--reflectednotifycodehandler"></a><a name="reflected_notify_code_handler"></a>REFLECTED_NOTIFY_CODE_HANDLER  
 ような[NOTIFY_CODE_HANDLER](#notify_code_handler)、親ウィンドウからの通知にマッピングします。  
  
```
REFLECTED_NOTIFY_CODE_HANDLER_EX( cd, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `cd`  
 [in]通知コード。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  

##  <a name="a-namereflectednotifyhandlera--reflectednotifyhandler"></a><a name="reflected_notify_handler"></a>REFLECTED_NOTIFY_HANDLER  
 ような[NOTIFY_HANDLER](#notify_handler)、親ウィンドウからの通知にマッピングします。  
  
```
REFLECTED_NOTIFY_HANDLER( id, cd, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]メニュー項目、コントロール、またはアクセラレータの識別子。  
  
 `cd`  
 [in]通知コード。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  

##  <a name="a-namereflectednotifyidhandlera--reflectednotifyidhandler"></a><a name="reflected_notify_id_handler"></a>REFLECTED_NOTIFY_ID_HANDLER  
 ような[NOTIFY_ID_HANDLER](#notify_id_handler)、親ウィンドウからの通知にマッピングします。  
  
```
REFLECTED_NOTIFY_ID_HANDLER( id, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]メニュー項目、コントロール、またはアクセラレータの識別子。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  

##  <a name="a-namereflectednotifyrangecodehandlera--reflectednotifyrangecodehandler"></a><a name="reflected_notify_range_code_handler"></a>REFLECTED_NOTIFY_RANGE_CODE_HANDLER  
 ような[NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler)、親ウィンドウからの通知にマッピングします。  
  
```
REFLECTED_NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```    
  
### <a name="parameters"></a>パラメーター  
 `idFirst`  
 [in]コントロール id は連続した範囲の先頭をマークします。  
  
 `idLast`  
 [in]コントロール id の連続した範囲の末尾をマークします。  
  
 `cd`  
 [in]通知コード。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h   
  
##  <a name="a-namereflectednotifyrangehandlera--reflectednotifyrangehandler"></a><a name="reflected_notify_range_handler"></a>REFLECTED_NOTIFY_RANGE_HANDLER  
 ような[NOTIFY_RANGE_HANDLER](#notify_range_handler)、親ウィンドウからの通知にマッピングします。  
  
```
REFLECTED_NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```  
  
### <a name="parameters"></a>パラメーター  
 `idFirst`  
 [in]コントロール id は連続した範囲の先頭をマークします。  
  
 `idLast`  
 [in]コントロール id の連続した範囲の末尾をマークします。  
  
 `func`  
 [in]メッセージ ハンドラー関数の名前。  
  
## <a name="see-also"></a>関連項目  
 [マクロ](../../atl/reference/atl-macros.md)

