---
title: "MFC コモン コントロール ライブラリの分離 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC, Common Controls ライブラリ"
ms.assetid: 7471e6f0-49b0-47f7-86e7-8d6bc3541694
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# MFC コモン コントロール ライブラリの分離
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コモン コントロール MFC ライブラリは内でマニフェストのバージョンを指定することにより、分離し、コモン コントロール ライブラリの別バージョンを使用するように、異なるモジュール \(ユーザー DLL など\) を表示します。  
  
 *FunctionName* が名前のコモン コントロール API です。で MFC アプリケーション \(または MFC によって呼び出されるユーザー コード `Afx`*FunctionName*というラッパー関数によってコモン コントロール ライブラリの API に\) を呼び出します。  これらのラッパー関数は afxcomctl32.h と afxcomctl32.inl で定義されます。  
  
 [AFX\_COMCTL32\_IF\_EXISTS](../Topic/AFX_COMCTL32_IF_EXISTS.md) と [AFX\_COMCTL32\_IF\_EXISTS2](../Topic/AFX_COMCTL32_IF_EXISTS2.md) マクロをできます \(コモン コントロール ライブラリが [GetProcAddress](../build/getprocaddress.md)を呼び出す代わりに特定の API を実装するかどうかを判断するために使用 afxcomctl32.h\) を定義します。  
  
 厳密には、ラッパー クラスを通じてコモン コントロール ライブラリ API、`CComCtlWrapper` を呼び出します \(afxcomctl32.h\) で定義されます。  `CComCtlWrapper` は comctl32.dll の読み込みとアンロードにも使用されます。  MFC のモジュール状態は `CComCtlWrapper`のインスタンスへのポインターが格納されます。  `afxComCtlWrapper` マクロを使用して、ラッパー クラスにアクセスできます。  
  
 MFC アプリケーションでコモン コントロール API を \(非 MFC ラッパー関数を使用して直接呼び出すことに注意してください。ユーザー DLL は、MFC のアプリケーションまたはユーザーの DLL がマニフェストに要求した\) コモン コントロール ライブラリにバインドされるため、ほとんどの場合です。  ただし、MFC コードが異なるコモン コントロール ライブラリ バージョンのユーザーの DLL から呼び出される可能性があるため、MFC コード自体はラッパーを使用する必要があります。