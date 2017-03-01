---
title: "レジストリ データ Exchange マクロ |Microsoft ドキュメント"
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
helpviewer_keywords:
- RegistryDataExchange function, macros
ms.assetid: c1bc5e79-2307-43d2-9d10-3a62ffadf473
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
ms.openlocfilehash: ee3c1d639ee4a6c6bd6cf26a8c59bb1a37a4fa02
ms.lasthandoff: 02/24/2017

---
# <a name="registry-data-exchange-macros"></a>レジストリ データ交換マクロ
これらのマクロは、レジストリのデータ交換操作を実行します。  
  
|||  
|-|-|  
|[BEGIN_RDX_MAP](#begin_rdx_map)|レジストリ データ エクス チェンジ マップの先頭をマークします。|  
|[END_RDX_MAP](#end_rdx_map)|レジストリ データ エクス チェンジ マップの最後をマークします。|  
|[RDX_BINARY](#rdx_binary)|指定されたレジストリ エントリ BYTE 型の指定したメンバー変数に関連付けます。|  
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|指定されたレジストリ エントリ CString 型の指定したメンバー変数に関連付けます。|  
|[RDX_DWORD](#rdx_dword)|指定されたレジストリ エントリを DWORD 型の指定したメンバー変数に関連付けます。|  
|[RDX_TEXT](#rdx_text)|指定されたレジストリ エントリは、TCHAR 型の指定したメンバー変数に関連付けます。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlplus.h  
   
##  <a name="a-namebeginrdxmapa--beginrdxmap"></a><a name="begin_rdx_map"></a>BEGIN_RDX_MAP  
 レジストリ データ エクス チェンジ マップの先頭をマークします。  
  
```
BEGIN_RDX_MAP
```  
  
### <a name="remarks"></a>コメント  
 次のマクロは、システム レジストリのエントリを読み書きするレジストリ データ エクス チェンジ マップ内で使用されます。  
  
|マクロ|説明|  
|-----------|-----------------|  
|[RDX_BINARY](#rdx_binary)|指定されたレジストリ エントリ BYTE 型の指定したメンバー変数に関連付けます。|  
|[RDX_DWORD](#rdx_dword)|指定されたレジストリ エントリを DWORD 型の指定したメンバー変数に関連付けます。|  
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|指定されたレジストリ エントリ CString 型の指定したメンバー変数に関連付けます。|  
|[RDX_TEXT](#rdx_text)|指定されたレジストリ エントリは、TCHAR 型の指定したメンバー変数に関連付けます。|  
  
 グローバル関数[RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)、またはによって作成された同じ名前のメンバー関数、`BEGIN_RDX_MAP`と`END_RDX_MAP`コードは、システム レジストリと RDX マップで指定された変数の間のデータを交換する必要があるたびに、マクロを使用する必要があります。  
  
##  <a name="a-nameendrdxmapa--endrdxmap"></a><a name="end_rdx_map"></a>END_RDX_MAP  
 レジストリ データ エクス チェンジ マップの最後をマークします。  
  
```
END_RDX_MAP
```  
  
##  <a name="a-namerdxbinarya--rdxbinary"></a><a name="rdx_binary"></a>RDX_BINARY  
 指定されたレジストリ エントリ BYTE 型の指定したメンバー変数に関連付けます。  
  
```
RDX_BINARY(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>パラメーター  
 `rootkey`  
 レジストリ キーのルートです。  
  
 `subkey`  
 レジストリのサブキーです。  
  
 `valuename`  
 レジストリ キーです。  
  
 `member`  
 指定されたレジストリ エントリに関連付けるメンバー変数です。  
  
 `member_size`  
 メンバー変数のバイト単位のサイズ。  
  
### <a name="remarks"></a>コメント  
 組み合わせてこのマクロを使用、`BEGIN_RDX_MAP`と`END_RDX_MAP`マクロにメンバー変数を指定されたレジストリ エントリに関連付けます。 グローバル関数[RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)、またはによって作成された同じ名前のメンバー関数、`BEGIN_RDX_MAP`と`END_RDX_MAP`マクロを使用して RDX マップでのシステム レジストリとメンバー変数の間のデータ交換を実行する必要があります。  
  
##  <a name="a-namerdxcstringtexta--rdxcstringtext"></a><a name="rdx_cstring_text"></a>RDX_CSTRING_TEXT  
 指定されたレジストリ エントリ CString 型の指定したメンバー変数に関連付けます。  
  
```
RDX_CSTRING_TEXT(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>パラメーター  
 `rootkey`  
 レジストリ キーのルートです。  
  
 `subkey`  
 レジストリのサブキーです。  
  
 `valuename`  
 レジストリ キーです。  
  
 `member`  
 指定されたレジストリ エントリに関連付けるメンバー変数です。  
  
 `member_size`  
 メンバー変数のバイト単位のサイズ。  
  
### <a name="remarks"></a>コメント  
 組み合わせてこのマクロを使用、`BEGIN_RDX_MAP`と`END_RDX_MAP`マクロにメンバー変数を指定されたレジストリ エントリに関連付けます。 グローバル関数[RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)、またはによって作成された同じ名前のメンバー関数、`BEGIN_RDX_MAP`と`END_RDX_MAP`マクロを使用して RDX マップでのシステム レジストリとメンバー変数の間のデータ交換を実行する必要があります。  
  
##  <a name="a-namerdxdworda--rdxdword"></a><a name="rdx_dword"></a>RDX_DWORD  
 指定されたレジストリ エントリを DWORD 型の指定したメンバー変数に関連付けます。  
  
```
RDX_DWORD(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>パラメーター  
 `rootkey`  
 レジストリ キーのルートです。  
  
 `subkey`  
 レジストリのサブキーです。  
  
 `valuename`  
 レジストリ キーです。  
  
 `member`  
 指定されたレジストリ エントリに関連付けるメンバー変数です。  
  
 `member_size`  
 メンバー変数のバイト単位のサイズ。  
  
### <a name="remarks"></a>コメント  
 組み合わせてこのマクロを使用、`BEGIN_RDX_MAP`と`END_RDX_MAP`マクロにメンバー変数を指定されたレジストリ エントリに関連付けます。 グローバル関数[RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)、またはによって作成された同じ名前のメンバー関数、`BEGIN_RDX_MAP`と`END_RDX_MAP`マクロを使用して RDX マップでのシステム レジストリとメンバー変数の間のデータ交換を実行する必要があります。  
  
##  <a name="a-namerdxtexta--rdxtext"></a><a name="rdx_text"></a>RDX_TEXT  
 指定されたレジストリ エントリは、TCHAR 型の指定したメンバー変数に関連付けます。  
  
```
RDX_TEXT(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>パラメーター  
 `rootkey`  
 レジストリ キーのルートです。  
  
 `subkey`  
 レジストリのサブキーです。  
  
 `valuename`  
 レジストリ キーです。  
  
 `member`  
 指定されたレジストリ エントリに関連付けるメンバー変数です。  
  
 `member_size`  
 メンバー変数のバイト単位のサイズ。  
  
### <a name="remarks"></a>コメント  
 組み合わせてこのマクロを使用、`BEGIN_RDX_MAP`と`END_RDX_MAP`マクロにメンバー変数を指定されたレジストリ エントリに関連付けます。 グローバル関数[RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)、またはによって作成された同じ名前のメンバー関数、`BEGIN_RDX_MAP`と`END_RDX_MAP`マクロを使用して RDX マップでのシステム レジストリとメンバー変数の間のデータ交換を実行する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [マクロ](../../atl/reference/atl-macros.md)   
 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)








