---
title: "MFC ライブラリのバージョンの自動リンク |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: defaultlib
dev_langs: C++
helpviewer_keywords:
- defaultlib in MFC
- automatic links [MFC]
- MFC libraries, linking to
- linking [MFC], automatic of MFC library version
- linking [MFC]
- linking [MFC], of MFC
- MFC libraries, versions
ms.assetid: 02af4a20-2034-4fce-b200-c2202c3c8311
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a9c9e9967fec6d52207e87803fa2d7a2bf42ccca
ms.sourcegitcommit: 0bbc9aac12c926b2b03726ae5b4a09d916e17d6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2017
---
# <a name="automatic-linking-of-mfc-library-version"></a>MFC ライブラリの自動的なバージョン選択リンク
(前に Visual C version 2.0) バージョン 3.0 より前に、のバージョンの MFC ライブラリの入力の一覧で、リンカーの MFC ライブラリの正しいバージョンを手動で指定する必要があります。 MFC バージョン 3.0 以降では、MFC ライブラリのバージョンを手動で指定するために必要なことが不要です。 代わりに、MFC ヘッダー ファイルを自動的に決定と定義されている値に基づき、MFC ライブラリの正しいバージョン`#define`など**_DEBUG**または**_UNICODE**です。 MFC ヘッダー ファイルを追加**/defaultlib**ディレクティブが、MFC ライブラリの特定のバージョンのリンクをリンカーに指示します。  
  
 たとえば、次のコード フラグメント、AFX からです。H ヘッダー ファイルを使用すると、リンカーは、リンクの一部を示します。LIB のまたは NAFXCW します。MFC のデバッグ バージョンを使用しているかどうかに応じて、MFC の LIB バージョン:  
  
```c++
#ifndef _UNICODE 
#ifdef _DEBUG
#pragma comment(lib, "nafxcwd.lib")
#else
#pragma comment(lib, "nafxcw.lib")
#endif
#else
#ifdef _DEBUG
#pragma comment(lib, "uafxcwd.lib")
#else
#pragma comment(lib, "uafxcw.lib")
#endif
#endif
```  
  
 MFC ヘッダー ファイルは、MFC ライブラリ、Win32 ライブラリ、OLE ライブラリが、OLE ライブラリのサンプルから構築された、ODBC ライブラリ、およびなどをなど、必要なすべてのライブラリでリンクもできます。 Win32 ライブラリには、Kernel32.Lib、User32.Lib、GDI32.Lib などがあります。  
  
## <a name="see-also"></a>関連項目  
 [MFC ライブラリのバージョン](../mfc/mfc-library-versions.md)

