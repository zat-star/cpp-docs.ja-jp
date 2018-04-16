---
title: "_com_ptr_t::GetActiveObject |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::GetActiveObject
dev_langs:
- C++
helpviewer_keywords:
- GetActiveObject method [C++]
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a67d571c2e5b80eaa1c095cc517872b8e3918fd6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="comptrtgetactiveobject"></a>_com_ptr_t::GetActiveObject
**Microsoft 固有の仕様**  
  
 指定されたオブジェクトの既存のインスタンスにアタッチ、 **CLSID**または**ProgID**です。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT GetActiveObject(  
   const CLSID& rclsid   
) throw( );  
HRESULT GetActiveObject(  
   LPCWSTR clsidString   
) throw( );  
HRESULT GetActiveObject(  
   LPCSTR clsidStringA   
) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `rclsid`  
 **CLSID**のオブジェクト。  
  
 `clsidString`  
 保持する Unicode 文字列、 **CLSID** (以降で"**{**") または**ProgID**です。  
  
 `clsidStringA`  
 保持する、ANSI コード ページを使用し、マルチバイト文字列、 **CLSID** (以降で"**{**") または**ProgID**です。  
  
## <a name="remarks"></a>コメント  
 これらのメンバー関数は、`GetActiveObject` を呼び出して、OLE に登録されている実行中のオブジェクトへのポインターを取得し、このスマート ポインターのインターフェイス型を照会します。 結果のポインターは、この `_com_ptr_t` オブジェクトの中にカプセル化されます。 **リリース**は以前にカプセル化されたポインターの参照カウントをデクリメントするために呼び出されます。 このルーチンは、成功または失敗を示すために、`HRESULT` を返します。  
  
-   **GetActiveObject (**`rclsid`**)**が指定されたオブジェクトの既存のインスタンスにアタッチ、 **CLSID**です。  
  
-   **GetActiveObject (**`clsidString`**)**を保持する Unicode 文字列を指定してオブジェクトの既存のインスタンスにアタッチ、 **CLSID** (以降で"**{**") または**ProgID**です。  
  
-   **GetActiveObject (**`clsidStringA`**)**を保持するマルチバイト文字の文字列を指定してオブジェクトの既存のインスタンスにアタッチ、 **CLSID** (以降で"**{**") または**ProgID**です。 呼び出し[MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)文字列は OEM コード ページではなく、ANSI コード ページで、ことを想定しています。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [_com_ptr_t クラス](../cpp/com-ptr-t-class.md)