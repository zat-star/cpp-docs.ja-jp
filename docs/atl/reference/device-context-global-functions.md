---
title: "デバイス コンテキストのグローバル関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
caps.latest.revision: 17
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 8c71781519b965717acbcefab6fe6a183686caef
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="device-context-global-functions"></a>デバイス コンテキストのグローバル関数
この関数では、特定のデバイスのデバイス コンテキストを作成します。  
  
|||  
|-|-|  
|[AtlCreateTargetDC](#atlcreatetargetdc)|デバイス コンテキストを作成します。|  
  
##  <a name="atlcreatetargetdc"></a>AtlCreateTargetDC  
 指定されたデバイスのデバイス コンテキストを作成、 [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613)構造体。  
  
```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```  
  
### <a name="parameters"></a>パラメーター  
 *hdc*  
 [in]デバイス コンテキストの既存のハンドルまたは**NULL**します。  
  
 `ptd`  
 [in]ポインター、 **DVTARGETDEVICE**ターゲット デバイスに関する情報を格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 指定されたデバイスのデバイス コンテキスト ハンドルを返します、 **DVTARGETDEVICE**します。 デバイスが指定されていない場合は、既定のディスプレイ デバイスのハンドルを返します。  
  
### <a name="remarks"></a>コメント  
 構造が場合**NULL**と*hdc*は**NULL**既定のディスプレイ デバイスのデバイス コンテキストを作成します。  
  
 場合*hdc*は**NULL**と`ptd`は**NULL**、返しますが、既存*hdc*します。  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
   
## <a name="see-also"></a>関連項目  
 [関数](../../atl/reference/atl-functions.md)

