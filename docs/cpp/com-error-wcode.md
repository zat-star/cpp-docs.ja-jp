---
title: "_com_error::WCode | Microsoft Docs"
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
  - "_com_error.WCode"
  - "_com_error::WCode"
  - "WCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WCode メソッド"
ms.assetid: f3b21852-f8ea-4e43-bff1-11c2d35454c4
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::WCode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 カプセル化された `HRESULT` にマップされた 16 ビット エラー コードを取得します。  
  
## 構文  
  
```  
  
WORD WCode ( ) const throw( );  
  
```  
  
## 戻り値  
 `HRESULT` が範囲 0x80040200 ～ 0x8004FFFF 内にある場合、**WCode** メソッドは `HRESULT` から 0x80040200 を引いた値を返します。それ以外の場合は、ゼロを返します。  
  
## 解説  
 **WCode** メソッドは、COM サポート コードでのマッピングを元に戻すために使用されます。  **dispinterface** プロパティまたはメソッドのラッパーは、引数をパッケージ化するサポート ルーチンを呼び出し、**IDispatch::Invoke** を呼び出します。  `DISP_E_EXCEPTION` の `HRESULT` エラーが返される場合は、**IDispatch::Invoke** に渡された **EXCEPINFO** 構造体からエラー情報が取得されます。  エラー コードは **EXCEPINFO** 構造体の `wCode` メンバーに格納される 16 ビット値、または **EXCEPINFO** 構造体の **scode** メンバー内の完全な 32 ビット値のいずれかです。  16 ビットの `wCode` が返された場合は、最初に 32 ビットのエラー `HRESULT` にマップする必要があります。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_com\_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [\_com\_error::WCodeToHRESULT](../Topic/_com_error::WCodeToHRESULT.md)   
 [\_com\_error クラス](../cpp/com-error-class.md)