---
title: "MFC ライブラリの自動的なバージョン選択リンク | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "defaultlib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "自動リンク [C++]"
  - "defaultlib (MFC)"
  - "リンク [C++]"
  - "リンク [C++], 自動 (MFC ライブラリのバージョンの)"
  - "リンク [C++], MFC の"
  - "MFC ライブラリ, リンク"
  - "MFC ライブラリ, バージョン"
ms.assetid: 02af4a20-2034-4fce-b200-c2202c3c8311
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC ライブラリの自動的なバージョン選択リンク
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC のバージョン 3.0 以前のバージョンでは、Visual C\+\+ バージョン 2.0 以前\) にリンカーにライブラリの入力リストに手動で MFC ライブラリの正しいバージョンを指定する必要がありました。  MFC Version 3.0 以降では、手動で MFC ライブラリのバージョンを指定する必要がなくなりました。  代わりに、MFC ヘッダー ファイルは **\_DEBUG** または **\_UNICODE**などの `#define`として定義される値に基づいて自動的に MFC ライブラリの正しいバージョンを決定します。  MFC ヘッダー ファイルは、MFC ライブラリの特定のバージョンに存在するようにリンカーに指示します **\/defaultlib** のディレクティブを追加します。  
  
 たとえば、AFX.H のヘッダー ファイルの次のコードは、MFC ライブラリのデバッグ バージョンを使用しているかに応じて、MFC の NAFXCWD.LIB または NAFXCW.LIB バージョンで、リンクするようにリンカーに指示します:  
  
 `#ifndef _UNICODE`  
  
 `#ifdef _DEBUG`  
  
 `#pragma comment(lib, "nafxcwd.lib")`  
  
 `#else`  
  
 `#pragma comment(lib, "nafxcw.lib")`  
  
 `#endif`  
  
 `#else`  
  
 `#ifdef _DEBUG`  
  
 `#pragma comment(lib, "uafxcwd.lib")`  
  
 `#else`  
  
 `#pragma comment(lib, "uafxcw.lib")`  
  
 `#endif`  
  
 `#endif`  
  
 MFC ヘッダー ファイルには、必要なすべてのライブラリでは、MFC ライブラリが、Win32 ライブラリ、OLE ライブラリ、サンプルでは ODBC ライブラリ ビルドされている OLE ライブラリをリンクします。  Win32 ライブラリは Kernel32.Lib、User32.Lib と GDI32.Lib が含まれます。  
  
## 参照  
 [MFC ライブラリのバージョン](../mfc/mfc-library-versions.md)