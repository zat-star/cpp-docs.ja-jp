---
title: _com_ptr_t::CreateInstance |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::CreateInstance
dev_langs:
- C++
helpviewer_keywords:
- CreateInstance method [C++]
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 70ccd73980295bdda67a4c49d034b6d185d2d93c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="comptrtcreateinstance"></a>_com_ptr_t::CreateInstance
**Microsoft 固有の仕様**  
  
 指定されたオブジェクトの新しいインスタンスを作成、 **CLSID**または**ProgID**です。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT CreateInstance(  
   const CLSID& rclsid,  
   IUnknown* pOuter=NULL,  
   DWORD dwClsContext = CLSCTX_ALL   
) throw( );  
HRESULT CreateInstance(  
   LPCWSTR clsidString,  
   IUnknown* pOuter=NULL,  
   DWORD dwClsContext = CLSCTX_ALL   
) throw( );  
HRESULT CreateInstance(  
   LPCSTR clsidStringA,  
   IUnknown* pOuter=NULL,  
   DWORD dwClsContext = CLSCTX_ALL   
) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `rclsid`  
 **CLSID**のオブジェクト。  
  
 `clsidString`  
 保持する Unicode 文字列、 **CLSID** (以降で"**{**") または**ProgID**です。  
  
 `clsidStringA`  
 保持する、ANSI コード ページを使用し、マルチバイト文字列、 **CLSID** (以降で"**{**") または**ProgID**です。  
  
 `dwClsContext`  
 実行可能コードを実行するコンテキスト。  
  
 `pOuter`  
 外側、不明な[集計](../atl/aggregation.md)です。  
  
## <a name="remarks"></a>コメント  
 これらのメンバー関数は、`CoCreateInstance` を呼び出して新しい COM オブジェクトを作成し、このスマート ポインターのインターフェイス型を照会します。 結果のポインターは、この `_com_ptr_t` オブジェクトの中にカプセル化されます。 **リリース**は以前にカプセル化されたポインターの参照カウントをデクリメントするために呼び出されます。 このルーチンは、成功または失敗を示すために、`HRESULT` を返します。  
  
-   **CreateInstance (** `rclsid` **、**`dwClsContext`**)** 指定されたオブジェクトの実行中の新しいインスタンスを作成、 **CLSID**です。        
  
-   **CreateInstance (** `clsidString` **、**`dwClsContext`**)** 保持する Unicode 文字列を指定してオブジェクトの実行中の新しいインスタンスを作成、 **CLSID**(以降で"**{**") または**ProgID**です。        
  
-   **CreateInstance (** `clsidStringA` **、**`dwClsContext`**)** 保持するマルチバイト文字の文字列を指定してオブジェクトの実行中の新しいインスタンスを作成、 **CLSID** (以降で"**{**") または**ProgID**です。       呼び出し[MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)文字列は OEM コード ページではなく、ANSI コード ページで、ことを想定しています。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_ptr_t クラス](../cpp/com-ptr-t-class.md)