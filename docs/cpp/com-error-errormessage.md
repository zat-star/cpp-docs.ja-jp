---
title: "_com_error::ErrorMessage | Microsoft Docs"
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
  - "_com_error::ErrorMessage"
  - "_com_error.ErrorMessage"
  - "ErrorMessage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ErrorMessage メソッド"
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::ErrorMessage
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 `_com_error` オブジェクトに格納された `HRESULT` の文字列メッセージを取得します。  
  
## 構文  
  
```  
  
const TCHAR * ErrorMessage( ) const throw( );  
  
```  
  
## 戻り値  
 `_com_error` オブジェクト内に記録された `HRESULT` の文字列メッセージを返します。  `HRESULT` がマップされた 16 ビット [wCode](../cpp/com-error-wcode.md) の場合、一般的なメッセージ "`IDispatch error #<wCode>`" が返されます。  メッセージがない場合、一般的なメッセージ "`Unknown error #<hresult>`" が返されます。  返される文字列は **\_UNICODE** マクロの状態によって、Unicode 文字列またはマルチバイト文字列です。  
  
## 解説  
 `_com_error` オブジェクト内に記録された `HRESULT` に適したシステム メッセージ テキストを取得します。  システム メッセージのテキストは Win32 [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351) 関数を呼び出すことで取得されます。  返される文字列は `FormatMessage` API によって割り当てられ、`_com_error` オブジェクトが破棄されるときに解放されます。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_com\_error クラス](../cpp/com-error-class.md)