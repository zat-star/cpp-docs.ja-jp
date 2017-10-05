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
- _com_ptr_t.GetActiveObject
- _com_ptr_t::GetActiveObject
- GetActiveObject
dev_langs:
- C++
helpviewer_keywords:
- GetActiveObject method
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
caps.latest.revision: 9
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: a61e41c750fdf5865a475d92ba9e1def0aefd748
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

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
  
-   **GetActiveObject (**`clsidStringA`**)**を保持するマルチバイト文字の文字列を指定してオブジェクトの既存のインスタンスにアタッチ、 **CLSID** (以降で"**{**") または**ProgID**です。     呼び出し[MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)文字列は OEM コード ページではなく、ANSI コード ページで、ことを想定しています。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_ptr_t クラス](../cpp/com-ptr-t-class.md)
