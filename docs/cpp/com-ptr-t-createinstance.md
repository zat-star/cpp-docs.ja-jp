---
title: "_com_ptr_t::CreateInstance | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t::CreateInstance"
  - "_com_ptr_t.CreateInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateInstance メソッド"
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_ptr_t::CreateInstance
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 **CLSID** または **ProgID** を指定してオブジェクトの新しいインスタンスを作成します。  
  
## 構文  
  
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
  
#### パラメーター  
 `rclsid`  
 オブジェクトの **CLSID**。  
  
 `clsidString`  
 **CLSID** \(先頭が "**{**"\) または **ProgID** を保持する Unicode 文字列。  
  
 `clsidStringA`  
 **CLSID** \(先頭が "**{**"\) または **ProgID** を保持する、ANSI コード ページを使用するマルチバイト文字列。  
  
 `dwClsContext`  
 実行可能コードを実行するコンテキスト。  
  
 `pOuter`  
 [集計](../atl/aggregation.md)で不明な外部の値。  
  
## 解説  
 これらのメンバー関数は、`CoCreateInstance` を呼び出して新しい COM オブジェクトを作成し、このスマート ポインターのインターフェイス型を照会します。  結果のポインターは、この `_com_ptr_t` オブジェクトの中にカプセル化されます。  **Release** は、以前にカプセル化されたポインターの参照カウントをデクリメントするために呼び出されます。  このルーチンは、成功または失敗を示すために、`HRESULT` を返します。  
  
-   **CreateInstance\(**  `rclsid` **,**  `dwClsContext`  **\) CLSID** を指定したオブジェクトの新しい実行中のインスタンスを作成します。  
  
-   **CreateInstance\(**  `clsidString` **,**  `dwClsContext`  **\) CLSID** \("**{**" で始まる\) または **ProgID** を保持する Unicode 文字列を指定したオブジェクトの新しい実行中のインスタンスを作成します。  
  
-   **CreateInstance\(**  `clsidStringA` **,**  `dwClsContext`  **\) CLSID** \("**{**" で始まる\) または **ProgID** を保持するマルチバイト文字列を指定したオブジェクトの新しい実行中のインスタンスを作成します。  [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072) を呼び出します。この関数では、文字列は OEM コード ページではなく ANSI コード ページが使用されていることを前提としています。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_com\_ptr\_t クラス](../cpp/com-ptr-t-class.md)