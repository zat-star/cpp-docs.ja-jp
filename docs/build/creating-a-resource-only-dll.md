---
title: "リソース専用 DLL の作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- resource-only DLLs [C++], creating
- DLLs [C++], creating
ms.assetid: e6b1d4da-7275-467f-a58c-a0a8a5835199
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 607960868aaefadcfa2f4eb548db88efd329620c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="creating-a-resource-only-dll"></a>リソースのみの DLL の作成  
  
リソースのみの DLL とは、リソース以外のものを一切含まず、アイコン、ビットマップ、文字列、ダイアログ ボックスだけを含む DLL です。 リソースのみの DLL は、複数のプログラム間でリソース群を共有するのに適しています。 複数の言語にローカライズされたリソースをアプリケーションに提供することをお勧めも (を参照してください[MFC アプリケーションのローカライズされたリソース: サテライト Dll](../build/localized-resources-in-mfc-applications-satellite-dlls.md))。  
  
リソースのみの DLL を作成するには、Win32 DLL (非 MFC) プロジェクトを新規作成し、ここにリソースを追加します。  
  
-   Win32 プロジェクトを選択して、**新しいプロジェクト** ダイアログ ボックスし、Win32 プロジェクト ウィザードで DLL プロジェクトの種類を指定します。  
  
-   DLL 用のリソース (文字列やメニューなど) を含むリソース スクリプトを新規作成し、.rc ファイルに保存します。  
  
-   **プロジェクト** メニューのをクリックして**既存項目の追加**、し、新しい .rc ファイルをプロジェクトに挿入します。  
  
-   指定して、 [/NOENTRY](../build/reference/noentry-no-entry-point.md)リンカー オプション。 /NOENTRY 防止リンカーへの参照をリンク`_main`DLL のリソース専用 DLL の作成には、このオプションが必要です。  
  
-   DLL をビルドします。  
  
リソース専用 DLL を使用するアプリケーションを呼び出す必要があります[LoadLibrary](../build/loadlibrary-and-afxloadlibrary.md) DLL に明示的にリンクします。 リソースへのアクセス、ジェネリック関数を呼び出す`FindResource`と`LoadResource`リソースの種類で機能または次のリソースに固有の機能の 1 つを呼び出しています。  
  
-   `FormatMessage`  
  
-   `LoadAccelerators`  
  
-   `LoadBitmap`  
  
-   `LoadCursor`  
  
-   `LoadIcon`  
  
-   `LoadMenu`  
  
-   `LoadString`  
  
アプリケーションを呼び出す必要があります`FreeLibrary`が完了したときのリソースを使用します。  
  
## <a name="see-also"></a>関連項目  
  
[リソース ファイルの操作](../windows/working-with-resource-files.md)  
[Visual C++ の DLL](../build/dlls-in-visual-cpp.md)